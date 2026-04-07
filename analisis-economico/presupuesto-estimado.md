# Presupuesto Estimado
## Desarrollo 29/01/2026 - 21/05/2026
### CAPEX (Coste total: 74.159,80 €)
#### Equipamiento Informático (Coste total: 16.000€)
Se opta por un modelo Bring Your Own Device (BYOD) para la fase de desarrollo y lanzamiento inicial, acumulando un CAPEX estimado de 16K € (16 equipos a 1.000 €/ud).

#### Propiedad Intelectual y Legal (Coste total: 7.350€)

Este apartado contempla la inversión inicial e ineludible para blindar la empresa, proteger el producto y cumplir con la legalidad vigente para una plataforma de interacción social.

- **Constitución de la Sociedad (SL):** 3.5K €
    - Incluye el Capital Social mínimo exigido por ley (3K€), gastos de Notaría y Registro Mercantil (500€).
- **Pacto de Socios:** 1.5K €
    - Con un equipo estructural de más de 15 personas, es imprescindible un contrato redactado por un abogado mercantil que regule el reparto de acciones, cláusulas de permanencia, y la cesión obligatoria de los derechos de propiedad intelectual del código y diseño a favor de la sociedad.
- **Auditoría y Adecuación GDPR/LOPDGDD:** 1.5K €
    - La aplicación recopila datos de geolocalización (mapas), preferencias personales, hábitos de vida (fumadores, mascotas) y gestiona transacciones económicas. Se requiere un bufete especializado para redactar Términos y Condiciones de Uso, Política de Privacidad y Consentimiento de Tratamiento de Datos Sensibles; y Política de Cookies.
- **Registro de Marca (Nacional / Europea):** 850 €
    - Tasas de la OEPM (Oficina Española de Patentes y Marcas) o la EUIPO (Oficina Europea) para proteger el nombre comercial "Rooma" y su logotipo en las clases correspondientes a software y servicios de emparejamiento.

#### Licencias Perpetuas y Activos Digitales (Coste total: 1300€)

Este apartado recoge la inversión inicial para adquirir los derechos de uso comercial y vitalicio sobre los activos digitales necesarios para el desarrollo, diseño y branding de la aplicación.

- **Tipografías y Recursos Tipográficos Comerciales:** 800 €
    - Adquisición de licencias de uso comercial (App/Web/Desktop) para las fuentes tipográficas integradas en la interfaz de usuario y utilizadas en los materiales de marketing. Las licencias Open Source a menudo prohíben su uso o exigen atribuciones incompatibles con un producto monetizado.
- **Librerías de Sonido, Iconografía y Multimedia:** 500 €
    - Compra de derechos (licencias Royalty-Free extendidas) para los efectos de sonido de la aplicación (ej. el feedback auditivo de los swipes, notificaciones de chat o alertas de sistema).

#### Laboral (Coste total: 42.768€)

Todo el salario de los 16 desarrolladores y el tiempo de gestión dedicado exclusivamente a construir la aplicación (antes de que esté lista para el público) es CAPEX.

Este apartado detalla el gasto operativo del capital humano. Para realizar una presupuestación realista y evitar la descapitalización de la empresa, es imperativo distinguir entre lo que percibe el trabajador y el impacto real en la tesorería.

- **Salario Líquido (Neto):** El importe final que recibe el empleado en su cuenta bancaria tras deducir IRPF y su cuota obrera de la Seguridad Social. No tiene relevancia para el presupuesto de la empresa.
- **Salario Bruto:** La base imponible negociada en el contrato. Incluye el líquido más las retenciones del trabajador.
- **Coste Total de Empresa (Coste Presupuestado):** El desembolso real. Es la suma del Salario Bruto más la cuota patronal a la Seguridad Social (aprox. 30-33% adicional en España por contingencias comunes, desempleo, formación y FOGASA). Esta es la única métrica utilizada para calcular el gasto mensual y anual.

Para reflejar fielmente la realidad operativa de la empresa y no desvirtuar el análisis financiero, los costes se han prorrateado en base a una dedicación parcial de 10 horas semanales por persona durante el periodo estipulado de 15 semanas.

| Rol | Unidades | Horas | Salario Líquido | Salario Bruto | Coste de Empresa | Total |
|---|---|---|---|---|---|---|
| Ingeniero Junior | 16 | 150 | 10,60€/h | 13,50€/h | 17,82€/h | 42.768€ |

#### Resumen de Inversión CAPEX

| Categoría | Partida | Importe | Subtotal |
| :--- | :--- | :---: | :---: |
| **Equipamiento Informático** | 16 Equipos Portátiles (BYOD - 1.000€/ud) | 16.000,00 € | **16.000,00 €** |
| **Propiedad Intelectual y Legal** | Constitución de la Sociedad (Capital + Notaría) | 3.500,00 € | |
| | Redacción de Pacto de Socios | 1.500,00 € | |
| | Auditoría y Adecuación GDPR/LOPDGDD | 1.500,00 € | |
| | Registro de Marca (OEPM / EUIPO) | 850,00 € | **7.350,00 €** |
| **Licencias y Activos Digitales** | Licencias Tipográficas Comerciales | 800,00 € | |
| | Librerías de Sonido e Iconografía | 500,00 € | **1.300,00 €** |
| **Laboral** | 16 Ingenieros Junior (150h/ud a 17,82€/h) | 42.768,00 € | **42.768,00 €** |
| **Seguridad y Previsión** | **Contingencia (10% sobre el coste fijo)** | 6.741,80 € | **6.741,80 €** |
| **TOTAL CAPEX** | | | **74.159,80 €** |

### OPEX (Coste total: 676,32 €/mes)
Este bloque recoge los costes operativos recurrentes necesarios para mantener el entorno técnico de desarrollo en funcionamiento durante la fase de construcción del producto.

#### Infraestructura (Coste total: 53,72 €/mes)
Incluye los servicios cloud base para desplegar y validar el entorno de desarrollo de forma continua, priorizando un proveedor con buen equilibrio entre coste, simplicidad y disponibilidad.

Para esta fase de desarrollo, se establece un **coste fijo** basado en el mantenimiento del entorno de desarrollo y el soporte técnico para un grupo cerrado de **40 usuarios piloto**. Al ser un número de usuarios conocido y controlado, no se aplican variables de escalabilidad hasta la fase de lanzamiento comercial.

| Despliegue para desarrollo | Usuarios Piloto (Fijo) | Coste Mensual |
|---|---|---|
| Digital Ocean (Servidor y Base de Datos) | 40 | 53,72 €/mes |

*El presupuesto contempla una base de 53,32€ para la infraestructura de computación, a la que se suma un margen de 0,40€ (0,01€/usuario) para cubrir el tráfico de datos y almacenamiento de imágenes generado por los 40 usuarios piloto durante el periodo de prueba.*

#### Herramientas de desarrollo (Coste total: 541,92€/mes)
Este apartado contempla las suscripciones mensuales del stack de productividad del equipo (repositorios, IA asistida y ofimática), imprescindibles para coordinar trabajo, documentar avances y acelerar entregas.

| Herramienta | Número de licencias | Coste unitario | Coste Total |
|---|---|---|---|
| Github Team | 16 | 3,67€/mes | 58,72€/mes |
| Gemini Pro | 16 | 18,50/mes | 296€/mes |
| Microsoft 365 Business | 16 | 11,70/mes | 187,2€/mes |

#### Luz (Coste total: 19,20€/mes)
Se estima el consumo eléctrico asociado al tiempo efectivo de desarrollo, tomando como base las horas mensuales del equipo, una potencia media por puesto y un precio unitario conservador por kWh.

| Horas mensuales equipo | Energía consumida | Precio Energía | Coste Total |
|---|---|---|---|
| 640 (16x40) | 128 (640x0,2) | 0,15/kWh€ | 19,20€/mes |

#### Resumen de Gastos Operativos (OPEX - Fase Desarrollo)
| Categoría | Partida | Importe | Subtotal |
| :--- | :--- | :---: | :---: |
| **Infraestructura Cloud** | Digital Ocean (Servidor y Base de Datos) | 53,32 € | |
| | Soporte 40 Usuarios Piloto | 0,40 € | **53,72 €** |
| **Herramientas de Desarrollo** | Github Team (16 licencias) | 58,72 € | |
| | Gemini Pro (16 licencias) | 296,00 € | |
| | Microsoft 365 Business (16 licencias) | 187,20 € | **541,92 €** |
| **Suministros** | Consumo eléctrico (128 kWh mensuales) | 19,20 € | **19,20 €** |
| **Seguridad y Previsión** | **Contingencia (10% sobre costes fijos)** | 61,48 € | **61,48 €** |
| **TOTAL OPEX MENSUAL** | | | **676,32 €** |

## Lanzamiento 21/05/2026 - 21/05/2027
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

#### Mantenimiento (Coste total: 10.777,536€/mes)

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


#### Suposiciones y Lógica de Negocio:
1. **Ratio de Contratación (25%):** Se estima que el 25% de la base de usuarios totales ($u$) son perfiles con un contrato en vigor que requiere gestión de pagos recurrente. El 75% restante representa usuarios en fase de búsqueda o perfiles inactivos que no generan coste en Stripe.
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
| **Mantenimiento Técnico** | Ingeniería (16 pers. x 37,8h/mes) | 10.777,54 € | **10.777,54 €** |
| **Marketing y Adquisición** | Estructura CM y Producción Audiovisual | 3.150,00 € | |
| | Inversión Publicitaria Ads | 0,80 $u$ | **3.150,00 € + 0,80 $u$** |
| **Operaciones Financieras** | Gestión Stripe y Transacciones | 4,44 $u$ | **4,44 $u$** |
| **Seguridad y Previsión** | **Contingencia (10% sobre costes fijos)** | 1.459,86 € | **1.459,86 €** |
| **TOTAL OPEX MENSUAL** |  | | **16.058,44 € + 5,25 $u$** |

### Ingresos

#### Vía de Ingresos 1: Modelo de Suscripción

Se establece un modelo escalonado para asegurar la adquisición masiva de usuarios en la base, monetizando a través de la aportación de valor añadido.

- **Nivel Free (0€):** Actúa exclusivamente como embudo de adquisición. Sus funciones están restringidas a 20 swipes diarios, chat básico y visualización de mapas. Estos usuarios son un gasto neto de infraestructura; su única función estratégica es generar la liquidez del mercado (efecto red) necesaria para que otros perfiles paguen.
- **Rooma Plus (9.99€/mes):** Orientado a usuarios con alta intención de interacción. Ofrece swipes ilimitados, visualización de likes, filtros avanzados de estilo de vida (mascotas, fumadores, teletrabajo) y experiencia sin anuncios.
- **Rooma Pro (29.99€/mes):** Orientado a caseros o heavy users. Incluye posicionamiento destacado (aparecen primero), analíticas de visitas, insignia de verificación "Pro" y soporte prioritario.

#### Vía de Ingresos 2: Modelo Transaccional y Comisiones

Para garantizar que la pasarela de pagos no sea deficitaria tras los costes de Stripe, se establece una tarifa de **"Gestión y Garantía"** mixta.

* **Tarifa Rooma:** **5% sobre el volumen ($Vol$) + 0,50€ fijos por transacción ($n$).**
* **Margen Neto Transaccional:** Tras descontar el coste de Stripe (1,75% + 0,35€), Rooma retiene un margen neto del **3,25% + 0,15€** por cada operación.

> **Ejemplo de Unidad de Negocio:** En un alquiler de 800€ con 5 transacciones mensuales:
> * **Ingreso Bruto Rooma (5% + 0,50€ x 5):** 42,50 €
> * **Coste Stripe (Tarifa técnica):** 17,75 €
> * **Beneficio Neto para la plataforma:** **24,75 €/mes por contrato activo.**

### Rentabilidad y Viabilidad Económica

#### Análisis de Ingreso Medio por Usuario ($ARPU$)
Se proyecta el ingreso bruto que genera cada usuario registrado ($u$) basándose en el embudo de conversión estimado para una plataforma de *matching* y gestión de alquileres:

| Canal de Ingreso | Conversión | Cuota/Margen Bruto | Ingreso Ponderado ($u$) |
| :--- | :---: | :---: | :---: |
| **Suscripción Rooma Plus** | 15% | 9,99 € | 1,50 € |
| **Suscripción Rooma Pro** | 2% | 29,99 € | 0,60 € |
| **Comisiones Transaccionales** | 25% | 24,75 € | 6,18 € |
| **TOTAL INGRESO BRUTO ($u$)** | | | **8,28 € / usuario** |

---

#### Análisis de Costes Variables y Margen de Contribución
Para que el umbral de rentabilidad sea realista, restamos los costes operativos que cada usuario genera individualmente a la plataforma:

* **Coste de Adquisición ($Ads$):** 0,80 €/u.
* **Coste de Infraestructura ($Cloud$):** 0,01 €/u.
* **Coste Operativo de Stripe (Promedio):** 4,44 €/u.
* **Total costes variables:** **5,25 € / usuario.**

> **Margen de Contribución Unitario:** 8,28 € (Ingreso) - 5,25 € (Gasto) = **3,03 € netos por usuario.**

---

#### Umbral de Rentabilidad (Breakeven)
El punto de equilibrio se alcanza cuando el margen neto generado por la base de usuarios cubre la estructura fija de la empresa:

* **Fórmula:** $Usuarios_{Breakeven} = \frac{Costes\_Fijos}{Margen\_Unitario}$
* **Cálculo:** $16.058,44 € / 3,03 €$

> **Resultado:** Rooma alcanza la rentabilidad operativa con **5.300 usuarios totales** registrados y activos en la plataforma.

#### Proyección de Escenario de Éxito (25.000 usuarios)
Una vez superado el umbral de rentabilidad, la escalabilidad del modelo transaccional permite un crecimiento acelerado del beneficio:

* **Ingresos Brutos Mensuales:** 207.000,00 €
* **Gastos Totales (Fijos + Variables):** 147.308,44 €
* **Benficio neto mensual:** **+ 59.691,56 €**

*Nota: Con este nivel de beneficios, la inversión inicial de CAPEX (74.159,80 €) se recuperaría íntegramente en poco más de un mes tras alcanzar el escenario de éxito, demostrando la alta eficiencia de retorno del proyecto.*