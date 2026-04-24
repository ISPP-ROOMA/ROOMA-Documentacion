# Análisis de riesgos

## Índice

1. [Análisis de riesgos](#análisis-de-riesgos)  
2. [Categorías de riesgos](#categorías-de-riesgos)  
3. [Metodología para análisis de riesgos](#metodología-para-análisis-de-riesgos)  
4. [Impacto](#impacto)  
5. [Metodología para priorización de riesgos](#metodología-para-priorización-de-riesgos)  
6. [Roles y responsables](#roles-y-responsables)  
7. [Matriz Probabilidad × Impacto](#matriz-probabilidad--impacto)  
8. [Identificación y Clasificación de Riesgos (Para la presentación complementaria)](#1-identificación-y-clasificación-de-riesgos-para-la-presentación-complementaria)  
9. [Escenarios económicos](#2-escenarios-económicos-optimista-vs-pesimista)  
10. [Análisis de viabilidad y puntos de equilibrio](#análisis-de-viabilidad-y-puntos-de-equilibrio)  
11. [Flujo de caja (caso optimista)](#flujo-de-caja-del-proyecto-caso-optimista)  
12. [Flujo de caja (caso pesimista)](#flujo-de-caja-del-proyecto-caso-pesimista)  
13. [Planes de contingencia](#4-planes-de-contingencia-acciones-de-mitigación)


## Categorías de riesgos

| RIESGO                  | DEFINICIÓN                                                                 |
|------------------------|----------------------------------------------------------------------------|
| Externo                | Riesgo que no depende de ninguna forma de la organización.                |
| Mercado                | Riesgo asociado al mercado de empresas.                                   |
| Legislativo            | Riesgo asociado a normas o legislaciones que apliquen sobre el desarrollo.|
| Licencias              | Riesgo asociado a licencias de productos.                                 |
| Financiero             | Riesgo asociado a la falta de capital.                                    |
| Recursos               | Riesgo asociado a la falta de recursos.                                   |
| Proveedores            | Riesgo asociado a proveedores.                                            |
| Adquisiciones          | Riesgo asociado a adquisiciones.                                          |
| Dirección del proyecto | Riesgo asociado a la dirección del proyecto.                              |
| Desempeño              | Riesgo asociado a desempeño no positivo del equipo de desarrollo.         |
| Calidad                | Riesgo asociado a la calidad del producto.                                |
| Alcance                | Riesgo asociado al alcance del proyecto.                                  |
| Requisitos             | Riesgo asociado a los requisitos del proyecto.                            |
| Tecnológico            | Riesgo asociado a tecnologías.                                            |
| Seguridad              | Riesgo asociado a baja seguridad.                                         |


## Metodología para análisis de riesgos

| PROBABILIDAD   | VALOR | DESCRIPCIÓN                          | RANGO (%)              |
|----------------|-------|--------------------------------------|------------------------|
| Muy bajo       | 1     | Casi imposible que ocurra            | 0% < P ≤ 1%            |
| Bajo           | 3     | Poco probable que ocurra             | 1% < P ≤ 10%           |
| Moderado       | 5     | Ocurre de vez en cuando              | 10% < P ≤ 50%          |
| Alto           | 7     | Ocurre con frecuencia                | 50% < P ≤ 80%          |
| Muy alto       | 9     | Casi seguro que ocurre               | 80% < P ≤ 100%*        |

## Impacto 
| DIMENSIÓN | MUY BAJO (1) | BAJO (3) | MODERADO (5) | ALTO (7) | MUY ALTO (9) |
|-----------|-------------|----------|--------------|----------|--------------|
| ALCANCE   | Afecta a menos del 5% de los paquetes de trabajo. | Afecta entre el 5% y el 10% de los paquetes de trabajo. | Afecta entre el 10% y el 20% de los paquetes de trabajo. | Afecta entre el 20% y el 30% de los paquetes de trabajo. | Afecta a más del 30% de los paquetes de trabajo. |
| TIEMPO    | No afecta a actividades de la cadena crítica. | Afecta a actividades de la cadena crítica, pero no extiende la duración del proyecto. | Extiende la duración del proyecto menos del 2%. | Extiende la duración del proyecto menos del 5%. | Extiende la duración del proyecto más del 5%. |
| COSTES    | Aumenta los costes en menos del 1%. | Aumenta los costes en menos del 3%. | Aumenta los costes en menos del 5%. | Aumenta los costes en menos del 7%. | Aumenta los costes en más del 7%. |

## METODOLOGÍA PARA PRIORIZACIÓN DE RIESGOS

La prioridad se determina calculando el Valor del Riesgo (R) mediante el producto de su probabilidad por el impacto:

R = P × I

Según su posición en la matriz, se categorizan en tres niveles:

- **Bajo**: R < 2  
- **Medio**: 2 ≤ R ≤ 4  
- **Alto**: R > 4  

## Roles y responsables

| ROL                              | RESPONSABLE       |
|----------------------------------|-------------------|
| RECOGIDA DE RIESGOS              | Jefe de proyecto  |
| ANÁLISIS Y PRIORIZACIÓN DE RIESGOS | Jefe de proyecto  |
| SEGUIMIENTO DE RIESGOS           | Jefe de proyecto  |
| APLICACIÓN PLAN DE CONTINGENCIA  | Jefe de proyecto  |

## Matriz Probabilidad × Impacto

La matriz Probabilidad × Impacto relaciona la probabilidad de que ocurra un riesgo (de alcance, tiempo o coste) con el impacto que tendría sobre el proyecto.

Cada casilla contiene un valor numérico obtenido multiplicando la probabilidad por el impacto (ambos normalizados). Ese valor sirve como puntuación de riesgo.

Se utiliza un código de colores:
- **Verde** = bajo  
- **Naranja** = medio  
- **Rojo** = alto  

para identificar rápidamente los riesgos que requieren respuesta prioritaria.

| Impacto \ Probabilidad | 1%  | 10% | 40% | 70% | 90% |
|------------------------|-----|-----|-----|-----|-----|
| Muy alto (9)           | 🟢 0,09 | 🟢 0,9 | 🟠 3,6 | 🔴 6,3 | 🔴 8,1 |
| Alto (7)               | 🟢 0,07 | 🟢 0,7 | 🟠 2,8 | 🔴 4,9 | 🔴 6,3 |
| Medio (5)              | 🟢 0,05 | 🟢 0,5 | 🟠 2   | 🟠 3,5 | 🔴 4,5 |
| Bajo (3)               | 🟢 0,03 | 🟢 0,3 | 🟢 1,2 | 🟠 2,1 | 🟠 2,7 |
| Muy bajo (1)           | 🟢 0,01 | 🟢 0,1 | 🟢 0,4 | 🟢 0,7 | 🟢 0,9 |

| ID DEL RIESGO | RIESGO | CATEGORÍA | PRIORIDAD | IMPACTO | ALCANCE | TIEMPO | COSTES | PROBABILIDAD | SEGUIMIENTO | RESPUESTA | PLAN DE CONTINGENCIA |
|--------------|--------|-----------|-----------|---------|----------|--------|--------|--------------|-------------|-----------|------------------------|
| R-001 | Requisitos ambiguos o incompletos | Requisitos | Alta | 4,2 | 7 | 5 | 3 | 60% | Jefe de proyecto | Jefe de proyecto | Workshops de requisitos, historias de usuario, definición de criterios de aceptación, acta de alcance firmada. |
| R-002 | Retraso o fallo en proveedor hosting / dominio / SSL | Proveedores | Baja | 1,75 | 3 | 7 | 3 | 25% | Jefe de proyecto | Desarrollador Analista | Contratar hosting inicial con opción de rescisión rápida; mantener cuenta alternativa y backups. |
| R-003 | Bugs críticos en funcionalidades clave | Calidad / Tecnológico | Alta | 4,05 | 5 | 9 | 5 | 45% | Analista | Desarrollador | Integrar revisiones de código, pruebas unitarias/funcionales y pruebas de aceptación por el cliente antes de despliegue. |
| R-004 | Recortes o falta de presupuesto para hosting / herramientas | Financiero | Baja | 1,4 | 3 | 3 | 7 | 20% | Jefe de proyecto | Jefe de proyecto | Priorizar MVP, usar soluciones gratuitas o de bajo coste temporalmente; preparar opciones alternativas. |
| R-005 | Pérdida / filtración de datos de usuarios | Seguridad | Baja | 1 | 3 | 5 | 20% | Desarrollador / Analista | Desarrollador / Analista | Política de privacidad/GDPR, cifrado, almacenamiento, test de penetración. |
| R-006 | Falta de habilidades específicas | Recursos | Media | 2,45 | 7 | 7 | 5 | 35% | Jefe de proyecto | Jefe de proyecto / Desarrollador Analista | Formación rápida, consultor externo puntual, tiempo adicional asignado en cronograma. |
| R-007 | API de terceros deja de funcionar o cambia condiciones | Proveedores | Media | 2 | 5 | 5 | 3 | 40% | Jefe de proyecto | Jefe de proyecto | Diseño de integración desacoplada; fallback local o caché; monitorización y alerta; cláusula de adaptación. |
| R-008 | Entregas fuera de plazo por mala estimación | Calidad | Alta | 4,55 | 7 | 7 | 5 | 65% | Jefe de proyecto | Jefe de proyecto | Revisar estimaciones, revisiones semanales, replanificación y reasignación rápida. |
| R-009 | Nuevas leyes de protección de datos (RGPD) | Legislativo | Baja | 0,6 | 3 | 3 | 1 | 20% | Jefe de proyecto | Equipo de desarrollo | Revisar cumplimiento legal al inicio, auditoría de datos, plan de corrección rápida. |
| R-010 | Demora en entrega de equipo de pruebas | Adquisiciones | Baja | 1,75 | 3 | 7 | 3 | 25% | Jefe de proyecto | Jefe de proyecto | Pedir reservas de equipo anticipado, plan B con emuladores o dispositivos de stock. |
| R-011 | Obsolescencia de librerías o frameworks | Tecnológico | Media | 2,1 | 7 | 3 | 1 | 30% | Desarrollador / Analista | Desarrollador / Analista | Monitoreo de librerías, actualizaciones programadas, plan de migración a versión nueva. |
| R-012 | Vulnerabilidad en la web | Seguridad | Media | 2,5 | 5 | 5 | 5 | 40% | Desarrollador / Analista | Desarrollador / Analista | Revisión de código y escaneo de vulnerabilidades. |
| R-013 | Riesgo de disrupción prolongada | Externo | Baja | 0,18 | 9 | 9 | 9 | 2% | Jefe de proyecto | Jefe de proyecto | Trabajo remoto. Replanificación por fases: priorizar entregables críticos. Mantener reserva para contratar recursos externos. |



## Identificación y Clasificación de Riesgos (Para la presentación complementaria)


| Categoría         | Riesgo Seleccionado              | Impacto en Rooma |
|------------------|----------------------------------|------------------|
| Mercado          | Baja conversión Premium          | El 15% estimado de usuarios con plan "Plus" cae al 5%. |
| Legal/Confianza  | Fraude y Perfiles Falsos        | Anuncios falsos dañan la reputación y obligan a gastar en verificación extra. |
| Económico        | Inflación del CAC               | El coste de adquirir un usuario sube de 0,80 € a 1,50 € por alta competencia. |
| Seguridad        | Brecha de Datos  | Acceso no autorizado a datos de pago y ubicación. Multas de GDPR y pérdida de confianza. |
| Producto         | Efecto "Ciudad Fantasma"        | Si un usuario hace swipe y no hay pisos en su zona, desinstala la app al instante. |

---

## Escenarios Económicos: Optimista vs. Pesimista

### Escenario A: Optimista (Plan Base)

Basado en el documento de presupuesto de lanzamiento:

- **Margen de Contribución Unitario**: 7,82 € por usuario  
- **Costes Fijos Mensuales**: 16.058,44 €  
- **Inversión Inicial a recuperar**: 76.865,08 €  

---

### Escenario B: Pesimista (Impacto de Riesgos)

Se aplican los riesgos de baja conversión (Plus 15% → 5%) e inflación de marketing (Ads 0,80 € → 1,20 €):

- **Nuevo Ingreso por Usuario (ARPU)**: 5,05 €  
- **Nuevos Gastos Variables**: 2,99 €  
- **Nuevo Margen Unitario**: 5,05 - 2,99 = **2,06 €** (reducción del 73%)  
- **Nuevos Costes Fijos**: 19.270,13 € (incremento del 20%)  

---

## Análisis de Viabilidad y Puntos de Equilibrio

### Mínimo de Clientes para Costes de Operación

Es el número de usuarios necesarios cada mes para que los ingresos igualen a los gastos corrientes.

- **Escenario Optimista**:  
  16.058,44 / 7,82 ≈ **2.054 usuarios**

- **Escenario Pesimista**:  
  19.270,13 / 2,06 ≈ **9.355 usuarios**

---

### Mínimo de Clientes para el ROI

Número de clientes necesarios para recuperar la inversión total de desarrollo y lanzamiento.

- **Escenario Optimista**:  
  Se alcanza en el **mes 13** con la curva prevista de **10.000 usuarios**.

- **Escenario Pesimista**:  
  El ROI se desplaza al **mes 23**, requiriendo **35.704 usuarios**.

---

## Flujo de Caja del Proyecto (Caso optimista)

| Mes | Usuarios (u) | Ingreso Mensual | Gasto Mensual | Beneficio Mes | **Caja Neta Acum.** |
| :--- | :---: | :---: | :---: | :---: | :---: |
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


## Flujo de Caja del Proyecto (Caso pesimista)

| Mes | Usuarios (u) | Ingreso Mensual | Gasto Mensual | Beneficio Mes | Caja Neta Acum. |
|-----|--------------|------------------|---------------|---------------|-----------------|
| Pre | 0            | 0,00 €           | 76.865,08 €   | -             | -76.865,08 €    |
| 1   | 100          | 505,00 €         | 19.569,13 €   | -19.064,13 €  | -95.929,21 €    |
| 2   | 152          | 767,60 €         | 19.724,61 €   | -18.957,01 €  | -114.886,22 €   |
| 3   | 231          | 1.166,55 €       | 19.960,82 €   | -18.794,27 €  | -133.680,49 €   |
| 4   | 352          | 1.777,60 €       | 20.322,61 €   | -18.545,01 €  | -152.225,50 €   |
| 5   | 535          | 2.701,75 €       | 20.869,78 €   | -18.168,03 €  | -170.393,53 €   |
| 6   | 813          | 4.105,65 €       | 21.701,00 €   | -17.595,35 €  | -187.988,88 €   |
| 7   | 1.235        | 6.236,75 €       | 22.962,78 €   | -16.726,03 €  | -204.714,91 €   |
| 8   | 1.878        | 9.483,90 €       | 24.885,35 €   | -15.401,45 €  | -220.116,36 €   |
| 9   | 2.854        | 14.412,70 €      | 27.803,59 €   | -13.390,89 €  | -233.507,25 €   |
| 10  | 4.338        | 21.906,90 €      | 32.240,75 €   | -10.333,85 €  | -243.841,10 €   |
| 11  | 6.597        | 33.314,85 €      | 38.995,16 €   | -5.680,31 €   | -249.521,41 €   |
| 12  | 10.000       | 50.500,00 €      | 49.170,13 €   | +1.329,87 €   | -248.191,54 €   |
| 13  | 11.227       | 56.696,35 €      | 52.838,86 €   | +3.857,49 €   | -244.334,05 €   |
| 14  | 12.604       | 63.650,20 €      | 56.956,09 €   | +6.694,11 €   | -237.639,94 €   |
| 15  | 14.150       | 71.457,50 €      | 61.578,63 €   | +9.878,87 €   | -227.761,07 €   |
| 16  | 15.885       | 80.219,25 €      | 66.766,28 €   | +13.452,97 €  | -214.308,10 €   |
| 17  | 17.833       | 90.056,65 €      | 72.590,80 €   | +17.465,85 €  | -196.842,25 €   |
| 18  | 20.021       | 101.106,05 €     | 79.132,92 €   | +21.973,13 €  | -174.869,12 €   |
| 19  | 22.477       | 113.508,85 €     | 86.476,36 €   | +27.032,49 €  | -147.836,63 €   |
| 20  | 25.233       | 127.426,65 €     | 94.716,80 €   | +32.709,85 €  | -115.126,78 €   |
| 21  | 28.329       | 143.061,45 €     | 103.973,84 €  | +39.087,61 €  | -76.039,17 €    |
| 22  | 31.803       | 160.605,15 €     | 114.361,10 €  | +46.244,05 €  | -29.795,12 €    |
| 23  | 35.704       | 180.305,20 €     | 126.025,09 €  | +54.280,11 €  | +24.484,99 €    |
| 24  | 40.083       | 202.419,15 €     | 139.118,30 €  | +63.300,85 €  | +87.785,84 €    |
| 25  | 45.000       | 227.250,00 €     | 153.820,13 €  | +73.429,87 €  | +161.215,71 €   |
| 26  | 50.520       | 255.126,00 €     | 170.324,93 €  | +84.801,07 €  | +246.016,78 €   |
| 27  | 56.716       | 286.415,80 €     | 188.850,97 €  | +97.564,83 €  | +343.581,61 €   |
| 28  | 63.673       | 321.548,65 €     | 209.652,40 €  | +111.896,25 € | +455.477,86 €   |

## Planes de Contingencia (Acciones de Mitigación)

- **Contingencia Legal/Confianza**:  
  Implementación de verificación por DNI obligatoria para anunciantes Pro.

- **Mitigación de Conversión**:  
  Si la conversión es baja, se reducen los beneficios del nivel Free. Por ejemplo, pasar de 20 swipes diarios a solo 5, incentivando la compra de Add-ons para desbloquear funciones puntuales.

- **Plan ante Escasez de Oferta**:  
  Acuerdos con inmobiliarias (modelo B2B) para importar catálogos automáticamente y evitar la “app vacía”.

- **Acción de Emergencia por CAC**:  
  "Pagar" a nuestros propios usuarios con funcionalidad. Por cada 3 amigos que se registren con su código, el usuario recibe 24h de Rooma Plus o un Pack de 5 Add-ons gratis. Esto convierte el gasto de marketing en un coste marginal de infraestructura casi nulo.

- **Contingencia de Seguridad (Brecha de Datos)**:  
  Auditorias de seguridad trimestrales.