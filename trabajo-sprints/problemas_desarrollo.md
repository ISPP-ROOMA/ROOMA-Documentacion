# REGISTRO DE PROBLEMAS Y LECCIONES APRENDIDAS DURANTE EL DESARROLLO

Este documento recopila de forma detallada todos los incidentes, bloqueos y áreas de mejora identificados durante el ciclo de vida del proyecto, incluyendo sus causas, lecciones aprendidas y los planes de mitigación correspondientes.

---

## 1. DESCOMPENSACIÓN DE TRABAJO
### Descripción
Se ha detectado una inversión de tiempo desigual entre los miembros del equipo debido a una asignación de actividades desequilibrada basada en una equivalencia rígida (1 punto de historia = 1 hora de trabajo estimada).

### Lecciones aprendidas
- Las estimaciones iniciales no reflejaron la complejidad real de las tareas.
- Faltó una validación cruzada de la carga total por integrante antes de iniciar los sprints.

### Mitigaciones
- Sesiones de Planning Poker más rigurosas para estimar esfuerzo real.
- Establecer límites máximos y mínimos de puntos por persona.

### Comprobación
- El 16/04: Verificar que la desviación típica entre integrantes sea de 2 horas o menos.

---

## 2. PROBLEMAS CON EL DESPLIEGUE EL DÍA DE LA ENTREGA
### Descripción
El despliegue se realizó demasiado cerca de la fecha límite, lo que provocó la aparición de errores críticos durante la entrega final.

### Lecciones aprendidas
- No se reservó tiempo específico en el cronograma para tareas de infraestructura y despliegue.

### Mitigaciones
- Congelación de funcionalidades (Feature Freeze) 72 horas antes de la entrega.
- Dedicar las últimas 48 horas exclusivamente a despliegue y pruebas en producción.

### Comprobación
- El 25/03: No debe haber más de 3 commits de corrección (fix).

---

## 3. RETRASOS EN EL DESARROLLO POR DEPENDENCIAS
### Descripción
Retrasos acumulados debido a tareas bloqueadas por otras no finalizadas. Miembros del equipo tuvieron que asumir tareas extra de forma improvisada para no detener el progreso.

### Lecciones aprendidas
- Ausencia de deadlines internos claros para cada tarea.
- Gestión deficiente de las dependencias críticas durante la planificación.

### Mitigaciones
- Definir deadlines internos para todas las tareas.
- Identificación proactiva de dependencias en la fase de planificación.

### Comprobación
- Seguimiento semanal mediante herramienta de gestión.
- El 16/04: Al menos un 80% de tareas completadas dentro de sus plazos internos.

---

## 4. COORDINACIÓN DE LA PRESENTACIÓN (CONTENIDO)
### Descripción
Incertidumbre y falta de alineación sobre el alcance de la presentación (proceso previo vs. solución final).

### Lecciones aprendidas
- No se definió el alcance y contenido esperado desde el inicio.
- Falta de comunicación entre los miembros sobre el enfoque de la exposición.

### Mitigaciones
- Definir estructura y contenido antes de empezar el diseño.
- Asignar un responsable de coordinación para centralizar decisiones.

### Comprobación
- La presentación debe estar lista antes de las 16:00 del día de la entrega.

---

## 5. CONTENIDO DE LA PRESENTACIÓN Y GESTIÓN DEL FEEDBACK
### Descripción
Se omitió contenido solicitado explícitamente en entregas previas (DP y Sprint 2), ignorando el feedback de los profesores y resultando en penalizaciones.

### Lecciones aprendidas
- No se puede delegar la revisión del feedback en una sola persona (riesgo de omisión).
- La revisión debe ser un proceso colectivo y estructurado frente a los criterios oficiales.

### Mitigaciones
- Checklist personal obligatorio para cada miembro.
- Consolidación de un checklist común basado en feedback y criterios oficiales.
- Designación de un responsable de versión inicial, pero con validación grupal final.

### Comprobación
- El 16/04: Cero penalizaciones por contenido en la evaluación oficial.

---

## 6. CAMBIO DE ROL
### Descripción
Incertidumbre operativa causada por una transición de roles dentro del equipo que no fue gestionada con fluidez.

### Causa
- Fallas en la comunicación: La transición no se comunicó con claridad ni antelación.

### Lecciones aprendidas
- Necesidad de roles definidos en todo momento para evitar solapamientos o vacíos.
- Las modificaciones estructurales deben notificarse formalmente.

### Mitigaciones
- Elaboración de un resumen de funciones tras cualquier cambio.
- Aclaración explícita y validación por parte del Product Owner (PO).

---

## 7. DEPENDENCIAS ENTRE CASOS DE USO
### Descripción
Bloqueos en el flujo de trabajo donde el avance de un equipo dependía directamente de la entrega de otro.

### Causa
- Análisis insuficiente de las tareas: No se estudió la relación técnica entre casos de uso antes de la asignación.

### Mitigaciones
- Análisis detallado y desglose de tareas para detectar dependencias tempranas.
- Establecer fechas límite escalonadas siguiendo el orden lógico de ejecución.

### Comprobación
- Semana 2: Verificar cumplimiento riguroso de deadlines para evitar bloqueos.

---

## 8. DESCOORDINACIÓN ENTRE GUION Y DIAPOSITIVAS
### Descripción
Falta de sincronía entre el discurso narrativo y el soporte visual, afectando la profesionalidad de la exposición.

### Causa
- Guion poco definido: No existía una estructura narrativa clara antes de diseñar el material visual.

### Mitigaciones
- Implementar el Modelo 1–3–3 (un hilo conductor, tres puntos clave, tres refuerzos visuales).

### Comprobación
- Semana 2: Entrega del material a tiempo con alineación total entre guion y soporte visual.
