# ROOMA
# Requisitos de información

## CU-01: Descubrimiento de viviendas
**Actor:** Buscadores
**Objetivo:** Explorar e expresar interés en viviendas compatibles para encontrar un hogar.

**Flujo Principal:**
1. El sistema presenta un deck de tarjetas basado en los filtros activos (precio, zona, reglas).
2. El usuario accede al detalle para ver fotos del inmueble e los perfiles de afinidad de los compañeros actuales (gustos, horarios, profesión).
3. El usuario desliza a la derecha (Like) para mostrar interés o a la izquierda (Dislike) para descartar.
4. (Opcional) El usuario Premium utiliza la función Rewind para recuperar una tarjeta descartada.

**Resultado:** Interés registrado o vivienda descartada.
**Estado:** Completado Parcialmente (Excepto el paso 4).

**Precondiciones:**
* El usuario debe estar registrado e autenticado.
* El usuario debe haber configurado al menos los filtros básicos de búsqueda.
* Deben existir inmuebles activos compatibles con dichos filtros.

**Flujos alternativos:**
* Si no existen viviendas compatibles, el sistema sugiere ampliar filtros.
* Si el usuario pierde la conexión, el sistema guarda el estado del deck para reanudarlo.

**Reglas de negocio:**
* Las viviendas descartadas no se vuelven a mostrar en el deck.
* La función Rewind es exclusiva para usuarios Premium.

---

## CU-02: Evaluación de Candidatos e Match
**Actor:** Anunciante
**Objetivo:** Evaluar a los interesados e filtrar quiénes pueden acceder al contacto directo.

**Flujo Principal:**
1. El sistema notifica al Anunciante que tiene nuevos perfiles interesados (Likes).
2. El Anunciante accede al panel de Gestión de Solicitudes.
3. El Anunciante revisa la ficha técnica del candidato (compatibilidad, verificación, profesión).
4. El Anunciante selecciona una acción: Aceptar (abre chat), En Espera (mueve a reserva) o Rechazar (descarta perfil).

**Resultado:** Match establecido e canal de comunicación habilitado.
**Estado:** Completado Parcialmente (Sin chat activo ni opción de espera).

**Precondiciones:**
* El inmueble debe estar publicado e en estado activo.
* El candidato debe haber dado "Like" previamente.

**Reglas de negocio:**
* El chat solo se habilita cuando la solicitud es aceptada.
* Un candidato rechazado no puede volver a solicitar el mismo inmueble.

---

## CU-03: Chat post Match
**Actor:** Buscadores e Anunciante
**Objetivo:** Coordinar un encuentro o contacto para avanzar en el alquiler.

**Flujo Principal:**
1. Los usuarios con Match acceden a la bandeja de mensajes.
2. Intercambian mensajes de texto, fotos o documentos en tiempo real.
3. Concretan mediante el chat la forma e medio para tener una quedada o visita formal.

**Resultado:** Acuerdo de visita o contacto registrado en el sistema.
**Estado:** Pendiente.

---

## CU-04: Gestión de Notificaciones
**Actor:** Todos los usuarios
**Objetivo:** Informar de eventos clave para no perder interacciones.

**Flujo Principal:**
1. Ocurre un evento relevante (match, mensaje, solicitud aceptada|rechazada).
2. El sistema comprueba preferencias del usuario e genera la notificación.
3. El usuario la abre e el sistema redirige a la pantalla correspondiente, marcándola como leída.

**Resultado:** Usuario informado e notificación registrada (leída).
**Estado:** Completado Parcialmente (Solo existen notificaciones de Likes).

---

## CU-05: Sistema de Favoritos
**Actor:** Buscadores
**Objetivo:** Guardar viviendas de interés para revisarlas más tarde sin perderlas en el deck.

**Flujo Principal:**
1. El usuario marca una vivienda como Favorito desde la tarjeta o el detalle.
2. El sistema lo añade a la lista de favoritos del usuario (Elemento Guardado).
3. El usuario accede a la sección "Favoritos", revisa e decide realizar Like o Dislike.

**Resultado:** Elemento guardado en favoritos e accesible para revisión.
**Estado:** Pendiente.

---

## CU-06: Gestión de Inmuebles
**Actor:** Anunciante
**Objetivo:** Dar de alta, editar e mantener la oferta de viviendas actualizada.

**Flujo Principal:**
1. El Anunciante completa o edita el formulario guiado (ubicación, precio, fotos, reglas).
2. El Anunciante define o actualiza el perfil de compañero ideal para el algoritmo.
3. El sistema valida los datos, guarda los cambios e hace visible el anuncio en el deck.

**Resultado:** Inmueble publicado o actualizado e visible para buscadores.
**Estado:** Completado (Alta) | Pendiente (Edición).

**Reglas de negocio:**
* El borrado de inmuebles está bloqueado si existen procesos de Match activos o inquilinos vinculados.
* Las modificaciones de precio notifican a los usuarios con Match activo.

---

## CU-07: Gestión de Cuentas e Perfil
**Actor:** Todos los usuarios
**Objetivo:** Administrar perfil, preferencias e estado de la cuenta.

**Flujo Principal:**
1. El usuario registra o edita datos personales, laborales e etiquetas de estilo de vida.
2. El usuario configura sus preferencias de búsqueda e notificaciones.
3. El usuario gestiona su suscripción Premium o métodos de acceso (OAuth, 2FA).

**Resultado:** Perfil optimizado e estado de cuenta actualizado.
**Estado:** Pendiente.

---

## CU-08: Filtros Avanzados para Arrendador
**Actor:** Anunciante
**Objetivo:** Definir criterios para priorizar candidatos e facilitar la selección.

**Flujo Principal:**
1. El Anunciante accede a la configuración del inmueble o panel de solicitudes.
2. Define filtros (verificación, rango de edad, ocupación, hábitos).
3. El sistema aplica los filtros e reordena la lista de candidatos mostrados.

**Resultado:** Lista de candidatos filtrada e priorizada según afinidad.
**Estado:** Pendiente.

---

## CU-09: Gestión de Facturas e Pagos
**Actor:** Anunciante (Casero) e Inquilinos
**Objetivo:** Automatizar el reparto e seguimiento de los pagos de suministros e renta.

**Flujo Principal:**
1. El Anunciante carga la factura (importe, concepto e documento adjunto).
2. El sistema asigna e divide el importe automáticamente según la configuración (partes iguales, % o fijo).
3. Los Inquilinos reciben notificación de deuda e proceden al pago desde la app.

**Resultado:** Transparencia financiera e control de cobros realizado.
**Estado:** Completado Parcialmente (Falta pasarela de pago real).

---

## CU-10: Gestión de Incidencias en la Vivienda
**Actor:** Inquilinos e Anunciante
**Objetivo:** Reportar e dar seguimiento a averías de mantenimiento de forma organizada.

**Flujo Principal:**
1. El Inquilino crea un reporte detallando el problema e adjunta evidencia fotográfica.
2. El Anunciante recibe la notificación e actualiza el estado (En proceso, Resuelta).
3. Ambas partes comentan e adjuntan presupuestos hasta que se marca como "Cerrada".

**Resultado:** Historial de mantenimiento documentado e resolución eficiente.
**Estado:** Pendiente.

---

## CU-11: Reseñas e Valoración de Convivencia
**Actor:** Todos los usuarios
**Objetivo:** Generar un sistema de confianza basado en la experiencia real.

**Flujo Principal:**
1. Al finalizar un contrato o convivencia, el sistema habilita la opción de valorar.
2. El usuario califica mediante estrellas e etiquetas predefinidas (limpieza, puntualidad).
3. El sistema aplica la regla de ciego mutuo e publica la valoración tras 30 días o reciprocidad.

**Resultado:** Perfiles con reputación verificada e pública.
**Estado:** Completado Parcialmente (Vista pública no implementada).