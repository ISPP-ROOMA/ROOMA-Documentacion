# Implementación Feedback Cerebrus

## 1. Feedback implementado en casos de uso
### 1.1. Descubrimiento de viviendas

- Se había corregido previamente el bug que existía para eliminar la solicitud a un piso. Este error ocurría porque un inquilino era capaz de solicitar de nuevo un piso al cual ya pertenecía y se lanzaba un error 409.

### 1.2. Gestión de inmuebles

- No existía validación para comprobar que el piso que se creaba no existía anteriormente. Como no se ha acordado una restricción de unicidad dependiente de varios campos en la base de datos para el piso, se ha optado por asegurar la idempotencia del método POST al crear el piso creando una clave de creación del piso necesaria que evita que se cree otro piso con los mismos datos en una ventana temporal. Asimismo, se ha añadido un estilo al botón de creación que muestra que el piso se está creando.
- También se ha eliminado el campo de fecha (al menos, de momento) ya que no se utilizaba para ninguna operación relevante dentro de la aplicación.
- La función de edición del inmueble se realizó posteriormente. Aún está en desarrollo.
- Por último, la tardanza en la creación del inmueble puede ser debida a tiempos de latencia grandes a causa de los proveedores de servidor en la nube en su capa gratuita, ya que en despliegue local la creación tarda sólo lo que tarda en enviar una petición a la API de Cloudinary para subir imágenes.

### 1.3. Gestión de Facturas y Pagos

- Se ha eliminado el botón de notificaciones.

### 1.4. Reseñas y valoración de la convivencia

- Esta funcionalidad se ha implementado completamente.

## Hallazgos generales y Feedback UI/UX

- Se corrigió la persistencia del inicio de sesión.
- Se ha redireccionado el inicio de sesión del casero a "Inicio" y se han reorganizado las pestañas de "Inicio" tanto en vista de inquilino como de casero para situarlas en la izquierda del navbar.