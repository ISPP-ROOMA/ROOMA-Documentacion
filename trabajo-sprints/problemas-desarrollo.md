# Problemas durante el desarrollo

Durante el desarrollo hemos encontrado los siguientes problemas:

## 1. Reparto de tareas desigual

### Descripción
Se ha detectado que algunos miembros del equipo han invertido más tiempo que otros. Esto se debe a una asignación de actividades desequilibrada basada en puntos de historia, donde **1 punto = 1 hora de trabajo estimada**.

### Lecciones aprendidas
- La estimación inicial de puntos de historia no fue lo suficientemente precisa o no tuvo en cuenta la complejidad real de ciertas tareas.
- No se realizó una validación cruzada de la carga total de puntos asignada a cada integrante antes de comenzar el sprint.

### Mitigaciones
- Realizar sesiones de **Planning Poker** o estimación grupal más rigurosas para asegurar que los puntos de historia reflejen el esfuerzo real.
- Establecer un límite máximo y mínimo de puntos de historia por persona para garantizar la equidad en el esfuerzo.

### Comprobación de mitigaciones
Se comprobará en el próximo sprint comparando el sumatorio de puntos de historia finalizados por cada miembro al cierre del periodo.

## 2. Conflictos en la integración de ramas

### Descripción
Se han experimentado dificultades técnicas y retrasos al integrar el código debido a la existencia de un número excesivo de ramas abiertas simultáneamente.

### Lecciones aprendidas
- Cuanto más tiempo permanece una rama sin integrarse en la principal, más probable es que surjan conflictos de código.

### Mitigaciones
- Adoptar una política de ramas más efímeras, integrándolas en la rama principal cada dos días.
- Realizar integraciones frecuentes de la rama principal hacia las ramas de desarrollo para resolver conflictos de forma incremental.

### Comprobación de mitigaciones
Revisar el historial de Git para verificar que el tiempo de vida de las ramas se ha reducido y que los conflictos en los *merges* finales son mínimos.

## 3. Retraso en la fecha límite de despliegue

### Descripción
El despliegue de la aplicación se realizó en una fecha cercana a la entrega final, incumpliendo el objetivo interno de tener la versión estable desplegada dos días antes.

### Lecciones aprendidas
- No se reservó el tiempo suficiente en el cronograma específicamente para tareas de infraestructura.

### Mitigaciones
- Establecer una **congelación de funcionalidades** 72 horas antes de la entrega para dedicar las últimas 48 horas exclusivamente al despliegue y pruebas en producción.

### Comprobación de mitigaciones
Se verificará comprobando la fecha del despliegue exitoso en el entorno de producción frente a la fecha de entrega del **Sprint 3**.

## 4. Incumplimiento de deadlines internos y dependencias

### Descripción
En varias tareas del sprint, se ha producido un retraso debido a que algunas tareas dependían de otras que no se completaron a tiempo. Esto ha obligado a miembros del equipo a asumir tareas adicionales que no tenían asignadas originalmente para evitar bloquear el progreso.

### Lecciones aprendidas
- No se han definido deadlines internos suficientemente claros para todas las tareas.

- No se han gestionado correctamente las dependencias entre tareas.

### Mitigaciones
- Definir deadlines internos para TODAS las tareas, no solo las más críticas.

- Identificar dependencias entre tareas durante la planificación.

### Comprobación de mitigaciones
Hacer seguimiento del cumplimiento de deadlines mediante la herramienta de gestión.

Medir semanalmente el porcentaje de tareas que cumplen su deadline.

Objetivo: al menos un 80% de las tareas completadas dentro del plazo establecido.

## 5. Coordinación de la presentación

### Descripción
Han existido dudas sobre cómo coordinar el trabajo de la presentación, especialmente sobre si incluir únicamente la solución final o también todo el proceso previo, lo que ha generado incertidumbre y falta de alineación.

### Lecciones aprendidas
No se definió claramente el alcance y contenido esperado de la presentación.

Falta de alineación inicial entre los miembros del equipo.

### Mitigaciones
Definir desde el inicio el contenido esperado de la presentación (qué incluir y qué no).

Establecer una estructura clara y validarla con el equipo antes de comenzar.

Asignar un responsable de coordinación que centralice decisiones.

### Comprobación de mitigaciones
Evaluar si en siguientes presentaciones no hay bloqueos ni dudas iniciales.

Medir si la preparación comienza antes y se cumple el planning sin retrasos.