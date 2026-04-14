# Sprint 3 Retrospective - ROOMA

Fecha de elaboración: 12/04/2026
Sprint analizado: Sprint 3 (deadline de referencia en ALM: 15/04)

## 1. Objetivo de esta retrospectiva

Analizar cómo ha ido el Sprint 3 frente a lo planificado, identificar desviaciones relevantes y definir acciones correctivas concretas para el siguiente ciclo (Project Launch).

## 2. Fuentes usadas (repositorio ROOMA-Documentacion)

- alm-stack/alm.md
- trabajo-sprints/3-sprint-3/deadlines.md
- trabajo-sprints/problemas-desarrollo.md
- entregas/checklist-entrega-sprint-3.md
- captacion-usuarios/planes-usuarios-piloto/plan-de-gestion-de-usuarios.md
- captacion-usuarios/usuarios-piloto/feedback-usuarios-piloto.md
- captacion-usuarios/usuarios-piloto/lista-usuarios-censurada.md
- analisis-diseno/cumplimiento-trazabilidad-requisitos/cu-09-gestion-facturas-pagos.md
- analisis-diseno/cumplimiento-trazabilidad-requisitos/cu-10-gestion-incidencias.md
- analisis-diseno/cumplimiento-trazabilidad-requisitos/cu-11-resenas-valoracion-convivencia.md
- analisis-diseno/cumplimiento-trazabilidad-requisitos/cu-04-gestion-notificaciones.md
- despliegues/despliegue-info.md

## 3. Qué se planificó para Sprint 3

Según ALM, el alcance principal comprometido para Sprint 3 fue:

- CU-10 Suministros (subida de tickets y división)
- CU-11 Incidencias
- CU-12 Reseñas y valoración
- Notificaciones push móvil
- Ajustes UI
- Corrección de bugs

Adicionalmente, desde el plan de usuarios piloto para Sprint 3 se fijó como objetivo:

- Entregable beta end-to-end (de búsqueda de compañero a pago simulado)
- Recoger feedback global para priorizar backlog de la versión 1.0

## 4. Qué se ejecutó realmente

### 4.1. Ejecución funcional por bloques

#### A) Facturas y pagos (CU-09 en documentación de trazabilidad)

Estado HU (12 HU totales):

- Completadas: 6
- No completadas: 6

Resultado: avance funcional relevante, pero el bloque de pagos avanzados y cumplimiento (pasarela real, autopago, metodos de pago, exportaciones) sigue incompleto.

#### B) Incidencias (CU-10)

Estado HU (9 HU totales):

- Completadas: 5
- Completadas parcialmente: 3
- No completadas: 1

Resultado: modulo utilizable en gran parte, pero con deuda funcional en cierre completo y notificaciones/presupuestos.

#### C) Reseñas y valoracion (CU-11)

Estado HU (10 HU totales):

- Completadas: 6
- No completadas: 4

Resultado: se cubre el nucleo de valoracion, pero faltan capacidades clave de reputacion visible y moderacion/reportes.

#### D) Notificaciones (CU-04)

Estado HU (5 HU totales):

- Completadas: 3
- Completadas parcialmente: 2

Resultado: base de notificaciones funcional, pero quedan huecos en experiencia push/indicadores y eventos concretos (por ejemplo nuevos match).

### 4.2. Ejecución de coordinación y entrega

- Existe checklist de entrega Sprint 3 con cobertura explicita de presentación, despliegue y documentos.
- En deadlines de Sprint 3 hay 29 tareas con fecha entre 04/04 y 12/04, con fuerte concentración entre 06/04 y 10/04.
- El propio repositorio documenta problemas de desarrollo ligados a equilibrio de carga, retrasos por dependencias y coordinación de presentación.

### 4.3. Usuarios piloto

- Se dispone de listado censurado de usuarios piloto con 29 entradas.
- Se recoge feedback de uso con incidencias concretas de producto (sesion, UX, match, favoritos, validaciones, etc.).

Resultado: objetivo de captación cumplido en volumen y se obtuvo feedback accionable.

## 5. Comparativa Sprint 3: planificado vs ejecutado

## 5.1. Resumen ejecutivo

- El sprint entrega valor funcional real y transversal, pero no completa todo el alcance comprometido al nivel de Definition of Done esperado.
- La parte de incidencias y reseñas avanza bien en el nucleo, mientras que el bloque financiero queda a medio cerrar en funcionalidades avanzadas.
- Se observa presión de calendario (muchas tareas concentradas en pocos dias) y dependencia entre tareas, con impacto directo en cierres y calidad final percibida.

## 5.2. Tabla de contraste

| Eje | Planificado | Ejecutado | Evaluacion |
| :-- | :-- | :-- | :-- |
| Alcance funcional Sprint 3 | Completar bloques de suministros/incidencias/reseñas + push | Progreso alto pero incompleto (varias HU por hacer o parciales) | Parcial |
| Calidad y cierre | Historias cerradas segun DoD | Varios RF/RNF/RI con estado parcial o pendiente | Parcial |
| Planificacion temporal | Deadlines distribuidos y controlables | Alta concentracion 06/04-10/04 y dependencia entre tareas | Riesgo alto |
| Entregable/documentacion | Checklist completo de entrega | Evidencia documental amplia y estructura de entrega preparada | Cumplido |
| Validacion con usuarios | Beta end-to-end + feedback para backlog | Usuarios piloto activos y feedback recogido | Cumplido |

## 6. Métricas observadas (a partir de la documentación)

- Tareas con deadline registradas en Sprint 3: 29
  - Documentación: 15
  - Desarrollo: 14
- Cobertura funcional por HU (bloques clave de Sprint 3):
  - Facturas/pagos (CU-09): 6/12 completas (50%)
  - Incidencias (CU-10): 5/9 completas (55.6%), 8/9 si se incluyen parciales
  - Reseñas (CU-11): 6/10 completas (60%)
  - Notificaciones (CU-04): 3/5 completas (60%), 5/5 si se incluyen parciales

Nota: los porcentajes reflejan estado documental de HU, no una auditoría de código ni de tests.

## 7. Principales desviaciones detectadas

1. Diferencia entre alcance comprometido y cierre real por DoD.
2. Sobrecarga de trabajo en la ultima ventana temporal del sprint.
3. Dependencias entre tareas sin buffer suficiente.
4. Deuda de producto en funcionalidades avanzadas de pagos y moderación/reputación.
5. Problemas recurrentes de coordinación en la preparación de presentación y orden de prioridades.

## 8. Causas raiz (síntesis)

- Estimación mejorable de esfuerzo real frente a story points.
- Planificación con demasiadas tareas cercanas al deadline.
- Dependencias técnicas y de validación no resueltas lo bastante pronto.
- Falta de congelación temprana estricta para estabilización final.
- Reparto de carga no uniforme entre integrantes.

## 9. Qué funcionó bien

- Base funcional del producto claramente más amplia que en sprints previos.
- Buen avance en incidencias y en el núcleo de reseñas.
- Recogida de feedback de usuarios piloto con suficiente volumen.
- Paquete de documentación del entregable bien estructurado.

## 10. Qué no funcionó bien

- Cierre incompleto de funcionalidades críticas en pagos y reputación.
- Exceso de trabajo de ultima hora.
- Defectos de UX detectados por usuarios piloto en flujos clave.
- Riesgo de mezclar finalización funcional, estabilización y preparación de entrega en la misma ventana corta.

## 11. Acciones concretas para el siguiente ciclo (priorizadas)

1. Congelación funcional real 72 horas antes de la entrega.
2. Reservar las ultimas 48 horas solo para QA, despliegue y verificación de checklist.
3. Replanificar tareas con dependencias explicitas y deadline interno intermedio obligatorio.
4. Cerrar deuda funcional pendiente por impacto:
   - Pago real/autopago/metodos de pago/exportaciones
   - Reputacion visible/moderacion/reportes
   - Notificaciones pendientes de match/push UX
5. Aplicar control de carga por persona (minimo-maximo de puntos y revisión semanal de desviaciones).
6. Definir criterios de salida del sprint con semaforo (verde/ambar/rojo) por cada bloque funcional.
7. Ejecutar revisión colectiva final de presentación contra checklist oficial (no delegada en una sola persona).

## 12. Conclusión

Sprint 3 ha sido un sprint de alto avance y alta presión: se consolidó una parte importante del producto y de la documentación, pero el cumplimiento frente al plan ha sido parcial en cierre funcional completo. El equipo llega con una base válida para el siguiente ciclo, siempre que priorice estabilización, cierre de deuda funcional crítica y disciplina de planificación temporal para evitar repetir la concentración de riesgo al final del sprint.
