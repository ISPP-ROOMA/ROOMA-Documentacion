# Problemas durante el desarrollo

Durante el desarrollo hemos encontrado los siguientes problemas:

## 1. Descompensación de trabajo

### Descripción
Se ha detectado que algunos miembros del equipo han invertido más tiempo que otros. Esto se debe a una asignación de actividades desequilibrada basada en puntos de historia, donde **1 punto = 1 hora de trabajo estimada**.

### Lecciones aprendidas
- La estimación inicial de puntos de historia no fue lo suficientemente precisa o no tuvo en cuenta la complejidad real de ciertas tareas.
- No se realizó una validación cruzada de la carga total de puntos asignada a cada integrante antes de comenzar el sprint.

### Mitigaciones
- Realizar sesiones de **Planning Poker** o estimación grupal más rigurosas para asegurar que los puntos de historia reflejen el esfuerzo real.
- Establecer un límite máximo y mínimo de puntos de historia por persona para garantizar la equidad en el esfuerzo.

### Comprobación de mitigaciones
El día 16/04 comprobar que todos los integrantes presentan una desviación típica de 2 horas o menos

## 2. Problemas con el despliegue el día de la entrega

### Descripción
El despliegue de la aplicación se realizó en una fecha cercana a la entrega final, lo que provocó que existieran errores el mismo día de la entrega

### Lecciones aprendidas
- No se reservó el tiempo suficiente en el cronograma específicamente para tareas de infraestructura.

### Mitigaciones
- Establecer una **congelación de funcionalidades** 72 horas antes de la entrega para dedicar las últimas 48 horas exclusivamente al despliegue y pruebas en producción.

### Comprobación de mitigaciones
El 25/03 no deben de haber mas de 3 commits de fix

## 3. Retrasos en el desarrollo

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

Para el 16/04 al menos un 80% de las tareas completadas dentro del plazo establecido.

## 4. Coordinación de la presentación

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
Comprobar que la presentación esta lista antes de las 16 del día de la entrega

## 5. Contenido de la presentación

### Descripción
En las presentaciones correspondientes al DP y Sprint 2 no incluimos contenido que se nos pidió explícitamente, lo que provocó penalizaciones en nuestra nota. A pesar de haber recibido feedback por parte de los profesores, dicho feedback no fue procesado ni trasladado correctamente al contenido final de la presentación.

### Leciones aprendidas
- A pesar de recopilar el feedback de los profesores y basar la presentación en dicho feedback, podemos concluir que no podemos dejar esta responsabilidad solo a una persona, ya que existe el riesgo de que se pasen por alto puntos importantes.
- La revisión del contenido de la presentación debe ser un proceso colectivo y estructurado, no informal.
- Es necesario contrastar siempre la presentación con los criterios de evaluación oficiales antes de darla por finalizada, y no basarse únicamente en el recuerdo o la interpretación de una sola persona.

### Mitigraciones
- Todas las personas del equipo deberán revisar individualmente la presentación mediante un checklist personal, comprobando que se incluyen todos los puntos requeridos. Posteriormente, se consolidará un checklist final común a partir de las revisiones individuales.
- El checklist debe elaborarse a partir del feedback recibido de los profesores y de los criterios de evaluación oficiales, y debe ser validado por todos los miembros antes de la presentación.
- Designar un responsable de hacer la primera versión del checklist, pero garantizando que la revisión final sea siempre colectiva.
### Comprobación de mitigraciones
Para el 16/04, no obtener ninguna penalización por contenido de la presentación en la evaluación.