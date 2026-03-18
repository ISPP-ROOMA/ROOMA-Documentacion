# Stack Tecnológico y Arquitectura: Rooma

A continuación, se detalla la arquitectura tecnológica, herramientas de desarrollo y metodologías de gestión adoptadas para el desarrollo de Rooma. El ecosistema está diseñado para ser ágil, escalable y ofrecer una experiencia de usuario nativa a través de la web.

---

## 1. Frontend (Progressive Web App - PWA)

El cliente está enfocado en el rendimiento, la interactividad móvil y la experiencia de usuario (UX), emulando una aplicación nativa.

- **Core:** React. Librería principal para la construcción de interfaces de usuario basadas en componentes reutilizables y reactivos.
- **Gestión del Estado:** Zustand. Solución minimalista, rápida y escalable para el estado global (sesión de usuario, preferencias de búsqueda, estado del chat), evitando el boilerplate excesivo de herramientas como Redux.
- **UI & UX (Estilos y Componentes):**
  - **TailwindCSS:** Framework de CSS utility-first para un diseño a medida, rápido y completamente responsivo.
  - **DaisyUI:** Biblioteca de componentes basada en Tailwind que acelera el desarrollo proporcionando elementos preconstruidos (botones, modales, cards) con soporte nativo para temas oscuros/claros.
  - **ReactTinderCard:** Lógica central de interacción (Swipe left/right) para la toma de decisiones ágil por parte del usuario.
  - **Leaflet:** Renderizado de mapas interactivos ligeros para la geolocalización de habitaciones y zonas de interés.
- **Comunicación con el Backend:**
  - **Axios:** Cliente HTTP basado en promesas para el consumo de la API REST (CRUD de perfiles, habitaciones, matches).
  - **WebSockets nativos:** Para mantener conexiones bidireccionales persistentes.
- **PWA & Notificaciones:**
  - **Service Worker:** Habilita el caché de recursos estáticos, permitiendo tiempos de carga casi instantáneos y soporte offline parcial.
  - **Push API:** Recepción de notificaciones enriquecidas en el dispositivo del usuario (nuevos matches, mensajes de chat).
- **Pagos (Cliente):** React Stripe.js. Uso de Stripe Elements para renderizar formularios de pago seguros. Tokeniza las tarjetas directamente en el navegador cumpliendo con la normativa PCI DSS, garantizando que los datos sensibles nunca toquen nuestros servidores.
- **Calidad de Código:** ESLint + Prettier. Estandarización del estilo de código, detección temprana de errores y formateo automático.

---

## 2. Backend (API REST & Real-Time)

El núcleo lógico de Rooma está construido para ser robusto, seguro y altamente eficiente utilizando el ecosistema Java moderno.

- **Core:** Java (JDK 25) + Spring Boot. Proporciona un entorno empresarial sólido, rápido y con un amplio soporte de la comunidad para la creación de microservicios o monolitos modulares.
- **Comunicación en Tiempo Real:** Spring WebSocket (STOMP). Subprotocolo de mensajería que estructura el envío de mensajes del chat en vivo, permitiendo canales y salas privadas entre usuarios con un overhead mínimo.
- **Gestión de Notificaciones:** `nl.martijndwars:web-push`. Librería para encriptar y enviar cargas útiles (payloads) de notificaciones Push directamente a los navegadores/dispositivos de los usuarios a través del protocolo Web Push.
- **Seguridad y Autenticación:**
  - **Spring Security:** Framework integral de seguridad.
  - **OAuth2 / JWT (nimbus-jose-jwt):** Implementación de autenticación stateless. Generación y validación de JSON Web Tokens cifrados y firmados para proteger los endpoints de la API.
- **Procesamiento de Pagos:** Stripe Java SDK. Gestión de la lógica de monetización. Se encarga de crear Payment Intents, gestionar clientes/suscripciones y exponer Webhooks seguros para escuchar eventos asíncronos de Stripe (ej. confirmación de pago exitoso) y actualizar el estado del usuario en la base de datos.
- **Persistencia y Base de Datos:**
  - **JPA (Hibernate):** Mapeo Objeto-Relacional (ORM) para interactuar con la base de datos mediante entidades Java.
  - **Flyway:** Control de versiones para la base de datos. Garantiza que las migraciones de esquemas se apliquen de forma predecible y consistente en todos los entornos.
  - **Spring Boot Validation:** Validación de datos de entrada (DTOs) garantizando la integridad de la información antes de procesarla.
  - **PostgreSQL:** Motor de base de datos relacional principal. Potente, open-source y preparado para futuras extensiones (como PostGIS para consultas geoespaciales avanzadas).

---

## 3. Infraestructura, Despliegue y Multimedia

Estrategia orientada a la eficiencia de costes durante el desarrollo y alta disponibilidad en producción.

- **Gestión de Imágenes:** Cloudinary. Servicio en la nube para el almacenamiento, optimización dinámica y entrega a través de CDN de todo el contenido multimedia (avatares de usuarios, fotos de habitaciones). Reduce la carga del backend y acelera la carga en el frontend.
- **Entornos de Desarrollo (Local):**
  - **Docker:** Contenerización de servicios (PostgreSQL, Redis si se necesitara) mediante docker-compose para garantizar que todo el equipo trabaja bajo exactamente las mismas condiciones.
  - **Requisitos Locales Nativos:** Alternativamente, el proyecto se levanta de forma ligera con Node.js 24, JDK 25 y PostgreSQL local.
- **Estrategia de Despliegue (CI/CD):** Para el desarrollo diario habrá un workflow encargado de desplegar el proyecto en las ramas trunk y main. Para las entregas, se creará un fork del repositorio de desarrollo para congelar el estado del código (no se debe cambiar). Posteriormente se creará a mano la base de datos y los servicios de despliegue.
  - **Backend (Render / DigitalOcean):** Empaquetado avanzado mediante GraalVM para compilar la aplicación Spring Boot como una imagen nativa, reduciendo drásticamente el tiempo de inicio y el consumo de memoria. Para sprints/pruebas se desplegará en Render la rama trunk y para entregas main. Para la entrega final se genera una nueva rama en Git, se construye la imagen Docker nativa, se sube al Container Registry de la organización y se crea el servicio en DigitalOcean.
  - **Frontend (Vercel):** Integración continua directa para el desarrollo y a mano en las entregas. Cada push a la rama principal (o PRs) dispara un build automático y despliegue global en el Edge Network de Vercel.
  - **Bases de Datos:** AlwaysData para instancias ligeras durante los sprints de desarrollo y clúster de PostgreSQL en DigitalOcean para el entorno de producción en la entrega final.

---

## 4. DevOps, Colaboración y Gestión del Proyecto

Herramientas enfocadas en la sincronización del equipo, el seguimiento del progreso y el mantenimiento del conocimiento.

- **Control de Versiones y Alojamiento:** Git + GitHub. Repositorio central del código fuente.
- **Automatización (CI/CD):** GitHub Actions. Flujos de trabajo automatizados para testing, builds de GraalVM, empaquetado Docker y despliegues.
- **Gestión de Tareas (Agile):** GitHub Projects. Tableros Kanban integrados directamente con los issues y Pull Requests del código para una trazabilidad perfecta.
- **Documentación Técnica:** Docusaurus. Alojado vía GitHub Pages. Centraliza la documentación de la API, guías de instalación, decisiones de arquitectura y manuales de usuario interno en un formato web navegable y versionado.
- **Comunicación:** Microsoft Teams. Hub central para chats rápidos, reuniones diarias (dailies), videollamadas y almacenamiento de archivos compartidos de negocio.
- **Seguimiento de Tiempos:** Clockify. Monitoreo del tiempo invertido por tarea y desarrollador para auditar la productividad y estimar futuros sprints con mayor precisión.
- **Entorno de Desarrollo (IDE):** VS Code + Java Extension Pack. Editor ligero y estandarizado para todo el equipo, abarcando tanto el desarrollo de React como el de Spring Boot.

---

## Análisis comparativo

### Frontend

**Medidas utilizadas en el frontend para la matriz de comparación:**

1. **Curva de Aprendizaje** — Tiempo necesario para que el equipo sea productivo: experiencia previa, complejidad conceptual y disponibilidad de documentación.
2. **Comunidad y ecosistema** — Librerías complementarias, tutoriales, cursos y soporte en foros (GitHub, Stack Overflow, etc.).
3. **Rendimiento** — Tiempo de carga inicial, consumo de recursos del navegador y optimización del código generado.
4. **Herramientas y experiencia de desarrollo** — CLI, DevTools para depuración e integración con herramientas modernas (bundlers, testing, etc.).
5. **Escalabilidad y arquitectura** — Organización del código, modularidad y buenas prácticas de arquitectura.
6. **Experiencia del equipo** — Experiencia previa del equipo con la tecnología.

| Medida | React | Vue.js | Angular |
|---|---|---|---|
| Curva de aprendizaje | Regular | Muy bueno | Malo |
| Comunidad y ecosistema | Muy bueno | Regular | Regular |
| Rendimiento | Muy bueno | Muy bueno | Regular |
| Herramientas y experiencia de desarrollo | Muy bueno | Regular | Muy bueno |
| Escalabilidad y arquitectura | Regular | Regular | Muy bueno |
| Experiencia previa | Muy bueno | Regular | Regular |

### Backend

**Medidas utilizadas en el backend para la matriz de comparación:**

1. **Tiempo de desarrollo** — Facilidad para crear endpoints, cantidad de configuración inicial y herramientas que aceleran el desarrollo.
2. **Tipado y mantenibilidad** — Tipado fuerte o estático, facilidad para entender el código en proyectos grandes y detección de errores en tiempo de compilación.
3. **Rendimiento y concurrencia** — Modelo de concurrencia (asíncrono, multihilo, event-loop), tiempo de respuesta y capacidad de manejar alto tráfico.
4. **Ecosistema e integraciones** — Integración con bases de datos, sistemas de autenticación y servicios externos (APIs, colas de mensajes, almacenamiento, etc.).
5. **Operacionalización y despliegue en producción** — Facilidad de despliegue en servidores o contenedores, monitorización, logging y gestión de configuración.
6. **Experiencia del equipo** — Experiencia previa del equipo con la tecnología.

| Medida | FastAPI/Flask | Spring Boot | Express |
|---|---|---|---|
| Tiempo de desarrollo | Muy bueno | Regular | Muy bueno |
| Tipado y mantenibilidad | Regular | Muy bueno | Regular |
| Rendimiento y concurrencia | Muy bueno | Muy bueno | Regular |
| Ecosistema e integraciones | Regular | Muy bueno | Muy bueno |
| Operacionalización & producción | Regular | Muy bueno | Regular |
| Experiencia del equipo | Regular | Muy bueno | Muy malo |

### Despliegue

**Medidas utilizadas en el despliegue para la matriz de comparación:**

1. **Experiencia de desarrollador y facilidad de uso** — Configuración inicial, integración con repositorios, automatización de despliegues (CI/CD) e interfaz de gestión.
2. **Claridad de precio y plan gratuito** — Existencia de plan gratuito, facilidad para estimar costes y modelo de facturación.
3. **Tipos de aplicaciones soportadas** — Flexibilidad de la plataforma para desplegar diferentes tipos de aplicaciones.
4. **Rendimiento global y red de distribución** — Presencia de CDN, infraestructura distribuida globalmente y posibilidad de desplegar servicios cerca del usuario.
5. **Escalabilidad y preparación para producción** — Escalado automático, balanceo de carga, alta disponibilidad y sistemas de backup y recuperación.
6. **Integraciones y herramientas de monitorización** — Integración con bases de datos y servicios externos, herramientas de logs, métricas de rendimiento y alertas de errores.

| Medida | Vercel | Render | DigitalOcean | Railway | Fly.io | Netlify |
|---|---|---|---|---|---|---|
| Experiencia de desarrollador | Muy bueno | Muy bueno | Regular | Muy bueno | Regular | Muy bueno |
| Claridad de precio & plan gratuito | Regular | Muy bueno | Muy bueno | Regular | Regular | Muy bueno |
| Tipos de aplicaciones soportadas | Muy bueno | Muy bueno | Muy bueno | Muy bueno | Muy bueno | Regular |
| Rendimiento global y red de distribución | Muy bueno | Regular | Regular | Regular | Muy bueno | Muy bueno |
| Escalabilidad y preparación para producción | Muy bueno | Muy bueno | Muy bueno | Regular | Regular | Regular |
| Integraciones y herramientas de monitorización | Muy bueno | Regular | Muy bueno | Regular | Regular | Regular |
