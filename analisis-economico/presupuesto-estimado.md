# Presupuesto Estimado
## Desarrollo 29/01/2026 - 21/05/2026
### CAPEX (Coste total: 7.350€)
#### Equipamiento Informático (Coste total: 16.000€)
Se opta por un modelo Bring Your Own Device (BYOD) para la fase de desarrollo y lanzamiento inicial, acumulando un CAPEX estimado de 16K € (16 equipos a 1.000 €/ud).

#### Propiedad Intelectual y Legal (Coste total: 7.350€)

Este apartado contempla la inversión inicial e ineludible para blindar la empresa, proteger el producto y cumplir con la legalidad vigente para una plataforma de interacción social.

- **Constitución de la Sociedad (SL):** 3.5K €
	- Incluye el Capital Social mínimo exigido por ley (3K €), gastos de Notaría y Registro Mercantil (500€).
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


### OPEX (Coste total: 614,44€/mes)
Este bloque recoge los costes operativos recurrentes necesarios para mantener el entorno técnico de desarrollo en funcionamiento durante la fase de construcción del producto.

#### Infraestructura (Coste total: 53,32€/mes)
Incluye los servicios cloud base para desplegar y validar el entorno de desarrollo de forma continua, priorizando un proveedor con buen equilibrio entre coste, simplicidad y disponibilidad.

| Despliegue para desarrollo | Coste Mensual |
|---|---|
| Digital Ocean | 53,32€/mes |

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
## Lanzamiento 21/05/2026 - 21/05/2027
### OPEX (Coste total: 14.483,576)

Este bloque detalla los costes operativos recurrentes durante la fase de lanzamiento y operación de la plataforma.

#### Infraestructura (Coste total: 88,32€/mes)

La infraestructura escala dinámicamente según el volumen de usuarios activos, garantizando disponibilidad y rendimiento.

| Número de usuarios | Coste Mensual |
|---|---|
| 0-1.0000 | 53,32€/mes |
| 1.0000 - 10.0000 | 65,32€/mes |
| +10.0000 | 88,32€/mes |

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

#### Marketing (Coste total: 3000€/mes)

Presupuesto inicial de adquisición de usuarios en canales digitales adaptados al perfil demográfico objetivo (Generación Z, móvil-first). Las campañas se distribuyen entre plataformas con mayor penetración en el segmento de inquilinos jóvenes.

| Canal | CPM | Alcance | Total |
|---|---|---|---|
| Tiktok | 3,5€ | 428.000 personas | 1500€/mes |
| Meta | 6€ | 250.000 personas | 1500€/mes |

### Operaciones y Transacciones

Este apartado detalla los costes asociados a la gestión de pagos y transferencias a través del PSP seleccionado, que introduce un peaje variable sobre los ingresos y pagos procesados en la plataforma.

| Proveedor | Coste por Ingreso | Coste por Transaferencia |
|---|---|---|
| Stripe | 1,5% + 0,25€ por pago | 2€/mes por cuenta activa + 0,25% + 0,10€ por envío |

### Ingresos

#### Vía de Ingresos 1: Modelo de Suscripción

Se establece un modelo escalonado para asegurar la adquisición masiva de usuarios en la base, monetizando a través de la aportación de valor añadido.

- **Nivel Free (0€):** Actúa exclusivamente como embudo de adquisición. Sus funciones están restringidas a 20 swipes diarios, chat básico y visualización de mapas. Estos usuarios son un gasto neto de infraestructura; su única función estratégica es generar la liquidez del mercado (efecto red) necesaria para que otros perfiles paguen.
- **Rooma Plus (9.99€/mes):** Orientado a usuarios con alta intención de interacción. Ofrece swipes ilimitados, visualización de likes, filtros avanzados de estilo de vida (mascotas, fumadores, teletrabajo) y experiencia sin anuncios.
- **Rooma Pro (29.99€/mes):** Orientado a caseros o heavy users. Incluye posicionamiento destacado (aparecen primero), analíticas de visitas, insignia de verificación "Pro" y soporte prioritario.

#### Vía de Ingresos 2: Modelo Transaccional y Comisiones

El planteamiento inicial establecía una comisión plana del 3% sobre cada transacción realizada dentro de la app en concepto de Gestión y Servicio. Este modelo era deficitario y ha sido reestructurado antes del lanzamiento.

- **El problema de las microtransacciones:** Los Proveedores de Servicios de Pago (PSP) como Stripe o Mangopay aplican tarifas mixtas (aproximadamente un porcentaje variable + un cargo fijo de ~0,25€ a 0,30€ por transacción). En un pago de 10€ gestionado por la app, la comisión del 3% genera 0,30€ de ingresos brutos para Rooma. El coste del PSP superará los 0,40€. La empresa asume pérdidas netas en cada transacción de bajo importe.
- **Corrección de Pricing:** La tarifa de "Gestión y Servicio" se modificará a un modelo de comisión mixta (ej. 3% + 0,50€ fijos) o, alternativamente, se establecerá un ticket mínimo de transacción para asegurar que el Margen Bruto sea matemáticamente positivo tras descontar el peaje del PSP.

### Rentabilidad
Para que nuestra app sea rentable, debemos superar los 14.483,576€/mes que tenemos en OPEX, por lo que necesitaríamos 1.442 usarios con el plan plus (9,99€mes) para llegar al breakeven.
