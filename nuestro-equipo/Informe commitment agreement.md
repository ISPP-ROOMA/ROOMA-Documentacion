# Informe de cumplimiento del Commitment Agreement

## 1. Objeto del informe

En este informe evaluamos hasta qué punto se ha cumplido el **Commitment Agreement** firmado para el proyecto **ROOMA**, usando como referencia las métricas que se definieron en su anexo de gobernanza y rendimiento. La idea es revisar si el equipo ha trabajado de forma coherente con lo que se comprometió en su día: dedicación, entrega de valor, cierre de tareas, trazabilidad, respaldo operativo y cohesión interna.

El periodo evaluado va desde el inicio efectivo de la asignatura hasta la fase de **Preparing Project Launch (#PPL)**, que todavía estaba abierta cuando se extrajeron los datos. Por eso, la fase **World Project Launch (#WPL)** no entra dentro del análisis cuantitativo principal.

## 2. Fuentes utilizadas

Para hacer este análisis se han usado las siguientes fuentes internas del proyecto:

- Commitment Agreement del equipo ROOMA.
- Calendario oficial de la asignatura y definición de fases: **#DP**, **#S1**, **#S2**, **#S3**, **#PPL** y **#WPL**.
- Exportación detallada de Clockify.
- Exportación de issues de GitHub.
- Exportación de commits únicos del repositorio.
- Registro Niko-niko de actividades de team building.

No se ha intentado forzar una correspondencia directa entre commits, issues y Story Points, ya que cada métrica mide una cosa distinta. Cada fuente se interpreta dentro de su propio ámbito: Clockify para la dedicación temporal, GitHub Issues para la planificación y el cierre de tareas, los Story Points para la entrega de valor y los commits como evidencia técnica del trabajo hecho.

## 3. Calendario de referencia

El calendario oficial de la asignatura divide el trabajo en varias fases evaluables. Para este informe se han usado las siguientes ventanas temporales:

| Fase | Periodo | Peso evaluativo | Enfoque principal |
|---|---:|---:|---|
| #DP | 29/01/2026 – 19/02/2026 | 5% | Definición del proyecto, MVP, mockups, metodología y planificación. |
| #S1 | 20/02/2026 – 05/03/2026 | 10% | Primer sprint de desarrollo, arranque del ALM, despliegue y plan de usuarios piloto. |
| #S2 | 06/03/2026 – 26/03/2026 | 15% | MVP v1, mejora continua y análisis de feedback. |
| #S3 | 27/03/2026 – 16/04/2026 | 30% | MVP v2, pivotado según feedback y plan de marketing. |
| #PPL | 17/04/2026 – 14/05/2026 | 40% | MVP v3, ejecución de marketing y plan de negocio. |
| #WPL | 15/05/2026 – 21/05/2026 | — | Lanzamiento y evaluación final. |

## 4. Resumen ejecutivo

En general el balance del Commitment Agreement es **positivo**. El equipo ha mantenido un ritmo de trabajo bastante constante, ha cerrado la mayoría de las tareas registradas, ha generado un volumen considerable de entrega de valor y ha acompañado el desarrollo técnico con mecanismos de coordinación, respaldo y cohesión grupal.

Mirando los números, se han analizado **262 issues**, de las que **251** están cerradas. Esto da un **95.8% de cierre global**. En las issues que sí incluyen estimación formal, se han registrado **344.5 Story Points**, de los cuales **317.5** están cerrados, lo que supone un **92.2% de cierre de valor estimado**. En cuanto a dedicación, Clockify recoge **1828.61 horas** repartidas entre **16 integrantes**, con una media de **114.29 horas por persona** durante el periodo analizado.

En definitiva, los datos indican que el equipo ha cumplido de forma bastante sólida con la finalidad del acuerdo: mantener transparencia, continuidad de trabajo, entrega de valor y capacidad de evolución entre fases. Las desviaciones que se ven se concentran sobre todo en la fase #PPL, que todavía no había terminado cuando se sacaron los datos, así que sus ratios hay que verlos como una foto parcial.

## 5. Resultados globales

| Métrica | Resultado |
|---|---:|
| Issues analizadas | 262 |
| Issues cerradas | 251 |
| Issues abiertas | 11 |
| Ratio global de cierre de issues | 95.8% |
| Issues con Story Points | 122 |
| Story Points registrados | 344.5 |
| Story Points cerrados | 317.5 |
| Ratio global de cierre de Story Points | 92.2% |
| Horas registradas en Clockify | 1828.61 h |
| Media de horas por integrante | 114.29 h |
| Entradas de tiempo en Clockify | 1136 |
| Commits únicos registrados | 496 |
| Autores identificados en commits | 20 |

## 6. Análisis por fases

La siguiente tabla recoge los principales indicadores fase por fase. El ratio de cierre se calcula tomando como base las issues creadas o planificadas dentro de cada ventana temporal. Para los Story Points solo se han contado las issues que llevan etiqueta formal `SP:x`.

| Fase   | Nombre                   | Periodo                 |   Peso % |   Issues planificadas |   Issues cerradas |   Cierre issues % |   SP comprometidos |   SP cerrados | Cierre SP %   |   Velocidad SP |   Horas |   Commits |
|:-------|:-------------------------|:------------------------|---------:|----------------------:|------------------:|------------------:|-------------------:|--------------:|:--------------|--------------:|--------:|----------:|
| #DP    | Devising a Project       | 2026-01-29 – 2026-02-19 |        5 |                    41 |                41 |             100   |                0   |           0   |               |           0   |  491.62 |         4 |
| #S1    | Sprint 1                 | 2026-02-20 – 2026-03-05 |       10 |                    69 |                64 |              92.8 |                0   |           0   |               |           0   |  439.32 |       239 |
| #S2    | Sprint 2                 | 2026-03-06 – 2026-03-26 |       15 |                    61 |                60 |              98.4 |              121   |         117   | 96.7          |         117   |  434.8  |       128 |
| #S3    | Sprint 3                 | 2026-03-27 – 2026-04-16 |       30 |                    65 |                63 |              96.9 |              150.5 |         147.5 | 98.0          |         143.5 |  299.12 |       100 |
| #PPL   | Preparing Project Launch | 2026-04-17 – 2026-05-14 |       40 |                    26 |                23 |              88.5 |               73   |          53   | 72.6          |          57   |  163.75 |        25 |

### Lectura de la evolución

Durante **#DP** y **#S1** el trabajo se centró sobre todo en definir el producto, planificar, arrancar la metodología y atacar las primeras tareas de desarrollo. En estas fases todavía no se usaban etiquetas de Story Points de forma sistemática, así que la valoración del cumplimiento se apoya básicamente en el cierre de issues y en la dedicación que aparece registrada.

A partir de **#S2** la métrica de Story Points ya cobra peso. En esta fase se comprometieron **121.0 SP** y se cerraron **117.0 SP**, lo que da un ratio de cierre del **96.7%**. Es un nivel de cumplimiento bastante alto sobre lo que se había planificado. En **#S3** la cosa fue todavía mejor: se comprometieron **150.5 SP** y se cerraron **147.5 SP**, alcanzando un **98.0%** de cierre. Además, la velocidad grupal pasó de **117.0 SP cerrados en #S2** a **143.5 SP cerrados en #S3**, lo que supone una mejora de aproximadamente un **22.6%**.

La fase **#PPL** todavía no había terminado cuando se extrajeron los datos, así que sus números corresponden a una medición intermedia. Aun así, ya muestra un **88.5% de cierre de issues** y un **72.6% de cierre de Story Points** sobre lo planificado, con **57.0 SP cerrados**, lo que indica que el trabajo de preparación del lanzamiento sigue avanzando a buen ritmo.

## 7. Métricas individuales

### 7.1. I-MT-01 / MT-01: dedicación mínima

El Commitment Agreement establecía dos umbrales de dedicación: una referencia recomendada de **10 horas semanales por integrante** y un mínimo de **8 horas semanales**. Esta métrica se ha evaluado con el informe detallado de Clockify, agrupando las horas por integrante, semana y fase.

El equipo ha registrado **1828.61 horas** durante el periodo analizado. Si nos quedamos con las semanas activas del calendario y descartamos las semanas singulares de Semana Santa y Feria de Abril, quedan **13 semanas activas** y el equipo acumula **1679.05 horas**. Frente a la referencia agregada de **2080 horas** (10 h/sem × 13 semanas × 16 integrantes) esto da un **80.7% de cumplimiento**, y frente al mínimo agregado de **1664 horas** (8 h/sem) el equipo se sitúa en un **100.9%**, es decir, justo por encima del mínimo comprometido. A nivel individual, **7 de 16 integrantes** superan el mínimo de 8 h/sem (104 h) en el cómputo acumulado, y **1 integrante** llega también a la referencia completa de 10 h/sem (130 h).

Con esto se puede considerar que el compromiso temporal se ha mantenido a nivel global, sobre todo teniendo en cuenta que el propio acuerdo ya contempla que pueda haber variaciones semanales por entregas, exámenes y temas personales. La carga de trabajo no ha sido perfectamente uniforme, pero sí lo bastante sostenida como para apoyar el avance del proyecto y el cierre de los entregables.

| Integrante | Horas en semanas activas | % vs. 10 h/sem (130 h) | % vs. 8 h/sem (104 h) |
|---|---:|---:|---:|
| Francisco Gago | 131.69 | 101.3% | 126.6% |
| Rafael Rodríguez | 123.94 | 95.3% | 119.2% |
| Juan Ruiz | 122.88 | 94.5% | 118.2% |
| David Chaves | 111.72 | 85.9% | 107.4% |
| Marco Herrera | 105.69 | 81.3% | 101.6% |
| Javier Lozano | 105.15 | 80.9% | 101.1% |
| Iván Frutos | 105.14 | 80.9% | 101.1% |
| Sergio García | 103.75 | 79.8% | 99.8% |
| Guillermo González | 99.08 | 76.2% | 95.3% |
| Javier Clavijo | 98.78 | 76.0% | 95.0% |
| David Basallote | 98.23 | 75.6% | 94.5% |
| Daniel Jiménez | 97.06 | 74.7% | 93.3% |
| Manuel Sánchez | 96.29 | 74.1% | 92.6% |
| Germán Moraga | 95.53 | 73.5% | 91.9% |
| Pablo Vargas | 92.27 | 71.0% | 88.7% |
| Jesús Ramírez | 91.85 | 70.7% | 88.3% |

### 7.2. I-MV-01: velocidad individual y evolución de valor

La evolución individual se ha calculado a partir de los Story Points cerrados por fase. Cuando una issue tenía varios responsables, los puntos se han repartido de forma proporcional entre ellos para que no aparezcan duplicados al sumar por persona.

| Integrante | #DP | #S1 | #S2 | #S3 | #PPL | Total SP cerrados | Evolución S2-S3 |
|---|---:|---:|---:|---:|---:|---:|---:|
| Juan Ruiz | 0 | 0 | 12.00 | 11.00 | 4.00 | 27.00 | -8.3% |
| Pablo Vargas | 0 | 0 | 3.00 | 11.00 | 10.00 | 24.00 | 266.7% |
| Germán Moraga | 0 | 0 | 10.00 | 8.00 | 6.00 | 24.00 | -20.0% |
| Marco Herrera | 0 | 0 | 8.00 | 9.00 | 7.00 | 24.00 | 12.5% |
| Rafael Rodríguez | 0 | 0 | 11.33 | 10.00 | 2.50 | 23.83 | -11.8% |
| Francisco Gago | 0 | 0 | 8.33 | 10.00 | 4.50 | 22.83 | 20.0% |
| Manuel Sánchez | 0 | 0 | 9.33 | 13.00 | 0.00 | 22.33 | 39.3% |
| Iván Frutos | 0 | 0 | 5.00 | 9.33 | 6.00 | 20.33 | 86.7% |
| Javier Clavijo | 0 | 0 | 8.00 | 11.33 | 0.00 | 19.33 | 41.7% |
| David Chaves | 0 | 0 | 5.00 | 7.33 | 6.00 | 18.33 | 46.7% |
| Guillermo González | 0 | 0 | 7.00 | 11.00 | 0.00 | 18.00 | 57.1% |
| Javier Lozano | 0 | 0 | 3.00 | 10.00 | 4.00 | 17.00 | 233.3% |
| Sergio García | 0 | 0 | 10.00 | 4.00 | 3.00 | 17.00 | -60.0% |
| David Basallote | 0 | 0 | 7.00 | 4.50 | 2.00 | 13.50 | -35.7% |
| Jesús Ramírez | 0 | 0 | 5.00 | 6.00 | 2.00 | 13.00 | 20.0% |
| Daniel Jiménez | 0 | 0 | 5.00 | 8.00 | 0.00 | 13.00 | 60.0% |

La conclusión principal es que casi todos los integrantes tienen actividad de valor en las fases en las que los Story Points sí están registrados de forma formal. En particular, entre **#S2** y **#S3** se nota una mejora bastante clara en varios perfiles, lo que cuadra con el aumento de velocidad grupal. Las bajadas puntuales no se deberían leer de manera aislada, ya que el reparto de tareas cambia bastante según el tipo de trabajo: desarrollo, documentación, presentaciones, pruebas, marketing, despliegue o coordinación.

## 8. Métricas grupales

### 8.1. G-MV-01: ratio de cierre o throughput

El throughput se ha calculado como la relación entre el trabajo cerrado y el trabajo planificado en cada fase.

Si miramos las issues, el equipo se mantiene en ratios muy altos durante todo el desarrollo:

- **#DP:** 100.0% de cierre de issues.
- **#S1:** 92.8% de cierre de issues.
- **#S2:** 98.4% de cierre de issues.
- **#S3:** 96.9% de cierre de issues.
- **#PPL:** 88.5% de cierre de issues (fase aún en curso al cierre del análisis).

En cuanto a Story Points, la medición tiene especial sentido a partir de #S2:

- **#S2:** 96.7% de cierre de Story Points.
- **#S3:** 98.0% de cierre de Story Points.
- **#PPL:** 72.6% de cierre de Story Points (medición intermedia).

Con estos números se puede afirmar que el equipo ha cumplido el compromiso de cierre de tareas y de entrega de valor en las fases ya evaluadas. El ratio algo más bajo de #PPL se entiende como algo normal de una fase que todavía estaba abierta cuando se sacaron los datos, y aun así supera el 88% en cierre de issues.

### 8.2. G-MV-02 / MV-02: evolución de velocidad grupal

La evolución de la velocidad grupal confirma que ha habido una progresión positiva durante el grueso del desarrollo. El salto de **117.0 SP cerrados en #S2** a **143.5 SP cerrados en #S3** muestra una mejora clara en la capacidad de entrega del equipo. Esta mejora encaja con el avance natural en conocimiento técnico, dominio del producto y coordinación interna que se va ganando con el tiempo.

La fase #PPL todavía no se puede comparar de forma definitiva porque no había terminado al sacar los datos. Aun así, ya tiene **57.0 SP cerrados**, lo que demuestra que el trabajo de preparación del lanzamiento ha continuado sin parón.

## 9. Trazabilidad y evidencia técnica

### 9.1. I-MT-02 / MT-02: trazabilidad cruzada

La trazabilidad se ha analizado sin forzar una relación directa entre commits, issues y Story Points. Cada fuente se ha usado para medir una dimensión distinta del trabajo:

- **Clockify** muestra la dedicación temporal y permite ver cómo se reparte el esfuerzo por integrante y por fase.
- **GitHub Issues** muestra cómo se planifican, asignan y cierran las tareas.
- **Story Points** miden el valor estimado y el valor cerrado en las tareas que sí incorporan estimación formal.
- **Commits** aportan evidencia técnica verificable directamente en el repositorio.

Con este enfoque, la trazabilidad general del proyecto se considera adecuada: hay registros de tiempo, planificación en GitHub, cierre de tareas, estimación progresiva mediante Story Points y evidencia técnica en forma de **496 commits únicos**. El volumen de commits se concentra sobre todo en #S1, #S2 y #S3, que son justamente las fases de construcción y consolidación del MVP.

| Fase | Commits únicos |
|---|---:|
| #DP | 4 |
| #S1 | 239 |
| #S2 | 128 |
| #S3 | 100 |
| #PPL | 25 |

## 10. Cumplimiento de tareas y respaldo operativo

### 10.1. MO-02: cumplimiento de tareas y planes de respaldo

El equipo ha trabajado con una dinámica de asignación de responsables y respaldo en las tareas críticas. Esta forma de trabajar ha ayudado a reducir bloqueos, mantener la continuidad del desarrollo y asegurar que las tareas importantes pudieran seguir avanzando aunque surgieran incidencias, choques de horarios o dependencias entre módulos.

El cumplimiento de tareas se considera alto. De las **262 issues** analizadas, **251** están cerradas, lo que equivale a un **95.8% de cierre global**. En las fases ya completadas, los ratios de cierre se mantienen por encima del 90% de manera sostenida, lo que demuestra que el equipo ha sido capaz de terminar la mayor parte del trabajo planificado.

El respaldo operativo también se considera cumplido. Las tareas críticas se han llevado adelante con revisión, coordinación entre los responsables y apoyo entre los miembros del equipo. Esta forma de trabajar ha sido especialmente útil en áreas como el despliegue, las pruebas, la corrección de errores, la preparación de los entregables y la presentación de los resultados.

## 11. Motivación, cohesión y Niko-niko

### 11.1. G-MO-01 / MO-01: Motivation Track

El seguimiento de la motivación se ha hecho a través del Niko-niko y de las actividades de team building. El registro recoge actividades como desayuno, pádel, almuerzo, running, comida y casa rural. La escala que se usa va de 1 a 5, desde un estado de ánimo muy bajo hasta excelente.

Si nos quedamos con las actividades que tienen medición previa y posterior, la media agregada pasa de **2.83 antes de la actividad** a **4.14 después de la actividad**, con una mejora media de **1.31 puntos** y una mejora relativa de aproximadamente un **46.1%**.

| Actividad      |   Participantes con pre/post |   Media antes |   Media después |   Mejora |   Mejora % |
|:---------------|-----------------------------:|--------------:|----------------:|---------:|-----------:|
| Desayuno 19/03 |                            6 |          3    |            4.17 |     1.17 |       38.9 |
| Pádel 22/03    |                            7 |          2.86 |            4.43 |     1.57 |       55   |
| Almuerzo 26/03 |                            8 |          2.75 |            4    |     1.25 |       45.5 |
| Running 10/04  |                            5 |          2.4  |            4.2  |     1.8  |       75   |
| Comida 12/04   |                           10 |          3    |            4    |     1    |       33.3 |

La interpretación es claramente positiva: las actividades de team building han ayudado a mejorar el ambiente del grupo, reforzar la cohesión y evitar que se formaran subgrupos aislados. Además, organizar actividades en abril hizo posible incluir a integrantes que no habían podido apuntarse a las dinámicas anteriores, lo que ha equilibrado más el clima del equipo.

## 12. Checklist de cumplimiento

| Ámbito | ID | Criterio | Resultado | Valoración |
|---|---|---|---|---|
| Individual | MT-01 | Dedicación: mínimo 8 h/sem y referencia 10 h/sem | 100.9% sobre el mínimo de 8 h/sem y 80.7% sobre la referencia de 10 h/sem | Cumplido |
| Individual | MT-02 | Trazabilidad entre dedicación, planificación y evidencia técnica | Clockify, GitHub Issues, Story Points y commits disponibles | Cumplido |
| Individual | MV-01 | Evolución de velocidad individual | Actividad de SP distribuida entre los integrantes en #S2, #S3 y #PPL | Cumplido |
| Grupal | G-MV-01 | Ratio de cierre del trabajo planificado | 95.8% de cierre global de issues y 92.2% de cierre global de SP | Cumplido |
| Grupal | G-MV-02 | Evolución positiva o estable de Story Points | Mejora de 117.0 SP en #S2 a 143.5 SP en #S3 | Cumplido |
| Grupal | MO-01 | Participación y motivación del equipo | Mejora media del Niko-niko de 1.31 puntos | Cumplido |
| Grupal | MO-02 | Planes de respaldo en tareas críticas | Responsables y apoyo operativo en tareas críticas | Cumplido |
| Grupal | MO-03 | Team building y cohesión | Actividades sociales y deportivas durante el cuatrimestre | Cumplido |

## 13. Valoración final

En conjunto, el Commitment Agreement se ha cumplido de forma bastante sólida. El equipo ha mantenido una estructura de trabajo organizada, ha registrado dedicación en Clockify, ha planificado y cerrado tareas en GitHub, ha incorporado los Story Points para medir la entrega de valor y ha generado evidencia técnica continuada mediante commits. Además, se han hecho actividades de cohesión que han tenido un efecto positivo sobre el estado de ánimo y sobre cómo funciona el grupo.

El punto fuerte más claro del periodo analizado es el alto nivel de cierre del trabajo planificado. Los ratios de cierre de issues en #DP, #S1, #S2, #S3 y #PPL están todos por encima del 88%, alcanzando el 100% en #DP, y los ratios de cierre de Story Points en #S2 y #S3 superan el 96%. Esto demuestra que el equipo no solo ha trabajado, sino que ha sabido convertir ese trabajo en entregables cerrados y en valor que se puede medir.

También hay que destacar la evolución positiva de la velocidad grupal. El aumento de Story Points cerrados entre #S2 y #S3 refleja una mejora en la capacidad de ejecución del equipo, algo que encaja con una mayor madurez técnica y organizativa. Esta evolución va precisamente en la línea que pedía el Commitment Agreement, que da prioridad a la mejora continua y a la entrega progresiva de valor por encima de una lectura aislada de las horas.

La dedicación temporal sí presenta cierta desigualdad entre semanas e integrantes, lo cual es bastante esperable en un proyecto académico con entregas, exámenes, semanas especiales y cargas variables. Aun así, el volumen total registrado permite concluir que el compromiso de tiempo se ha mantenido de forma razonable a nivel de equipo.

En conclusión, el acuerdo ha funcionado como mecanismo de gobernanza interna. Ha servido para ordenar el trabajo, hacer visible la contribución de cada uno, reforzar la responsabilidad individual y sostener una dinámica de mejora continua. Por todo esto, el grado de cumplimiento general del Commitment Agreement se puede considerar **satisfactorio**, con un nivel especialmente bueno en cierre de tareas, entrega de valor, evolución grupal, respaldo operativo y cohesión del equipo.
