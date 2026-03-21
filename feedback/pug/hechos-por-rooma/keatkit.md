# Keakit

## CU-GENERAL-01 – Registro e inicio de sesión

- **T-13**: No se valida el campo del teléfono en el formulario de registro de usuario (se ha creado un usuario con el número de teléfono `prueba`).
- **T-13**: No se valida el campo de la dirección en el formulario de registro de usuario (se ha creado un usuario con la dirección `12211212`).

## CU-GENERAL-02 – Gestión de datos personales

- **T-13**: No se valida el campo del teléfono en el formulario de editar perfil (se ha modificado el perfil con número de teléfono `prueba`).
- **T-13**: No se valida el campo de la dirección en el formulario de editar perfil (se ha creado un usuario con la dirección `12211212`).

## Feedback general

- Está muy chula la función de elegir país y posteriormente ciudad.
- En general, en todos los CU se ha hecho muy complicado probarlos debido a los constantes errores mencionados con la primera carga.

## CU-GENERAL-03 – Valoraciones

### Feedback

Hemos probado que se muestran correctamente las valoraciones recibidas y realizadas, pero se nos ha hecho imposible valorar a un usuario porque no hemos encontrado dónde se realiza dicha acción. No encontramos la opción de ver perfiles de los usuarios (tampoco aparece en el vídeo tutorial que nos proporcionasteis).

## CU-GENERAL-04 – Soporte

- **T-12**: No se puede crear una incidencia de tipo objeto dañado; se queda cargando y no deja elegir producto.

### Feedback

Hemos visto que las incidencias generales se muestran correctamente, pero no nos deja de ninguna forma crear una incidencia de tipo objeto dañado.

## CU-ARRENDADOR-01 – Subida de artículos

- **T-12**: Al intentar subir un artículo como `owner@example.com` no permite elegir una categoría. Al ser este campo obligatorio, no se ha podido seguir con la comprobación de creación de un artículo.

## CU-ARRENDADOR-02 – Listado de artículos subidos

- Ningún error encontrado.

## CU-ARRENDADOR-03 – Gestión de artículos subidos

- **T-13**: Al editar un artículo se puede mandar el formulario con fechas inexistentes como `2024-15-99`, por lo que no se comprueba el campo como fecha sino como string (posiblemente con una expresión regex). Si se pulsa guardar cambios, se queda cargando y no cambian los valores ni se muestra ningún tipo de advertencia al usuario.
- **T-13**: Al editar un artículo se puede mandar el formulario con una URL inexistente y con formato incorrecto (`no_url`) y se ha dado como válido.
- **T-13**: Al editar un artículo se puede mandar el formulario con una ciudad con formato incorrecto, por ejemplo `1234`, y se da como válido.

## CU-ADMIN-01 – Gestión de categorías

- **T-14**: Cualquier usuario puede gestionar, editar y crear categorías. Solo debería ser posible para el ADMIN.
- **T-13**: Al crear una categoría no valida que el precio mínimo tenga que ser menor que el precio máximo.

### Feedback

No hemos podido acceder con las credenciales proporcionadas de admin.

## CU-ADMIN-02 – Listado de usuarios

### Feedback

No hemos podido acceder con las credenciales proporcionadas de admin.
