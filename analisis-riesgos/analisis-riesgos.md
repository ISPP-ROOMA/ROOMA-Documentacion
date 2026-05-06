# Análisis de riesgos

## Índice

1. [Análisis de riesgos](#análisis-de-riesgos)  
2. [Categorías de riesgos](#categorías-de-riesgos)  
3. [Metodología para análisis de riesgos](#metodología-para-análisis-de-riesgos)  
4. [Impacto](#impacto)  
5. [Metodología para priorización de riesgos](#metodología-para-priorización-de-riesgos)  
6. [Roles y responsables](#roles-y-responsables)  
7. [Matriz Probabilidad × Impacto](#matriz-probabilidad--impacto)  
8. [Identificación y Clasificación de Riesgos](#identificación-y-clasificación-de-riesgos)  
9. [Escenarios económicos](#escenarios-económicos-optimista-vs-pesimista)  
10. [Análisis de viabilidad y puntos de equilibrio](#análisis-de-viabilidad-y-puntos-de-equilibrio)  
11. [Flujo de caja del proyecto: caso optimista](#flujo-de-caja-del-proyecto-caso-optimista)  
12. [Flujo de caja del proyecto: caso pesimista](#flujo-de-caja-del-proyecto-caso-pesimista)  
13. [Planes de contingencia](#planes-de-contingencia-acciones-de-mitigación)

---

## Categorías de riesgos

| Riesgo | Definición |
|:---|:---|
| Externo | Riesgo que no depende de ninguna forma de la organización. |
| Mercado | Riesgo asociado al mercado, demanda, competencia, conversión y adopción. |
| Legislativo | Riesgo asociado a normas o legislaciones que apliquen sobre el desarrollo. |
| Licencias | Riesgo asociado a licencias de productos. |
| Financiero | Riesgo asociado a la falta de capital, desviaciones de costes o retraso del retorno. |
| Recursos | Riesgo asociado a falta de personal, conocimiento o disponibilidad del equipo. |
| Proveedores | Riesgo asociado a proveedores externos, APIs, pasarelas de pago o hosting. |
| Adquisiciones | Riesgo asociado a adquisiciones o disponibilidad de equipamiento. |
| Dirección del proyecto | Riesgo asociado a planificación, coordinación y toma de decisiones. |
| Desempeño | Riesgo asociado a desempeño no positivo del equipo de desarrollo. |
| Calidad | Riesgo asociado a errores, baja estabilidad o mala experiencia de usuario. |
| Alcance | Riesgo asociado a crecimiento no controlado del alcance del proyecto. |
| Requisitos | Riesgo asociado a requisitos ambiguos, incompletos o cambiantes. |
| Tecnológico | Riesgo asociado a tecnologías, librerías, frameworks e integraciones. |
| Seguridad | Riesgo asociado a baja seguridad, pérdida de datos o accesos no autorizados. |

---

## Metodología para análisis de riesgos

| Probabilidad | Valor | Descripción | Rango (%) |
|:---|:---:|:---|:---|
| Muy bajo | 1 | Casi imposible que ocurra | 0% < P ≤ 1% |
| Bajo | 3 | Poco probable que ocurra | 1% < P ≤ 10% |
| Moderado | 5 | Ocurre de vez en cuando | 10% < P ≤ 50% |
| Alto | 7 | Ocurre con frecuencia | 50% < P ≤ 80% |
| Muy alto | 9 | Casi seguro que ocurre | 80% < P ≤ 100% |

---

## Impacto

| Dimensión | Muy bajo (1) | Bajo (3) | Moderado (5) | Alto (7) | Muy alto (9) |
|:---|:---|:---|:---|:---|:---|
| Alcance | Afecta a menos del 5% de los paquetes de trabajo. | Afecta entre el 5% y el 10% de los paquetes de trabajo. | Afecta entre el 10% y el 20% de los paquetes de trabajo. | Afecta entre el 20% y el 30% de los paquetes de trabajo. | Afecta a más del 30% de los paquetes de trabajo. |
| Tiempo | No afecta a actividades de la cadena crítica. | Afecta a actividades de la cadena crítica, pero no extiende la duración del proyecto. | Extiende la duración del proyecto menos del 2%. | Extiende la duración del proyecto menos del 5%. | Extiende la duración del proyecto más del 5%. |
| Costes | Aumenta los costes en menos del 1%. | Aumenta los costes en menos del 3%. | Aumenta los costes en menos del 5%. | Aumenta los costes en menos del 7%. | Aumenta los costes en más del 7%. |

---

## Metodología para priorización de riesgos

La prioridad se determina calculando el valor del riesgo mediante el producto de probabilidad por impacto:

**R = P × I**

La probabilidad se expresa como porcentaje normalizado y el impacto se valora en escala de 1 a 9. Según su posición en la matriz, se categorizan los riesgos en tres niveles:

- 🟢 **Bajo:** R < 2  
- 🟠 **Medio:** 2 ≤ R ≤ 4  
- 🔴 **Alto:** R > 4  

---

## Roles y responsables

| Rol | Responsable |
|:---|:---|
| Recogida de riesgos | Jefe de proyecto |
| Análisis y priorización de riesgos | Jefe de proyecto |
| Seguimiento de riesgos | Jefe de proyecto |
| Aplicación de planes de contingencia | Jefe de proyecto |
| Seguimiento técnico de riesgos críticos | Equipo de desarrollo |
| Seguimiento económico de riesgos de mercado | Jefe de proyecto + responsable económico |

---

## Matriz Probabilidad × Impacto

La matriz Probabilidad × Impacto relaciona la probabilidad de que ocurra un riesgo con el impacto que tendría sobre el proyecto.

Cada casilla contiene un valor numérico obtenido multiplicando la probabilidad por el impacto. Ese valor sirve como puntuación de riesgo.

Se utiliza el siguiente código:

- 🟢 Verde = bajo  
- 🟠 Naranja = medio  
- 🔴 Rojo = alto  

| Impacto \ Probabilidad | 1% | 10% | 40% | 70% | 90% |
|:---|:---:|:---:|:---:|:---:|:---:|
| Muy alto (9) | 🟢 0,09 | 🟢 0,9 | 🟠 3,6 | 🔴 6,3 | 🔴 8,1 |
| Alto (7) | 🟢 0,07 | 🟢 0,7 | 🟠 2,8 | 🔴 4,9 | 🔴 6,3 |
| Medio (5) | 🟢 0,05 | 🟢 0,5 | 🟠 2 | 🟠 3,5 | 🔴 4,5 |
| Bajo (3) | 🟢 0,03 | 🟢 0,3 | 🟢 1,2 | 🟠 2,1 | 🟠 2,7 |
| Muy bajo (1) | 🟢 0,01 | 🟢 0,1 | 🟢 0,4 | 🟢 0,7 | 🟢 0,9 |

---

## Identificación de riesgos del proyecto

| ID | Riesgo | Categoría | Prioridad | Impacto | Alcance | Tiempo | Costes | Probabilidad | Seguimiento | Respuesta | Plan de contingencia |
|:---|:---|:---|:---:|---:|---:|---:|---:|---:|:---|:---|:---|
| R-001 | Requisitos ambiguos o incompletos | Requisitos | 🔴 Alta | 4,20 | 7 | 5 | 3 | 60% | Jefe de proyecto | Jefe de proyecto | Workshops de requisitos, historias de usuario, definición de criterios de aceptación y acta de alcance firmada. |
| R-002 | Retraso o fallo en proveedor hosting / dominio / SSL | Proveedores | 🟢 Baja | 1,75 | 3 | 7 | 3 | 25% | Jefe de proyecto | Desarrollador analista | Contratar hosting inicial con opción de rescisión rápida; mantener cuenta alternativa y backups. |
| R-003 | Bugs críticos en funcionalidades clave | Calidad / Tecnológico | 🔴 Alta | 4,05 | 5 | 9 | 5 | 45% | Analista | Desarrollador | Integrar revisiones de código, pruebas unitarias, pruebas funcionales y pruebas de aceptación antes de despliegue. |
| R-004 | Recortes o falta de presupuesto para hosting / herramientas | Financiero | 🟢 Baja | 1,40 | 3 | 3 | 7 | 20% | Jefe de proyecto | Jefe de proyecto | Priorizar MVP, usar soluciones gratuitas o de bajo coste temporalmente y preparar opciones alternativas. |
| R-005 | Pérdida o filtración de datos de usuarios | Seguridad | 🟢 Baja | 1,00 | 3 | 5 | 7 | 20% | Desarrollador / Analista | Desarrollador / Analista | Política de privacidad, cumplimiento RGPD, cifrado, control de accesos, revisión de almacenamiento y pruebas de seguridad. |
| R-006 | Falta de habilidades específicas | Recursos | 🟠 Media | 2,45 | 7 | 7 | 5 | 35% | Jefe de proyecto | Jefe de proyecto / Desarrollador analista | Formación rápida, apoyo puntual, revisión de tareas críticas y tiempo adicional asignado en cronograma. |
| R-007 | API de terceros deja de funcionar o cambia condiciones | Proveedores | 🟠 Media | 2,00 | 5 | 5 | 3 | 40% | Jefe de proyecto | Jefe de proyecto | Diseño de integración desacoplada, fallback local o caché, monitorización y alerta. |
| R-008 | Entregas fuera de plazo por mala estimación | Calidad / Dirección | 🔴 Alta | 4,55 | 7 | 7 | 5 | 65% | Jefe de proyecto | Jefe de proyecto | Revisar estimaciones, seguimiento semanal, replanificación y reasignación rápida. |
| R-009 | Nuevas exigencias de protección de datos | Legislativo | 🟢 Baja | 0,60 | 3 | 3 | 1 | 20% | Jefe de proyecto | Equipo de desarrollo | Revisar cumplimiento legal, auditar datos tratados y preparar plan de corrección rápida. |
| R-010 | Demora en entrega de equipo de pruebas | Adquisiciones | 🟢 Baja | 1,75 | 3 | 7 | 3 | 25% | Jefe de proyecto | Jefe de proyecto | Pedir reservas de equipo anticipado, plan B con emuladores o dispositivos de stock. |
| R-011 | Obsolescencia de librerías o frameworks | Tecnológico | 🟠 Media | 2,10 | 7 | 3 | 1 | 30% | Desarrollador / Analista | Desarrollador / Analista | Monitorización de librerías, actualizaciones programadas y plan de migración. |
| R-012 | Vulnerabilidad en la web | Seguridad | 🟠 Media | 2,50 | 5 | 5 | 5 | 40% | Desarrollador / Analista | Desarrollador / Analista | Revisión de código, escaneo de vulnerabilidades y endurecimiento de configuración. |
| R-013 | Riesgo de disrupción prolongada | Externo | 🟢 Baja | 0,18 | 9 | 9 | 9 | 2% | Jefe de proyecto | Jefe de proyecto | Trabajo remoto, replanificación por fases y priorización de entregables críticos. |
| R-014 | Baja conversión Premium | Mercado / Financiero | 🔴 Alta | 4,50 | 5 | 5 | 9 | 50% | Jefe de proyecto | Responsable económico / Marketing | Revisar propuesta de valor, mejorar beneficios de Plus/Pro, probar descuentos temporales y campañas de reactivación. |
| R-015 | Inflación del CAC efectivo | Mercado / Financiero | 🔴 Alta | 4,90 | 5 | 5 | 9 | 70% | Responsable económico | Marketing | Reforzar canales orgánicos, referidos, SEO, grupos universitarios y usuarios piloto para reducir dependencia de Ads. |
| R-016 | Baja adopción del módulo transaccional | Mercado / Producto | 🔴 Alta | 4,95 | 7 | 5 | 9 | 55% | Jefe de proyecto | Producto / Marketing | Mejorar confianza, explicar garantías, reforzar onboarding financiero y simplificar pagos/facturas. |
| R-017 | Efecto "ciudad fantasma" | Mercado / Producto | 🔴 Alta | 4,90 | 9 | 5 | 7 | 70% | Jefe de proyecto | Producto / Marketing | Captar oferta antes de escalar demanda, acuerdos con propietarios, agencias y residencias. |

---

## Identificación y clasificación de riesgos

| Categoría | Riesgo seleccionado | Impacto en Rooma |
|:---|:---|:---|
| Mercado | Baja conversión Premium | La conversión de Rooma Plus puede bajar del 25% al 10% y la de Rooma Pro del 3,75% al 1%. |
| Legal / Confianza | Fraude y perfiles falsos | Anuncios falsos dañan la reputación y obligan a invertir en verificación, soporte y control. |
| Económico | Inflación del CAC | El coste efectivo de adquisición puede subir de 0,80 €/usuario a 1,24 €/usuario o más si falla el canal orgánico. |
| Seguridad | Brecha de datos | Acceso no autorizado a datos personales, ubicación o información de pagos, con pérdida de confianza y posible sanción. |
| Producto | Efecto "ciudad fantasma" | Si un usuario hace swipe y no hay pisos o perfiles suficientes en su zona, abandona la app. |
| Operativo | Baja adopción del módulo financiero | Si los usuarios no usan facturas/pagos, cae la principal vía de ingresos del modelo. |

---

## Escenarios Económicos: Optimista vs. Pesimista

### Escenario A: Optimista / Plan base

Basado en el documento de presupuesto de lanzamiento:

- **Margen de contribución unitario:** 7,82 € por usuario  
- **Costes fijos mensuales:** 16.058,44 €  
- **Inversión inicial a recuperar:** 76.865,08 €  

| Vía de ingreso | Base de cálculo | Ingreso por unidad | Ingreso ponderado ($u$) |
|:---|:---:|---:|---:|
| **Suscripción Rooma Plus** | 25% | 5,99 € | 1,50 € |
| **Suscripción Rooma Pro** | 3,75% | 15,99 € | 0,60 € |
| **Add-on: Pack Individual** | 15% | 0,99 € | 0,15 € |
| **Add-on: Pack de Ahorro** | 5% | 3,99 € | 0,20 € |
| **Comisiones transaccionales** | 25% | 42,50 € | 10,62 € |
| **TOTAL INGRESO BRUTO (ARPU)** | — | — | **13,07 €** |

### Lectura del escenario base

El escenario base depende especialmente de tres hipótesis:

1. Que la conversión Premium alcance el 28,75% combinado entre Plus y Pro.
2. Que el 25% de usuarios tenga contrato activo y use el módulo transaccional.
3. Que el CAC efectivo se mantenga en torno a 0,80 €/usuario gracias a la combinación de Ads, orgánico, referidos, pilotos y captación directa.

---

### Escenario B: Pesimista / Impacto de riesgos

Se aplica una caída severa en conversión y monetización:

- Rooma Plus: **25% → 10%**
- Rooma Pro: **3,75% → 1%**
- Add-ons: **20% combinado → 7%**
- Usuarios con contrato activo / comisiones: **25% → 9,8%**
- Ads / CAC efectivo: **0,80 €/usuario → 1,24 €/usuario**
- Costes fijos: incremento del **20%** por contingencias, soporte y mitigación.

| Vía de ingreso | Conversión | Ingreso unitario | Ingreso ponderado |
|:---|:---:|---:|---:|
| Suscripción Plus | 10,0% | 5,99 € | 0,60 € |
| Suscripción Pro | 1,0% | 15,99 € | 0,16 € |
| Add-ons media | 7,0% | 2,00 € | 0,14 € |
| Comisiones transaccionales | 9,8% | 42,50 € | 4,15 € |
| **ARPU TOTAL** | — | — | **5,05 €** |

### Nuevas hipótesis de coste pesimista

- **Stripe ponderado:** 1,74 €/usuario  
- **Ads / CAC efectivo:** 1,24 €/usuario  
- **Cloud:** 0,01 €/usuario  
- **Gastos variables totales:** 2,99 €/usuario  
- **Margen unitario:** 5,05 € - 2,99 € = **2,06 €/usuario**  
- **Costes fijos mensuales:** 19.270,13 €  

### Lectura del escenario pesimista

El escenario pesimista no implica que el proyecto sea inviable, pero sí retrasa de forma importante la recuperación de la inversión. El problema principal no es solo captar menos usuarios, sino captar usuarios que generan menos ingresos y cuestan más de adquirir.

---

## Análisis de Viabilidad y Puntos de Equilibrio

### Mínimo de clientes para cubrir costes de operación

Es el número de usuarios necesarios cada mes para que los ingresos igualen a los gastos corrientes.

- **Escenario optimista / base:**  
  16.058,44 / 7,82 ≈ **2.054 usuarios**

- **Escenario pesimista:**  
  19.270,13 / 2,06 ≈ **9.355 usuarios**

| Escenario | Costes fijos | Margen unitario | Punto de equilibrio |
|:---|---:|---:|---:|
| Optimista / Base | 16.058,44 € | 7,82 €/usuario | 2.054 usuarios |
| Pesimista | 19.270,13 € | 2,06 €/usuario | 9.355 usuarios |

---

### Mínimo de clientes para el ROI

Número de clientes necesarios para recuperar la inversión total de desarrollo y lanzamiento.

- **Escenario optimista / base:**  
  Se alcanza en el **mes 13** con la curva prevista de **10.000 usuarios**.

- **Escenario pesimista:**  
  El ROI se desplaza al **mes 23**, requiriendo aproximadamente **35.704 usuarios**.

| Hito | Escenario optimista / base | Escenario pesimista |
|:---|:---:|:---:|
| Break-even operativo | Mes 9 | Mes 12 |
| Usuarios para break-even | 2.054 | 9.355 |
| Payback / ROI | Mes 13 | Mes 23 |
| Usuarios aproximados para ROI | 10.000 | 35.704 |

---

## Flujo de Caja del Proyecto: Caso optimista

| Mes | Usuarios (u) | Ingreso mensual | Gasto mensual | Beneficio mes | Caja neta acum. |
|:---|---:|---:|---:|---:|---:|
| **Pre** | 0 | 0,00 € | 76.865,08 € | - | **-76.865,08 €** |
| **1** | 100 | 1.307,00 € | 16.583,44 € | -15.276,44 € | **-92.141,52 €** |
| **2** | 152 | 1.986,64 € | 16.856,44 € | -14.869,80 € | **-107.011,32 €** |
| **3** | 231 | 3.019,17 € | 17.271,19 € | -14.252,02 € | **-121.263,34 €** |
| **4** | 352 | 4.600,64 € | 17.906,44 € | -13.305,80 € | **-134.569,14 €** |
| **5** | 535 | 6.992,45 € | 18.867,19 € | -11.874,74 € | **-146.443,88 €** |
| **6** | 813 | 10.625,91 € | 20.326,69 € | -9.700,78 € | **-156.144,66 €** |
| **7** | 1.235 | 16.141,45 € | 22.542,19 € | -6.400,74 € | **-162.545,40 €** |
| **8** | 1.878 | 24.545,46 € | 25.917,94 € | -1.372,48 € | **-163.917,88 €** |
| **9** | **2.854** | 37.301,78 € | 31.041,94 € | **+6.259,84 €** | **-157.658,04 €** |
| **10** | 4.338 | 56.697,66 € | 38.832,94 € | +17.864,72 € | **-139.793,32 €** |
| **11** | 6.597 | 86.222,79 € | 50.692,69 € | +35.530,10 € | **-104.263,22 €** |
| **12** | **10.000** | 130.700,00 € | 68.558,44 € | **+62.141,56 €** | **-42.121,66 €** |
| **13** | 10.000 | 130.700,00 € | 68.558,44 € | +62.141,56 € | **+20.019,90 €** |
| **14** | 10.000 | 130.700,00 € | 68.558,44 € | +62.141,56 € | **+82.161,46 €** |

---

## Flujo de Caja del Proyecto: Caso pesimista

| Mes | Usuarios (u) | Ingreso mensual | Gasto mensual | Beneficio mes | Caja neta acum. |
|:---|---:|---:|---:|---:|---:|
| Pre | 0 | 0,00 € | 76.865,08 € | - | -76.865,08 € |
| 1 | 100 | 505,00 € | 19.569,13 € | -19.064,13 € | -95.929,21 € |
| 2 | 152 | 767,60 € | 19.724,61 € | -18.957,01 € | -114.886,22 € |
| 3 | 231 | 1.166,55 € | 19.960,82 € | -18.794,27 € | -133.680,49 € |
| 4 | 352 | 1.777,60 € | 20.322,61 € | -18.545,01 € | -152.225,50 € |
| 5 | 535 | 2.701,75 € | 20.869,78 € | -18.168,03 € | -170.393,53 € |
| 6 | 813 | 4.105,65 € | 21.701,00 € | -17.595,35 € | -187.988,88 € |
| 7 | 1.235 | 6.236,75 € | 22.962,78 € | -16.726,03 € | -204.714,91 € |
| 8 | 1.878 | 9.483,90 € | 24.885,35 € | -15.401,45 € | -220.116,36 € |
| 9 | 2.854 | 14.412,70 € | 27.803,59 € | -13.390,89 € | -233.507,25 € |
| 10 | 4.338 | 21.906,90 € | 32.240,75 € | -10.333,85 € | -243.841,10 € |
| 11 | 6.597 | 33.314,85 € | 38.995,16 € | -5.680,31 € | -249.521,41 € |
| 12 | 10.000 | 50.500,00 € | 49.170,13 € | +1.329,87 € | -248.191,54 € |
| 13 | 11.227 | 56.696,35 € | 52.838,86 € | +3.857,49 € | -244.334,05 € |
| 14 | 12.604 | 63.650,20 € | 56.956,09 € | +6.694,11 € | -237.639,94 € |
| 15 | 14.150 | 71.457,50 € | 61.578,63 € | +9.878,87 € | -227.761,07 € |
| 16 | 15.885 | 80.219,25 € | 66.766,28 € | +13.452,97 € | -214.308,10 € |
| 17 | 17.833 | 90.056,65 € | 72.590,80 € | +17.465,85 € | -196.842,25 € |
| 18 | 20.021 | 101.106,05 € | 79.132,92 € | +21.973,13 € | -174.869,12 € |
| 19 | 22.477 | 113.508,85 € | 86.476,36 € | +27.032,49 € | -147.836,63 € |
| 20 | 25.233 | 127.426,65 € | 94.716,80 € | +32.709,85 € | -115.126,78 € |
| 21 | 28.329 | 143.061,45 € | 103.973,84 € | +39.087,61 € | -76.039,17 € |
| 22 | 31.803 | 160.605,15 € | 114.361,10 € | +46.244,05 € | -29.795,12 € |
| 23 | 35.704 | 180.305,20 € | 126.025,09 € | +54.280,11 € | +24.484,99 € |
| 24 | 40.083 | 202.419,15 € | 139.118,30 € | +63.300,85 € | +87.785,84 € |
| 25 | 45.000 | 227.250,00 € | 153.820,13 € | +73.429,87 € | +161.215,71 € |
| 26 | 50.520 | 255.126,00 € | 170.324,93 € | +84.801,07 € | +246.016,78 € |
| 27 | 56.716 | 286.415,80 € | 188.850,97 € | +97.564,83 € | +343.581,61 € |
| 28 | 63.673 | 321.548,65 € | 209.652,40 € | +111.896,25 € | +455.477,86 € |

---

## Planes de Contingencia (Acciones de Mitigación)

### Contingencia Legal / Confianza

**Riesgo:** fraude, perfiles falsos o anuncios no verificados.  
**Acciones:**

- Verificación por DNI obligatoria para anunciantes Pro.
- Validación manual de perfiles sospechosos.
- Sistema de reporte de anuncios.
- Revisión prioritaria de publicaciones nuevas en zonas con alta demanda.
- Mensajes claros sobre seguridad y verificación en onboarding.

---

### Mitigación de baja conversión Premium

**Riesgo:** caída de Rooma Plus del 25% al 10% y Rooma Pro del 3,75% al 1%.  
**Acciones:**

- Reforzar beneficios visibles de Rooma Plus.
- Aplicar promociones de lanzamiento o cuentas fundador.
- Reducir beneficios del nivel Free si la conversión es baja.
- Pasar de 20 swipes diarios a 5 swipes diarios si el modelo necesita mayor incentivo de pago.
- Potenciar Add-ons como alternativa de bajo coste para usuarios que no quieren suscripción completa.

---

### Plan ante escasez de oferta

**Riesgo:** efecto "ciudad fantasma" por falta de pisos, habitaciones o propietarios activos.  
**Acciones:**

- Captación directa de propietarios antes de escalar campañas de demanda.
- Acuerdos con inmobiliarias, residencias o propietarios particulares.
- Importación controlada de catálogos para evitar que la app parezca vacía.
- Priorizar zonas concretas antes de abrir expansión general.
- Mostrar disponibilidad realista al usuario para evitar expectativas falsas.

---

### Acción de emergencia por CAC

**Riesgo:** incremento del CAC efectivo por encima de 0,80 €/usuario.  
**Acciones:**

- Programa de referidos: por cada 3 amigos registrados con código, el usuario recibe 24h de Rooma Plus o un Pack de 5 Add-ons.
- Reforzar grupos universitarios, WhatsApp, Telegram y canales orgánicos.
- Convertir usuarios piloto en embajadores.
- Potenciar SEO y contenidos evergreen para reducir dependencia de Ads.
- Reasignar presupuesto de canales con peor conversión hacia canales de mayor intención.

---

### Contingencia de seguridad

**Riesgo:** brecha de datos, acceso no autorizado o exposición de información sensible.  
**Acciones:**

- Auditorías de seguridad trimestrales.
- Revisión de permisos y roles.
- Cifrado de datos sensibles.
- Monitorización de accesos anómalos.
- Plan de comunicación y respuesta ante incidente.
- Revisión de cumplimiento RGPD antes de escalar la base de usuarios.

---

### Contingencia por baja adopción del módulo financiero

**Riesgo:** los usuarios usan Rooma para hacer match, pero no gestionan facturas ni pagos dentro de la app.  
**Acciones:**

- Simplificar el flujo de facturas.
- Explicar garantías, trazabilidad y utilidad del sistema.
- Mostrar recordatorios de pagos y beneficios de centralizar gastos.
- Usar demos de facturas en marketing.
- Conectar facturas con incidencias, calendario y convivencia.

---

## Conclusión del análisis de riesgos

El proyecto Rooma presenta riesgos técnicos, comerciales y económicos relevantes, especialmente en conversión Premium, CAC efectivo, seguridad, adopción del módulo transaccional y disponibilidad de oferta.

El escenario base muestra viabilidad con un punto de equilibrio operativo en torno a **2.054 usuarios** y recuperación de inversión en el **mes 13**. Sin embargo, el escenario pesimista demuestra que una caída combinada de conversión, margen y eficiencia de adquisición puede desplazar el ROI hasta el **mes 23**.

Por tanto, la estrategia de mitigación debe centrarse en:

- reducir dependencia de Ads;
- reforzar canales orgánicos y referidos;
- asegurar suficiente oferta antes de escalar demanda;
- justificar claramente Rooma Plus y Rooma Pro;
- aumentar confianza en pagos, facturas y verificación;
- mantener control técnico y de seguridad antes de crecer.
