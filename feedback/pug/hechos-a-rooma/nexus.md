# Pilot User Review

## Índice

1. Identificación
2. Resumen del Esfuerzo
	1. Equipo de Revisión
	2. Esfuerzo Total
3. Resultados por Caso de Uso
	1. Descubrimiento de viviendas
	2. Evaluación de Candidatos y Match
	3. Gestión de inmuebles
	4. Gestión de Facturas y Pagos
	5. Reseñas y Valoración de la Convivencia

## 1. Identificación

- Entregable: #SP1
- Grupo Revisado (RG): 1
- Grupo Usuario Piloto (PUG): 7

## 2. Resumen del Esfuerzo

### 2.1. Equipo de Revisión

- Alberto García Sanz
- Jesús García Pérez
- Ángel Mateos Marín

### 2.2. Esfuerzo Total

Se ha dedicado un total de 3 horas, 1 hora por miembro.

## 3. Resultados por Caso de Uso

### 3.1. Descubrimiento de viviendas

- **Descripción**: Explorar y expresar interés en viviendas compatibles.
- **Fallos**: Ninguno.
- **Feedback**: Las tarjetas de los pisos se muestran correctamente, pudiendo seleccionar si ese piso nos interesa o no; al marcar alguno como interesante, se guardan en solicitudes.

### 3.2. Evaluación de Candidatos y Match

- **Descripción**: Evaluar a los interesados y filtrar quiénes pueden acceder al contacto directo o a la reserva de visita.
- **Fallos**: Desde el panel de landlord, puedo añadir a mi vivienda a tenants aunque estos estén en un piso ya, lo cual no tiene efecto, y el tenant al aceptar el match no hace nada; vuelve a aparecer el inmueble en match.
- **Feedback**: No permitir la búsqueda de piso si ya estás en uno, o al menos que no permita que el landlord te añada a su piso.

### 3.3. Gestión de inmuebles

- **Descripción**: Dar de alta y mantener la oferta de inmuebles actualizada en la plataforma.
- **Fallos**: El mapa no funciona; no se sabe si falta implementación y no está contemplado en este sprint, o hay algo a instalar/habilitar que falta. El botón de edición de inmuebles y el de los tres puntos tampoco funcionan.
- **Feedback**: No se puede poner límite de personas al crear un nuevo inmueble, por lo que no se puede controlar cuántas personas meter. Un tenant no tiene opción de salir del piso en el que se encuentra ahora mismo.

### 3.4. Gestión de Facturas y Pagos

- **Descripción**: Automatizar la notificación, el reparto y el seguimiento de los pagos de suministros y renta del inmueble.
- **Fallos**:
  - El botón de notificaciones no genera ningún tipo de interacción.
  - Incongruencia entre paneles: pulsas en “Facturas” y te lleva a un panel llamado “Mis Pagos”.
  - Al pulsar en la flecha hacia atrás desde “Mis Pagos” te lleva a los detalles del piso, en vez de al panel del perfil.
- **Feedback**: Crear un pop-up al hacer clic en el icono de la campana y que se vean las notificaciones. Tener mayor concordancia en cuanto a nombres de paneles y sus respectivas redirecciones. Al crear facturas como landlord se actualiza correctamente a los inquilinos de dicha propiedad.

### 3.5. Reseñas y Valoración de la Convivencia

- **Descripción**: Generar un sistema de confianza basado en la experiencia real de convivencia o gestión.
- **Fallos**: Ningún tenant tiene ninguna valoración realizada o pendiente de realizar.
- **Feedback**: El panel de valoraciones aparece y es correcto, pero deberían aparecer los compañeros de piso en “valoraciones pendientes” o “realizadas”, y que se enlace con cada tenant para que aparezca la valoración en su apartado de “recibidas”.
