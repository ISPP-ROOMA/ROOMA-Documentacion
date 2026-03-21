# Plan de Gestión de Usuarios Piloto y Validación Ágil (Proyecto Rooma)

## 1. Estrategia de Adquisición de "Early Adopters"

Para garantizar un feedback realista y accionable durante las fases de desarrollo, hemos establecido un grupo cerrado de Usuarios Piloto (Beta Testers). La captación se ha segmentado en los dos actores principales de nuestra plataforma (C2C):

- **Perfil Inquilino (Estudiantes o jóvenes)**: Seleccionados a través de redes universitarias y contactos de primer grado (compañeros de facultad y amigos que residen actualmente en pisos compartidos).
- **Perfil Propietario (Caseros Particulares e inmobiliarias)**: Captados a través de nuestros propios arrendadores actuales y su red de contactos, de plataformas como Idealista y de presentaciones en despachos de inmobiliarias.

**Incentivo de participación**: A los propietarios se les ofrecerá el estatus de "Cuenta Fundador" (cero comisiones en la gestión de gastos durante el primer año de lanzamiento). A los inquilinos se les sortearán incentivos menores (ej. tarjetas de plataformas de comida a domicilio) por completar el ciclo de los 3 Sprints.

## 2. Gestión de Datos y Acuerdo de Compromiso

La relación con los usuarios piloto está estrictamente regulada para simular un entorno profesional y cumplir con las normativas básicas de protección de datos:

- **Datos recopilados**: Nombre, edad, rol (inquilino/propietario), correo electrónico y hábitos de uso de apps financieras/inmobiliarias. En la fase piloto no se recopilarán documentos de identidad reales (KYC) ni datos bancarios reales; se utilizarán datos ficticios (dummy data) para probar los flujos.
- **Acuerdo de compromiso (SLA del piloto)**: Se ha firmado digitalmente (mediante formulario) un compromiso bidireccional:
	- El Equipo Rooma se compromete a: Entregar un prototipo funcional/mockup interactivo al final de cada Sprint y respetar la privacidad de los datos.
	- El Usuario Piloto se compromete a: Dedicar un máximo de 20 minutos al final de cada Sprint para probar el entregable y proporcionar feedback honesto.

## 3. Ciclo de Pruebas y Metodología (3 Sprints)

El desarrollo iterativo se validará de forma continua. Nuestro Community Manager será el canal único de comunicación para evitar saturar al usuario y centralizar los insights.

### Sprint 1: Validación del "Core" y Matchmaking

- **Entregable**: Prototipo interactivo (alta fidelidad en diseño, ej. Figma) enfocado en el Onboarding, creación de perfil y el sistema de Slide-Match (Double Opt-In).
- **Métrica de éxito**: Tiempo que tarda el usuario en entender la interfaz y completar un "Match".
- **Método de feedback**: Sesión asíncrona. Se envía un enlace al prototipo y un cuestionario corto (escala Likert) sobre la fricción de la interfaz.

### Sprint 2: Validación del Diferenciador (Gestión de Gastos)

- **Entregable**: MVP funcional de la subida de facturas (simulación de OCR) y división automática de gastos.
- **Métrica de éxito**: Nivel de confianza del propietario en el sistema y comprensión del flujo de pago por parte del inquilino.
- **Método de feedback**: Llamada/Videollamada de 15 minutos guiada por el Community Manager (Prueba de Usabilidad Moderada) pidiendo al usuario que "pague una factura de luz de 50€".

### Sprint 3: Flujo Completo y "Stress Test"

- **Entregable**: Aplicación Beta (End-to-End). Desde la búsqueda del compañero hasta el pago de la primera mensualidad simulada.
- **Métrica de éxito**: Net Promoter Score (NPS) inicial. ¿Recomendarían esta app a un amigo?
- **Método de feedback**: Encuesta final de valoración global y recogida de sugerencias abiertas para el backlog de la versión 1.0.

## 4. Tratamiento del Feedback

Al finalizar cada Sprint, el Community Manager procesará los datos cualitativos (comentarios, dudas) y cuantitativos (tiempo de uso, clics erróneos). Estos datos se presentarán al equipo de desarrollo en la reunión de Sprint Retrospective para aplicar pivotes o correcciones antes de iniciar el siguiente bloque de código.
