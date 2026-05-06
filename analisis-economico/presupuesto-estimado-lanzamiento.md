# Presupuesto Estimado

## Lanzamiento 21/05/2026 - 21/05/2027

### Suposiciones de mercado y crecimiento

Para asegurar la coherencia del modelo financiero durante el primer año de operación comercial, se establecen las siguientes premisas basadas en el comportamiento esperado de la comunidad Rooma:

#### 1. Previsión del número de usuarios

Se proyecta una curva de crecimiento exponencial moderada que permite validar la infraestructura y el coste de adquisición de forma controlada, alcanzando la cifra de 10.000 usuarios un año después del lanzamiento.

| Mes | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Usuarios ($u$) | 40 | 100 | 152 | 231 | 352 | 535 | 813 | 1.235 | 1.878 | 2.854 | 4.338 | 6.597 | 10.000 |

#### 2. Previsión de transacciones y tasa de conversión

El modelo transaccional se basa en usuarios que formalizan su contrato a través de la App.

* **Tasa de conversión transaccional:** Se estima que el **25%** de la base total de usuarios registrados ($u$) tendrán un contrato de alquiler en activo y utilizarán la plataforma para gestionar pagos de rentas y servicios.
* **Ticket medio:** Se proyecta un volumen de **800,00 € mensuales** por contrato activo (alquiler + suministros).
* **Volumen de operaciones:** Cada contrato activo genera una media de **5 transacciones mensuales** (pago de inquilino, depósitos, dispersión a propietarios y proveedores).

#### 3. Previsión de suscripciones y Add-ons

La monetización directa se divide en ingresos recurrentes y compras de funcionalidades extra, enfocándose en la conversión de la base de usuarios gratuita hacia servicios de valor añadido.

* **Suscripciones mensuales:**
    * **Rooma Plus:** Se estima una conversión del **25%** de la base total de usuarios registrados.
    * **Rooma Pro:** Se estima una conversión del **3,75%** de la base total de usuarios registrados.

* **Uso de Add-ons (microtransacciones):**
    * Se proyecta que el uso de funcionalidades puntuales (*Rewind, Boost* o *Chat de difusión*) se distribuya de la siguiente forma:
        * **Pack Individual (1 unidad):** Adquirido mensualmente por el **15%** de los usuarios.
        * **Pack de Ahorro (5 unidades):** Adquirido mensualmente por el **5%** de los usuarios.
    * Esta vía permite monetizar a perfiles que operan bajo el modelo gratuito, maximizando el rendimiento de la plataforma sin elevar los costes fijos de estructura.

### Supuestos críticos del modelo económico

Para mejorar la trazabilidad del análisis, se identifican las hipótesis principales que sostienen el escenario base. Estas hipótesis permiten conectar el presupuesto de lanzamiento con el plan de marketing, el análisis de riesgos y el feedback de usuarios piloto.

| Hipótesis | Valor base | Justificación | Riesgo asociado |
|---|---:|---|---|
| Usuarios objetivo año 1 | 10.000 | Curva de crecimiento moderada durante 12 meses | Menor adopción inicial |
| Conversión Rooma Plus | 25% | Usuarios con alta intención de búsqueda y uso recurrente | Baja conversión Premium |
| Conversión Rooma Pro | 3,75% | Caseros, agencias o usuarios intensivos | Sensibilidad al precio |
| Usuarios con contrato activo | 25% | Usuarios que formalizan alquiler y gestionan pagos en Rooma | Baja adopción del módulo financiero |
| Ticket mensual por contrato | 800 € | Alquiler + suministros + posibles gastos asociados | Variación del alquiler medio |
| Operaciones por contrato | 5/mes | Pago de renta, suministros, depósitos o dispersión de fondos | Menor uso operativo |
| CAC medio combinado | 0,80 €/usuario | Ads + orgánico + referidos + captación directa | Inflación del CAC |
| Coste Stripe por contrato | 17,75 €/mes | Connect + comisión por volumen + coste por operación | Mayor coste transaccional |
| Margen unitario base | 7,82 €/usuario | ARPU 13,07 € - costes variables 5,25 € | Caída de conversión o subida de costes |

Estas hipótesis no deben interpretarse como certezas, sino como valores de referencia para construir el escenario base. El escenario pesimista del análisis de riesgos evalúa el impacto de desviaciones en conversión, CAC y margen unitario.

---

### OPEX (Coste total: 16.058,44 € + 5,25 $u$ / mes)

Este bloque detalla los costes operativos recurrentes durante la fase de lanzamiento y operación de la plataforma.

#### Infraestructura (Coste total: 53,32 €/mes + 0,01 · u/mes)

En la fase de explotación comercial, la infraestructura de **Digital Ocean** escala dinámicamente para absorber el tráfico real. El coste se calcula mediante una función lineal que garantiza la sostenibilidad técnica del servicio:

**Fórmula de escalabilidad:**

> $Coste_{Infra} = 53,32€ + (0,01€ \cdot u)$

| Usuarios activos ($u$) | Cálculo (fijo + 0,01 €/u) | Coste mensual |
|---|---|---:|
| 1.000 | 53,32 € + 10,00 € | **63,32 €/mes** |
| 10.000 | 53,32 € + 100,00 € | **153,32 €/mes** |
| 25.000 | 53,32 € + 250,00 € | **303,32 €/mes** |

*El coste fijo de 53,32 € garantiza que la aplicación esté siempre disponible, segura y con copias de seguridad automáticas. El coste variable de 0,01 € por usuario cubre el gasto de Internet por el uso de la app, el espacio en la nube para guardar las fotos de los perfiles y pisos, y la potencia de cálculo necesaria para realizar los emparejamientos en tiempo real.*

#### Herramientas de desarrollo (Coste total: 541,92 €/mes)

Este apartado contempla las suscripciones mensuales del stack de productividad del equipo (repositorios, IA asistida y ofimática), imprescindibles para coordinar trabajo, documentar avances y acelerar entregas.

| Herramienta | Número de licencias | Coste unitario | Coste total |
|---|---:|---:|---:|
| Github Team | 16 | 3,67 €/mes | 58,72 €/mes |
| Gemini Pro | 16 | 18,50 €/mes | 296,00 €/mes |
| Microsoft 365 Business | 16 | 11,70 €/mes | 187,20 €/mes |

#### Luz (Coste total: 75,80 €/mes)

Proyección del consumo eléctrico para una jornada laboral completa (160 horas mensuales por desarrollador en turno de 8h), manteniendo una estimación prudente del consumo medio por puesto de trabajo.

| Horas mensuales equipo | Energía consumida | Precio medio efectivo | Coste total |
|---|---|---:|---:|
| 2.560 (16 × 160) | 512 kWh (2.560 × 0,2) | 0,148 €/kWh | 75,80 €/mes |

> **Comprobación:** 512 kWh × 0,148 €/kWh = 75,78 €, redondeado a **75,80 €/mes**. Se utiliza un precio medio efectivo para mantener la consistencia del presupuesto operativo.

#### Laboral (mantenimiento) (Coste total: 10.777,54 €/mes)

Del equipo estructural de 16 ingenieros, durante la fase de lanzamiento se dedica 37,8 horas mensuales por persona a mantenimiento, bugs críticos, operaciones y soporte de infraestructura en producción.

| Rol | Unidades | Horas | Salario líquido | Salario bruto | Coste de empresa | Total |
|---|---:|---:|---:|---:|---:|---:|
| Ingeniero Junior | 16 | 37,8 h/mes | 10,60 €/h | 13,50 €/h | 17,82 €/h | 10.777,54 €/mes |

#### Marketing (Coste total: 3.150,00 € + 0,80 € · u / mes)

El presupuesto de marketing se divide en dos áreas operativas: los costes fijos de estructura (personal y creación de contenidos) y la inversión variable en adquisición de usuarios (Ads).

##### Estructura y producción (Coste total: 3.150,00 €/mes)

Representa el gasto operativo fijo necesario para mantener la presencia de marca, generar el material audiovisual y gestionar la comunidad de usuarios.

| Partida de gasto | Descripción del servicio | Coste mensual |
| :--- | :--- | ---: |
| **Contratación de Community Manager** | Gestión de redes sociales, atención al usuario, publicación de contenidos, seguimiento de feedback y dinamización de comunidad. | 1.000,00 € |
| **Producción de anuncios** | Grabación y edición de vídeos: spots publicitarios, Reels, TikToks, demos y piezas de lanzamiento. | 2.000,00 € |
| **Recursos creativos** | Suscripciones de diseño, música comercial, plantillas, bancos de recursos y material gráfico. | 150,00 € |

##### Inversión publicitaria (Coste total: 0,80 € · u / mes)

Presupuesto neto destinado a la compra de alcance y conversión. La inversión escala linealmente según el objetivo de usuarios activos ($u$), asumiendo un coste de adquisición competitivo en el sector de apps de servicios.

**Fórmula de escalabilidad:**

> $Inversión_{Ads} = 0,80€ \cdot u$

> **Nota de coherencia con el plan de marketing:** el valor de **0,80 €/usuario** se interpreta como un coste medio combinado de adquisición, no como un CPI puramente publicitario. Este coste medio incluye la inversión en Ads, pero también el efecto de canales orgánicos, referidos, difusión en grupos universitarios, reactivación de usuarios piloto y captación directa de propietarios o agencias. Por ello, los segmentos con CPI pagado superior se compensan con canales de bajo coste o sin coste publicitario directo.

| Escenario de usuarios ($u$) | Inversión TikTok Ads (50%) | Inversión Meta Ads (50%) | Inversión total Ads |
| :--- | ---: | ---: | ---: |
| **1.000 usuarios** | 400,00 € | 400,00 € | **800,00 €** |
| **10.000 usuarios** | 4.000,00 € | 4.000,00 € | **8.000,00 €** |
| **25.000 usuarios** | 10.000,00 € | 10.000,00 € | **20.000,00 €** |

#### Operaciones y transacciones (Coste total: 4,44 € · $u$ / mes)

Este apartado detalla los costes de gestión de cobros (Pay-ins) y transferencias (Payouts) a través de **Stripe Connect**. Se asume un modelo transaccional donde Rooma actúa como intermediario seguro para el pago de rentas y servicios.

#### Fórmulas de cálculo operativo:

> $Coste_{Fijo\_Connect} = 2,00€ \cdot u_{piso}$

> $Coste_{Comisiones} = (1,75\% \cdot Vol) + (0,35€ \cdot n)$

* **$u_{piso}$ (25% de $u$):** Número de perfiles con un alquiler o servicio activo en la plataforma. Se estima que 1 de cada 4 usuarios registrados llega a formalizar y gestionar su contrato a través de la App.
* **$Vol$ ($u_{piso} \times 800€$):** Volumen total de capital procesado (alquiler + suministros + reparaciones).
* **$n$ ($u_{piso} \times 5$):** Cantidad de transacciones ejecutadas (pagos de inquilino + payouts a propietarios/proveedores).

#### Desglose del coste por usuario con contrato ($u_{piso}$)

Para el cálculo, se supone una media de **5 transacciones** y **800,00 €** transferidos mensualmente por cada usuario con contrato activo:

* **Gestión de cuenta (Connect):** 2,00 € fijo/mes.
* **Comisión por volumen (1,75% de 800 €):** 14,00 € variable/mes.
* **Comisión por transacciones (0,35 € × 5):** 1,75 € fijo/mes.
* **Total por usuario con contrato:** **17,75 €/mes.**
* **Total ponderado por usuario registrado:** **4,4375 €/mes**, redondeado a **4,44 €/mes** en el resumen operativo.

| Escenario de usuarios ($u$) | Usuarios con contrato ($u_{piso}$) | Volumen mensual ($Vol$) | Nº operaciones ($n$) | Coste total Stripe |
| :--- | ---: | ---: | ---: | ---: |
| **1.000 usuarios** | 250 | 200.000 € | 1.250 | **4.437,50 €/mes** |
| **10.000 usuarios** | 2.500 | 2.000.000 € | 12.500 | **44.375,00 €/mes** |
| **25.000 usuarios** | 6.250 | **5.000.000 €** | **31.250** | **110.937,50 €/mes** |

#### Suposiciones y lógica de negocio

1. **Ratio de contratación y volumen de pagos:** como definimos anteriormente, se supone un 25% de usuarios con contrato, gastando 800 € mensuales divididos en 5 transacciones.
2. **Activación de Connect:** el coste de 2,00 € por cuenta se aplica únicamente si el usuario recibe fondos ese mes. Al asumir que todos los contratos en vigor liquidan pagos mensualmente, este coste se vuelve estructural para el 25% de la base.
3. **Cumplimiento normativo:** el coste fijo de Stripe Connect cubre la validación de identidad, prevención de blanqueo de capitales y el soporte técnico de la pasarela, delegando la responsabilidad legal bancaria en el proveedor.
4. **Estimación de comisiones:** el cálculo de las comisiones variables se basa en un ticket medio transaccionado proporcional a la densidad de usuarios, garantizando que la infraestructura soporte el flujo de caja proyectado.

#### Resumen de gastos operativos (OPEX - Fase Lanzamiento)

| Categoría | Partida | Importe (f($u$)) | Subtotal |
| :--- | :--- | :---: | ---: |
| **Infraestructura Cloud** | Digital Ocean | **53,32 € + 0,01 $u$** | |
| **Herramientas de equipo** | Github Team (16 licencias) | 58,72 € | |
| | Gemini Pro (16 licencias) | 296,00 € | |
| | Microsoft 365 Business (16 licencias) | 187,20 € | **541,92 €** |
| **Suministros** | Consumo eléctrico (jornada completa) | 75,80 € | **75,80 €** |
| **Laboral (mantenimiento)** | Ingeniería (16 pers. × 37,8 h/mes) | 10.777,54 € | **10.777,54 €** |
| **Marketing y adquisición** | Estructura CM y producción audiovisual | 3.150,00 € | |
| | Inversión publicitaria Ads | 0,80 $u$ | **3.150,00 € + 0,80 $u$** |
| **Operaciones financieras** | Gestión Stripe y transacciones | 4,44 $u$ | **4,44 $u$** |
| **Seguridad y previsión** | **Contingencia (10% sobre costes fijos)** | 1.459,86 € | **1.459,86 €** |
| **TOTAL OPEX MENSUAL** |  | | **16.058,44 € + 5,25 $u$** |

---

### Ingresos

#### Vía de ingresos 1: Modelo de suscripción

Se establece un modelo escalonado para asegurar la adquisición masiva de usuarios en la base, monetizando a través de la aportación de valor añadido.

- **Nivel Free (0 €):** Actúa como embudo de adquisición. Sus funciones están restringidas a 20 swipes diarios, chat básico y visualización de mapas.
- **Rooma Plus (5,99 €/mes):** Orientado a usuarios con alta intención de interacción. Ofrece swipes ilimitados, visualización de likes, filtros avanzados y experiencia sin anuncios.
- **Rooma Pro (15,99 €/mes):** Orientado a caseros, agencias o heavy users. Incluye posicionamiento destacado, analíticas de visitas, insignia de verificación y soporte prioritario.

> **Nota sobre sensibilidad al precio:** la disposición a pagar detectada durante el piloto se interpreta como una señal inicial de sensibilidad al precio, no como sustitución directa del escenario económico base. Rooma Plus, con precio de 5,99 €/mes, queda alineado con el perfil inquilino. Rooma Pro, con precio de 15,99 €/mes, se mantiene como hipótesis para propietarios intensivos, agencias o usuarios profesionales que obtienen mayor valor por posicionamiento destacado, analíticas, verificación y soporte prioritario. Durante el lanzamiento se podrán aplicar promociones, cuentas fundador o descuentos temporales para validar la elasticidad de precio sin alterar el modelo financiero base.

#### Vía de ingresos 2: Funcionalidades extra (Add-ons)

Para complementar las suscripciones recurrentes, se habilita una vía de monetización por "impulso" dirigida a usuarios que requieren funciones específicas de forma puntual.

* **Add-ons disponibles:** 
    * **Rewind:** Deshacer el último like o dislike.
    * **Boost:** Posicionamiento prioritario en el feed por 24 h.
    * **Chat de difusión:** Apertura de tablón de anuncios grupal para coordinar visitas.

**Estructura de precios:**

| Producto | Unidades | Precio PVP | Precio por unidad |
| :--- | :---: | ---: | ---: |
| **Pack Individual** | 1 ud. | **0,99 €** | 0,99 € |
| **Pack de Ahorro** | 5 uds. | **3,99 €** | 0,80 € |

> **Cálculo del ingreso ponderado (Add-ons):**
>
> Basado en las suposiciones de conversión (15% adquiere Pack Individual y 5% adquiere Pack de Ahorro):
>
> $(0,15 \times 0,99 €) + (0,05 \times 3,99 €) = \mathbf{0,35 € \text{ adicionales por usuario } (u)}$

#### Vía de ingresos 3: Modelo transaccional y comisiones

Para garantizar que la pasarela de pagos no sea deficitaria tras los costes de Stripe, se establece una tarifa de **"Gestión y Garantía"** mixta.

* **Tarifa Rooma:** **5% sobre el volumen ($Vol$) + 0,50 € fijos por transacción ($n$).**
* **Margen transaccional tras coste PSP:** Tras descontar el coste de Stripe (1,75% + 0,35 €), Rooma retiene un margen estimado del **3,25% + 0,15 €** por cada operación.

> **Ejemplo de unidad de negocio:** En un alquiler de 800 € con 5 transacciones mensuales:
>
> * **Ingreso bruto Rooma (5% + 0,50 € × 5):** 42,50 €
> * **Coste Stripe (tarifa técnica):** 17,75 €
> * **Margen transaccional estimado:** **24,75 €/mes por contrato activo.**

#### Resumen de monetización por usuario ($u$)

La siguiente tabla consolida el potencial de generación de ingresos brutos mensuales por cada usuario registrado, desglosando cada vía según su tasa de conversión y su aportación al ingreso medio:

| Vía de ingreso | Base de cálculo (conversión) | Ingreso por unidad | Ingreso ponderado ($u$) |
| :--- | :---: | ---: | ---: |
| **Suscripción Rooma Plus** | 25% | 5,99 € | 1,50 € |
| **Suscripción Rooma Pro** | 3,75% | 15,99 € | 0,60 € |
| **Add-on: Pack Individual** | 15% | 0,99 € | 0,15 € |
| **Add-on: Pack de Ahorro** | 5% | 3,99 € | 0,20 € |
| **Comisiones transaccionales** | 25% | 42,50 € | 10,62 € |
| **TOTAL INGRESO BRUTO ($ARPU$)** | | | **13,07 €** |

#### Desglose de ingresos por tipo de usuario

Para comprender la contribución real de cada segmento de usuarios al ingreso total, se distingue entre usuarios gratuitos, usuarios de pago y usuarios con contrato activo:

| Tipo de usuario | % de la base | Usuarios (a 10.000) | Ingreso unitario/mes | Ingreso total/mes | % del ingreso |
| :--- | :---: | ---: | ---: | ---: | ---: |
| **Free** (solo add-ons) | 71,25% | 7.125 | 0,35 € | 2.493,75 € | ~1,9% |
| **Rooma Plus** | 25,00% | 2.500 | 5,99 € + 0,35 € = 6,34 € | 15.850,00 € | ~12,1% |
| **Rooma Pro** | 3,75% | 375 | 15,99 € + 0,35 € = 16,34 € | 6.127,50 € | ~4,7% |
| **Con contrato activo** (comisiones) | 25,00% (transversal) | 2.500 | 42,50 € | 106.250,00 € | ~81,3% |
| **TOTAL** | — | 10.000 | **13,07 €** (ARPU) | **~130.700 €** | **100%** |

> **Nota:** Un usuario Plus o Pro también puede tener contrato activo. Las categorías de suscripción y de contrato transaccional no son mutuamente excluyentes.

**Insights clave:**

- El **81,3% del ingreso** proviene de comisiones transaccionales → el módulo de pagos es crítico para la viabilidad del negocio.
- Los usuarios **Free** contribuyen solo un **1,9%** del ingreso directo, pero son esenciales como embudo de adquisición y masa crítica de la plataforma.
- La conversión a **Premium** (25% Plus + 3,75% Pro = **28,75%**) es la palanca de crecimiento más directa en ingresos recurrentes.
- Los usuarios de pago (Plus + Pro) representan solo el **28,75%** de la base pero generan el **16,8%** del ingreso por suscripciones + add-ons.

*Nota: el ingreso ponderado por usuario ($u$) es el resultado de multiplicar el ingreso por unidad por su respectiva base de cálculo. Este valor representa la facturación bruta media que genera cada usuario registrado en la plataforma.*

#### ROI y margen por tipo de usuario

Para responder con mayor precisión al retorno económico del modelo, se distingue entre usuarios normales, usuarios de pago y usuarios con contrato activo. Esta separación es necesaria porque no todos los perfiles activan las mismas fuentes de ingresos ni soportan los mismos costes variables.

| Tipo de usuario | Ingreso mensual estimado | Coste variable asociado | Margen unitario aproximado |
|---|---:|---:|---:|
| Free sin contrato activo | 0,35 € | 0,81 € | -0,46 € |
| Rooma Plus sin contrato activo | 6,34 € | 0,81 € | 5,53 € |
| Rooma Pro sin contrato activo | 16,34 € | 0,81 € | 15,53 € |
| Usuario con contrato activo | 42,50 € | 18,56 € | 23,94 € |

**Criterio de cálculo:**

Para usuarios sin contrato activo se consideran únicamente los costes variables básicos:

- Ads: 0,80 €/usuario.
- Infraestructura cloud: 0,01 €/usuario.
- Total: 0,81 €/usuario.

Para usuarios con contrato activo se añade el coste operativo de Stripe:

- Coste Stripe por contrato activo: 17,75 €/mes.
- Coste básico Ads + Cloud: 0,81 €/mes.
- Coste variable total: 18,56 €/mes.

**Interpretación:**

El usuario Free no es rentable de forma aislada, pero cumple una función necesaria como masa crítica, liquidez del marketplace y embudo de conversión. El usuario Plus ya presenta margen positivo sin necesidad de contrato activo. El usuario Pro aporta mayor margen recurrente dentro de las suscripciones. El usuario con contrato activo es el perfil económico más relevante porque activa la vía transaccional, que representa la mayor parte del ingreso mensual.

Por tanto, el ROI de Rooma no depende solo de captar usuarios, sino de convertir usuarios normales en usuarios de pago o en usuarios con contrato activo.

---

### Rentabilidad y viabilidad económica

#### Análisis de costes variables y margen de contribución

Para obtener el margen de contribución unitario, restamos todos los costes operativos variables asociados a cada usuario:

* **Coste de adquisición (Ads):** 0,80 €/u
* **Coste de infraestructura (Cloud):** 0,01 €/u
* **Coste operativo de Stripe:** 4,44 €/u
* **Total costes variables:** **5,25 €/usuario**

> **Margen de contribución unitario:** 13,07 € (ingreso ponderado) - 5,25 € (coste variable ponderado) = **7,82 € de margen de contribución por usuario.**

#### Comprobaciones de consistencia del modelo

Para validar la coherencia interna del presupuesto, se incluyen las principales comprobaciones aritméticas del escenario base:

| Elemento revisado | Cálculo | Resultado |
|---|---:|---:|
| ARPU | 1,50 + 0,60 + 0,15 + 0,20 + 10,62 | 13,07 €/usuario |
| Costes variables | 0,80 Ads + 0,01 Cloud + 4,44 Stripe | 5,25 €/usuario |
| Margen unitario | 13,07 - 5,25 | 7,82 €/usuario |
| Break-even operativo | 16.058,44 / 7,82 | ≈ 2.054 usuarios |
| Stripe ponderado | 17,75 × 25% | 4,4375 €/usuario |
| Ads a 10.000 usuarios | 0,80 × 10.000 | 8.000 €/mes |
| Infraestructura a 10.000 usuarios | 53,32 + 0,01 × 10.000 | 153,32 €/mes |

Estas comprobaciones permiten detectar desviaciones entre las hipótesis de ingresos, costes variables y punto de equilibrio.

#### Hitos de rentabilidad: comparativa de escenarios

Para una visión estratégica, comparamos los hitos de viabilidad entre el escenario base y el escenario de riesgo (pesimista):

| Hito financiero | Métrica | Escenario realista (base) | Escenario pesimista (riesgo) |
| :--- | :---: | :---: | :---: |
| **Punto de equilibrio** | Usuarios necesarios | **2.054 $u$** | **9.355 $u$** |
| **Mes de break-even** | Cuándo ocurre | **Mes 9** | **Mes 12** |
| **Retorno de inversión** | Usuarios necesarios | **10.000 $u$** | **35.704 $u$** |
| **Mes de payback** | Cuándo ocurre | **Mes 13** | **Mes 23** |

> **Interpretación:** En el escenario realista, la plataforma es autosuficiente antes del primer año. En el escenario pesimista, la necesidad de masa crítica se triplica, desplazando el retorno total casi un año adicional (Mes 23). Estas estimaciones se explican en el documento [análisis-riesgos](/analisis-riesgos/analisis-riesgos.md).

#### Punto de retorno de la inversión total (Payback)

Este hito financiero determina el momento en el que el resultado operativo acumulado iguala la suma de toda la inversión inicial y el déficit generado durante la fase de crecimiento.

**Inversión inicial consolidada ($I_{prev}$):**

Incluye el CAPEX (74.159,80 €) y el OPEX de la fase de desarrollo (2.705,28 €).

* **Total inversión pre-lanzamiento:** **76.865,08 €**

**Cálculo del retorno total ($RT$):**

El punto de retorno se alcanza cuando el sumatorio del resultado mensual ($R_m$) compensa la inversión inicial y el gasto operativo acumulado de lanzamiento.

$$RT = I_{prev} + \sum_{m=1}^{n} (Gastos\_totales_m - Ingresos\_brutos_m) = 0$$

* **$I_{prev}$:** 76.865,08 € (inversión fija inicial).
* **Déficit de lanzamiento:** suma del resultado negativo de los meses 1 al 8.

| Mes | Usuarios ($u$) | Ingreso mensual | Gasto mensual | Resultado mes | **Caja neta acum.** |
| :--- | ---: | ---: | ---: | ---: | ---: |
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

> **Conclusión del retorno:** Como se observa en la columna de **Caja Neta Acumulada**, el punto de recuperación total de la inversión se alcanza durante el **Mes 13**. Tras absorber el déficit acumulado, la plataforma finaliza el mes 13 con un saldo positivo de **+20.019,90 €**. A partir de este hito, Rooma deja de recuperar capital invertido y comienza a generar caja operativa positiva para la sociedad.

#### Proyección de escenario realista (10.000 usuarios)

Una vez superado el umbral de rentabilidad en el mes 9, la eficiencia del margen unitario permite una consolidación financiera acelerada hacia el cierre del primer año:

* **Ingresos brutos mensuales:** 130.700,00 €
* **Gastos operativos totales (fijos + variables):** 68.558,44 €
* **Resultado operativo mensual estimado:** **+62.141,56 €**

*Nota: Con este nivel de resultado operativo al finalizar el año, el modelo presenta capacidad de recuperación acelerada de la inversión inicial siempre que se cumplan las hipótesis de usuarios, conversión y adopción del módulo transaccional. Esta conclusión debe interpretarse junto con el escenario pesimista del análisis de riesgos, donde una caída de conversión o una subida del CAC retrasan significativamente el retorno.*
