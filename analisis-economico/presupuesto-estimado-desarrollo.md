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