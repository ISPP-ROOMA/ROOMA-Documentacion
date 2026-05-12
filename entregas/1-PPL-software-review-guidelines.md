# Software Review Guidelines S3

## 1. Acceso al Sistema y Versiones (Releases)

### 1.1 Enlace de Despliegue
* **Despliegue Final:** https://rooma-sprint-3.vercel.app

### 1.2 Release en GitHub
* **Página de la Release:** https://github.com/ISPP-ROOMA/ROOMA-sprint-3/releases/tag/s3
* **Registro de Cambios:** *Se pueden ver todos los cambios realizados desde la página de la release indicada arriba*

---

## 2. Casos de Uso

### 2.1 Casos de Uso Desarrollados Previamente (S1 y S2 aunque se han realizado extensiónes a estos)

#### CU: Descubrimiento de Viviendas
| Nombre | Descripción | Estado |
| :--- | :--- | :--- |
| Gestión del Deck | El sistema debe generar un mazo dinámico de viviendas basado en los filtros de búsqueda (precio, zonas, reglas) que el usuario indique | Completado Parcialmente (no estan desarrollados los filtros todavía) |
| Visualizar Detalles | El sistema debe permitir abrir una vista expandida de cada vivienda que aparezca en el deck para consultar los detalles de esta, las fotos expandidas, su ubicación, la reglas de la vivienda (si hay alguna) y los inquilinos actuales (si hay alguno), junto con los detalles de estos para así poder evaluar la convivencia. | Completado |
| Swipe | El sistema debe procesar el gesto táctil de swipe a la vivienda que este actualmente al frente del deck (derecha “Like”, izquierda “Dislike”). Además, el gesto de swipe se debe poder realizar con dos botones que indiquen las mismas acciones (“Like” / “Dislike”) | Completado |
| Gestión de Estados | El sistema debe registrar cada interacción del usuario con cada inmueble para asegurar que una vivienda descartada no vuelva a aparecer | Completado |
| Persistencia | El sistema debe guardar la posición actual del deck para cada usuario que este usando la aplicación, para en el caso de pérdida de conexión, que el usuario pueda retomar las acciones desde donde lo dejó y no se recarguen los inmuebles aleatoriamente | Completado |

#### CU: Evaluación de Candidatos y Match
| Nombre | Descripción | Estado |
| :--- | :--- | :--- |
| Gestión de Solicitudes | El sistema debe mostrar para los usuarios anunciantes un dashboard que permita organizar a los candidatos para cada vivienda que tengan anunciada | Completado |
| Visualización Candidato | El sistema debe permitir a los anunciantes acceder a los perfiles detallados de cada interesado por una vivienda que tengan anunciada, donde se puedan ver sus datos públicos (edad, profesión…) | Completado |
| Gestión de Candidatos | El anunciante de una vivienda debe poder modificar el estado de cada candidato para esa misma vivienda, pudiendo seleccionar 2 estados distintos: <br>- Aceptar -> Se abriría el chat bidireccional y el calendario para concertar citas <br>- Rechazar -> Se archivaría la solicitud y el candidato no podría realizar ninguna acción con ese inmueble en específico | Completado |
| Gestión de Estados del Inmueble | El sistema debe gestionar la modificación del estado de una vivienda (Pausado, libre) con sus respectivos candidatos. Si un inmueble pasa a estar Pausado, se cancelarán todas las solicitudes pendientes, o sea, se eliminarán a los candidatos para ese inmueble | Completado |
| Match | El sistema debe permitir dar like o dislikes a las propuestas de apartamentos en casos de ser un usuario que busca piso o a las propuestas de inquilinos si el usuario es casero. El Match además guardará estados para saber si esté está a la espera de una de las partes (Activo), si ambas partes dieron like (Match), si alguna de las partes dio dislike o si durante el proceso posterior por chat una de las partes decide no continuar (Rechazado) o si el match se define como exitoso y se pasa al chat y las citas | Completado |

#### CU: Gestión de Inmuebles
| Nombre | Descripción | Estado |
| :--- | :--- | :--- |
| Formulario de Alta Guiado | El sistema debe permitir al anunciante registrar un inmueble mediante un formulario que capture: ubicación exacta, precio mensual, fotografías, y reglas de convivencia (ej. mascotas, fumadores, etc.). | Completado |
| Consulta de miembros de la vivienda | El sistema debe permitir visualizar los usuarios vinculados a un inmueble, mostrando su rol dentro de la vivienda y la fecha de incorporación, con el fin de proporcionar información sobre la composición actual del piso. | Completado |
| Gestión de anuncios | El sistema debe permitir al anunciante editar toda la información del anuncio mediante formulario guiado ( precio, fotos, reglas, perfil ideal, disponibilidad), validar y persistir cambios | Completado |
| Pausar y reactivar anuncio | El sistema debe permitir pausar temporalmente un anuncio para que deje de aparecer en búsquedas y en el deck mientras conserva matches y solicitudes existentes; mostrar el estado “Pausado” en el panel del anunciante; impedir nuevas solicitudes durante la pausa; y permitir reactivar el anuncio en cualquier momento y actualizando timestamp. Al reactivar, ofrecer opción de notificar candidatos en espera. | Completado |

#### CU: Gestión de Facturas y Pagos (simulado)
| Nombre | Descripción | Estado |
| :--- | :--- | :--- |
| Pantalla de Registro de Gastos | El sistema debe disponer de una interfaz de formulario para el Casero que incluya: selector de fecha tipo calendario (datepicker nativo), campos numéricos para importes con formato monetario (€), un desplegable de conceptos predefinidos (Alquiler, Luz, Agua, Gas, Internet, Comunidad, Otro), un campo de texto libre para descripción adicional, y un área de carga (drag & drop o botón de selección) para adjuntar el documento de la factura (PDF o imagen). El archivo adjunto debe mostrarse en previsualización antes de confirmar el guardado. El formulario debe incluir validación en línea de campos obligatorios con mensajes de error descriptivos. | Completado |
| Selector Visual de Inquilinos y Modo de Reparto | El sistema debe mostrar, dentro de la pantalla de registro de gasto, una lista interactiva de todos los inquilinos actualmente vinculados al inmueble. Cada inquilino se representará mediante una tarjeta compacta con su avatar, nombre y un checkbox para incluirlo o excluirlo del reparto. Adicionalmente, el sistema debe ofrecer un selector de modo de reparto con las opciones: (a) Partes iguales — divide el total equitativamente; (b) Porcentaje personalizado — permite asignar un % a cada inquilino seleccionado; (c) Importe fijo por persona — permite escribir una cantidad concreta para cada uno. Si el Casero también participa en el gasto, debe poder incluirse a sí mismo en la lista. | Completado |
| Visualización de Cuotas en Tiempo Real | El sistema debe recalcular y actualizar dinámicamente en pantalla el importe que le corresponde a cada inquilino seleccionado cada vez que el Casero modifique el importe total, cambie el modo de reparto o marque/desmarque participantes, sin necesidad de recargar la página. Debe mostrarse una fila resumen con la suma de cuotas individuales para verificar que coincide con el total. Si hay discrepancia por redondeo (céntimos), el sistema la asignará al último participante de la lista y mostrará un aviso informativo. El Casero podrá ajustar manualmente la cuota de cualquier inquilino; al hacerlo, el sistema redistribuirá el remanente entre los demás de forma proporcional. | Completado |
| Dashboard de "Mis Pagos" (Vista Inquilino) | El sistema debe presentar al Inquilino una pantalla dedicada a sus finanzas con dos pestañas: (a) Pendientes — lista de deudas activas ordenadas por urgencia (vencidas primero, luego próximas a vencer) mediante tarjetas visuales que muestren concepto (icono + texto), importe, fecha límite y un indicador semáforo (Rojo = Vencido, Amarillo = Próximo a vencer en ≤ 3 días, Verde = Al día); (b) Historial — lista cronológica descendente de todos los pagos realizados, filtrable por mes, concepto y vivienda. En la cabecera de la pantalla se mostrará un resumen con el total pendiente acumulado. | Completado |
| Indicadores de Estado de Pago | Indicadores de Estado de Pago,"El sistema debe reflejar visualmente el estado de cada deuda en las listas de ambos usuarios (Casero e Inquilino) mediante etiquetas (badges) con los estados: 'Pendiente' (gris), 'Vencido' (rojo), 'Procesando' (amarillo/naranja pulsante), 'Pagado' (verde) y 'Rechazado' (rojo oscuro). Además, para garantizar accesibilidad a personas con daltonismo, cada badge incluirá un icono diferenciador (reloj, exclamación, spinner, check, cruz). | Completado |
| Dashboard de Cobros (Vista Casero) | El sistema debe proporcionar al Casero una pantalla de seguimiento de cobros por vivienda que muestre: (a) una lista de todas las facturas emitidas con su estado global (Cobrado totalmente, Cobro parcial, Pendiente); (b) al pulsar sobre una factura, un desglose por inquilino con el estado individual de cada cuota (Pagado/Pendiente/Vencido); (c) un resumen financiero mensual con totales cobrados vs. pendientes, representado mediante un gráfico de barras o donut chart; (d) la posibilidad de enviar un recordatorio push manual a los inquilinos con pagos vencidos. | Completado |
| Notificaciones de Pagos | El sistema debe enviar notificaciones push automáticas en los siguientes eventos: (a) nueva factura registrada — a todos los inquilinos participantes; (b) pago recibido — al Casero, indicando quién pagó y el importe; (c) recordatorio de vencimiento — al Inquilino, 3 días antes y el mismo día del vencimiento; (d) pago vencido — al Inquilino diariamente tras el vencimiento y al Casero una vez; (e) auto-pago ejecutado — al Inquilino confirmando el cargo. Todas las notificaciones deben ser también visibles en un centro de notificaciones in-app. | Completado |

#### CU: Reseñas y Valoración de Convivencia
| Nombre | Descripción | Estado |
| :--- | :--- | :--- |
| Tarjeta de Valoración Pendiente | El sistema debe hacer aparecer una tarjeta de llamada a la acción ('Valora tu experiencia') en la pantalla principal (Home) del usuario una vez que se detecte la finalización del contrato o que el Casero marque el fin de la convivencia. La tarjeta debe incluir: (a) foto y nombre de la persona/vivienda a valorar; (b) un botón 'Valorar ahora'; (c) un enlace 'Recordarme más tarde' que pospone la tarjeta 48 horas. Si el usuario ignora la tarjeta, se mostrarán recordatorios progresivos durante 30 días naturales, tras los cuales el sistema cierra el periodo de valoración sin reseña. | Completado |
| Interfaz de Estrellas y Etiquetas | El sistema debe presentar un formulario de reseña compuesto por: (a) una puntuación global mediante un componente de 5 estrellas interactivas (obligatorio, mínimo 1 estrella); (b) puntuaciones por categorías específicas (también 1-5 estrellas): para valorar a Inquilinos (Limpieza, Convivencia, Puntualidad en pagos, Respeto de normas, Comunicación), para valorar a Caseros (Mantenimiento, Comunicación, Resolución de incidencias, Honestidad, Relación calidad-precio); (c) una nube de etiquetas pulsables (chips) positivas y negativas preconfiguradas (ej: 'Silencioso', 'Fiestero', 'Ordenado', 'Puntual', 'Respetuoso', 'Ruidoso', 'Impuntual'); (d) un campo de texto libre opcional (máx. 500 caracteres) para escribir un comentario personal. | Completado |
| Sistema de Ciego Mutuo | El sistema debe implementar un mecanismo de 'Ciego Mutuo' para la publicación de reseñas: ambas partes (Inquilino y Casero) podrán enviar su valoración de forma independiente, pero ninguna de las dos será visible hasta que ambas hayan sido enviadas (o hasta que expire el plazo de 30 días). Mientras la reseña esté oculta, el perfil público del valorado mostrará una tarjeta con efecto blur/desenfocado con el texto 'Reseña pendiente de reciprocidad'. Una vez ambas partes hayan valorado o el plazo haya expirado, las reseñas se harán visibles simultáneamente. | Completado |
| Hilo de Réplica | El sistema debe permitir al usuario valorado escribir una respuesta única a cada reseña recibida. La réplica (máx. 300 caracteres) se mostrará anidada visualmente debajo de la reseña original en el perfil público, con fondo de color diferenciado e indicación de 'Respuesta del propietario/inquilino'. Solo se permite una réplica por reseña, no editable una vez publicada. | Completado |
| Resumen de Reputación en Tarjetas de Swipe/Solicitud | El sistema debe mostrar un resumen compacto de la reputación del usuario (puntuación media + nº de reseñas + 3 etiquetas más frecuentes) en: (a) las tarjetas de pisos durante el swipe (reputación del Casero); (b) las tarjetas de solicitudes que ve el Casero (reputación del Inquilino); (c) las tarjetas de búsqueda de compañeros. Al pulsar sobre el resumen se navega al perfil completo de reseñas. | Completado |
| Recordatorios de Valoración | El sistema debe enviar notificaciones push de recordatorio para valorar en los siguientes momentos: (a) al detectar fin de contrato o desvinculación; (b) a las 48h si se pospuso; (c) a los 7 días si no se ha valorado; (d) a los 21 días como último aviso. Tras 30 días sin acción, el periodo se cierra y se publica la reseña de la otra parte (si existe) unilateralmente. | Completado |

#### CU: Chat post Match
| Nombre | Descripción | Estado |
| :--- | :--- | :--- |
| Gestión de Chats entre Usuarios | El sistema deberá habilitar un chat activo para cada par de usuarios (inquilino/arrendatario) que tengan un Match confirmado. Esta sección será habilitada tanto en la interfaz de usuario como en la lógica de negocio y debe ser imposible acceder sin Match | Completado |
| Mensajería Multimedia en Tiempo Real | El sistema debe permitir el envío y recepción instantánea de mensajes de texto, imágenes y documentos como parte del chat ya abierto entre dos usuarios. | Completado |
| Indicadores de Estado | El sistema debe guardar y mostrar el estado de los mensajes dentro de un chat (Entregado / Leído) y este se debe mostrar en los mensajes de un usuario hacia el otro que forme parte del chat | Completado |
| Gestión de Citas | El sistema debe permitir al anunciante proponer una fecha y hora para concertar una cita (normalmente sería una visita para ver el inmueble o concertar ciertos aspectos sobre el alquiler) y al usuario inquilino aceptarla o proponer una fecha alternativa | Completado |
| Cancelación de Citas | El sistema debe permitir al anunciante o inquilino cancelar una cita programada con antelación, enviando una notificación l usuario que formara parte de la cita | Completado |

#### CU: Sistema de Favoritos
| Nombre | Descripción | Prioridad |
| :--- | :--- | :--- |
| Gestión de Favoritos | El sistema debe permitir al usuario marcar o desmarcar una vivienda/perfil como "Favorito" desde la tarjeta, el detalle o directamente desde el listado de favoritos. | Completado |
| Visualización del Listado de favoritos | El sistema debe ofrecer una sección específica donde el usuario pueda revisar todos los elementos guardados y acceder a su detalle. | Completado |
| Control de Disponibilidad en Favoritos | El sistema debe detectar si una vivienda ya no está disponible (por haberse completado el grupo) y mostrar un aviso informativo en el listado indicando que no se puede acceder al detalle por este motivo. | Completado |

#### CU: Gestión de Cuentas y Perfil
| Nombre | Descripción | Estado |
| :--- | :--- | :--- |
| Registro con email y contraseña | El sistema debe ofrecer un formulario de registro (email, contraseña, confirmar contraseña), validar formato de email (regex) y unicidad, validar la política de contraseña configurable (mín. 4 caracteres u equivalente), comprobar coincidencia de contraseña/confirmar. | Completado |
| Inicio de sesión con proveedores | El sistema debe permitir autenticación mediante Google, solicitar y guardar consentimiento para leer email y perfil básico; si el proveedor devuelve un email verificado que coincide con una cuenta existente, ofrecer la opción de vincular la credencial o iniciar sesión; si el proveedor no devuelve email o no está verificado, guiar al usuario para introducir y verificar un email (mismo flujo de token).| Completado |
| Completar y editar perfil | El sistema debe permitir completar/editar: fotos de perfil, nombre, fecha de nacimiento (validar y calcular edad), género, teléfono, estudio/trabajo, descripción libre y preguntas de convivencia con opciones predefinidas (ej. Fumar: Sí/No/Ocasional). | Completado |

#### CU: Gestión de Incidencias en la Vivienda
| Nombre | Descripción | Estado |
| :--- | :--- | :--- |
| Formulario de Nueva Incidencia | El sistema debe ofrecer al Inquilino una pantalla de creación de tickets que incluya: (a) un campo de título obligatorio (máx. 100 caracteres); (b) un campo de descripción multilínea (máx. 1000 caracteres); (c) un selector desplegable de categoría (Fontanería, Electricidad, Electrodomésticos, Cerrajería, Pintura/Paredes, Climatización, Plagas, Otro); (d) un selector de urgencia (Baja, Media, Alta, Urgente) representado con código de color; (e) acceso a la cámara del dispositivo para tomar fotos directamente o seleccionarlas de la galería, con previsualización y opción de eliminar antes de enviar (máx. 5 fotos); (f) un selector de zona del piso (Cocina, Baño, Salón, Dormitorio, Zonas comunes, Exterior). | Completado |
| Línea de Tiempo de Estado | El sistema debe mostrar en la vista de detalle de cada incidencia una barra de progreso o línea de tiempo (timeline) vertical que indique visualmente en qué fase se encuentra la reparación, con los estados: 'Abierta' (gris) → 'Recibida por el casero' (azul) → 'En Proceso' (amarillo) → 'Técnico Avisado' (naranja, opcional) → 'Resuelta por Casero' (verde claro) → 'Cerrada' (verde). Cada paso debe mostrar la fecha y hora en que se alcanzó. El Casero puede avanzar el estado; el Inquilino solo puede cerrar la incidencia tras la resolución. | Completado |
| Pestaña de Chat Técnico | El sistema debe incorporar dentro del detalle de cada incidencia una pestaña o sección de conversación dedicada, separada del chat general de convivencia. Esta conversación debe permitir: (a) enviar mensajes de texto; (b) adjuntar fotos adicionales (por ejemplo, progreso de la reparación); (c) mostrar los mensajes con avatar, nombre, hora y estado de lectura (doble check). Solo participan en esta conversación el Inquilino que abrió el ticket y el Casero/Anunciante de la vivienda. | Completado |
| Botonera de Validación del Inquilino | El sistema debe mostrar al Inquilino que reportó la incidencia dos botones de acción claros ('Confirmar Solución' / 'Rechazar Solución') únicamente cuando la incidencia alcance el estado 'Resuelta por Casero'. Al confirmar, la incidencia pasa a 'Cerrada'. Al rechazar, vuelve a 'En Proceso' y se notifica al Casero con un campo obligatorio de motivo del rechazo. | Completado |
| Listado de Incidencias (Vista Inquilino) | El sistema debe presentar al Inquilino una pantalla con la lista de todas las incidencias reportadas en sus viviendas, filtrables por: estado (Abiertas / Cerradas), categoría y vivienda. Cada elemento de la lista mostrará: título, categoría (badge de color), urgencia (badge), fecha de apertura, estado actual y miniatura de la primera foto adjunta. Al pulsar sobre una incidencia se accede a la vista de detalle. | Completado |
| Panel de Incidencias (Vista Casero) | El sistema debe proporcionar al Casero un panel con todas las incidencias recibidas en sus viviendas, organizadas por defecto en columnas tipo Kanban: 'Nuevas', 'En Proceso', 'Resueltas', 'Cerradas'. El Casero podrá alternar esta vista a formato lista. Cada tarjeta mostrará título, urgencia (color), inquilino reportador (avatar + nombre), fecha y miniatura de foto. El Casero puede pulsar sobre una tarjeta para acceder al detalle, cambiar el estado o responder en el chat técnico. | Completado |
| Historial de Incidencias por Vivienda | El sistema debe mantener un historial completo de todas las incidencias (abiertas y cerradas) asociadas a cada vivienda, accesible tanto para el Casero como para los Inquilinos actuales. El historial debe ser buscable por texto libre y filtrable por categoría, fecha y estado, y servirá como documentación de mantenimiento del inmueble. | Completado |
| Adjuntar Presupuesto de Reparación | El sistema debe permitir al Casero adjuntar un documento (PDF/imagen, máx. 10 MB) con el presupuesto de reparación dentro de la vista de detalle de la incidencia. El Inquilino podrá visualizar dicho documento. Opcionalmente, el Casero puede indicar si el coste será compartido con los inquilinos, en cuyo caso el sistema ofrecerá la opción de generar un gasto en el CU-10 vinculado a la incidencia. | Completado |

### 2.1 Nuevos Casos de Uso (Entregable S3)

*(Estos son los casos de uso desarrollados desde 0 en este sprint, los anteriores casos de uso fueron desarrollados en gran parte en los anteriores pero han sido mejorados)*

#### CU: Gestión de notificaciones
| Nombre | Descripción | Estado |
| :--- | :--- | :--- |
| Generación de notificaciones por eventos | El sistema debe generar automáticamente una notificación cuando ocurra un match o se reciba un mensaje. | Completado |
| Visualización de Listado | El sistema debe permitir al usuario acceder a una pantalla o sección de "Notificaciones" donde se listen cronológicamente las notificaciones recibidas. | Completado |
| Indicador de nuevas notificaciones | El sistema debe mostrar un indicador visual en la interfaz cuando existan notificaciones nuevas. | Completado |
| Navegación Directa desde la notificación | El sistema debe redirigir al usuario a la pantalla específica del evento al interactuar con una notificación interna, evitando que el usuario tenga que buscar manualmente el mensaje o la solicitud dentro de la app. | Completado |
| Actualización de Estado leída | El sistema debe marcar automáticamente la notificación como "Leída" cuando el usuario haga clic en ella o acceda a su enlace directo, permitiendo también al usuario marcar todas las notificaciones del listado como leídas de forma simultánea mediante una acción global. | Completado |

#### CU: Filtros avanzados para arrendador
| Nombre | Descripción | Estado |
| :--- | :--- | :--- |
| Definición de Perfil Ideal | El sistema debe permitir al anunciante parametrizar las características deseadas del compañero de piso (rango de edad, ocupación, hábitos) para alimentar el algoritmo de afinidad. | Completado |
| Filtrado Manual de Solicitudes | El sistema debe permitir al Arrendador filtrar la lista de candidatos recibidos mediante selectores básicos de perfil: rango de edad, género, ocupación (estudiante/trabajador) y hábitos (fumador/mascotas), para localizar rápidamente a los perfiles que mejor encajen. | Completado |
| Ordenación de Candidatos | El sistema debe permitir al Arrendador ordenar el listado de solicitudes recibidas por diferentes criterios: fecha de recepción (más reciente/antigua), mayor puntuación de reseñas o por mayor afinidad con el perfil ideal definido. | Completado |

---

## 3. Fallos, Feedback y Mejoras

Esta sección aborda los fallos y mejoras identificados por los PUGs (Grupos de Usuarios Pares) y, donde corresponde, por el profesor revisor, indicando claramente las medidas tomadas y los resultados logrados.

### 3.1 Feedback de los PUGs

#### Sprint 1
| Fallo / Mejora Identificada | Medida Correctiva Tomada | Resultado Obtenido |
| :--- | :--- | :--- |
| **Descubrimiento de viviendas:** No se pueden eliminar solicitudes en estado "Pendiente". El botón no funciona (la vivienda vuelve a mostrarse) y debería arreglarse u ocultarse temporalmente. | Se modificó la consulta que se hace al crear el deck de inmuebles para que se tome en cuenta el estado de las solicitudes. | Se ha solucionado el error. |
| **Evaluación de Candidatos y Match:** El *landlord* puede añadir a su vivienda inquilinos que ya están en otro piso (la acción no tiene efecto). Además, cuando el inquilino acepta el *match*, la acción no se registra y el inmueble vuelve a aparecer en la lista. *Mejora:* Bloquear la búsqueda o adición si el inquilino ya tiene piso. | Se ha bloqueado la adición a un inmueble por parte de un propietario si el usuario está añadido a algún inmueble | Error solucionado |
| **Gestión de inmuebles:** Falta indicador de carga al crear un piso (provoca creación múltiple). El mapa no funciona. Los botones "Editar" y el de los tres puntos fallan. El campo "Fecha disponible" carece de validación (permite años como 1901). *Mejoras:* No se puede limitar la capacidad máxima de personas del inmueble, ni los inquilinos tienen opción para salir de su piso actual. | Se ha controlado la idempotencia al crear un piso y se ha solucionado el botón de "Editar" de un piso. | Se ha solucionado el error reportado sobre la creación y edición. |
| **Gestión de Facturas y Pagos:** El icono de campana (notificaciones) no realiza ninguna acción. Incongruencia de navegación: el apartado "Facturas" lleva a un panel llamado "Mis Pagos", y el botón de retroceso desde ahí redirige a los detalles del piso en lugar de al perfil del usuario. | Se ha eliminado el botón de la campana ya que no aportaba ningún valor. | Se ha solucionado el error del botón. |
| **Reseñas y Valoración:** Funcionalidad incompleta/no implementada. El panel es visible, pero los compañeros de piso no aparecen en las listas de valoraciones "pendientes" o "realizadas", y las reseñas no se enlazan con el perfil del inquilino (apartado "recibidas"). | Los usuarios de prueba no tenían contratos terminados, por lo que era imposible comprobar la funcionalidad. Ahora el usuario `tenant1` está configurado para ello. | Ya se puede probar la funcionalidad. |
| **Hallazgos Generales UI/UX:** La sesión de usuario no persiste al recargar la página. Al iniciar sesión como *landlord*, el sistema redirige de forma poco coherente a "Mis inmuebles" en lugar de a la pestaña de "Inicio". | Se ha arreglado el error de persistencia debido a un fallo de gestión de las cookies así como se ha modificado el redireccionamiento | Se ha solucionado el error |

#### Sprint 2

| Fallo / Mejora Identificada | Medida Correctiva Tomada | Resultado Obtenido |
| :--- | :--- | :--- |
| **CU Descubrimiento de viviendas:** El deck de tarjetas no está basado en ningún tipo de filtro.  No existe la opción de añadir preferencias (precio, zona, reglas) ni en "Inicio" ni en "Editar Perfil". Además, no queda clara la forma de probar la funcionalidad Premium. | En el anterior Software Review Guidelines se añadieron todos los CU sin contar que requisitos estaban completados del mismo, se han añadido a este documento los requisot exactos a probar de cada CU y los mencionados en este feedback se realizarán en la siguiente semana (excepto el rewind) | Se ha mejorado la redacción de los CU en el documento de Software Review Guidelines |
| **CU Evaluación de Candidatos y Match:** El *landlord* no recibe notificaciones de nuevos *likes* en sus pisos. Faltan opciones al gestionar solicitudes (solo se puede aceptar/rechazar, faltando una tercera) y el chat no se abre automáticamente al aceptar. *Mejora:* Añadir un botón de "reservar". | Se han corregido las notificaciones para los landlords y se han reducido los estados de las solicitudes a aceptar/rechazar, además ya se abre el chat automáticamente | Solucionados todos los errores y adaptados los requisitos necesarios |
|  **CU Chat post Match:** No funciona correctamente la opción de adjuntar imágenes o documentos.  Los archivos no se envían si no van acompañados de un mensaje de texto, a pesar de que el *placeholder* indica que es opcional.  Tampoco están claros los tipos de archivo permitidos (ej. los MP3 fallan).  *Mejoras:* Mostrar formatos admitidos y límites de tamaño, y permitir selección múltiple. | Se han solucionado los errores relacionados a la subida de imagenes junto con texto. Además ahora se deja claro en el requisito asociado que archivos se permiten | Solucinado los errores relacionados al chat y aclaración de los CU |
|  **CU Sistema de Favoritos:** Solo se puede añadir a favoritos la tarjeta que sale en el *top* de la pila de inicio, o no aparece el botón de favoritos en la tarjeta de inicio.  Desde la pantalla de favoritos, no se puede dar *like* o *dislike* para seguir el flujo, solo ver el detalle o desmarcar. | Se ha solucionado la adición a favoritos, la visualización de detalles y el desmarcar. | Se ha solucionado los errores de la funcionalidad, pero todavía se está decidiendo si implementar la funcionalidad de like / dislike desde la pantalla como gratis o premium |
|  **CU Gestión de Inmuebles:** La funcionalidad de definir el "compañero ideal" no está implementada en la creación, solo permite hacerlo al editar.  El botón de "usar mi ubicación actual" no funciona.  Hay inconsistencias entre crear y editar: los gastos y la fianza son seleccionables al crear, pero solo texto al editar.  Problema de rendimiento: la lentitud del despliegue permite crear un mismo piso múltiples veces si se hace clic repetidamente. | La funcionalidad de compañero ideal se implementará en el siguiente sprint, aparte de esto se ha solucionado el botón de ubicación actual y como hemos explicado antes se ha gestionado la imdepotencia al crear inmuebles | Solucionado los errores encontrados |
|  **CU Gestión de Cuentas y Perfil:** No se pueden configurar búsquedas, notificaciones, suscripciones, OAuth ni 2FA.  La fecha de nacimiento falla con años antiguos (se guarda con un día de menos), por lo que requiere validación de rangos.  *Mejora UI:* Los estilos de los desplegables se camuflan con el fondo y dificultan la lectura.  Sigue sin persistir la sesión al recargar la página. | Al igual que los anteriores, ahora se deja más claro los requisitos implementados del CU ya que la mayoría de estos no estaban implementados. Se ha probado con años hasta 1920 en la modificaciñon del perfil y se guarda correctamente la fecha. Se ha solucionado la persistencia de la sesión al recargar la página | Se han dejado más claro los requisitos implementados a probar y se han solucionado los errores encontrados |
|  **CU Gestión de Facturas y Pagos:** No permite crear facturas desde la vista del *landlord*  y la pantalla de facturas en el perfil aparece completamente vacía.  *Fallo detectado:* El *landlord* aparece erróneamente como compañero de piso del primer inmueble que acepte el *tenant*. | No se ha podido solucionar para el sprint porque se recibio el feedback cuando el despliegue ya estaba completado, se realizará su correción en el próximo sprint | Se anota para el próximo sprint |
|  **CU Gestión de Incidencias en la Vivienda:** No hay forma de acceder a las incidencias desde el perfil de *landlord*, imposibilitando su gestión o pruebas. | Se ha solucionado el error y ya el landlord puede acceder a las incidencias de cada inmueble | Solucionado el error |
|  **CU Reseñas y Valoración:** Al valorar al *landlord*, el mensaje mostrado es erróneo y lo trata como inquilino ("Tu valoración de tu compañero/a..."). | No se ha podido solucionar para el sprint porque se recibio el feedback cuando el despliegue ya estaba completado, se realizará su correción en el próximo sprint | Se anota para el siguiente sprint |

### 3.2 Feedback del Profesor
| Fallo / Mejora Identificada | Medida Correctiva Tomada | Resultado Obtenido |
| :--- | :--- | :--- |
| **Datos de Prueba:** Se debe mantener datos de prueba realistas para que la aplicación siempre sea lo más cercana a la realidad | Se han añadido datos de prueba realistas para el despliegue de este sprint y para el despliegue para los usuarios piloto | La aplicación tiene un estilo realista |
| **Análisis Económico:** El análisis económico debe siempre consistir de datos agregados y teniendo en cuenta la estimación de usuarios | Se ha realizado el análisis económico tomando en cuenta en estos consejos | El análisis económico ahora es mucho más detallado y más realista con la progresión de usuarios y tiempo |
| **Análisis de Problemas:** Los análisis de problemas deben siempre contener sus mitigaciones, los plazos para ver si la mitigación ha funcionado o la solución y usar métricas completas para medir elproblema y su solución | Se ha utilizado una estructura de "Lección", "Mitigación" y "Comprobación" para cada problema encontrado con métricas específicas | Se ha conseguido una mayor eficiencia en el control de los problemas y su seguimiento |
| **Calendario de Citas centralizado:** Se aconsejó realizar una funcionalidad por la que un propietario pudiera centralizar las visitas a sus inmuebles para todos los matches del mismo. | Se ha seguido este consejo y ahora los propietarios pueden crear visitas centralizadas que se mandarán automáticamente a todos los matches del inmueble mediante el chat de cada interesado, y desde aquí el interesado podrá elegir un horario al que asistir. | Un manejo de las citas mucho más como para el propietario y los interesados |

---

## 4. Datos de Prueba y Credenciales

Datos necesarios para poder realizar la revisión (usuarios, contraseñas o ejemplos de datasets si son complejos):

### 4.1 Cuentas de Prueba
#### Inquilinos

| Email | Contraseña |
| :--- | :--- |
| tenant1@test.com | 123456 |
| tenant2@test.com | 123456 |
| tenant3@test.com | 123456 |

#### Caseros

| Email | Contraseña |
| :--- | :--- |
| landlord1@test.com | 123456 |
| landlord2@test.com | 123456 |
| landlord3@test.com | 123456 |

### 4.2 Ejemplos de Conjuntos de Datos de Entrada
*(No contamos con campos complejos para probar cualquier funcionalidad)*

---

## 5. Requisitos del Sistema y Permisos

Posibles requisitos necesarios para poder utilizar el sistema:
* Activar acceso a la ubicación en el navegador
* Permitir permisos de cámara para subir la foto de una incidencia si se está en móvil
* Permitir el acceso a las notificaciones push al activar las notificaciones desde el perfil
