# ROOMA
# Requisitos de información

## CU-01: Descubrimiento de Viviendas

### HU-01: Visualización del Deck
**Historia de Usuario:** Como Buscador, quiero ver un deck de tarjetas con inmuebles filtrados por mis preferencias para explorar opciones de alquiler de forma rápida.

**Criterios de aceptación:**
1. El deck solo debe mostrar viviendas que complan con los fieltros impuestos por el buscador.
2. Si el usuario pierde la conexión, debe aparecer la misma tarjeta en la que se quedó.
3. El usuario debe poder ver como mínimo 10 viviendas más si se queda sin conexión.

**Especificación:**
Nº de viviendas por carga: El backend debe devolver como máximo 20 inmuebles por carga (los que se mantendrán si se pierde la conexión). Priorizar: Los inmuebles deben ordenarse por coincidencia en filtros e luego por publicación. Sin resultados: Si no se devuelve ningún inmueble, se debe mostrar un mensaje personalizado para modificar los filtros. Se debe guardar por parte del servidor la última vivienda vista por el Buscador como punto de partida de la siguiente sesión.

**Riesgos:**
Performance: Si crece muchísimo el número de inmuebles, el filtrado puede volverse lento (ya pasa en plataformas como idealista).

---

### HU-02: Navegación por Gestos (Swipe)
**Historia de Usuario:** Como Buscador, quiero descartar o mostrar interés mediante gestos táctiles laterales para que la navegación sea fluida, intuitiva e rápida.

**Criterios de aceptación:**
1. Al deslizar la tarjeta hacia la derecha más del 50% de la pantalla, el sistema debe marcar el inmueble como "Interesado" e registrar el estado.
2. Al deslizar hacia la izquierda, el sistema debe marcar el inmueble como "Descartado" e asegurar que no vuelva a aparecer en el deck.
3. Durante el deslizamiento, deben aparecer indicadores visuales (ej. un icono de corazón verde o una "X" roja) que varíen su opacidad según la distancia del arrastre.
4. Una vez completado el gesto, la siguiente tarjeta del deck debe cargarse inmediatamente.
5. Esta acción debe ser posible realizarla también mediante dos botones (uno para dislike e otro para like) que se diferencien claramente.

**Especificación:**
El "Match" o "Descarte" se dispara al superar el 50% del ancho de la pantalla o alcanzar una velocidad de arrastre (velocity) de 0.5 px|ms. La tarjeta superior debe tener siempre el foco táctil; las tarjetas inferiores pueden ser simplemente falsas o renderizarlas pasivamente.

**Riesgos:**
Usuarios que deslizan por error al intentar hacer scroll vertical para leer el detalle. Las animaciones pueden generar sensación de "lag" en dispositivos de gama media|baja.

---

### HU-03: Detalle del Inmueble
**Historia de Usuario:** Como Buscador, quiero acceder al detalle de una vivienda para ver fotos, descripción e el perfil de los actuales compañeros (si existen), para evaluar si mi estilo de vida es compatible con el de ellos.

**Criterios de aceptación:**
1. Debe mostrarse una descripción e la galería de fotos del inmueble.
2. Deben aparecer los perfiles de los compañeros junto con un resumen de sus perfiles, mostrando las cualidades que más los identifiquen (profesión, edad…).
3. El botón de "Like" e "Dislike" debe seguir accesible a la vez que se muestran los detalles.

**Especificación:**
Carga de Imágenes: Implementar Lazy Loading e miniaturas en baja resolución antes de cargar la imagen original.

**Riesgos:**
Perfiles de compañeros incompletos que hagan que la "afinidad" parezca inexistente o errónea.

---

### HU-04: Función Rewind (Premium)
**Historia de Usuario:** Como Buscador Premium, quiero deshacer mi último "Dislike", para recuperar un inmueble que descarté por error.

**Criterios de aceptación:**
1. La función solo debe estar activa para usuarios con el estado de Premium.
2. Solo se permite recuperar la última tarjeta descartada.
3. Se permitirá un máximo de 5 rewinds al día para los Buscadores Premium.
4. Al realizar el rewind se deberá actualizar el estado de el inmueble con el usuario, eliminando acciones pasadas.

**Especificación:**
El sistema solo debe guardar el ID de la última tarjeta descartada en la sesión actual. Si se intenta realizar Rewind sin ser Premium, saltará un Pop Up para acceder a la suscripción.

**Riesgos:**
No identificados.

---

## CU-02: Gestión de Candidatos y Match

### HU-05: Dashboard de Candidatos
**Historia de Usuario:** Como Anunciante quiero visualizar un dashboard organizado por estados para cada una de mis viviendas, para gestionar de manera eficiente el volumen de candidatos.

**Criterios de aceptación:**
1. El sistema debe listar de forma independiente cada vivienda activa del anunciante.
2. Dentro de cada vivienda, los candidatos deben agruparse visualmente en tres categorías: "Nuevos|Pendientes", "En Espera" e "Aceptados".
3. Debe mostrarse un contador numérico de candidatos en cada estado.
4. Si el inmueble cambia a estado "Pausado" o "Alquilado", el sistema debe eliminar|cancelar todas las solicitudes en estado "Pendiente" e "En Espera".

**Especificación:**
Interfaz tipo "Tablero Kanban" o lista filtrable por estado. Los candidatos se cargarán mediante paginación para evitar latencia en viviendas con alta demanda (>50 solicitudes).

**Riesgos:**
Un anunciante con muchos inmuebles e cientos de "Likes" puede verse desbordado visualmente. Si un anunciante "Pausa" por error, podría perder una lista valiosa de candidatos interesados si la eliminación es física (hard delete) en lugar de lógica (soft delete).

---

### HU-06: Ficha Técnica del Candidato
**Historia de Usuario:** Como Anunciante quiero acceder a la ficha técnica e pública de cada candidato para verificar su idoneidad e compatibilidad antes de tomar una decisión.

**Criterios de aceptación:**
1. Al hacer clic en un candidato del dashboard, se debe abrir una vista expandida.
2. La ficha debe mostrar obligatoriamente: edad, profesión|estudios, descripción personal e etiquetas de estilo de vida.
3. Debe incluir un indicador visual de "Perfil Verificado" si el usuario ha validado su identidad.

**Especificación:**
Solo se muestran datos marcados como "públicos" por el candidato. Datos sensibles (como teléfono) permanecen ocultos hasta que haya un "Match".

**Riesgos:**
La visualización de ciertos datos personales puede dar lugar a discriminación (riesgo ético|legal). Datos desactualizados en el perfil del candidato.

---

### HU-07: Gestión de Decisiones
**Historia de Usuario:** Como Anunciante quiero poder aceptar o rechazar solicitudes de candidatos para avanzar en el proceso de aceptar o descartar perfiles.

**Criterios de aceptación:**
1. Al pulsar “Aceptar”, el sistema debe crear un canal de chat e habilitar el módulo de calendario. Se envía notificación de "Match" al candidato.
2. Al pulsar “Rechazar”, La solicitud se archivará e el candidato ya no verá el anuncio e no podrá volver a dar "Like" a ese inmueble.

**Especificación:**
Al pulsar “Aceptar” se habilita el módulo de calendario (no core).

**Riesgos:**
Pulsar "Rechazar" por error (se puede implementar una acción de deshacer inmediatamente después).

---

## CU-03: Sistema de Chats

### HU-08: Mensajería Multimedia
**Historia de Usuario:** Como Candidato con un Match quiero intercambiar mensajes, fotos e documentos con la otra parte (el Anunciante) para agilizar la resolución de dudas e el envió de detalles necesarios.

**Criterios de aceptación:**
1. El sistema debe permitir el envío de texto, imágenes (JPG|PNG) e documentos (PDF).
2. Se deben mostrar indicadores visuales de estado: un check (Entregado) e doble check coloreado (Leído).
3. La actualización de los mensajes en pantalla debe ser instantánea sin necesidad de refrescar la vista (Websockets).

**Especificación:**
Uso de WebSockets (Socket.io) para la persistencia de la conexión. Límite de subida de 10MB por archivo. Los documentos deben almacenarse en un bucket seguro (S3 o similar) con URLs prefirmadas de acceso temporal.

**Riesgos:**
El intercambio masivo de imágenes de alta resolución puede disparar los costes de servidor. Riesgo de envío de spam o contenido ofensivo.

---

### HU-09: Proponer Visitas
**Historia de Usuario:** Como Anunciante quiero proponer fechas para una visita e el candidato pueda aceptarlas o sugerir otras para organizar mi agenda sin salir de la aplicación.

**Criterios de aceptación:**
1. El anunciante debe poder seleccionar la fecha e hora dentro del chat o en una sección pareja a este.
2. El Candidato debe visualizar la propuesta con dos botones claros: "Aceptar" o "Proponer otra fecha".
3. Si el Candidato propone otra fecha, el anunciante recibe una contrapropuesta que debe validar.

**Especificación:**
Se podría implementar la creación de archivos .ics para la integración con calendarios externos.

**Riesgos:**
Usuarios que no responden a las propuestas de cita ("Ghosting logístico").

---

### HU-10: Cancelación de Citas
**Historia de Usuario:** Como Usuario con una cita programada quiero poder cancelarla en caso de improviso para avisar automáticamente a la otra parte.

**Criterios de aceptación:**
1. Ambas partes deben tener un botón de "Cancelar Cita" dentro del apartado de citas.
2. Al cancelar, el sistema debe enviar una notificación push inmediata a la otra parte.
3. Se debe solicitar un motivo breve de cancelación (opcional) para informar al otro usuario.

**Especificación:**
Uso de Firebase Cloud Messaging (FCM) para asegurar que la alerta llegue aunque la app esté en segundo plano.

**Riesgos:**
Cancelaciones de último minuto recurrentes.

---

### HU-11: Cierre de Chats
**Historia de Usuario:** Como Usuario quiero que el chat se cierre o archive si la vivienda asociada ya no está disponible o decido terminar la conversación para mantener unos chats limpios e funcionales.

**Criterios de aceptación:**
1. El usuario debe poder archivar un chat manualmente (ocultarlo de la vista principal).
2. Si el inmueble cambia su estado a "Alquilado" o "Pausado", el chat debe bloquearse para nuevos mensajes automáticamente.
3. Debe aparecer un aviso informativo dentro del chat: "Esta vivienda ya no está disponible".

**Especificación:**
Los chats no se borran de la base de datos por temas legales|seguridad, solo se cambia su estado a archived: true.

**Riesgos:**
Usuarios que quieren recuperar información de un chat cerrado e no encuentran la conversación.

---

## CU-04: Gestión de notificaciones

### HU-43: Notificaciones Automáticas
**Historia de Usuario:** Como usuario, quiero recibir notificaciones automáticas cuando ocurra un match o reciba un mensaje, para estar informado de interacciones importantes en la plataforma.

**Criterios de aceptación:**
1. Se genera una notificación automáticamente al producirse un evento relevante.
2. La notificación se almacena con su información obligatoria.
3. La notificación aparece como no leída.

**Especificación:**
El sistema detecta eventos relevantes e crea un registro en la entidad Notificación, incluyendo tipo, fecha, origen, descripción e enlace directo.

**Riesgos:**
Generación duplicada de notificaciones. Retrasos en la entrega de notificaciones. Problemas de sincronización en tiempo real.

---

### HU-44: Visualización Cronológica
**Historia de Usuario:** Como usuario, quiero acceder a una sección donde pueda visualizar todas mis notificaciones en orden cronológico, para consultarlas fácilmente.

**Criterios de aceptación:**
1. Existe una pantalla de notificaciones.
2. Se muestran en orden descendente.
3. Solo se muestran las notificaciones del usuario autenticado.

**Especificación:**
El sistema debe listar las notificaciones almacenadas en la base de datos ordenadas por fecha descendente.

**Riesgos:**
Carga lenta con muchas notificaciones.

---

### HU-45: Indicador de Pendientes
**Historia de Usuario:** Como usuario, quiero ver un indicador visual cuando tenga nuevas notificaciones, para saber que existen eventos pendientes.

**Criterios de aceptación:**
1. Se muestra un icono cuando hay notificaciones no leídas.
2. El indicador desaparece cuando todas están marcadas como leídas.

**Especificación:**
El sistema cuenta las notificaciones no leídas e muestra un indicador visual en la interfaz.

**Riesgos:**
Actualización en tiempo real del indicador.

---

### HU-46: Navegación desde Notificación
**Historia de Usuario:** Como usuario, quiero ser redirigido a la pantalla relacionada al pulsar una notificación, para acceder rápidamente al contenido.

**Criterios de aceptación:**
1. Al hacer clic se abre la pantalla correspondiente.
2. El enlace funciona correctamente.

**Especificación:**
Cada notificación incluye un enlace directo al recurso relacionado.

**Riesgos:**
Errores de navegación. Cambios de rutas.

---

### HU-47: Gestión de Estado de Lectura
**Historia de Usuario:** Como usuario, quiero que las notificaciones se marquen como leídas al abrirlas e poder marcarlas todas como leídas, para gestionar mejor mis avisos.

**Criterios de aceptación:**
1. Una notificación cambia a estado leída al abrirse.
2. Existe una opción para marcar todas como leídas.

**Especificación:**
El sistema actualiza el campo booleano “Leído” en la entidad Notificación.

**Riesgos:**
Errores en la actualización masiva.

---

## CU-05: Sistema de favoritos

### HU-48: Marcar como Favorito
**Historia de Usuario:** Como buscador, quiero poder marcar una vivienda como favorita, para revisarla más tarde.

**Criterios de aceptación:**
1. Se puede guardar desde tarjeta o detalle.
2. El sistema almacena la relación usuario-vivienda.

**Especificación:**
Se crea un registro en la entidad Elemento Guardado.

**Riesgos:**
Duplicación de favoritos. Problemas de sincronización. Accesibilidad a este botón.

---

### HU-49: Listado de Favoritos
**Historia de Usuario:** Como buscador, quiero ver un listado de mis favoritos, para acceder fácilmente a ellos.

**Criterios de aceptación:**
1. Existe una sección de favoritos.
2. Se muestran todos los elementos guardados disponibles.

**Especificación:**
El sistema consulta la entidad Elemento Guardado filtrada por usuario.

**Riesgos:**
Rendimiento en listados grandes.

---

### HU-50: Control de Disponibilidad en Favoritos
**Historia de Usuario:** Como buscador, quiero ver si una vivienda favorita ya no está disponible, para evitar intentar acceder a un anuncio cerrado.

**Criterios de aceptación:**
1. Se muestra un aviso si la vivienda está cerrada.
2. No permite acceder al detalle.

**Especificación:**
El sistema valida el estado de la vivienda antes de permitir acceso.

**Riesgos:**
Información desactualizada.

---

## CU-06: Gestión de inmuebles

### HU-51: Registro de Inmueble
**Historia de Usuario:** Como anunciante, quiero registrar un inmueble mediante un formulario guiado para poder publicarlo en la plataforma.

**Criterios de aceptación:**
1. El sistema permite introducir ubicación, precio e descripción.
2. El usuario puede subir fotografías.
3. El usuario puede definir reglas de convivencia.
4. El sistema guarda correctamente la información.

**Especificación:**
El sistema presenta un formulario paso a paso que almacena los datos en las entidades Vivienda, FotosViviendas e ReglasVivienda.

**Riesgos:**
Errores en la carga de imágenes. Datos incompletos o inválidos. Elementos duplicados.

---

### HU-53: Control de Disponibilidad
**Historia de Usuario:** Como anunciante, quiero cambiar el estado de mi anuncio para controlar su disponibilidad.

**Criterios de aceptación:**
1. El sistema permite activar, pausar o cerrar el anuncio.
2. El cambio se guarda inmediatamente.
3. El estado se refleja en la visibilidad del inmueble.

**Especificación:**
El sistema actualiza el atributo Estado de la entidad Vivienda e modifica la disponibilidad del anuncio en el deck de buscadores.

**Riesgos:**
Estados inconsistentes. Desincronización con el sistema de visibilidad.

---

### HU-54: Previsualización de Anuncio
**Historia de Usuario:** Como anunciante, quiero previsualizar mi anuncio antes de publicarlo para verificar su contenido e apariencia.

**Criterios de aceptación:**
1. Se muestra una vista previa completa.
2. El anuncio aún no es visible para buscadores.
3. Se reflejan correctamente fotos, datos e reglas.

**Especificación:**
El sistema renderiza una vista simulada del deck utilizando la información almacenada del inmueble.

**Riesgos:**
Diferencias entre vista previa e publicación real. Problemas de renderizado de imágenes.

---

### HU-55: Eliminación Protegida
**Historia de Usuario:** Como anunciante, quiero eliminar un anuncio solo si no existen inquilinos activos para evitar inconsistencias en el sistema.

**Criterios de aceptación:**
1. El sistema verifica si existen miembros asociados.
2. Si hay inquilinos activos, se bloquea la eliminación.
3. Se solicita confirmación antes del borrado.

**Especificación:**
El sistema consulta la entidad MiembrosViviendas para validar si existen usuarios vinculados antes de permitir la eliminación.

**Riesgos:**
Eliminación accidental de datos. Inconsistencias en relaciones entre entidades.

---

### HU-56: Visualización de Convivientes
**Historia de Usuario:** Como usuario buscador, quiero ver quiénes viven actualmente en un inmueble para evaluar la compatibilidad antes de solicitar unirse.

**Criterios de aceptación:**
1. Se muestra un listado de miembros del piso.
2. Se indica el rol de cada miembro.
3. Se muestra la fecha de ingreso.
4. Solo se muestra información permitida según privacidad.

**Especificación:**
El sistema consulta la entidad MiembrosViviendas e presenta los datos asociados al inmueble seleccionado.

**Riesgos:**
Problemas de privacidad. Información desactualizada. Exposición de datos sensibles.

---

### HU-65: Edición de Información
**Historia de Usuario:** Como anunciante quiero modificar la información de mi anuncio para mantenerlo actualizado.

**Criterios de aceptación:**
1. El sistema permite editar la información del anuncio.
2. Los cambios se guardan correctamente.
3. El sistema muestra mensaje de confirmación.
4. Se actualiza la fecha de "última modificación".
5. Si el anuncio tiene matches activos, se notifica el cambio relevante (ej. cambio de precio).

**Especificación:**
Formulario con los datos preestablecidos del anuncio.

**Riesgos:**
No identificados.

---

### HU-66: Pausa de Anuncio
**Historia de Usuario:** Como anunciante quiero pausar temporalmente mi anuncio para no recibir más solicitudes mientras gestiono candidatos.

**Criterios de aceptación:**
1. El anuncio deja de aparecer en búsquedas.
2. Se conservan los matches existentes.
3. Puede reactivarse en cualquier momento.

**Especificación:**
Botón de desactivación del anuncio.

**Riesgos:**
No identificados.

---

### HU-67: Reactivación de Anuncio
**Historia de Usuario:** Como anunciante quiero reactivar mi anuncio para volver a recibir solicitudes.

**Criterios de aceptación:**
1. El anuncio vuelve a aparecer en búsquedas si cumple filtros.
2. Se actualiza timestamp.

**Especificación:**
Botón de activación del anuncio.

**Riesgos:**
No identificados.

---

## CU-07: Gestión de cuentas y perfil
### HU-57: Registro de Usuario
**Historia de Usuario:** Como nuevo usuario, quiero registrarme con email e contraseña para crear una cuenta.

**Criterios de aceptación:**
1. Usuario creado e email verificado.

**Especificación:**
Pantalla Registro: campos email, contraseña, Confirmar contraseña, checkbox T&C + link a política. Rate-limit por IP e email. Password: solo hash. Almacenar consentimiento e fecha creación.

**Riesgos:**
Spam|registros masivos. Fuga de credenciales. Cumplimiento RGPD.

---

### HU-58: Inicio de Sesión Social
**Historia de Usuario:** Como usuario, quiero iniciar sesión con proveedores para evitar crear credenciales nuevas.

**Criterios de aceptación:**
1. El usuario puede loguearse con Google, Apple e Facebook.

**Especificación:**
Botones en pantalla de login e registro. Pantalla intermedia para unir cuentas si ya existe correo asociado. Registrar solo datos mínimos del provider.

**Riesgos:**
Cuenta de proveedor comprometida. Privacidad: registro de datos mínimos.

---

### HU-59: Recuperación de Acceso
**Historia de Usuario:** Como usuario, quiero recuperar acceso si olvido la contraseña.

**Criterios de aceptación:**
1. Se modifica la contraseña del usuario.

**Especificación:**
Pantalla “Olvidé mi contraseña”. Email con link e CTA. Post-cambio: notificación e opción de cerrar sesiones. Rate-limit e no revelar existencia de email.

**Riesgos:**
No identificados.

---

### HU-60: Autenticación en Dos Pasos (2FA)
**Historia de Usuario:** Como usuario, quiero activar la autenticación en dos pasos para evitar robos de cuentas.

**Criterios de aceptación:**
1. Usuario puede activar 2FA por app (TOTP).
2. Al activar, se generan 10 códigos de recuperación de un solo uso.

**Especificación:**
Pantalla Seguridad con toggle Activar 2FA. Flujo guiado con QR e códigos de backup. Capacidad de desactivar.

**Riesgos:**
Pérdida de acceso si pierden dispositivo e códigos; soporte verificado.

---

### HU-61: Completar Perfil
**Historia de Usuario:** Como usuario, quiero completar mi perfil con foto, nombre, edad, género, teléfono estudio|trabajo, descripción, hábitos e estilo de vida.

**Criterios de aceptación:**
1. El perfil se ha actualizado de forma exitosa.

**Especificación:**
Onboarding guiado “Completa tu perfil” con pasos: fotos, datos personales, preferencias convivencia.

**Riesgos:**
Perfiles falsos | bots. Discriminación: evitar preguntas sobre raza|religión.

---

### HU-62: Reporte de Usuarios
**Historia de Usuario:** Como usuario, quiero reportar perfiles por fraude o comportamiento para que soporte investigue.

**Criterios de aceptación:**
1. Formulario de reporte accesible desde perfil e chat con categorías (Fraude, Abuso, Spam, etc.).
2. Permitir adjuntar evidencia (JPG|PNG|PDF).

**Especificación:**
Modal|form con campos: tipo, descripción libre, adjuntos. Panel en Admin con filtros e evidencia.

**Riesgos:**
Abuso de reportes maliciosos. Carga operativa para soporte. Privacidad de terceros.

---

### HU-63: Moderación Administrativa
**Historia de Usuario:** Como admin, quiero suspender o bloquear cuentas tras revisión.

**Criterios de aceptación:**
1. Admin puede suspender temporalmente o banear permanentemente tras registrar motivo e evidencia.
2. Sistema guarda razón, admin id e duración.
3. Usuario recibe notificación por email con motivo.

**Especificación:**
Panel con búsqueda por user_id|email, historial, botón Suspend|Ban. Opción reversible.

**Riesgos:**
Suspensiones erróneas; procesos con revisión humana.

---

### HU-64: Verificación de Identidad
**Historia de Usuario:** Como usuario, quiero verificar mi identidad para aumentar mi credibilidad.

**Criterios de aceptación:**
1. Delegar verificación a un proveedor.
2. Si es exitosa, obtiene badge Verificado.
3. Firma consentimiento explícito previo.

**Especificación:**
Mensaje previa aceptación del consentimiento.

**Riesgos:**
Falsos positivos|negativos del proveedor externo.

---

## CU-08: Filtros avanzados para arrendador
### HU-52: Definición de Perfil Ideal
**Historia de Usuario:** Como anunciante, quiero definir las características del compañero ideal para mejorar la compatibilidad en el algoritmo de afinidad.

**Criterios de aceptación:**
1. El sistema permite introducir preferencias.
2. Los datos quedan almacenados correctamente.
3. Se vinculan al inmueble correspondiente.

**Especificación:**
El sistema permite parametrizar características del perfil buscado mediante un formulario específico vinculado al anuncio.

**Riesgos:**
Configuración incorrecta de preferencias. Datos incompletos que afecten al algoritmo.

---

## CU-09: Gestión de facturas y pagos
### HU-12: Registro de Facturas
**Historia de Usuario:** Como Casero, quiero registrar una factura de suministro o renta desde la app, adjuntando el documento original, para notificar automáticamente el cobro a los inquilinos del piso.

**Criterios de aceptación:**
1. Formulario incluye campos obligatorios: concepto, importe, fecha de vencimiento e periodo.
2. Adjuntar PDF o imagen máx. 5 MB.
3. Previsualización del archivo antes de guardar.
4. Validación en línea de campos obligatorios e mensajes de error descriptivos.
5. Confirmación con resumen del gasto registrado.

**Especificación:**
Input: Datepicker nativo. Archivo: Validación MIME en cliente|servidor. Backend: Endpoint POST |api|gastos con validación de esquema. Permisos: Rol Casero e vivienda activa.

**Riesgos:**
Archivos corruptos o virus. Pérdida de datos si la app se cierra durante la carga.

---

### HU-13: Selección de Participantes e Reparto
**Historia de Usuario:** Como Casero, quiero seleccionar qué inquilinos participan en un gasto e elegir el modo de reparto para que cada uno pague lo que le corresponde.

**Criterios de aceptación:**
1. Lista de inquilinos muestra avatar, nombre e checkbox.
2. Al desmarcar un inquilino, la cuota del resto se recalcula instantáneamente sin recarga.
3. Modos de reparto: partes iguales, porcentaje personalizado, importe fijo.
4. Validar suma de % (100%) o que la suma de importes coincida con el total.
5. Gestión de discrepancia por redondeo asignada al último participante.

**Especificación:**
Frontend: Estado reactivo. Cálculo: Math.round a 2 decimales. UI: Componente ToggleGroup para modos de reparto.

**Riesgos:**
Error de redondeo visual.

---

### HU-14: Dashboard de Cobros (Vista Casero)
**Historia de Usuario:** Como Casero, quiero ver un panel con el estado de cobro de todas mis facturas agrupadas por vivienda, para saber de un vistazo cuánto me deben e quién ha pagado.

**Criterios de aceptación:**
1. Panel muestra lista por vivienda con estados: 'Todo cobrado', 'Cobro parcial', 'Pendiente'.
2. Desglose individual por inquilino (Pagado|Pendiente|Vencido).
3. Resumen financiero mensual: total cobrado vs pendiente.
4. Botón de recordatorio push manual (máximo uno cada 24h por deuda).

**Especificación:**
Backend: Endpoint GET |api|casero|cobros. UI: Tarjetas colapsables con desglose.

**Riesgos:**
Casero envía spam de recordatorios (mitigado con cooldown). Desfase entre pasarela e dashboard.

---

### HU-15: Edición e Anulación de Facturas
**Historia de Usuario:** Como Casero, quiero poder editar o anular una factura que registré por error, para corregir importes o conceptos equivocados.

**Criterios de aceptación:**
1. Permitir editar campos si ningún inquilino ha pagado aún.
2. Si ya existen pagos parciales, solo permitir la anulación completa de la factura.
3. Al anular, generar automáticamente una nota de crédito para los que ya pagaron.
4. Notificar a todos los inquilinos afectados por el cambio o anulación.
5. Mantener registro de versiones en el historial.

**Especificación:**
Backend: PUT |api|gastos con validación de estado de pagos. Auditoría: Tabla de log con versiones anteriores.

**Riesgos:**
Anulación accidental de factura cobrada. Confusión del inquilino ante notificaciones de cambio.

---

### HU-16: Exportación Contable (Casero)
**Historia de Usuario:** Como Casero, quiero exportar un informe mensual de todos los cobros de un piso en PDF para mi contabilidad personal o administración.

**Criterios de aceptación:**
1. Seleccionar vivienda, rango de fechas e formato (PDF|CSV).
2. Documento incluye datos del piso, lista de facturas, desglose e totales recaudados.
3. PDF con encabezado e logo de ROOMA.
4. Descarga rápida (menos de 10 segundos para rangos anuales).

**Especificación:**
Backend: Generación de PDF con librería. Endpoint GET |api|casero|exportar. Límite: Máximo 12 meses por exportación.

**Riesgos:**
Informes muy grandes que tarden en generar (mitigar con generación asíncrona).

---

### HU-17: Dashboard "Mis Pagos" (Inquilino)
**Historia de Usuario:** Como Inquilino, quiero ver un dashboard con todas mis deudas pendientes ordenadas por urgencia e con colores claros, para identificar rápidamente lo que tengo que pagar.

**Criterios de aceptación:**
1. Orden: Vencidas (rojo) > Próximas a vencer ≤ 3 días (amarillo) > Al día (verde).
2. Tarjeta muestra icono de concepto, importe, fecha límite e vivienda.
3. Accesibilidad daltónicos: Iconos diferenciadores (! para vencido, reloj para próximo, check para al día).
4. Total pendiente acumulado destacado en cabecera.
5. Acceso al detalle e factura original pulsando la tarjeta.

**Especificación:**
Lógica: Ordenación por fecha_vencimiento ASC con prioridad de vencidas.

**Riesgos:**
Daltónicos no distinguen colores (mitigado con iconos). Lista larga (mitigar con paginación).

---

### HU-18: Historial de Pagos (Inquilino)
**Historia de Usuario:** Como Inquilino, quiero consultar mi historial de pagos realizados filtrado por mes e concepto para llevar un control de mis gastos.

**Criterios de aceptación:**
1. Pestaña 'Historial' con lista cronológica descendente.
2. Filtros por mes, concepto e vivienda.
3. Detalle muestra importe pagado, fecha e últimos 4 dígitos de la tarjeta.
4. Opción de descargar recibo detallado en PDF.

**Especificación:**
Backend: GET |api|inquilino|pagos. Paginación: 20 elementos con carga infinita.

**Riesgos:**
Historial muy extenso afectando rendimiento (mitigar con paginación e caché).

---

### HU-19: Pago con un Clic
**Historia de Usuario:** Como Inquilino, quiero pagar una deuda pulsando un solo botón e usando mi tarjeta guardada para completar el pago sin salir de la app.

**Criterios de aceptación:**
1. Modal resumen del cargo al pulsar 'Pagar'.
2. Selección de tarjeta predeterminada o añadir nueva.
3. Spinner de carga durante el procesamiento (máximo 5 segundos).
4. Animación de éxito (check) e opción de descargar recibo.
5. Mensajes de error claros e botón de reintento.
6. Bloqueo de botón tras clic para evitar cargos duplicados.

**Especificación:**
API: Stripe Payment Intents con idempotency key. Seguridad: HTTPS|TLS 1.2+, no PAN en backend propio. Webhooks: Stripe webhook para confirmar estado.

**Riesgos:**
Cierre de app durante el pago. Doble cobro por doble clic (mitigado con idempotencia e bloqueo UI).

---

### HU-20: Activación de Auto-Pago
**Historia de Usuario:** Como Inquilino, quiero activar el auto-pago con un interruptor para que las facturas recurrentes se cobren automáticamente de mi tarjeta.

**Criterios de aceptación:**
1. Toggle switch 'Auto-Pago' visible en Métodos de Pago.
2. Popup de confirmación con términos legales explícitos.
3. Selección de tarjeta asociada para los cobros recurrentes.
4. Visualización de la fecha del próximo cargo previsto.
5. Confirmación al desactivar el servicio.
6. Notificación e desactivación automática si el cobro falla.

**Especificación:**
Backend: Stripe Customer con Setup Intent. Cron: Job diario a las 08:00 para procesar deudas. Reintentos: Máximo 3 con backoff exponencial.

**Riesgos:**
Tarjeta caducada sin aviso previo. Cobro en fecha errónea.

---

### HU-21: Gestión de Métodos de Pago
**Historia de Usuario:** Como Inquilino, quiero gestionar mis tarjetas guardadas (añadir, eliminar, establecer predeterminada) para tener control sobre mis métodos de pago.

**Criterios de aceptación:**
1. Lista de tarjetas con máscara (•••• 4242), marca e fecha de caducidad.
2. Badge de 'Predeterminada' para la tarjeta principal.
3. Formulario seguro embebido (Stripe Elements) para añadir nuevas.
4. Bloqueo de eliminación si la tarjeta está asociada a un Auto-Pago activo.
5. Aviso visual si la tarjeta caduca en ≤ 30 días.

**Especificación:**
API: Stripe Setup Intents para tokenizar. Almacenamiento: Solo token + últimos 4 dígitos + caducidad.

**Riesgos:**
Tarjeta eliminada que estaba asociada a auto-pago (mitigado con validación previa).

---

### HU-22: Exportación de Justificantes (Inquilino)
**Historia de Usuario:** Como Inquilino, quiero exportar mi historial de pagos en PDF o CSV para tener un justificante de todos los pagos realizados.

**Criterios de aceptación:**
1. Botón 'Exportar' disponible en pestaña de Historial.
2. Selector de formato: PDF o CSV.
3. Filtros opcionales por rango de fechas e vivienda.
4. Documento incluye nombre, vivienda, lista de pagos e método utilizado.
5. Envío al email si el archivo es demasiado pesado.

**Especificación:**
Backend: Generación con librería. Endpoint GET |api|inquilino|exportar. Límite: Máximo 24 meses por exportación.

**Riesgos:**
Archivo muy grande en CSV (mitigado con límite de rango).

---

### HU-23: Sistema de Alertas de Pago
**Historia de Usuario:** Como Inquilino, quiero recibir notificaciones cuando se registre un nuevo gasto e cuando esté a punto de vencer un pago, para no olvidarme.

**Criterios de aceptación:**
1. Notificación push al registrarse un nuevo gasto asignado.
2. Aviso 3 días antes del vencimiento e el mismo día del vencimiento.
3. Notificación diaria tras vencimiento durante un máximo de 7 días.
4. Centro de notificaciones in-app para revisar todos los avisos.
5. Deep link a la tarjeta de deuda al pulsar la notificación.

**Especificación:**
Backend: Scheduler diario que evalúa fechas a las 09:00. Navegación directa al detalle desde el push.

**Riesgos:**
Exceso de notificaciones (mitigar con configuración en ajustes). Notificación llega tras haber pagado.

---

## CU-10: Gestión de incidencias
### HU-24: Reporte de Avería
**Historia de Usuario:** Como Inquilino, quiero abrir un ticket de incidencia describiendo la avería, seleccionando categoría, zona e urgencia, e adjuntando fotos para que el Casero reciba toda la información necesaria para actuar.

**Criterios de aceptación:**
1. Formulario con título, descripción, categoría e urgencia representada por colores.
2. Selector de zona del piso opcional.
3. Posibilidad de adjuntar hasta 5 fotos con previsualización e opción de eliminación.
4. Compresión automática en el cliente (máximo 2MB por archivo).
5. Confirmación de envío con identificador único (INC-XXXX).
6. Guardado como borrador si la subida de archivos falla.

**Especificación:**
Permisos: Cámara|Storage en runtime. Compresión: Client-side resize (máx 1920px). Backend: POST |api|incidencias con formato multipart|form-data.

**Riesgos:**
Fotos borrosas o oscuras que resulten inutilizables (mitigar con sugerencias visuales en la interfaz).

---

### HU-25: Listado de Incidencias (Inquilino)
**Historia de Usuario:** Como Inquilino, quiero ver un listado de todas mis incidencias con filtros por estado e categoría para hacer seguimiento fácilmente.

**Criterios de aceptación:**
1. Tarjetas visuales con título, categoría, urgencia, fecha, estado e miniatura de la foto.
2. Filtros funcionales: Abiertas|Cerradas, categoría e vivienda (si aplica).
3. Indicador numérico (badge) de tickets abiertos en el menú de navegación.
4. Acceso directo al detalle al pulsar sobre cualquier tarjeta.

**Especificación:**
Backend: GET |api|incidencias con parámetros de filtrado. UI: Uso de FlatList con carga diferida (lazy loading) de imágenes.

**Riesgos:**
Lista vacía sin contexto (mitigar con estados vacíos ilustrados e texto explicativo).

---

### HU-26: Seguimiento por Línea de Tiempo
**Historia de Usuario:** Como Inquilino, quiero ver la línea de tiempo de mi incidencia con fechas e estados para saber en qué punto está la reparación.

**Criterios de aceptación:**
1. Visualización de línea de tiempo vertical con los estados alcanzados resaltados.
2. Registro de fecha e hora exacta en cada cambio de estado.
3. Indicador visual pulsante para destacar el estado actual.
4. Visualización de notas aclaratorias del Casero junto al cambio de estado.
5. Recepción de notificación push inmediata ante cualquier actualización de estado.

**Especificación:**
UI: Componente Stepper vertical personalizado. Backend: Estructura de historial_estados (array de objetos con metadatos).

**Riesgos:**
El Casero no actualiza el estado manualmente (mitigar con recordatorios automáticos tras 48h de inactividad).

---

### HU-27: Validación de Solución
**Historia de Usuario:** Como Inquilino, quiero confirmar o rechazar la solución propuesta por el Casero para cerrar la incidencia o reabrirla si el problema persiste.

**Criterios de aceptación:**
1. Botones de 'Confirmar' e 'Rechazar' visibles únicamente en estado 'Resuelta por Casero'.
2. Al confirmar, paso a estado 'Cerrada' con notificación mutua.
3. Al rechazar, motivo de rechazo obligatorio e regreso a estado 'En Proceso'.
4. Cierre automático por inactividad del sistema tras 72 horas sin respuesta.
5. Notificación push de aviso 24 horas antes del auto-cierre.

**Especificación:**
Timeout: Job programado en servidor para incidencias estancadas > 72h. Lógica de renderizado condicional en frontend.

**Riesgos:**
Inquilino inactivo que no gestiona la resolución (mitigado con la lógica de auto-cierre).

---

### HU-28: Chat Técnico de Incidencia
**Historia de Usuario:** Como Inquilino, quiero enviar mensajes e fotos adicionales en el chat de la incidencia para proporcionar más información al Casero.

**Criterios de aceptación:**
1. Pestaña de chat específica con avatares, registro horario e estado de lectura.
2. Capacidad de enviar tanto texto como imágenes adicionales.
3. Mensajes informativos de sistema (cambios de estado) integrados en la conversación.
4. Actualización de mensajes en tiempo real sin recargar.
5. Notificación push si el usuario recibe un mensaje e la app está en segundo plano.

**Especificación:**
Backend: Implementación mediante WebSockets. Gestión de estados de red para evitar pérdida de mensajes.

**Riesgos:**
Mensajes perdidos o duplicados por inestabilidad en la conexión.

---

### HU-29: Panel Kanban (Vista Casero)
**Historia de Usuario:** Como Casero, quiero ver todas las incidencias de mis viviendas organizadas en columnas Kanban para gestionar las reparaciones de forma visual.

**Criterios de aceptación:**
1. Organización en columnas: 'Nuevas', 'En Proceso', 'Resueltas', 'Cerradas'.
2. Opción de alternar entre vista de tablero e vista de lista tradicional.
3. Priorización visual: Incidencias 'Urgentes' con borde destacado e posición superior.
4. Contadores numéricos de tickets por cada columna.
5. Navegación al detalle de la incidencia al pulsar sobre la tarjeta del tablero.

**Especificación:**
UI: Componente de tablero Kanban reactivo con filtros dinámicos por vivienda.

**Riesgos:**
Acumulación excesiva de tarjetas que dificulte la gestión (mitigar con filtros e ordenación por severidad).

---

### HU-30: Actualización de Estado (Casero)
**Historia de Usuario:** Como Casero, quiero cambiar el estado de una incidencia para que el Inquilino vea el progreso de la reparación.

**Criterios de aceptación:**
1. Selector de estados con validación de transiciones permitidas.
2. Campo opcional para añadir notas explicativas (ej: fecha de visita del técnico).
3. Actualización inmediata e reflejo automático en la línea de tiempo del inquilino.
4. Notificación push automática al inquilino informando del cambio.
5. Restricción lógica para no retroceder estados en la secuencia temporal.

**Especificación:**
Backend: Método PATCH con lógica de validación de transiciones. Push: Payload de FCM detallado.

**Riesgos:**
El Casero olvida actualizar el flujo (mitigar con recordatorios automáticos del sistema).

---

### HU-31: Gestión de Presupuestos
**Historia de Usuario:** Como Casero, quiero adjuntar un presupuesto de reparación a una incidencia para que el Inquilino conozca el coste estimado.

**Criterios de aceptación:**
1. Botón de adjunto visible en fases de proceso o reparación.
2. Soporte para archivos PDF e imágenes (máximo 10 MB) con previsualización.
3. Checkbox para definir si el coste será compartido con los inquilinos.
4. Opción de generar un gasto vinculado automáticamente en el módulo de pagos (CU-09).
5. Notificación informativa al Inquilino sobre el nuevo presupuesto disponible.

**Especificación:**
Backend: Endpoint PATCH para asociación de documentos. Vinculación mediante ID_Factura opcional.

**Riesgos:**
Presupuesto ilegible o incompleto (mitigar con previsualización previa al envío e validación de formato).

---

### HU-32: Historial de Mantenimiento
**Historia de Usuario:** Como Casero, quiero consultar el historial completo de incidencias de una vivienda para documentar el mantenimiento realizado.

**Criterios de aceptación:**
1. Filtros avanzados por categoría, rango de fechas e estado final.
2. Buscador por texto libre que escanee títulos e descripciones.
3. Listado detallado con fechas de apertura|cierre e tiempo total de resolución.
4. Acceso al detalle histórico completo de tickets cerrados.
5. Resumen de indicadores (KPIs) en cabecera: promedio de resolución e categorías frecuentes.

**Especificación:**
Backend: GET con lógica de filtrado complejo. Cálculo dinámico: AVG(fecha_cierre - fecha_apertura) para métricas.

**Riesgos:**
Historial masivo que degrade el rendimiento (mitigar con paginación e optimización de consultas).

---

## CU-11: Reseñas y valoración de convivencia

### HU-33: Valoración de la Estancia (Inquilino)
**Historia de Usuario:** Como Inquilino, quiero recibir un aviso al finalizar mi contrato e poder valorar al Casero con estrellas, etiquetas e un comentario, para que futuros inquilinos conozcan mi experiencia.

**Criterios de aceptación:**
1. Aparición de una tarjeta 'Valora tu experiencia' en el Home al detectar el fin del contrato.
2. Puntuación global obligatoria mediante selector de 1 a 5 estrellas.
3. Puntuación por categorías específicas (Mantenimiento, Comunicación, etc.).
4. Selección de etiquetas (chips) e campo de comentario libre opcional.
5. Visualización de pantalla de confirmación antes del envío definitivo.

**Especificación:**
UI: Star Rating con feedback háptico. Chips: Uso de etiquetas predefinidas. Validación: Mínimo 1 estrella global e 1 etiqueta seleccionada. Backend: POST |api|valoraciones. Estado inicial de la reseña: 'Oculta_Ciego_Mutuo'.

**Riesgos:**
Valoración accidental (mitigado con la confirmación). El usuario ignora la acción (mitigado con el sistema de recordatorios).

---

### HU-34: Sistema de Ciego Mutuo
**Historia de Usuario:** Como Inquilino, quiero que mi reseña permanezca oculta hasta que el Casero también valore, para evitar represalias e garantizar honestidad.

**Criterios de aceptación:**
1. El perfil del valorado muestra la tarjeta con efecto blur e el texto 'Reseña pendiente de reciprocidad'.
2. El autor ve su reseña en estado 'Oculta - esperando a la otra parte' con un icono de candado.
3. Publicación automática e simultánea cuando ambas partes han valorado o al expirar los 30 días.
4. Notificación push a ambos usuarios en el momento de la publicación.
5. Bloqueo de edición o eliminación una vez que la reseña es pública.

**Especificación:**
Frontend: CSS filter: blur(8px) para tarjetas ocultas. Backend: Flag de estado 'Oculta_Ciego_Mutuo' que cambia a 'Publicada'. Job: Scheduler diario que libera reseñas tras 30 días.

**Riesgos:**
Confusión del usuario al no ver su reseña publicada (mitigado con tooltips explicativos).

---

### HU-35: Consulta de Reputación del Casero
**Historia de Usuario:** Como Inquilino, quiero ver la reputación de un Casero en su perfil e tarjetas de pisos durante el swipe para tomar decisiones informadas.

**Criterios de aceptación:**
1. Las tarjetas del deck (swipe) deben mostrar: puntuación media, número de reseñas e las 3 etiquetas más frecuentes.
2. El perfil detallado debe mostrar el desglose por categorías mediante barras de progreso.
3. Visualización de una nube de etiquetas con sus respectivos contadores.
4. Listado de reseñas individuales con fecha, estrellas, comentario e la réplica del casero si existe.
5. Opciones de ordenación por fecha (reciente) o por puntuación.

**Especificación:**
Backend: Endpoint GET |api|usuarios|{id}|reputacion con datos agregados en caché (Redis). UI: Paginación mediante scroll infinito para las reseñas.

**Riesgos:**
Sensación de desconfianza ante perfiles sin reseñas (mitigado con badge informativo de 'Nuevo en ROOMA').

---

### HU-36: Valoración del Inquilino (Casero)
**Historia de Usuario:** Como Casero, quiero valorar a un Inquilino al finalizar su estancia con puntuaciones específicas para ayudar a otros caseros.

**Criterios de aceptación:**
1. Aparición de tarjeta de valoración en el panel del Casero al finalizar la convivencia.
2. Categorías de valoración específicas: Limpieza, Convivencia, Puntualidad en pagos e Respeto de normas.
3. Capacidad de valorar de forma individual a cada uno de los inquilinos vinculados a la vivienda.
4. Aplicación de las mismas reglas de ciego mutuo e anonimato temporal.

**Especificación:**
Backend: Entidad Valoracion con Tipo_Relacion = 'Casero_Valora_Inquilino'. UI: Reutilización del componente de estrellas adaptando las categorías al rol.

**Riesgos:**
Saturación del casero si debe valorar a muchos inquilinos simultáneamente (mitigado con cola secuencial e opción de posponer).

---

### HU-37: Reputación del Candidato
**Historia de Usuario:** Como Casero, quiero ver la reputación de un Inquilino en su solicitud de interés para decidir si acepto su solicitud.

**Criterios de aceptación:**
1. La tarjeta de solicitud en el dashboard debe incluir: puntuación media, número de valoraciones e etiquetas destacadas.
2. Navegación directa al perfil de reputación del inquilino al pulsar sobre su resumen.
3. Mensaje informativo 'Nuevo en ROOMA - sin valoraciones aún' si el usuario no tiene historial.

**Especificación:**
Backend: Uso del mismo endpoint de reputación agregada. UI: Componente de resumen de reputación reutilizable.

**Riesgos:**
Sesgo negativo hacia usuarios nuevos (mitigado con un diseño de badge neutral para perfiles sin historial).

---

### HU-38: Valoración entre Compañeros
**Historia de Usuario:** Como Compañero de piso, quiero valorar a otro compañero con el que he convivido para informar sobre su estilo de convivencia.

**Criterios de aceptación:**
1. Opción habilitada tras la desvinculación o cierre del grupo en la vivienda.
2. Categorías específicas: Ruido, Respeto de espacios comunes e Comunicación.
3. Chips de etiquetas adaptados: 'Silencioso', 'Ordenado', 'Buen ambiente', 'Fiestero'.
4. Aplicación estricta de la regla de ciego mutuo de 30 días.
5. Identificación visual clara en el perfil como 'Valoración de compañero de piso'.

**Especificación:**
Backend: Atributo Tipo_Relacion = 'Compañero_Valora_Compañero'. UI: Adaptación de etiquetas e categorías en el formulario.

**Riesgos:**
Pactos entre compañeros para inflar puntuaciones (mitigado con algoritmos de detección de patrones e moderación).

---

### HU-39: Réplica a Valoraciones
**Historia de Usuario:** Como Usuario valorado, quiero poder escribir una réplica a una reseña que he recibido para dar mi versión de los hechos.

**Criterios de aceptación:**
1. Botón 'Responder' visible debajo de cada reseña publicada (solo si no hay réplica previa).
2. Campo de texto con límite de 300 caracteres e contador en tiempo real.
3. Obligatoriedad de pasar por el filtro de moderación antes de la publicación.
4. Visualización anidada con diseño diferenciado (sangría e color de fondo).
5. Restricción de respuesta única e no editable tras el envío.

**Especificación:**
Backend: PATCH |api|valoraciones|{id}|replica. UI: Diseño de card anidada con indentación visual.

**Riesgos:**
Uso de la réplica para ataques personales u ofensas (mitigado con moderación automática obligatoria).

---

### HU-40: Reporte de Reseñas Inadecuadas
**Historia de Usuario:** Como Usuario, quiero poder reportar una reseña que considero inapropiada para que el equipo de moderación la revise.

**Criterios de aceptación:**
1. Icono de reporte accesible en cada tarjeta de reseña pública.
2. Selector con motivos: Lenguaje ofensivo, Información falsa, Spam o Datos personales.
3. Confirmación de recepción tras el envío del reporte.
4. Ocultación automática de la reseña si acumula 3 o más reportes hasta que un humano la valide.
5. Notificación al reportador una vez se tome una decisión administrativa.

**Especificación:**
Backend: POST |api|valoraciones|{id}|reportes. Umbral de auto-ocultación configurado en 3 reportes.

**Riesgos:**
Reportes falsos masivos para censurar críticas legítimas (mitigado con revisión humana obligatoria tras el reporte).

---

### HU-41: Moderación Automática
**Historia de Usuario:** Como Usuario, quiero que las reseñas pasen por un filtro de moderación automático antes de publicarse para evitar contenido ofensivo.

**Criterios de aceptación:**
1. Procesamiento inmediato tras el envío para detectar insultos, teléfonos, emails o enlaces.
2. Cambio de estado a 'En revisión' si se detecta contenido problemático.
3. Notificación al autor permitiendo la edición e reenvío de la reseña.
4. Descarte automático de la reseña si no se edita en un plazo de 7 días naturales.

**Especificación:**
Backend: Servicio de moderación con Regex e integración con APIs de lenguaje (ej. Perspective API).

**Riesgos:**
Falsos positivos que bloqueen lenguaje natural (mitigado permitiendo la edición manual del usuario).

---

### HU-42: Sistema de Recordatorios e Cierre
**Historia de Usuario:** Como Usuario, quiero recibir recordatorios progresivos para valorar e que el sistema cierre el periodo a los 30 días.

**Criterios de aceptación:**
1. Envío de notificación push e aviso en el Home al finalizar la convivencia.
2. Recordatorio a las 48h si se seleccionó 'Recordarme más tarde'.
3. Recordatorios adicionales a los 7 e 21 días.
4. Cierre forzoso del periodo a los 30 días con publicación unilateral de la otra parte si existe.
5. Opción de silenciar los recordatorios push desde el panel de ajustes.

**Especificación:**
Backend: Scheduler con tabla de control de tiempos. Configuración de notificaciones en el perfil de usuario.

**Riesgos:**
Percepción de spam por parte del usuario (mitigado con la frecuencia decreciente e opción de silenciado).