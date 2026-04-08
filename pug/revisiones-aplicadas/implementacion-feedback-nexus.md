# Implementación de Feedback en Nexus

## 1. Feedback implementado en casos de uso

### 1.1. Descubrimiento de viviendas

No se han reportado incidencias ni se han identificado recomendaciones de mejora en este caso de uso.

### 1.2. Evaluación de candidatos y proceso de emparejamiento (Match)

Se ha corregido el comportamiento por el cual un propietario (landlord) podía enviar una solicitud a un inquilino (tenant) que ya pertenecía a una vivienda. Actualmente, si el inquilino forma parte de un piso, no es posible enviar dicha solicitud. 

De igual manera, se ha resuelto la situación en la que un inquilino recibía múltiples solicitudes para unirse a diferentes viviendas: una vez que el inquilino acepta una de ellas y pasa a formar parte de un piso, el sistema impide la aceptación de solicitudes adicionales.

En relación con el feedback recibido, se planteó que no resulta coherente permitir que un inquilino busque vivienda mientras ya pertenece a una. Sin embargo, conforme a las reglas de diseño establecidas, se permite esta funcionalidad. La justificación radica en que un inquilino puede necesitar buscar una nueva vivienda con antelación (por ejemplo, ante una salida próxima del piso actual). No obstante, el sistema restringe que un usuario pueda ser miembro de más de una vivienda simultáneamente.

### 1.3. Gestión de inmuebles

Se ha incorporado un mapa en el proceso de creación de anuncios de viviendas, mejorando así la contextualización geográfica de los inmuebles.

Respecto al feedback que indicaba que un inquilino no puede abandonar actualmente un piso, se trata de una decisión de diseño que se encuentra en proceso de definición y cuya implementación está prevista a corto plazo.

### 1.4. Gestión de facturas y pagos

Se ha eliminado el botón de notificaciones.

Asimismo, se ha corregido la incongruencia existente entre distintos paneles y sus respectivas redirecciones, garantizando una navegación más coherente dentro del sistema.

### 1.5. Reseñas y valoración de la convivencia

En relación con el feedback recibido —según el cual ningún inquilino disponía de valoraciones realizadas o pendientes—, se ha verificado que anteriormente sí existían datos correspondientes a múltiples inquilinos con valoraciones tanto completadas como pendientes.

## 2. Hallazgos generales y feedback de UI/UX

Este apartado no ha sido incluido en el feedback proporcionado.