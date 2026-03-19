# Application Lifecycle Management (ALM)
**Equipo Rooma – Marzo 2026**

---

## 1. Herramientas de soporte al ciclo de vida

- **Repositorio y control de versiones:** Git + GitHub
- **CI/CD:** GitHub Actions + Container Registry
- **Gestión de tareas:** GitHub Projects
- **Comunicación:** Microsoft Teams
- **Documentación técnica:** Docusaurus (integrado/alojado vía GitHub)
- **Seguimiento de tiempo:** Clockify

---

## 2. Modelo de trabajo - Sprints

La planificación del proyecto se organiza en tres sprints principales y una fase de preparación del lanzamiento.

### 2.1. Capacidad, estimación y compromiso

La planificación del proyecto Rooma se estructura en tres sprints principales y una fase final de preparación del lanzamiento, tal y como se recoge en el documento de planificación.

En una primera fase de definición del proyecto (Devising a Project) se establecen los elementos fundamentales. A partir de esta base, cada sprint se define mediante un conjunto concreto de casos de uso (CU) que conforman el alcance comprometido para cada entrega.

### 2.2. Calendario y alcance por iteración

| Iteración | Deadline | Alcance principal |
|---|---|---|
| Sprint 1 | 04/03 | CU-01 Descubrimiento de viviendas (deck + swipe), CU-02 Match, CU-03 Chat texto, CU-04 Notificaciones básicas, CU-06 Gestión de inmuebles, CU-07 Cuentas y perfil, preparación Stripe (endpoint de prueba en Sprint 1) y despliegue en Cloud. |
| Sprint 2 | 25/03 | CU-10 Pagos y facturas (estado pagado/pendiente), verificación de identidad, favoritos, filtros avanzados, edición de anuncios y corrección de bugs. |
| Sprint 3 | 15/04 | CU-10 Suministros (subida de tickets y división), CU-11 Incidencias, CU-12 Reseñas y valoración, notificaciones push móvil, ajustes UI y corrección de bugs. |
| Project Launch | 13/05 | Refinamiento UX/UI, panel de métricas (analytics), optimización de rendimiento/costes y preparación del material de presentación y lanzamiento. |

---

## 3. Flujo de trabajo

El flujo de trabajo combina la gestión de tareas en GitHub Projects con un ciclo de vida de desarrollo basado en ramas y una integración progresiva hacia producción.

### 3.1. Artefactos de planificación

Para cada sprint se mantiene un backlog de historias con: historia refinada, criterios de aceptación, prioridad, business value, story points, compromiso (Committed/Stretch), dependencias y estado. Además, se mantiene un desglose técnico de tareas por historia con estimación (h).

### 3.2. Ciclo de vida de una funcionalidad

1. **Planificación:** historia de usuario priorizada y refinada en el backlog del sprint (incluye criterios de aceptación y estimación en puntos de historia).
2. **Implementación:** desarrollo en rama `feat/xxxx` con commits atómicos y descriptivos usando Conventional Commits.
3. **Integración:** subida de cambios a trunk mediante una pull request cumpliendo el umbral de CI.

---

## 4. Git y branching

La estrategia de ramas define un flujo Trunk-based en la que las features que se terminen se volcarán sobre la rama trunk, dejando main como una rama para solo las entregas.

### 4.1. Normas de escritura y commits

- Todo el código debe estar escrito en inglés y correctamente tabulado/espaciado.
- Se sigue Conventional Commits; los commits en `feat/xxxx` deben ser atómicos e identificativos.
- No se permiten commits a ramas distintas de `feat/xxxx`.

### 4.2. Política de ramas e integración

- Desarrollo de nuevas funcionalidades en `feat/xxxx` (xxxx: nombre descriptivo).
- Consolidación periódica de trunk para reflejar avances grupales.
- Volcado de trunk hacia main (producción).

### 4.3. Cuándo hacer Pull Request

- **`feat/xxxx` → trunk:** Pull Request si CI no superado, cambios > 300 líneas, cambios de configuración/base del proyecto, cambios en esquemas/migraciones o revisión requerida por coordinador.
- **`trunk` → `main`:** Pull Request obligatoria.

---

## 5. CI/CD

El proyecto utiliza GitHub Actions para automatizar la verificación de cambios y apoyar el despliegue.

### 5.1. Explicitación de ciclo CI

Este workflow se ejecuta siempre que hay un push en cualquier rama que siga la nomenclatura propuesta en la política de trabajo. El workflow está compuesto por tres jobs: backend, frontend y codacy. Los jobs de frontend y backend se ejecutan en paralelo y el de codacy depende de los dos anteriores.

#### 5.1.1. Job de Backend

El job inicia preparando el entorno de ejecución para la máquina de Github tomando como directorio `./backend`.

Una vez preparado el entorno, en la rama main se ejecuta una compilación, tests y un análisis de dependencias usando el servicio externo NVD (solo para main). El resto de las ramas solo compilan y ejecutan los tests. No se realiza análisis de dependencias para reducir tiempos en ramas de desarrollo.

#### 5.1.2. Job de Frontend

Al igual que el job anterior, inicia preparando el entorno con las versiones usadas en el proyecto e instalando las dependencias, pero en el directorio `./frontend`.

Seguido, se ejecuta un linteo del código de frontend para verificar la calidad y estilo del código. Posteriormente se ejecutan los tests y se hace un análisis de vulnerabilidades de las dependencias usadas. Actualmente este último paso de seguridad pasa aunque haya vulnerabilidades.

#### 5.1.3. Job de Codacy

Una vez se han ejecutado correctamente los jobs de backend y frontend, se llama a Codacy mediante una API key para que realice un análisis estático del código. Ahí se pueden observar bugs, code smells, etc. Esto añade una capa adicional de control de calidad independiente del CI local.

### 5.2. Explicitación de ciclo CD

#### 5.2.1. Despliegues en fase de desarrollo

Durante la fase de desarrollo hay un workflow (`cd.yml`) encargado de realizar un despliegue automático tras finalizar el workflow CI, solo en trunk y main.

El workflow inicia haciendo una petición de despliegue a la API de Render mediante una API_KEY. Este despliegue se monitoriza mediante consultas periódicas al servidor para comprobar el estado del despliegue. La monitorización se realiza durante un máximo de 10 minutos, que puede acortarse si el despliegue es un éxito o si falla. En caso de éxito se pasa al siguiente paso; si no, se cancela el workflow con un error.

El último paso del workflow es realizar un despliegue en Vercel usando el backend que se ha desplegado con éxito en Render previamente.

#### 5.2.2. Despliegue para fase de entregas

El día de la entrega se forkeará la rama main en un nuevo repositorio con todas las funcionalidades que se van a presentar para la evaluación. Una vez creada la rama, se creará manualmente una base de datos nueva en AlwaysData, un nuevo servicio de Render y un nuevo despliegue de Vercel usando el backend desplegado en Render.

> **Importante:** una vez creado el fork NO se deben hacer commits para que el código quede congelado con sus respectivos despliegues.

La idea inicial de crear los nuevos servicios y base de datos dentro del workflow se ha descartado por la complejidad del uso de las APIs y la incertidumbre del tiempo restante. También se ha eliminado la creación de contenedores para congelar el código; el fork del repositorio suple estas necesidades.

#### 5.2.3. Despliegue para entrega final

El despliegue final cambia las tecnologías usadas y deberá crearse a mano al igual que en el resto de las entregas. Primero se creará una imagen del backend que se subirá al Container Registry de la organización. Posteriormente se creará una nueva base de datos PostgreSQL en DigitalOcean para luego crear un despliegue del backend usando la imagen y la base de datos creadas. Por último, se crea el servicio de Vercel de frontend con el backend ya desplegado.

| Componente | Sprint (iteración) | Producción | Notas |
|---|---|---|---|
| Frontend (PWA) | Vercel | Vercel | Despliegue del cliente en plataforma de hosting web. |
| Backend (API) | Render | DigitalOcean | Render se utiliza en sprints; producción en DigitalOcean. |
| Base de datos | AlwaysData | DigitalOcean | PostgreSQL en AlwaysData para sprints y en DigitalOcean para producción. |

---

## 6. Versionado y releases

Se adopta versionado semántico (SemVer) para etiquetar releases del producto con el formato `MAJOR.MINOR.PATCH`. Ejemplo: `3.12.6`.

### 6.1. Criterio de incremento

- **MAJOR:** cambios incompatibles o que requieran adaptación significativa.
- **MINOR:** incorporación de nuevas funcionalidades manteniendo compatibilidad.
- **PATCH:** corrección de errores y ajustes sin cambios funcionales relevantes.

---

## 7. Estrategia de testing

El aseguramiento de calidad combina QA/Tester, revisiones de Pull Requests y control mediante CI. En el desglose técnico de tareas por historia se contemplan tareas de pruebas (unitarias/E2E) y QA.

### 7.1. Estrategia general del testing

El modelo de testing se diseña para:

- Mitigar riesgos críticos desde fases tempranas.
- Garantizar fiabilidad en transacciones financieras, privacidad en comunicaciones e integridad del sistema de reputación.
- Mantener agilidad en integración continua (CI/CD).

**Decisión arquitectónica clave:**
- **Backend:** fuerte foco en pruebas unitarias e integración.
- **Frontend:** foco exclusivo en pruebas End-to-End (E2E).

Se prioriza validar el sistema desde la perspectiva real del usuario final en lugar de mantener tests unitarios frágiles en UI dinámica.

### 7.2. Stack tecnológico del testing

#### 7.2.1. Backend

- **Unit Testing:** JUnit 5 + Mockito — validación atómica de lógica de negocio.
- **Integration Testing:** RestAssured + Testcontainers — se levantan instancias reales efímeras de PostgreSQL en Docker (no mocks), garantizando validación real de migraciones, claves foráneas y queries complejas.

#### 7.2.2. Frontend

- **E2E Testing:** Playwright con TypeScript — permite simular múltiples usuarios simultáneamente y validar flujos completos.
- **IA aplicada al testing:** GitHub Copilot + MCP (Model Context Protocol) — generación automática de tests, escaneo dinámico del DOM, self-healing de selectores y reducción drástica de mantenimiento manual.

### 7.3. Tipología de pruebas

Las pruebas se clasifican para optimizar el pipeline CI/CD.

#### 7.3.1. Smoke Tests

- Subconjunto mínimo de E2E.
- Validan únicamente Happy Paths críticos.
- Duración < 3 minutos.
- Si fallan, rollback automático.

**Objetivo:** comprobar que la aplicación es utilizable.

#### 7.3.2. Sanity Tests

- Pruebas profundas pero acotadas a un módulo concreto.
- Validan casos borde, excepciones y límites funcionales.
- Se ejecutan cuando un módulo ha sido modificado.

#### 7.3.3. Regression Tests

- Suite completa de flujos automatizados.
- Garantizan el principio de no regresión.
- Se ejecutan antes de producción.
- Incluyen validación end-to-end completa del ciclo de vida del producto.

---

## 8. Definition of Done (DoD)

El Definition of Done (DoD) establece los criterios obligatorios que deben cumplirse para que una Historia de Usuario (HU) o requisito funcional se considere completamente finalizado dentro del ciclo de vida del producto.

Su propósito es garantizar calidad homogénea en todos los incrementos y alinear Desarrollo, QA, DevOps y Product Owner. Una historia no se considera "Done" hasta cumplir todos los puntos siguientes.

### 8.1. Criterios Generales de Finalización

#### 8.1.1. Cumplimiento Funcional

- Implementa completamente los requisitos asociados (RF / RI / RNF).
- Cumple todos los criterios de aceptación definidos en la HU correspondiente.
- No introduce regresiones en funcionalidades existentes.

#### 8.1.2. Calidad de Código

- El código sigue las convenciones acordadas (inglés, formato, linting).
- Se han aplicado buenas prácticas de arquitectura.

#### 8.1.3. Testing Obligatorio

**Backend:**
- Incluye pruebas unitarias (JUnit).
- Si aplica, incluye pruebas de integración (Testcontainers).

**Frontend:**
- Se han añadido o actualizado pruebas E2E (Playwright) cuando el cambio afecta a flujos críticos.
- No se rompen Smoke Tests.

#### 8.1.4. Validación Funcional (QA)

- La funcionalidad ha sido validada manualmente en entorno de sprint.
- Se han probado los flujos principales (Happy Path).
- Se han probado al menos los casos borde más relevantes.
- No existen defectos críticos asociados a la HU.

#### 8.1.5. Despliegue

- La funcionalidad está desplegada en entorno de sprint (Render + Vercel).
- Es accesible y operativa en dicho entorno.
- No genera errores en logs del servidor.

---

## 9. Métricas de Calidad y Seguimiento

Con el fin de garantizar la mejora continua del producto y del proceso de desarrollo, el proyecto establece un conjunto reducido pero significativo de métricas de calidad (KPIs).

Estas métricas permiten evaluar la salud técnica del producto, detectar riesgos tempranos, medir la eficacia del pipeline CI/CD y reducir defectos en producción. Se revisan al final de cada sprint.

### 9.1. Cobertura de Código (Coverage %)

Porcentaje de líneas y ramas del backend cubiertas por pruebas automatizadas (JUnit + integración).

**Herramienta:** JaCoCo.

**Objetivo:** ≥ 80% de cobertura global en backend. No se permite integración en ramas principales si el porcentaje baja del umbral.

**Interpretación:**
- < 80% → riesgo técnico elevado.
- ≥ 85% → nivel óptimo para producto en crecimiento.

### 9.2. Defect Leakage

Número de defectos detectados en producción respecto al total detectado en el ciclo de desarrollo.

**Objetivo:** mantener Defect Leakage < 10%.

**Interpretación:**
- 15% → testing insuficiente o cobertura inadecuada.
- < 5% → proceso de validación sólido.

Esta métrica evalúa la eficacia de Smoke Tests, Sanity Tests, Regression Suite y QA manual.

### 9.3. Lead Time

Tiempo desde que se abre una issue hasta que se cierra. Se usa para medir la velocidad media de cada miembro en realizar una tarea.

**Objetivo:** las issues de cada miembro deben terminarse en un tiempo medio inferior a 7 días.

**Interpretación:** un lead time > 7 días indica que la persona ha estado bloqueada demasiado tiempo y podría haber realizado otras tareas previamente.
