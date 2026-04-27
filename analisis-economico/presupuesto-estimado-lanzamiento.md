# Presupuesto Estimado
## Lanzamiento 21/05/2026 - 21/05/2027
### Suposiciones de mercado y crecimiento

Para asegurar la coherencia del modelo financiero durante el primer año de operación comercial, se establecen las siguientes premisas basadas en el comportamiento esperado de la comunidad Rooma:

#### 1. Previsión del número de usuarios 
Se proyecta una curva de crecimiento exponencial moderada que permite validar la infraestructura y el coste de adquisición de forma controlada, alcanzando la cifra de 10000 usuarios un año después del lanzamiento.

| Mes | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Usuarios ($u$) | 40 | 100 | 152 | 231 | 352 | 535 | 813 | 1.235 | 1.878 | 2.854 | 4.338 | 6.597 | 10.000 |

#### 2. Previsión de transacciones y tasa de conversión
El modelo transaccional se basa en usuarios que formalizan su contrato a través de la App.

* **Tasa de conversión transaccional:** Se estima que el **25%** de la base total de usuarios registrados ($u$) tendrán un contrato de alquiler en activo y utilizarán la plataforma para gestionar pagos de rentas y servicios.
* **Ticket medio:** Se proyecta un volumen de **800,00 € mensuales** por contrato activo (Alquiler + Suministros).
* **Volumen de Operaciones:** Cada contrato activo genera una media de **5 transacciones mensuales** (pago de inquilino, depósitos, dispersión a propietarios y proveedores).

#### 3. Previsión de suscripciones y Add-ons
La monetización directa se divide en ingresos recurrentes y compras de funcionalidades extra, enfocándose en la conversión de la base de usuarios gratuita hacia servicios de valor añadido.

* **Suscripciones Mensuales:**
    * **Rooma Plus:** Se estima una conversión del **25%** de la base total de usuarios registrados.
    * **Rooma Pro:** Se estima una conversión del **3,75%** de la base total de usuarios registrados.


* **Uso de Add-ons (Microtransacciones):**
    * Se proyecta que el uso de funcionalidades puntuales (*Rewind, Boost* o *Chat de difusión*) se distribuya de la siguiente forma:
        * **Pack Individual (1 unidad):** Adquirido mensualmente por el **15%** de los usuarios.
        * **Pack de Ahorro (5 unidades):** Adquirido mensualmente por el **5%** de los usuarios.
    * Esta vía permite monetizar a perfiles que operan bajo el modelo gratuito, maximizando el rendimiento de la plataforma sin elevar los costes fijos de estructura.

### OPEX (Coste total: 16.058,44 € + 5,25 $u$ / mes)
Este bloque detalla los costes operativos recurrentes durante la fase de lanzamiento y operación de la plataforma.

#### Infraestructura (Coste total: 53,32€/mes + 0,01 · u/mes)
En la fase de explotación comercial, la infraestructura de **Digital Ocean** escala dinámicamente para absorber el tráfico real. El coste se calcula mediante una función lineal que garantiza la sostenibilidad técnica del servicio:

**Fórmula de Escalabilidad:** 
>$Coste_{Infra} = 53,32€ + (0,01€ \cdot u)$

| Usuarios Activos ($u$) | Cálculo (Fijo + 0,01€/u) | Coste Mensual |
|---|---|---|
| 1.000 | 53,32€ + 10,00€ | **63,32€/mes** |
| 10.000 | 53,32€ + 100,00€ | **153,32€/mes** |
| 25.000 | 53,32€ + 250,00€ | **303,32€/mes** |

*El coste fijo de 53,32€ garantiza que la aplicación esté siempre disponible, segura y con copias de seguridad automáticas. El coste variable de 0,01€ por usuario cubre el gasto de Internet por el uso de la app, el espacio en la nube para guardar las fotos de los perfiles y pisos, y la potencia de cálculo necesaria para realizar los emparejamientos en tiempo real.*

#### Herramientas de desarrollo (Coste total: 541,92€/mes)
Este apartado contempla las suscripciones mensuales del stack de productividad del equipo (repositorios, IA asistida y ofimática), imprescindibles para coordinar trabajo, documentar avances y acelerar entregas.

| Herramienta | Número de licencias | Coste unitario | Coste Total |
|---|---|---|---|
| Github Team | 16 | 3,67€/mes | 58,72€/mes |
| Gemini Pro | 16 | 18,50/mes | 296€/mes |
| Microsoft 365 Business | 16 | 11,70/mes | 187,2€/mes |

#### Luz (Coste total: 75,8€/mes)

Proyección del consumo eléctrico para una jornada laboral completa (160 horas mensuales por desarrollador en turno de 8h), manteniendo estimaciones en conservadoras respecto al hardware utilizado.

| Horas mensuales equipo | Energía consumida | Precio Energía | Coste Total |
|---|---|---|---|
| 2560 (16x160) | 512 (2560x0,2) | 0,15/kWh€ | 75,8€/mes |

#### Laboral (mantenimiento) (Coste total: 10.777,536€/mes)

Del equipo estructural de 16 ingenieros, durante la fase de lanzamiento se dedica 37,8 horas mensuales por persona a mantenimiento, bugs críticos, operaciones y soporte de infraestructura en producción.

| Rol | Unidades | Horas | Salario Líquido | Salario Bruto | Coste de Empresa | Total |
|---|---|---|---|---|---|---|
| Ingeniero Junior | 16 | 37,8h/mes | 10,60€/h | 13,50€/h | 17,82€/h | 10.777,536€/mes |


#### Marketing (Coste total: 31500 +  0,80€ · u / mes)

El presupuesto de marketing se divide en dos áreas operativas: los costes fijos de estructura (personal y creación de contenidos) y la inversión variable en adquisición de usuarios (Ads).

##### Estructura y Producción (Coste total: 3.150,00 €/mes)
Representa el gasto operativo fijo necesario para mantener la presencia de marca, generar el material audiovisual y gestionar la comunidad de usuarios.

| Partida de Gasto | Descripción del Servicio | Coste Mensual |
| :--- | :--- | :---: |
| **Contratación de Community Manager** | Gestión de redes sociales, atención al usuario y tendencias. | 1000,00 € |
| **Producción de Anuncios** | Grabación y edición de vídeos (Spots publicitarios, Reels y TikToks). | 2000,00 € |
| **Recursos Creativos** | Suscripciones de diseño, música comercial y stock. | 150,00 € |


##### Inversión Publicitaria (Coste total: 0,80€ · u € / mes)
Presupuesto neto destinado a la compra de alcance y conversión. La inversión escala linealmente según el objetivo de usuarios activos ($u$), asumiendo un coste de adquisición competitivo en el sector de apps de servicios.

**Fórmula de Escalabilidad:** 
> $Inversión_{Ads} = 0,80€ \cdot u$

| Escenario de Usuarios ($u$) | Inversión TikTok Ads (50%) | Inversión Meta Ads (50%) | Inversión Total Ads |
| :--- | :---: | :---: | :---: |
| **1.000 usuarios** | 400,00 € | 400,00 € | **800,00 €** |
| **10.000 usuarios** | 4.000,00 € | 4.000,00 € | **8.000,00 €** |
| **25.000 usuarios** | 10.000,00 € | 10.000,00 € | **20.000,00 €** |

#### Operaciones y Transacciones (Coste total: 4,44€ · $u$ / mes)

Este apartado detalla los costes de gestión de cobros (Pay-ins) y transferencias (Payouts) a través de **Stripe Connect**. Se asume un modelo transaccional donde Rooma actúa como intermediario seguro para el pago de rentas y servicios.

#### Fórmulas de Cálculo Operativo:
> $Coste_{Fijo\_Connect} = 2,00€ \cdot u_{piso}$

> $Coste_{Comisiones} = (1,75\% \cdot Vol) + (0,35€ \cdot n)$

* **$u_{piso}$ (25% de $u$):** Número de perfiles con un alquiler o servicio activo en la plataforma. Se estima que 1 de cada 4 usuarios registrados (25%) llega a formalizar y gestionar su contrato a través de la App.
* **$Vol$ ($u_{piso} \times 800€$):** Volumen total de capital procesado (Alquiler + Suministros + Reparaciones).
* **$n$ ($u_{piso} \times 5$):** Cantidad de transacciones ejecutadas (Pagos de inquilino + Payouts a propietarios/proveedores).

#### Desglose del coste por usuario con contrato ($u_{piso}$):
Para el cálculo, se supone una media de **5 transacciones** y **800,00 €** transferidos mensualmente por cada usuario con contrato activo:
* **Gestión de cuenta (Connect):** 2,00 € fijo/mes.
* **Comisión por volumen (1,75% de 800€):** 14,00 € variable/mes.
* **Comisión por transacciones (0,35€ x 5):** 1,75 € fijo/mes.
* **Total por usuario con contrato:** **17,75 €/mes.**
* **Total por usuario:** **4,4375 €/mes.**



| Escenario de Usuarios ($u$) | Usuarios con Contrato ($u_{piso}$) | Volumen Mensual ($Vol$) | Nº Operaciones ($n$) | Coste Total Stripe |
| :--- | :---: | :---: | :---: | :---: |
| **1.000 usuarios** | 250 | 200.000 € | 1.250 | **4.437,50 €/mes** |
| **10.000 usuarios** | 2.500 | 2.000.000 € | 12.500 | **44.375,00 €/mes** |
| **25.000 usuarios** | 6.250 | **5.000.000 €** | **31.250** | **110.937,50 €/mes** |


#### Suposiciones y lógica de Negocio:
1. **Ratio de contratación y volumen de pagos:** Como definimos anteriormente, se supone un 25% de usuarios con contrato, gastando 800€ mensuales divididos en 5 transacciones.
2. **Activación de Connect:** El coste de 2,00€ por cuenta se aplica únicamente si el usuario recibe fondos ese mes. Al asumir que todos los contratos en vigor liquidan pagos mensualmente, este coste se vuelve estructural para el 25% de la base.
3. **Cumplimiento Normativo:** El coste fijo de Stripe Connect cubre la validación de identidad, prevención de blanqueo de capitales y el soporte técnico de la pasarela, delegando la responsabilidad legal bancaria en el proveedor.
4. **Estimación de Comisiones:** El cálculo de las comisiones variables se basa en un ticket medio transaccionado proporcional a la densidad de usuarios, garantizando que la infraestructura soporte el flujo de caja proyectado.

#### Resumen de Gastos Operativos (OPEX - Fase Lanzamiento)

| Categoría | Partida | Importe (f($u$)) | Subtotal |
| :--- | :--- | :---: | :---: |
| **Infraestructura Cloud** | Digital Ocean | **53,32 € + 0,01 $u$** |
| **Herramientas de Equipo** | Github Team (16 licencias) | 58,72 € | |
| | Gemini Pro (16 licencias) | 296,00 € | |
| | Microsoft 365 Business (16 licencias) | 187,20 € | **541,92 €** |
| **Suministros** | Consumo eléctrico (Jornada completa) | 75,80 € | **75,80 €** |
| **Laboral (mantenimiento)** | Ingeniería (16 pers. x 37,8h/mes) | 10.777,54 € | **10.777,54 €** |
| **Marketing y Adquisición** | Estructura CM y Producción Audiovisual | 3.150,00 € | |
| | Inversión Publicitaria Ads | 0,80 $u$ | **3.150,00 € + 0,80 $u$** |
| **Operaciones Financieras** | Gestión Stripe y Transacciones | 4,44 $u$ | **4,44 $u$** |
| **Seguridad y Previsión** | **Contingencia (10% sobre costes fijos)** | 1.459,86 € | **1.459,86 €** |
| **TOTAL OPEX MENSUAL** |  | | **16.058,44 € + 5,25 $u$** |

### Ingresos

#### Vía de Ingresos 1: Modelo de Suscripción

Se establece un modelo escalonado para asegurar la adquisición masiva de usuarios en la base, monetizando a través de la aportación de valor añadido.

- **Nivel Free (0€):** Actúa exclusivamente como embudo de adquisición. Sus funciones están restringidas a 20 swipes diarios, chat básico y visualización de mapas.
- **Rooma Plus (5,99€/mes):** Orientado a usuarios con alta intención de interacción. Ofrece swipes ilimitados, visualización de likes, filtros avanzados y experiencia sin anuncios.
- **Rooma Pro (15,99€/mes):** Orientado a caseros o heavy users. Incluye posicionamiento destacado, analíticas de visitas, insignia de verificación y soporte prioritario.


#### Vía de Ingresos 2: Funcionalidades Extra (Add-ons)

Para complementar las suscripciones recurrentes, se habilita una vía de monetización por "impulso" dirigida a usuarios que requieren funciones específicas de forma puntual.

* **Add-ons disponibles:** 
    * **Rewind:** Deshacer el último like o dislike.
    * **Boost:** Posicionamiento prioritario en el feed por 24h.
    * **Chat de difusión:** Apertura de tablón de anuncios grupal para coordinar visitas.

**Estructura de Precios:**
| Producto | Unidades | Precio PVP | Precio por Unidad |
| :--- | :---: | :---: | :---: |
| **Pack Individual** | 1 ud. | **0,99 €** | 0,99 € |
| **Pack de Ahorro** | 5 uds. | **3,99 €** | 0,80 € |

> **Cálculo del Ingreso Ponderado (Add-ons):**
> Basado en las suposiciones de conversión (15% adquiere Pack Individual y 5% adquiere Pack de Ahorro):
> * $(0,15 \times 0,99 €) + (0,05 \times 3,99 €) = \mathbf{0,35 € \text{ adicionales por usuario (u)}}$

#### Vía de Ingresos 3: Modelo Transaccional y Comisiones

Para garantizar que la pasarela de pagos no sea deficitaria tras los costes de Stripe, se establece una tarifa de **"Gestión y Garantía"** mixta.

* **Tarifa Rooma:** **5% sobre el volumen ($Vol$) + 0,50€ fijos por transacción ($n$).**
* **Margen Neto Transaccional:** Tras descontar el coste de Stripe (1,75% + 0,35€), Rooma retiene un margen neto del **3,25% + 0,15€** por cada operación.

> **Ejemplo de Unidad de Negocio:** En un alquiler de 800€ con 5 transacciones mensuales:
> * **Ingreso Bruto Rooma (5% + 0,50€ x 5):** 42,50 €
> * **Coste Stripe (Tarifa técnica):** 17,75 €
> * **Beneficio Neto para la plataforma:** **24,75 €/mes por contrato activo.**

#### Resumen de Monetización por Usuario ($u$)

La siguiente tabla consolida el potencial de generación de ingresos brutos mensuales por cada usuario registrado, desglosando cada vía según su tasa de conversión y su aportación al ingreso medio:

| Vía de Ingreso | Base de Cálculo (Conversión) | Ingreso por Unidad | Ingreso Ponderado ($u$) |
| :--- | :---: | :---: | :---: |
| **Suscripción Rooma Plus** | 25% | 5,99 € | 1,50 € |
| **Suscripción Rooma Pro** | 3,75% | 15,99 € | 0,60 € |
| **Add-on: Pack Individual** | 15% | 0,99 € | 0,15 € |
| **Add-on: Pack de Ahorro** | 5% | 3,99 € | 0,20 € |
| **Comisiones Transaccionales** | 25% | 42,50 € | 10,62 € |
| **TOTAL INGRESO BRUTO ($ARPU$)** | | | **13,07 €** |


*Nota: El ingreso ponderado por usuario ($u$) es el resultado de multiplicar el Ingreso por Unidad por su respectiva Base de Cálculo. Este valor representa la facturación bruta media que genera cada usuario registrado en la plataforma.*

### Rentabilidad y Viabilidad Económica

#### Análisis de Costes Variables y Margen de Contribución
Para obtener el margen de contribución unitario, restamos todos los costes operativos variables asociados a cada usuario:

* **Coste de Adquisición (Ads):** 0,80 €/u
* **Coste de Infraestructura (Cloud):** 0,01 €/u
* **Coste Operativo de Stripe:** 4,44 €/u
* **Total costes variables:** **5,25 € / usuario**

> **Margen de Contribución Unitario:** 13,07 € (Ingreso) - 5,25 € (Gasto) = **7,82 € netos por usuario.**


#### Punto de equilibrio: Ingresos vs. Gastos Operativos
Este hito representa el momento en que la facturación mensual de Rooma es suficiente para cubrir la totalidad de sus costes de estructura (16.058,44 €). A partir de este número de usuarios, la empresa deja de consumir caja operativa y comienza a generar beneficios.

* **Fórmula:** $Usuarios_{Equilibrio} = \frac{Costes\_Fijos\_Mensuales}{Margen\_Unitario}$
* **Cálculo:** $16.058,44 € / 7,82 €$

> **Resultado:** Rooma alcanza la rentabilidad operativa mensual con **2.054 usuarios totales** registrados y activos (mes 9).

#### Punto de Retorno de la Inversión Total (Payback)
Este hito financiero determina el momento en el que el beneficio neto acumulado iguala a la suma de toda la inversión inicial y el déficit generado durante la fase de crecimiento. 

**Inversión Inicial Consolidada ($I_{prev}$):**
Incluye el CAPEX (74.159,80 €) y el OPEX de la fase de desarrollo (2.705,28 €).
* **Total Inversión Pre-lanzamiento:** **76.865,08 €**

**Cálculo del Retorno Total ($RT$):**
El punto de retorno se alcanza cuando el sumatorio del beneficio mensual ($B_m$) compensa la inversión inicial y el gasto operativo acumulado de lanzamiento.

$$RT = I_{prev} + \sum_{m=1}^{n} (Gastos\_totales_m - Ingresos\_brutos_m) = 0$$

* **$I_{prev}$:** 76.865,08 € (Inversión fija inicial).
* **Déficit de Lanzamiento:** Suma del beneficio negativo de los meses 1 al 8.

| Mes | Usuarios ($u$) | Ingreso Mensual | Gasto Mensual | Beneficio Mes | **Caja Neta Acum.** |
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

> **Conclusión del Retorno:** Como se observa en la columna de **Caja Neta Acumulada**, el punto de recuperación total de la inversión se alcanza durante el **Mes 13**. Tras absorber el déficit acumulado, la plataforma logra sanear completamente su balance y finalizar el mes 13 con un saldo positivo de **+20.019,90 €**. A partir de este hito, Rooma deja de recuperar capital invertido para comenzar a generar valor neto y liquidez real para la sociedad.

#### Proyección de Escenario Realista (10.000 usuarios)
Una vez superado el umbral de rentabilidad en el mes 9, la eficiencia del margen unitario permite una consolidación financiera acelerada hacia el cierre del primer año:

* **Ingresos Brutos Mensuales:** 127.200,00 €
* **Gastos Totales (Fijos + Variables):** 68.558,44 €
* **Beneficio Neto Mensual:** **+ 58.641,56 €**

*Nota: Con este nivel de beneficios operativos al finalizar el año, la inversión inicial de CAPEX (74.159,80 €) se recuperaría íntegramente en apenas 1,3 meses de operación en este escenario. Esto demuestra un retorno de inversión (ROI) extremadamente sólido y una alta capacidad de autofinanciación del proyecto tras alcanzar su masa crítica inicial.*