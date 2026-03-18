# Documento de análisis de requisitos de ROOMA

Organizado por **Caso de Uso > Requisitos (RF / RI / RNF) > Historias de Usuario**


## Índice de Casos de Uso

| ID | Nombre | 
|----|--------|
| [CU-01](#cu-01-descubrimiento-de-viviendas) | Descubrimiento de viviendas |
| [CU-02](#cu-02-evaluación-de-candidatos-y-match) | Evaluación de Candidatos y Match |
| [CU-03](#cu-03-coordinación-de-visita-y-contacto-personal) | Coordinación de visita y contacto personal |
| [CU-04](#cu-04-gestión-de-notificaciones) | Gestión de Notificaciones |
| [CU-05](#cu-05-sistema-de-favoritos) | Sistema de Favoritos |
| [CU-06](#cu-06-gestión-de-inmuebles) | Gestión de Inmuebles |
| [CU-07](#cu-07-gestión-de-cuentas-y-perfil) | Gestión de Cuentas y Perfil |
| [CU-08](#cu-08-edición-de-anuncios) | Edición de Anuncios | 
| [CU-10](#cu-10-gestión-de-facturas-y-pagos) | Gestión de Facturas y Pagos |
| [CU-11](#cu-11-gestión-de-incidencias-en-la-vivienda) | Gestión de Incidencias en la Vivienda | 
| [CU-12](#cu-12-reseñas-y-valoración-de-convivencia) | Reseñas y Valoración de Convivencia |

---

# CU-01: Descubrimiento de Viviendas


## Requisitos Funcionales

### RF-46 — Gestión del Deck de Viviendas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe generar un mazo dinámico de viviendas basado en los filtros de búsqueda (precio, zonas, reglas) que el usuario indique. |

**Historias de usuario vinculadas:** [HU01](#hu01)


### RF-47 — Visualizar Detalles de Vivienda
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir abrir una vista expandida de cada vivienda que aparezca en el deck para consultar los detalles, fotos expandidas, ubicación, reglas de la vivienda e inquilinos actuales junto con sus detalles. |

**Historias de usuario vinculadas:** [HU03](#hu03)


### RF-48 — Swipe
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe procesar el gesto táctil de swipe a la vivienda que esté actualmente al frente del deck (derecha "Like", izquierda "Dislike"). Además, el gesto de swipe debe poder realizarse con dos botones que indiquen las mismas acciones. |

**Historias de usuario vinculadas:** [HU01](#hu01), [HU02](#hu02)


### RF-49 — Rewind de Viviendas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | El sistema debe permitir deshacer el último "Dislike" (que supone no volver a ver un inmueble), validando previamente si el usuario tiene una suscripción premium. |

**Historias de usuario vinculadas:** [HU04](#hu04)


### RF-50 — Gestión de Estados al hacer Swipe en una vivienda
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe registrar cada interacción del usuario con cada inmueble para asegurar que una vivienda descartada no vuelva a aparecer. |

**Historias de usuario vinculadas:** [HU02](#hu02)


### RF-51 — Persistencia del Deck de Viviendas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe guardar la posición actual del deck para cada usuario, para que en caso de pérdida de conexión pueda retomar las acciones desde donde lo dejó y no se recarguen los inmuebles aleatoriamente. |

**Historias de usuario vinculadas:** [HU01](#hu01)


### RF-52 — Sugerencia de Filtros de Viviendas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe proponer automáticamente la ampliación de los filtros aplicados si no hay viviendas disponibles con los ya aplicados. |

**Historias de usuario vinculadas:** [HU01](#hu01) *(gestión de estado vacío del deck)*


## Requisitos No Funcionales

### RNF-08 — Respuesta de Interfaz
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | La interfaz visual del sistema debe ser altamente responsiva, sobre todo el gesto táctil de "swipe", para mantener una buena experiencia de usuario sin latencia y fluida. |


### RNF-09 — Disponibilidad Online
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | El sistema debe tener cargadas un número determinado de viviendas del deck para permitir un uso breve del usuario sin conexión y no romper bruscamente la experiencia del usuario. |


### RNF-10 — Carga del Deck
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El filtrado de los inmuebles no puede afectar gravemente al tiempo de carga del deck; se debe estandarizar el tiempo de carga en todos los casos posibles. |


## Historias de Usuario

### HU01
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-46, RF-48, RF-51 |
| **Historia** | Como Buscador, quiero ver un deck de tarjetas con inmuebles filtrados por mis preferencias para explorar opciones de alquiler de forma rápida. |
| **Criterios de aceptación** | 1. El deck solo muestra viviendas que cumplan con los filtros del buscador. <br> 2. Si el usuario pierde la conexión, aparece la misma tarjeta en la que se quedó. <br> 3. El usuario debe poder ver como mínimo 10 viviendas más si se queda sin conexión. |
| **Especificación** | El backend devuelve máximo 20 inmuebles por carga. Los inmuebles se ordenan por coincidencia de filtros y luego por publicación. Si no hay resultados, se muestra un mensaje para modificar los filtros. El servidor guarda la última vivienda vista como punto de partida de la siguiente sesión. |
| **Riesgos** | Si crece mucho el número de inmuebles, el filtrado puede volverse lento (ya ocurre en plataformas como Idealista). |


### HU02
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-48, RF-49, RF-50 |
| **Historia** | Como Buscador, quiero descartar o mostrar interés mediante gestos táctiles laterales para que la navegación sea fluida, intuitiva y rápida. |
| **Criterios de aceptación** | 1. Al deslizar la tarjeta hacia la derecha más del 50% de la pantalla, el sistema marca el inmueble como "Interesado" y registra el estado. <br> 2. Al deslizar hacia la izquierda, el sistema marca el inmueble como "Descartado" y asegura que no vuelva a aparecer. <br> 3. Durante el deslizamiento, deben aparecer indicadores visuales (corazón verde / X roja) que varíen su opacidad. <br> 4. Una vez completado el gesto, la siguiente tarjeta se carga inmediatamente. <br> 5. Esta acción debe realizarse también mediante dos botones diferenciados. |
| **Especificación** | El "Match" o "Descarte" se dispara al superar el 50% del ancho de la pantalla o alcanzar una velocidad de arrastre (velocity) de 0,5 px/ms. La tarjeta superior tiene siempre el foco táctil; las tarjetas inferiores pueden renderizarse pasivamente. |
| **Riesgos** | Usuarios que deslizan por error al intentar hacer scroll vertical. Las animaciones pueden generar sensación de "lag" en dispositivos de gama media/baja. |


### HU03
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-47 |
| **Historia** | Como Buscador, quiero acceder al detalle de una vivienda para ver fotos, descripción y el perfil de los actuales compañeros (si existen), para evaluar si mi estilo de vida es compatible con el de ellos. |
| **Criterios de aceptación** | 1. Debe mostrarse descripción y galería de fotos del inmueble. <br> 2. Deben aparecer los perfiles de los compañeros con resumen de sus cualidades (profesión, edad…). <br> 3. El botón de "Like" y "Dislike" debe seguir accesible mientras se muestran los detalles. |
| **Especificación** | Implementar Lazy Loading y miniaturas en baja resolución antes de cargar la imagen original. |
| **Riesgos** | Perfiles de compañeros incompletos que hagan que la "afinidad" parezca inexistente o errónea. |


### HU04
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-49 |
| **Historia** | Como Buscador Premium, quiero deshacer mi último "Dislike" para recuperar un inmueble que descarté por error. |
| **Criterios de aceptación** | 1. La función solo está activa para usuarios Premium. <br> 2. Solo se permite recuperar la última tarjeta descartada. <br> 3. Se permite un máximo de 5 rewinds al día. <br> 4. Al realizar el rewind se actualiza el estado del inmueble eliminando acciones pasadas. |
| **Especificación** | El sistema solo guarda el ID de la última tarjeta descartada en la sesión actual. Si se intenta Rewind sin ser Premium, aparece un pop-up para acceder a la suscripción. |
| **Riesgos** | — |

---

# CU-02: Evaluación de Candidatos y Match

## Requisitos Funcionales

### RF-53 — Gestión de Solicitudes
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | El sistema debe mostrar para los usuarios anunciantes un dashboard que permita organizar a los candidatos por estado para cada vivienda que tengan anunciada. |

**Historias de usuario vinculadas:** [HU05](#hu05)


### RF-54 — Visualización Candidato
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir a los anunciantes acceder a los perfiles detallados de cada interesado por una vivienda que tengan anunciada, donde se puedan ver sus datos públicos (edad, profesión…). |

**Historias de usuario vinculadas:** [HU06](#hu06)


### RF-55 — Gestión de Candidatos
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El anunciante de una vivienda debe poder modificar el estado de cada candidato, pudiendo seleccionar 2 estados: **Aceptar** (abre chat bidireccional) y **Rechazar** (archiva la solicitud). |

**Historias de usuario vinculadas:** [HU07](#hu07)


### RF-56 — Gestión de Estados del Inmueble
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe gestionar la modificación del estado de una vivienda (Alquilado, Pausado, Libre). Si un inmueble pasa a Pausado o Alquilado, se cancelarán todas las solicitudes pendientes. |

**Historias de usuario vinculadas:** [HU05](#hu05)


### RF-74 — Match
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir dar like o dislike a las propuestas. El Match guardará estados: **Activo** (esperando una de las partes), **Match** (ambas partes dieron like), **Rechazado** (alguna parte dio dislike o decidió no continuar), **Exitoso** (candidato ahora es inquilino). |

**Historias de usuario vinculadas:** [HU07](#hu07)


## Requisitos de Información

### RI-21 — Match
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe guardar los datos relacionados con el match. |

**Atributos:**
- `ID` (PK)
- `ID_Usuario` — candidato (FK a Usuario)
- `ID_Apartamento` (FK a Vivienda)
- `InteresCasero` (Boolean)
- `InteresInquilino` (Boolean)
- `Fecha_del_Match`
- `Estado_del_Match` — Enum: Activo / Match / Rechazado / Exitoso


## Historias de Usuario

### HU05
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-53, RF-56 |
| **Historia** | Como Anunciante, quiero visualizar un dashboard organizado por estados para cada una de mis viviendas, para gestionar de manera eficiente el volumen de candidatos. |
| **Criterios de aceptación** | 1. El sistema lista de forma independiente cada vivienda activa del anunciante. <br> 2. Dentro de cada vivienda, los candidatos se agrupan en: "Nuevos/Pendientes", "En Espera" y "Aceptados". <br> 3. Se muestra un contador numérico de candidatos en cada estado. <br> 4. Si el inmueble cambia a "Pausado" o "Alquilado", se eliminan/cancelan todas las solicitudes pendientes y en espera. |
| **Especificación** | Interfaz tipo tablero Kanban o lista filtrable por estado. Los candidatos se cargan mediante paginación para evitar latencia en viviendas con alta demanda (>50 solicitudes). |
| **Riesgos** | Un anunciante con muchos inmuebles puede verse desbordado visualmente. Si pausa por error, podría perder candidatos valiosos si la eliminación es física (hard delete) en lugar de lógica (soft delete). Chats ya abiertos (Match) quedan "huérfanos" si el piso se alquila. |


### HU06
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-54 |
| **Historia** | Como Anunciante, quiero acceder a la ficha técnica y pública de cada candidato para verificar su idoneidad y compatibilidad antes de tomar una decisión. |
| **Criterios de aceptación** | 1. Al hacer clic en un candidato del dashboard, se abre una vista expandida. <br> 2. La ficha muestra obligatoriamente: edad, profesión/estudios, descripción personal y etiquetas de estilo de vida. <br> 3. Incluye un indicador visual de "Perfil Verificado" si el usuario ha validado su identidad. |
| **Especificación** | Solo se muestran datos marcados como "públicos" por el candidato. Datos sensibles (como teléfono) permanecen ocultos hasta que haya un "Match". |
| **Riesgos** | La visualización de ciertos datos personales puede dar lugar a discriminación (riesgo ético/legal). Datos desactualizados pueden llevar al anunciante a tomar decisiones erróneas. |


### HU07
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-55, RF-74 |
| **Historia** | Como Anunciante, quiero poder aceptar, poner en espera o rechazar solicitudes de candidatos para avanzar en el proceso de selección de perfiles. |
| **Criterios de aceptación** | 1. Al pulsar "Aceptar", el sistema crea un canal de chat y habilita el módulo de calendario. Se envía notificación de "Match" al candidato. <br> 2. Al pulsar "En Espera", el candidato se mueve a la lista secundaria sin notificación negativa. <br> 3. Al pulsar "Rechazar", la solicitud se archiva y el candidato no verá el anuncio ni podrá volver a dar "Like". |
| **Especificación** | — |
| **Riesgos** | Pulsar "Rechazar" por error (se puede implementar una acción de deshacer inmediatamente después). |

---

# CU-03: Coordinación de Visita y Contacto Personal

## Requisitos Funcionales

### RF-57 — Gestión de Chats entre Usuarios
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe habilitar un chat activo para cada par de usuarios (inquilino/arrendatario) que tengan un Match confirmado. Debe ser imposible acceder sin Match. |

**Historias de usuario vinculadas:** [HU08](#hu08), [HU11](#hu11)


### RF-58 — Mensajería Multimedia en Tiempo Real
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | El sistema debe permitir el envío y recepción instantánea de mensajes de texto, imágenes y documentos como parte del chat ya abierto entre dos usuarios. |

**Historias de usuario vinculadas:** [HU08](#hu08)


### RF-59 — Indicadores de Estado
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe guardar y mostrar el estado de los mensajes dentro de un chat (Entregado / Leído) y mostrarlo en los mensajes de un usuario hacia el otro que forme parte del chat. |

**Historias de usuario vinculadas:** [HU08](#hu08)


### RF-60 — Gestión de Citas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | El sistema debe permitir al anunciante proponer una fecha y hora para concertar una cita y al usuario inquilino aceptarla o proponer una fecha alternativa. |

**Historias de usuario vinculadas:** [HU09](#hu09)


### RF-61 — Cancelación de Citas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe permitir al anunciante o inquilino cancelar una cita programada con antelación, enviando una notificación al usuario que formaría parte de la cita. |

**Historias de usuario vinculadas:** [HU10](#hu10)


### RF-62 — Cierre de Chats
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe permitir archivar o cerrar chats entre dos usuarios si alguna de las partes lo decide o si el inmueble al que está relacionado el chat deja de estar disponible. |

**Historias de usuario vinculadas:** [HU11](#hu11)


## Requisitos de Información

### RI-12 — Mensaje
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **CU** | CU-11 / CU-03 |
| **Descripción** | Datos para la vista de cualquier chat dentro del sistema. |

**Atributos:**
- `ID_Mensaje` (PK, autogenerado)
- `ID_Incidencia` — FK a Incidencia, si el mensaje es de un chat de incidencia
- `ID_Remitente` — FK a Usuario
- `Nombre_Remitente`
- `Tipo` — Enum: Texto / Imagen / Sistema
- `Contenido` — texto del mensaje o URL de imagen adjunta
- `Fecha_Envio`
- `Leido` (Boolean)
- `Fecha_Lectura` — null si no leído


### RI-15 — Citas / Visitas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | Datos a almacenar para cada visita que se concrete. |

**Atributos:**
- `ID_Usuario1` — usuario que crea la cita
- `ID_Usuario2` — usuario que acepta la cita
- `Fecha` — fecha y hora de la cita acordada
- `Ubicación` — lugar de enlace que impone quien crea la cita


## Requisitos No Funcionales

### RNF-18 — Latencia de Mensajes
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | Los mensajes deben entregarse en un tiempo inferior a un segundo (suponiendo buena conexión desde los dos usuarios) para garantizar la sensación de "tiempo real". |


## Historias de Usuario

### HU08
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-58, RF-59 |
| **Historia** | Como Candidato con un Match, quiero intercambiar mensajes, fotos y documentos con la otra parte (el Anunciante) para agilizar la resolución de dudas y el envío de detalles necesarios. |
| **Criterios de aceptación** | 1. El sistema permite el envío de texto, imágenes (JPG/PNG) y documentos (PDF). <br> 2. Se muestran indicadores visuales de estado: un check (Entregado) y doble check coloreado (Leído). <br> 3. La actualización de los mensajes en pantalla debe ser instantánea sin necesidad de refrescar (WebSockets). |
| **Especificación** | Uso de WebSockets (Socket.io) para la persistencia de la conexión. Límite de subida de 10 MB por archivo. Los documentos deben almacenarse en un bucket seguro (S3 o similar) con URLs prefirmadas de acceso temporal. |
| **Riesgos** | El intercambio masivo de imágenes de alta resolución puede disparar los costes de servidor. Riesgo de envío de spam o contenido ofensivo. |


### HU09
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-60 |
| **Historia** | Como Anunciante, quiero proponer fechas para una visita y que el candidato pueda aceptarlas o sugerir otras para organizar mi agenda sin salir de la aplicación. |
| **Criterios de aceptación** | 1. El anunciante puede seleccionar fecha y hora dentro del chat o en una sección adjunta. <br> 2. El Candidato visualiza la propuesta con dos botones claros: "Aceptar" o "Proponer otra fecha". <br> 3. Si el Candidato propone otra fecha, el anunciante recibe una contrapropuesta que debe validar. |
| **Especificación** | Se podría implementar la creación de archivos `.ics` para integración con calendarios externos. |
| **Riesgos** | Usuarios que no responden a las propuestas de cita ("Ghosting logístico"). |


### HU10
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-61 |
| **Historia** | Como Usuario con una cita programada, quiero poder cancelarla en caso de imprevisto para avisar automáticamente a la otra parte. |
| **Criterios de aceptación** | 1. Ambas partes deben tener un botón de "Cancelar Cita" dentro del apartado de citas. <br> 2. Al cancelar, el sistema envía una notificación push inmediata a la otra parte. <br> 3. Se solicita un motivo breve de cancelación (opcional). |
| **Especificación** | Uso de Firebase Cloud Messaging (FCM) para asegurar que la alerta llegue aunque la app esté en segundo plano. |
| **Riesgos** | Cancelaciones de último minuto recurrentes. |


### HU11
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-62 |
| **Historia** | Como Usuario, quiero que el chat se cierre o archive si la vivienda asociada ya no está disponible o decido terminar la conversación para mantener unos chats limpios y funcionales. |
| **Criterios de aceptación** | 1. El usuario puede archivar un chat manualmente. <br> 2. Si el inmueble cambia su estado a "Alquilado" o "Pausado", el chat se bloquea para nuevos mensajes automáticamente. <br> 3. Aparece un aviso informativo: "Esta vivienda ya no está disponible". |
| **Especificación** | Los chats no se borran de la base de datos por temas legales/seguridad; solo se cambia su estado a `archived: true`. |
| **Riesgos** | Usuarios que quieren recuperar información de un chat cerrado y no encuentran la conversación. |

---

# CU-04: Gestión de Notificaciones 


## Requisitos Funcionales

### RF-01 — Generación de Notificaciones por Eventos
| Campo | Valor |
|-------|-------|
| **Prioridad** | Medio |
| **Descripción** | El sistema debe generar automáticamente una notificación cuando ocurra un match o se reciba un mensaje. |

**Historias de usuario vinculadas:** [HU43](#hu43)


### RF-02 — Visualización de Listado
| Campo | Valor |
|-------|-------|
| **Prioridad** | Medio |
| **Descripción** | El sistema debe permitir al usuario acceder a una pantalla o sección de "Notificaciones" donde se listen cronológicamente las notificaciones recibidas. |

**Historias de usuario vinculadas:** [HU44](#hu44)


### RF-03 — Indicador de Nuevas Notificaciones
| Campo | Valor |
|-------|-------|
| **Prioridad** | Medio |
| **Descripción** | El sistema debe mostrar un indicador visual en la interfaz cuando existan notificaciones nuevas. |

**Historias de usuario vinculadas:** [HU45](#hu45)


### RF-04 — Navegación Directa desde la Notificación
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe redirigir al usuario a la pantalla específica del evento al interactuar con una notificación interna, evitando que el usuario tenga que buscar manualmente el mensaje o la solicitud dentro de la app. |

**Historias de usuario vinculadas:** [HU46](#hu46)


### RF-05 — Actualización de Estado Leída
| Campo | Valor |
|-------|-------|
| **Prioridad** | Medio |
| **Descripción** | El sistema debe marcar automáticamente la notificación como "Leída" cuando el usuario haga clic en ella o acceda a su enlace directo, permitiendo también marcar todas las notificaciones como leídas de forma simultánea mediante una acción global. |

**Historias de usuario vinculadas:** [HU47](#hu47)


## Requisitos de Información

### RI-01 — Notificación
| Campo | Valor |
|-------|-------|
| **Prioridad** | Medio |
| **Descripción** | El sistema debe almacenar y mostrar para cada notificación los siguientes datos obligatorios. |

**Atributos:**
- `Identificador_de_origen` — quién originó el mensaje
- `Tipo_de_evento` — Enum: Match / Mensaje / Pago pendiente
- `Fecha_y_hora` — momento exacto del evento
- `Descripcion` — mensaje breve sobre el contenido
- `Leido` — indicador booleano
- `Enlace_directo` — URL al lugar donde se lanzó el evento


## Requisitos No Funcionales

### RNF-01 — Orden de las Notificaciones
| Campo | Valor |
|-------|-------|
| **Prioridad** | Medio |
| **Descripción** | Las notificaciones se deben mostrar en orden descendiente, de más nuevas a más viejas. |


### RNF-02 — Privacidad de Notificaciones
| Campo | Valor |
|-------|-------|
| **Prioridad** | Medio |
| **Descripción** | El sistema debe garantizar que las notificaciones internas sean accesibles única y exclusivamente por el usuario destinatario. Se debe implementar una capa de autorización que valide la identidad del usuario antes de entregar o listar cualquier notificación. |


## Historias de Usuario

### HU43
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-01, RI-01 |
| **Historia** | Como usuario, quiero recibir notificaciones automáticas cuando ocurra un match o reciba un mensaje, para estar informado de interacciones importantes en la plataforma. |
| **Criterios de aceptación** | 1. Se genera una notificación automáticamente al producirse un evento relevante. <br> 2. La notificación se almacena con su información obligatoria. <br> 3. La notificación aparece como no leída. |
| **Especificación** | El sistema detecta eventos relevantes y crea un registro en la entidad Notificación, incluyendo tipo, fecha, origen, descripción y enlace directo. |
| **Riesgos** | Generación duplicada de notificaciones. Retrasos en la entrega. Problemas de sincronización en tiempo real. |


### HU44
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-02, RI-01, RNF-01, RNF-02 |
| **Historia** | Como usuario, quiero acceder a una sección donde pueda visualizar todas mis notificaciones en orden cronológico, para consultarlas fácilmente. |
| **Criterios de aceptación** | 1. Existe una pantalla de notificaciones. <br> 2. Se muestran en orden descendente. <br> 3. Solo se muestran las notificaciones del usuario autenticado. |
| **Especificación** | El sistema lista las notificaciones almacenadas en la base de datos ordenadas por fecha descendente. |
| **Riesgos** | Carga lenta con muchas notificaciones. |


### HU45
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-03, RI-01 |
| **Historia** | Como usuario, quiero ver un indicador visual cuando tenga nuevas notificaciones, para saber que existen eventos pendientes. |
| **Criterios de aceptación** | 1. Se muestra un icono cuando hay notificaciones no leídas. <br> 2. El indicador desaparece cuando todas están marcadas como leídas. |
| **Especificación** | El sistema cuenta las notificaciones no leídas y muestra un indicador visual en la interfaz. |
| **Riesgos** | Actualización en tiempo real del indicador. |


### HU46
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-04, RI-01 |
| **Historia** | Como usuario, quiero ser redirigido a la pantalla relacionada al pulsar una notificación, para acceder rápidamente al contenido. |
| **Criterios de aceptación** | 1. Al hacer clic se abre la pantalla correspondiente. <br> 2. El enlace funciona correctamente. |
| **Especificación** | Cada notificación incluye un enlace directo al recurso relacionado. |
| **Riesgos** | Errores de navegación. Cambios de rutas. |


### HU47
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-05, RI-01, RNF-02 |
| **Historia** | Como usuario, quiero que las notificaciones se marquen como leídas al abrirlas y poder marcarlas todas como leídas, para gestionar mejor mis avisos. |
| **Criterios de aceptación** | 1. Una notificación cambia a estado leída al abrirse. <br> 2. Existe una opción para marcar todas como leídas. |
| **Especificación** | El sistema actualiza el campo booleano "Leído" en la entidad Notificación. |
| **Riesgos** | Errores en la actualización masiva. |

---

# CU-05: Sistema de Favoritos

## Requisitos Funcionales

### RF-06 — Gestión de Favoritos
| Campo | Valor |
|-------|-------|
| **Prioridad** | Bajo |
| **Descripción** | El sistema debe permitir al usuario marcar o desmarcar una vivienda/perfil como "Favorito" desde la tarjeta, el detalle o directamente desde el listado de favoritos. |

**Historias de usuario vinculadas:** [HU48](#hu48)


### RF-07 — Visualización del Listado de Favoritos
| Campo | Valor |
|-------|-------|
| **Prioridad** | Bajo |
| **Descripción** | El sistema debe ofrecer una sección específica donde el usuario pueda revisar todos los elementos guardados y acceder a su detalle. |

**Historias de usuario vinculadas:** [HU49](#hu49)


### RF-08 — Control de Disponibilidad en Favoritos
| Campo | Valor |
|-------|-------|
| **Prioridad** | Bajo |
| **Descripción** | El sistema debe detectar si una vivienda ya no está disponible (por haberse completado el grupo) y mostrar un aviso informativo en el listado indicando que no se puede acceder al detalle. |

**Historias de usuario vinculadas:** [HU50](#hu50)


## Requisitos de Información

### RI-02 — Elemento Guardado
| Campo | Valor |
|-------|-------|
| **Prioridad** | Bajo |
| **Descripción** | El sistema debe gestionar una entidad relacional denominada Elemento Guardado que vincule de forma única a un Usuario con una Vivienda específica. |

**Atributos:**
- `ID_Usuario`
- `ID_Vivienda`
- `Favorito` — booleano que marca si el usuario ha guardado la vivienda


## Requisitos No Funcionales

### RNF-03 — Privacidad de Favoritos
| Campo | Valor |
|-------|-------|
| **Prioridad** | Bajo |
| **Descripción** | El sistema debe garantizar que los registros de la clase Elemento Guardado sean privados y exclusivos del propietario de la cuenta. Ningún otro usuario podrá consultar la lista de favoritos de terceros. |


### RNF-04 — Depuración de Favoritos
| Campo | Valor |
|-------|-------|
| **Prioridad** | Bajo |
| **Descripción** | El sistema debe eliminar automáticamente el registro de la clase Elemento Guardado cuando la vivienda vinculada sea eliminada de la plataforma o cuando se marque como "Cerrada". |


## Historias de Usuario

### HU48
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-06, RI-02, RNF-04 |
| **Historia** | Como buscador, quiero poder marcar una vivienda como favorita para revisarla más tarde. |
| **Criterios de aceptación** | 1. Se puede guardar desde tarjeta o detalle. <br> 2. El sistema almacena la relación usuario-vivienda. |
| **Especificación** | Se crea un registro en la entidad Elemento Guardado. |
| **Riesgos** | Duplicación de favoritos. Problemas de sincronización. Accesibilidad al botón. |


### HU49
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-07, RI-02, RNF-03 |
| **Historia** | Como buscador, quiero ver un listado de mis favoritos para acceder fácilmente a ellos. |
| **Criterios de aceptación** | 1. Existe una sección de favoritos. <br> 2. Se muestran todos los elementos guardados disponibles. |
| **Especificación** | El sistema consulta la entidad Elemento Guardado filtrada por usuario. |
| **Riesgos** | Rendimiento en listados grandes. |


### HU50
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-08, RI-02, RNF-04 |
| **Historia** | Como buscador, quiero ver si una vivienda favorita ya no está disponible, para evitar intentar acceder a un anuncio cerrado. |
| **Criterios de aceptación** | 1. Se muestra un aviso si la vivienda está cerrada. <br> 2. No permite acceder al detalle. |
| **Especificación** | El sistema valida el estado de la vivienda antes de permitir el acceso. |
| **Riesgos** | Información desactualizada. |

---

# CU-06: Gestión de Inmuebles


## Requisitos Funcionales

### RF-09 — Formulario de Alta Guiado
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir al anunciante registrar un inmueble mediante un formulario que capture: ubicación exacta, precio mensual, fotografías, número máximo de miembros y reglas de convivencia (mascotas, fumadores, etc.). |

**Historias de usuario vinculadas:** [HU51](#hu51)


### RF-10 — Definición de Perfil Ideal
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir al anunciante parametrizar las características deseadas del compañero de piso (rango de edad, ocupación, hábitos) para alimentar el algoritmo de afinidad. |

**Historias de usuario vinculadas:** [HU52](#hu52)


### RF-11 — Gestión de Estado del Anuncio de la Vivienda
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir al anunciante activar, pausar o marcar como "Cerrado" (inquilino encontrado) su anuncio en cualquier momento. |

**Historias de usuario vinculadas:** [HU53](#hu53)


### RF-12 — Previsualización del Anuncio de la Vivienda
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir al anunciante visualizar cómo se mostrará su inmueble en el deck de los buscadores antes de confirmar la publicación. |

**Historias de usuario vinculadas:** [HU54](#hu54)


### RF-13 — Restricción de Eliminación de Vivienda
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | El sistema debe controlar las condiciones bajo las cuales se puede eliminar un anuncio. Solo se permitirá la eliminación definitiva si no existen inquilinos activos vinculados a la vivienda. |

**Historias de usuario vinculadas:** [HU55](#hu55)


### RF-14 — Consulta de Miembros de la Vivienda
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir visualizar los usuarios vinculados a un inmueble, mostrando su rol dentro de la vivienda y la fecha de incorporación. |

**Historias de usuario vinculadas:** [HU56](#hu56)


## Requisitos de Información

### RI-03 — Vivienda
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alto |
| **Descripción** | El sistema debe almacenar para cada inmueble los siguientes datos obligatorios. |

**Atributos:**
- `Título` — nombre descriptivo del anuncio
- `Descripción` — texto detallado con características y condiciones
- `Precio` — valor numérico del alquiler mensual
- `Gastos` — especificación de suministros incluidos o adicionales
- `Ubicación` — coordenadas y zona para el filtrado en el mapa
- `Número max de miembros` — Número máximo de personas de una vivienda
- `Estado` — Enum: Activo / Pausado / Cerrado


### RI-04 — FotosViviendas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alto |
| **Descripción** | El sistema debe gestionar la información individual de cada archivo visual. |

**Atributos:**
- `ID_Vivienda` — referencia al inmueble
- `URL_Imagen` — enlace al almacenamiento del recurso visual
- `Orden` — posición numérica dentro de la galería
- `Portada` — booleano que define la imagen principal del deck


### RI-05 — MiembrosViviendas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alto |
| **Descripción** | El sistema debe almacenar los datos de los usuarios que ya habitan el inmueble. |

**Atributos:**
- `ID_Vivienda`
- `ID_Usuario`
- `Rol` — Enum: Propietario / Inquilino principal / Compañero
- `Fecha_Ingreso`
- `Fecha_Salida`


### RI-06 — ReglasVivienda
| Campo | Valor |
|-------|-------|
| **Prioridad** | Medio |
| **Descripción** | El sistema debe almacenar las normas de convivencia mediante indicadores booleanos para facilitar el filtrado. |

**Atributos:**
- `ID_Vivienda`
- `Permite_Mascotas` (Boolean)
- `Permite_Fumadores` (Boolean)
- `Fiestas_Permitidas` (Boolean)


## Requisitos No Funcionales

### RNF-05 — Integridad de Datos
| Campo | Valor |
|-------|-------|
| **Prioridad** | Medio |
| **Descripción** | El sistema debe impedir el borrado accidental de viviendas que tengan procesos de Match o chats activos, solicitando una confirmación adicional del anunciante. |


### RNF-06 — Estado de Revisión Publicación
| Campo | Valor |
|-------|-------|
| **Prioridad** | Medio |
| **Descripción** | Al completar el alta, el inmueble no será visible para los buscadores inmediatamente; quedará en estado "En Revisión" hasta que se valide la veracidad de las imágenes y la coherencia de los datos. |


### RNF-07 — Privacidad de Datos del Inmueble
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alto |
| **Descripción** | El sistema debe asegurar que los datos sensibles del inmueble (dirección exacta o documentos) solo sean accesibles para usuarios que posean un Match verificado por el anunciante. |


## Historias de Usuario

### HU51
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-09, RI-03, RI-04, RI-06, RNF-06, RNF-07 |
| **Historia** | Como anunciante, quiero registrar un inmueble mediante un formulario guiado para poder publicarlo en la plataforma. |
| **Criterios de aceptación** | 1. El sistema permite introducir ubicación, precio y descripción. <br> 2. El usuario puede subir fotografías. <br> 3. El usuario puede definir reglas de convivencia. <br> 4. El sistema guarda correctamente la información. |
| **Especificación** | El sistema presenta un formulario paso a paso que almacena los datos en las entidades Vivienda, FotosViviendas y ReglasVivienda, dejando el anuncio en estado inicial de revisión. |
| **Riesgos** | Errores en la carga de imágenes. Datos incompletos o inválidos. Elementos duplicados. |


### HU52
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-10 |
| **Historia** | Como anunciante, quiero definir las características del compañero ideal para mejorar la compatibilidad en el algoritmo de afinidad. |
| **Criterios de aceptación** | 1. El sistema permite introducir preferencias. <br> 2. Los datos quedan almacenados correctamente. <br> 3. Se vinculan al inmueble correspondiente. |
| **Especificación** | El sistema permite parametrizar características del perfil buscado mediante un formulario específico vinculado al anuncio. |
| **Riesgos** | Configuración incorrecta de preferencias. Datos incompletos que afecten al algoritmo. |


### HU53
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-11, RI-03 |
| **Historia** | Como anunciante, quiero cambiar el estado de mi anuncio para controlar su disponibilidad. |
| **Criterios de aceptación** | 1. El sistema permite activar, pausar o cerrar el anuncio. <br> 2. El cambio se guarda inmediatamente. <br> 3. El estado se refleja en la visibilidad del inmueble. |
| **Especificación** | El sistema actualiza el atributo Estado de la entidad Vivienda y modifica la disponibilidad del anuncio en el deck de buscadores. |
| **Riesgos** | Estados inconsistentes. Desincronización con el sistema de visibilidad. |


### HU54
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-12, RI-03, RI-04, RI-06 |
| **Historia** | Como anunciante, quiero previsualizar mi anuncio antes de publicarlo para verificar su contenido y apariencia. |
| **Criterios de aceptación** | 1. Se muestra una vista previa completa. <br> 2. El anuncio aún no es visible para buscadores. <br> 3. Se reflejan correctamente fotos, datos y reglas. |
| **Especificación** | El sistema renderiza una vista simulada del deck utilizando la información almacenada del inmueble. |
| **Riesgos** | Diferencias entre vista previa y publicación real. Problemas de renderizado de imágenes. |


### HU55
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-13, RI-03, RI-05, RNF-05 |
| **Historia** | Como anunciante, quiero eliminar un anuncio solo si no existen inquilinos activos para evitar inconsistencias en el sistema. |
| **Criterios de aceptación** | 1. El sistema verifica si existen miembros asociados. <br> 2. Si hay inquilinos activos, se bloquea la eliminación. <br> 3. Se solicita confirmación antes del borrado. |
| **Especificación** | El sistema consulta la entidad MiembrosViviendas para validar si existen usuarios vinculados antes de permitir la eliminación del registro en Vivienda. |
| **Riesgos** | Eliminación accidental de datos. Inconsistencias en relaciones entre entidades. |


### HU56
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-14, RI-05, RNF-07 |
| **Historia** | Como usuario buscador, quiero ver quiénes viven actualmente en un inmueble para evaluar la compatibilidad antes de solicitar unirme. |
| **Criterios de aceptación** | 1. Se muestra un listado de miembros del piso. <br> 2. Se indica el rol de cada miembro. <br> 3. Se muestra la fecha de ingreso. <br> 4. Solo se muestra información permitida según privacidad. |
| **Especificación** | El sistema consulta la entidad MiembrosViviendas y presenta los datos asociados al inmueble seleccionado. |
| **Riesgos** | Problemas de privacidad de datos personales. Información desactualizada. Exposición de datos sensibles. |

---

# CU-07: Gestión de Cuentas y Perfil


## Requisitos Funcionales

### RF-63 — Registro con Email y Contraseña
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe ofrecer un formulario de registro (email, contraseña, confirmar contraseña), validar formato de email (regex) y unicidad, validar la política de contraseña configurable (mín. 8 caracteres, mayúscula, minúscula y número), comprobar coincidencia de contraseñas, y crear la cuenta en estado "Pendiente de verificación". |

**Historias de usuario vinculadas:** [HU57](#hu57)


### RF-64 — Validación, Verificación y Reenvío
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | Enviar un correo con token único que caduca a las 24 h. Debe impedir el acceso a funcionalidades protegidas hasta verificar email, mostrar mensajes claros para todos los errores y permitir reenvío controlado del email de verificación (límite configurable, p.ej. 3/hora). |

**Historias de usuario vinculadas:** [HU57](#hu57)


### RF-65 — Inicio de Sesión con Proveedores
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir autenticación mediante Google, Apple y Facebook (OAuth/OIDC), solicitar y guardar consentimiento, gestionar vinculación de cuentas y permitir desvincular proveedores siempre que exista otro método de acceso activo. |

**Historias de usuario vinculadas:** [HU58](#hu58), [HU59](#hu59)


### RF-66 — Recuperación de Contraseña
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir solicitar recuperación introduciendo el email; enviar enlace con token único de un solo uso con caducidad (1 h recomendado); mostrar formulario para establecer nueva contraseña; invalidar el token tras su uso; ofrecer opción de invalidar todas las sesiones activas; y aplicar rate-limits y captcha. |

**Historias de usuario vinculadas:** [HU59](#hu59)


### RF-67 — Autenticación en Dos Pasos (2FA TOTP)
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe permitir activar 2FA vía TOTP generando secreto y QR, validar con primer código, almacenar el secreto cifrado; al activar generar 10 códigos de recuperación de un solo uso; permitir desactivar 2FA solo tras reautenticación; y mostrar estado de 2FA en la cuenta. |

**Historias de usuario vinculadas:** [HU60](#hu60)


### RF-68 — Completar y Editar Perfil
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir completar/editar: fotos de perfil, nombre, fecha de nacimiento, género, teléfono, estudio/trabajo, descripción libre, tipo de búsqueda (habitación / piso completo / compañero) y preguntas de convivencia (fumar, etc.). Debe mapear respuestas a pesos para el motor de matching. |

**Historias de usuario vinculadas:** [HU61](#hu61)


### RF-69 — Reportes de Usuarios
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe ofrecer un formulario de reporte accesible desde perfil y chat con categorías (Fraude, Contenido inapropiado, Abuso/hostigamiento, Spam, Otro), permitir adjuntar evidencia, generar ticket único con metadatos y aplicar controles anti-abuso. |

**Historias de usuario vinculadas:** [HU62](#hu62)


### RF-70 — Sanciones Administrativas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe permitir a administradores suspender temporalmente o banear permanentemente una cuenta registrando motivo, evidencia, admin ID y duración; notificar al usuario afectado por email con motivo; y revocar acceso inmediatamente. |

**Historias de usuario vinculadas:** [HU63](#hu63)


### RF-71 — Verificación de Identidad Delegada
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir iniciar un proceso de verificación delegada a proveedor externo previa firma de consentimiento; integrar la respuesta del proveedor y, en caso de éxito, asignar badge "Verificado"; y gestionar estados (En proceso, Exitoso, Rechazado). |

**Historias de usuario vinculadas:** [HU64](#hu64)


## Requisitos de Información

### RI-16 — Usuario
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |

**Atributos:**
- `ID_Usuario` (PK autogenerada)
- `Email` (único, indexado)
- `PasswordHash`
- `Nombre`
- `Apellido` (opcional)
- `Fecha_Nacimiento`
- `Telefono` (opcional)
- `Foto_Perfil_URL`
- `Estado_Cuenta` — Enum: Pendiente_Verificacion / Activa / Suspendida / Banneada
- `Fecha_Alta`
- `Fecha_Ultima_Conexion`
- `Etiquetas` de información del usuario
- `Es_Fumador` (Boolean)
- `Género`
- `Metodos_Acceso`
- `Rol` — Enum: Tenant / Landlord


### RI-17 — Tokens de Verificación y Recuperación
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | El sistema debe gestionar tablas de tokens firmados/hashed para EmailVerificationToken y PasswordResetToken. |

**Atributos:**
- `ID_Token` (PK)
- `ID_Usuario` (FK)
- `Token_Hash` — no almacenar token en claro
- `Tipo` — Enum: EmailVerification / PasswordReset
- `Fecha_Creacion`
- `Fecha_Expiracion`
- `Usado` (Boolean)
- `Origen_IP` (opcional)
- `Intentos` — contador de uso fallido


### RI-18 — ProveedorOAuth / Vinculación Externa
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |

**Atributos:**
- `ID`
- `ID_Usuario` (FK)
- `Proveedor` — Enum: Google / Apple / Facebook
- `Proveedor_UserID`
- `Email_Proveedor`
- `Email_Verificado` (Boolean)
- `Fecha_Vinculacion`
- `Consentimiento_Registro`


### RI-19 — 2FA (TOTP) y Códigos de Recuperación
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |

**Atributos (TwoFactor):**
- `ID_Usuario`
- `Secret_Encrypted`
- `Fecha_Activacion`
- `Activo` (Boolean)

**Atributos (RecoveryCodes):**
- `ID_Usuario`
- lista (hash) de códigos de un solo uso
- `Usados`
- `Fecha_Generacion`


### RI-20 — Audit Log / Eventos de Seguridad
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | Registro inmutable de eventos críticos. |

**Atributos (AuditEvent):**
- `ID_Evento`
- `ID_Usuario` (si aplica)
- `Tipo_Evento` — login fallido, verificación, suspender cuenta…
- `Timestamp`
- `IP`
- `Agent`
- `Detalle` (JSON)
- `Actor_Admin` (si admin)


## Historias de Usuario

### HU57
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-63, RF-64 |
| **Historia** | Como nuevo usuario, quiero registrarme con email y contraseña para crear una cuenta. |
| **Criterios de aceptación** | 1. Usuario creado y email verificado. <br> 2. Pantalla de registro con campos email, contraseña, confirmar contraseña, checkbox T&C + link a política de privacidad. <br> 3. Botón registrar deshabilitado hasta validar. <br> 4. Tras registro: UI "Correo enviado — revisa tu bandeja" con opción de reenviar. |
| **Especificación** | Email: regex + verificación de existencia (409 si existe). Password: verificar política y almacenar solo hash. Rate-limit por IP y por email para evitar registros masivos. Almacenar fecha de creación, si aceptó los T&C, IP y versión de los T&C. |
| **Riesgos** | Spam / registros masivos (mitigado con rate-limits, CAPTCHA). Fuga de credenciales (almacenar solo hash). Cumplimiento RGPD (almacenar consentimiento T&C con timestamp/IP). |


### HU58
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-65 |
| **Historia** | Como usuario, quiero iniciar sesión con proveedores para evitar crear credenciales nuevas. |
| **Criterios de aceptación** | 1. El usuario puede loguearse con Google, Apple y Facebook. <br> 2. Botones "Iniciar con Google / Apple / Facebook" en pantalla de login y registro. <br> 3. Pantalla intermedia para unir cuentas si ya existe correo asociado. |
| **Especificación** | — |
| **Riesgos** | Si la cuenta Google está comprometida, un atacante puede acceder a ROOMA. Privacidad: registrar solo datos mínimos del provider. |


### HU59
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-65, RF-66 |
| **Historia** | Como usuario, quiero recuperar acceso si olvido la contraseña. |
| **Criterios de aceptación** | 1. Se modifica la contraseña del usuario. <br> 2. Pantalla "Olvidé mi contraseña" → pedir email. <br> 3. Email con link y CTA. <br> 4. Página de cambio de contraseña con confirmación y requisitos visibles. <br> 5. Post-cambio: notificación y botón "Cerrar sesiones". |
| **Especificación** | Rate-limit solicitudes; no revelar existencia de email (responder siempre con 200 OK + mensaje genérico). |
| **Riesgos** | — |


### HU60
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-67 |
| **Historia** | Como usuario, quiero activar la autenticación en dos pasos para evitar robos de cuentas. |
| **Criterios de aceptación** | 1. Usuario puede activar 2FA por app (TOTP, p.ej. Google Authenticator). <br> 2. Al activar, se generan 10 códigos de recuperación de un solo uso que el usuario debe guardar. <br> 3. Pantalla Seguridad con toggle Activar 2FA y flujo guiado con QR. <br> 4. Capacidad de desactivar la doble autenticación. |
| **Especificación** | Flujo guiado con QR, campo para introducir código de verificación y botón "Guardar códigos de recuperación". |
| **Riesgos** | Pérdida de acceso: usuarios que pierden su dispositivo de 2FA; mitigación: recovery codes, proceso de soporte verificado. |


### HU61
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-68 |
| **Historia** | Como usuario, quiero completar mi perfil con foto, nombre, edad, género, teléfono, estudio/trabajo, descripción, hábitos (fumar, limpieza, invitados, mascotas, horarios) y estilo de vida en el piso. |
| **Criterios de aceptación** | 1. El perfil se ha actualizado de forma exitosa. <br> 2. Onboarding guiado "Completa tu perfil" con pasos: foto, datos personales, preferencias de convivencia. |
| **Especificación** | — |
| **Riesgos** | Perfiles falsos / bots. Discriminación: evitar preguntas sobre información sensible (raza, religión, orientación). Protección de datos: fotos y PII deben almacenarse cifradas; derechos RGPD para borrar/portabilidad. |


### HU62
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-69 |
| **Historia** | Como usuario, quiero reportar perfiles por fraude o comportamiento para que soporte investigue. |
| **Criterios de aceptación** | 1. Formulario de reporte accesible desde perfil y chat con categorías: Fraude, Contenido inapropiado, Abuso/hostigamiento, Spam, Otro. <br> 2. Permite adjuntar evidencia (imágenes, capturas, mensajes). <br> 3. Al enviar, se genera ticket con ID y se envía confirmación al administrador. |
| **Especificación** | Modal/form con campos: tipo, descripción libre (mín. 20 caracteres), adjuntos. Panel en Admin con filtros, evidencia y posibilidad de bloquear. |
| **Riesgos** | Abuso de reportes maliciosos. Carga operativa: muchos reportes requieren equipo humano. Privacidad: manejar evidencias con cuidado. |


### HU63
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-70 |
| **Historia** | Como admin, quiero suspender o bloquear cuentas tras revisión. |
| **Criterios de aceptación** | 1. Admin puede suspender temporalmente o banear permanentemente una cuenta. <br> 2. El sistema guarda la razón, identificador del admin y duración. <br> 3. El usuario recibe notificación por email con motivo y pasos para apelación. |
| **Especificación** | Panel con búsqueda por user_id/email, vista de historial, botón Suspend / Ban con formulario para reason, fecha de expiración y evidencia adjunta. Opción reversible. |
| **Riesgos** | Suspensiones erróneas: los procesos deben incluir revisión humana y posible doble-check antes de ban permanente. |


### HU64
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-71 |
| **Historia** | Como usuario, quiero verificar mi identidad para aumentar mi credibilidad. |
| **Criterios de aceptación** | 1. Delegación de verificación a proveedor externo. <br> 2. Si la verificación es exitosa, el perfil obtiene badge "Verificado". <br> 3. Antes del proceso el usuario firma consentimiento explícito y se informa de retención y uso. |
| **Especificación** | Mensaje previo de aceptación del consentimiento. |
| **Riesgos** | Falsos positivos/negativos: riesgo de rechazar usuarios legítimos o aceptar fraudes. |

---

# CU-08: Edición de Anuncios


## Requisitos Funcionales

### RF-72 — Gestión de Anuncios
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | El sistema debe permitir al anunciante editar toda la información del anuncio mediante formulario guiado (precio, fotos, reglas, perfil ideal, disponibilidad), validar y persistir cambios, mostrar confirmación, actualizar fecha de "última modificación" y notificar in-app a matches activos sobre cambios relevantes. |

**Historias de usuario vinculadas:** [HU65](#hu65)


### RF-73 — Pausar y Reactivar Anuncio
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | El sistema debe permitir pausar temporalmente un anuncio para que deje de aparecer en búsquedas mientras conserva matches y solicitudes existentes; y permitir reactivar el anuncio en cualquier momento actualizando timestamp. Al reactivar, ofrecer opción de notificar candidatos en espera. |

**Historias de usuario vinculadas:** [HU66](#hu66), [HU67](#hu67)


## Historias de Usuario

### HU65
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-72 |
| **Historia** | Como anunciante, quiero modificar la información de mi anuncio para mantenerlo actualizado. |
| **Criterios de aceptación** | 1. El sistema permite editar la información del anuncio. <br> 2. Los cambios se guardan correctamente. <br> 3. El sistema muestra mensaje de confirmación. <br> 4. Se actualiza la fecha de "última modificación". <br> 5. Si el anuncio tiene matches activos, se notifica el cambio relevante. |
| **Especificación** | Formulario con los datos preestablecidos del anuncio. |
| **Riesgos** | — |


### HU66
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-73 |
| **Historia** | Como anunciante, quiero pausar temporalmente mi anuncio para no recibir más solicitudes mientras gestiono candidatos. |
| **Criterios de aceptación** | 1. El anuncio deja de aparecer en búsquedas. <br> 2. Se conservan los matches existentes. <br> 3. Puede reactivarse en cualquier momento. |
| **Especificación** | Botón de desactivación del anuncio. |
| **Riesgos** | — |


### HU67
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-73 |
| **Historia** | Como anunciante, quiero reactivar mi anuncio para volver a recibir solicitudes. |
| **Criterios de aceptación** | 1. El anuncio vuelve a aparecer en búsquedas si cumple los filtros. <br> 2. Se actualiza el timestamp. |
| **Especificación** | Botón de activación del anuncio. |
| **Riesgos** | — |

---

# CU-10: Gestión de Facturas y Pagos

## Requisitos Funcionales

### RF-15 — Pantalla de Registro de Gastos
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe disponer de una interfaz de formulario para el Casero que incluya: datepicker nativo, campos numéricos con formato monetario (€), desplegable de conceptos predefinidos (Alquiler, Luz, Agua, Gas, Internet, Comunidad, Otro), campo de texto libre para descripción adicional, y área de carga para adjuntar el documento de la factura (PDF o imagen) con previsualización. El formulario debe incluir validación en línea de campos obligatorios. |

**Historias de usuario vinculadas:** [HU12](#hu12)


### RF-16 — Selector Visual de Inquilinos y Modo de Reparto
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe mostrar una lista interactiva de todos los inquilinos vinculados al inmueble con avatar, nombre y checkbox para incluirlos/excluirlos del reparto. Debe ofrecer un selector de modo de reparto: (a) Partes iguales, (b) Porcentaje personalizado, (c) Importe fijo por persona. |

**Historias de usuario vinculadas:** [HU12](#hu12), [HU13](#hu13)


### RF-17 — Visualización de Cuotas en Tiempo Real
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe recalcular y actualizar dinámicamente en pantalla el importe que le corresponde a cada inquilino cada vez que el Casero modifique el importe total, cambie el modo de reparto o marque/desmarque participantes, sin necesidad de recargar la página. Si hay discrepancia por redondeo, el sistema la asignará al último participante de la lista. |

**Historias de usuario vinculadas:** [HU13](#hu13)


### RF-18 — Dashboard de "Mis Pagos" (Vista Inquilino)
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe presentar al Inquilino una pantalla con dos pestañas: (a) Pendientes — lista de deudas activas ordenadas por urgencia con indicador semáforo (Rojo = Vencido, Amarillo = Próximo ≤ 3 días, Verde = Al día); (b) Historial — lista cronológica descendente de todos los pagos realizados, filtrable. |

**Historias de usuario vinculadas:** [HU17](#hu17), [HU18](#hu18), [HU23](#hu23)


### RF-19 — Pasarela de Pago Integrada
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe desplegar un modal de checkout segura cuando el Inquilino pulse "Pagar". Dicho modal debe: mostrar resumen del cargo, listar métodos de pago guardados, ofrecer botón "Añadir nuevo método de pago" con formulario embebido (Stripe Elements), solicitar confirmación final, mostrar animación de éxito y recibo descargable tras el pago, y en caso de error mostrar mensaje descriptivo y permitir reintentar. |

**Historias de usuario vinculadas:** [HU19](#hu19)


### RF-20 — Indicadores de Estado de Pago
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe reflejar visualmente el estado de cada deuda mediante etiquetas (badges) con los estados: 'Pendiente' (gris), 'Vencido' (rojo), 'Procesando' (amarillo/naranja pulsante), 'Pagado' (verde) y 'Rechazado' (rojo oscuro). Para garantizar accesibilidad a personas con daltonismo, cada badge incluirá un icono diferenciador. |

**Historias de usuario vinculadas:** [HU17](#hu17)


### RF-21 — Interruptor de Auto-Pago
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe incluir en la sección "Métodos de Pago" del Inquilino un toggle switch para activar/desactivar el cobro automático. Al activarlo, se mostrará un popup de confirmación con los términos legales. Al desactivarlo, se pedirá confirmación. |

**Historias de usuario vinculadas:** [HU20](#hu20)


### RF-22 — Dashboard de Cobros (Vista Casero)
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe proporcionar al Casero una pantalla de seguimiento de cobros por vivienda que muestre: lista de todas las facturas emitidas con su estado global, desglose por inquilino al pulsar sobre una factura, resumen financiero mensual con gráfico, y posibilidad de enviar un recordatorio push manual a inquilinos con pagos vencidos. |

**Historias de usuario vinculadas:** [HU14](#hu14)


### RF-23 — Notificaciones de Pagos
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe enviar notificaciones push automáticas en los siguientes eventos: nueva factura registrada, pago recibido, recordatorio de vencimiento (3 días antes y el mismo día), pago vencido (al Inquilino diariamente y al Casero una vez), y auto-pago ejecutado. |

**Historias de usuario vinculadas:** [HU14](#hu14), [HU23](#hu23)


### RF-24 — Exportación de Historial Financiero
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | El sistema debe permitir tanto al Casero como al Inquilino exportar el historial de pagos en formato PDF o CSV, filtrable por rango de fechas, vivienda y concepto. El documento generado debe incluir un encabezado con los datos del piso y las partes involucradas. |

**Historias de usuario vinculadas:** [HU16](#hu16), [HU22](#hu22)


### RF-25 — Gestión de Métodos de Pago
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe ofrecer al Inquilino una pantalla para gestionar sus métodos de pago guardados donde pueda: ver la lista de tarjetas registradas, añadir una nueva tarjeta (PCI-compliant), eliminar una tarjeta existente con confirmación, establecer una tarjeta como predeterminada, y recibir aviso cuando una tarjeta esté próxima a caducar (≤ 30 días). |

**Historias de usuario vinculadas:** [HU21](#hu21)


### RF-26 — Anulación y Edición de Facturas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir al Casero editar una factura previamente registrada siempre que ningún inquilino haya realizado el pago. Si ya existe algún pago parcial, solo podrá anular la factura completa, lo que generará automáticamente una nota de crédito visible para los inquilinos que hayan pagado. |

**Historias de usuario vinculadas:** [HU15](#hu15)


## Requisitos de Información

### RI-07 — FacturaGasto
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alto |

**Atributos:**
- `ID_Factura` (autogenerado)
- `ID_Vivienda` (FK a Vivienda)
- `ID_Casero` (FK a Usuario)
- `Concepto` — Enum: Alquiler / Luz / Agua / Gas / Internet / Comunidad / Otro
- `Descripcion` — texto libre opcional
- `Importe_Total` — decimal, 2 decimales
- `Moneda` — código ISO 4217 (por defecto EUR)
- `Periodo_Consumo_Inicio`
- `Periodo_Consumo_Fin`
- `Fecha_Vencimiento`
- `Fecha_Creacion`
- `Modo_Reparto` — Enum: Partes_Iguales / Porcentaje / Importe_Fijo
- `Estado_Global` — Enum: Pendiente / Parcialmente_Cobrado / Cobrado / Anulado
- `Archivo_URL` — ruta al documento adjunto (PDF/IMG)
- `Archivo_Nombre` — nombre original del fichero
- `Archivo_Tamaño` — peso en bytes (máx. 5 MB validado)


### RI-08 — DeudaInquilino
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alto |

**Atributos:**
- `ID_Deuda` (autogenerado)
- `ID_Factura` (FK a FacturaGasto)
- `ID_Usuario` (FK a Usuario)
- `Nombre_Usuario`
- `Avatar_URL`
- `Cuota` — decimal, 2 decimales
- `Porcentaje` (opcional)
- `Estado` — Enum: Pendiente / Procesando / Pagado / Vencido / Rechazado
- `Fecha_Vencimiento` — heredada de la factura padre
- `Fecha_Pago` — null si no pagado
- `ID_Transaccion` — referencia de la pasarela (null si no pagado)
- `Semaforo` (derivado) — Verde: Pagado / Amarillo: ≤ 3 días / Rojo: Vencido / Gris: Pendiente


### RI-09 — TransaccionPago
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alto |

**Atributos:**
- `ID_Transaccion` (autogenerado)
- `ID_Deuda` (FK a DeudaInquilino)
- `ID_Usuario` (FK a Usuario)
- `Importe` — decimal, 2 decimales
- `Metodo_Pago_ID` (FK a MetodoPago)
- `Estado` — Enum: Pendiente / Exitoso / Fallido / Reembolsado
- `Codigo_Pasarela` — ID de transacción de Stripe u otra pasarela
- `Fecha_Creacion`
- `Fecha_Resolucion`
- `Motivo_Error` — null si éxito
- `Es_AutoPago` (Boolean)


### RI-10 — MetodoPago
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alto |

**Atributos:**
- `ID_MetodoPago` (autogenerado)
- `ID_Usuario` (FK a Usuario)
- `Token_Pasarela` — token seguro de Stripe (nunca se almacena el número completo)
- `Mascara_Tarjeta` — últimos 4 dígitos (ej.: '•••• 4242')
- `Logo_Marca` — Enum: Visa / Mastercard / Amex / Otro
- `Titular`
- `Caducidad_Mes` (01–12)
- `Caducidad_Año` (AA)
- `Es_Predeterminada` (Boolean)
- `AutoPago_Activo` (Boolean)
- `Fecha_Registro`
- `Alerta_Caducidad` (derivado) — true si faltan ≤ 30 días para caducar


## Requisitos No Funcionales

### RNF-11 — Cumplimiento PCI-DSS
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema de pagos debe cumplir PCI-DSS. Nunca se almacenarán números de tarjeta completos. Información sensible tokenizada mediante Stripe. Comunicaciones con pasarela exclusivamente HTTPS/TLS 1.2+. |


### RNF-12 — Cifrado de Datos Financieros
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | Datos financieros cifrados en reposo (AES-256) y en tránsito (TLS 1.2+). Documentos de facturas en bucket privado con URL firmada con expiración. |


### RNF-16 — Disponibilidad del Sistema de Pagos
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | Uptime mínimo: 99,00%. Caída de pasarela → mensaje "Servicio temporalmente no disponible" + reintentar sin perder datos. |


### RNF-17 — Idempotencia en Transacciones
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | Sin cargos duplicados si el usuario pulsa varias veces o se interrumpe la conexión. Claves de idempotencia (idempotency keys) en cada llamada a la pasarela. |


## Historias de Usuario

### HU12
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-15, RF-16 |
| **Historia** | Como Casero, quiero registrar una factura de suministro o renta desde la app, adjuntando el documento original, para notificar automáticamente el cobro a los inquilinos del piso. |
| **Criterios de aceptación** | 1. El formulario incluye campos obligatorios: concepto (desplegable), importe (numérico con formato €), fecha de vencimiento (datepicker nativo) y periodo de consumo (rango de fechas). <br> 2. El Casero puede adjuntar un archivo PDF o imagen (JPG/PNG) de máximo 5 MB. <br> 3. El sistema muestra previsualización del archivo adjunto antes de guardar. <br> 4. Al guardar, se validan todos los campos obligatorios y se muestran mensajes de error en línea si falta alguno. <br> 5. Se muestra confirmación de éxito con resumen del gasto registrado. |
| **Especificación** | Input: Datepicker nativo del SO. Archivo: PDF/IMG < 5 MB, validación de tipo MIME en cliente y servidor. Backend: Endpoint `POST /api/gastos` con validación de esquema. Permisos: Solo usuarios con rol Casero y viviendas activas. |
| **Riesgos** | Archivos corruptos o con virus (mitigar con escaneo en servidor). Pérdida de datos si la app se cierra durante la carga (mitigar con borrador automático). |


### HU13
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-16, RF-17 |
| **Historia** | Como Casero, quiero seleccionar qué inquilinos participan en un gasto y elegir el modo de reparto (partes iguales, porcentaje o importe fijo) para que cada uno pague lo que le corresponde. |
| **Criterios de aceptación** | 1. La lista de inquilinos muestra avatar, nombre y checkbox — por defecto todos seleccionados. <br> 2. Al desmarcar un inquilino, la cuota del resto se recalcula instantáneamente. <br> 3. Existen 3 modos de reparto: partes iguales, porcentaje personalizado, importe fijo. <br> 4. En modo porcentaje, la suma debe ser 100%. <br> 5. En modo importe fijo, la suma de importes debe coincidir con el total. <br> 6. Si hay discrepancia por redondeo, el sistema la asigna al último participante y muestra aviso informativo. |
| **Especificación** | Frontend: Estado reactivo (React useState / Vue ref). Cálculo: Math.round a 2 decimales; discrepancia asignada al último. UI: Componente ToggleGroup para modos de reparto. |
| **Riesgos** | Error de redondeo visual (mitigar mostrando siempre 2 decimales y validando suma). |


### HU14
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-22, RF-23 |
| **Historia** | Como Casero, quiero ver un panel con el estado de cobro de todas mis facturas agrupadas por vivienda, para saber de un vistazo cuánto me deben y quién ha pagado. |
| **Criterios de aceptación** | 1. El panel muestra lista de facturas por vivienda con estado global: 'Todo cobrado' (verde), 'Cobro parcial' (amarillo), 'Pendiente' (gris). <br> 2. Al pulsar una factura, se despliega el desglose por inquilino. <br> 3. La cabecera muestra un resumen financiero: total cobrado del mes vs. total pendiente. <br> 4. El Casero puede enviar un recordatorio push manual a inquilinos con pagos vencidos. <br> 5. El recordatorio solo se puede enviar una vez cada 24 horas por deuda para evitar spam. |
| **Especificación** | Backend: Endpoint `GET /api/casero/cobros?vivienda={id}&mes={MMYYYY}`. UI: Tarjetas colapsables con desglose; gráfico donut opcional. |
| **Riesgos** | Casero envía demasiados recordatorios (mitigar con cooldown). Desfase entre estado real de la pasarela y lo mostrado. |


### HU15
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-26 |
| **Historia** | Como Casero, quiero poder editar o anular una factura que registré por error, para corregir importes o conceptos equivocados. |
| **Criterios de aceptación** | 1. Si ningún inquilino ha pagado, el Casero puede editar cualquier campo de la factura y se recalculan las cuotas. <br> 2. Si ya hay pagos parciales, solo se permite anular la factura completa. <br> 3. Al anular, se genera una nota de crédito automática para los inquilinos que ya pagaron. <br> 4. Se notifica a todos los inquilinos afectados sobre la edición o anulación. <br> 5. El historial mantiene un registro de la versión original y la modificada. |
| **Especificación** | Backend: `PUT /api/gastos/{id}` con validación de estado de pagos. Lógica: If any DeudaInquilino.estado == 'Pagado' then solo permitir anulación. Auditoría: Tabla de log con versiones anteriores. |
| **Riesgos** | Anulación accidental de factura con pagos realizados (mitigar con confirmación doble y nota de crédito). Confusión del inquilino al recibir notificación de cambio. |


### HU16
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-24 |
| **Historia** | Como Casero, quiero exportar un informe mensual de todos los cobros de un piso en PDF para mi contabilidad personal o para presentarlo ante la administración. |
| **Criterios de aceptación** | 1. El Casero selecciona vivienda, rango de fechas y formato (PDF o CSV). <br> 2. El documento incluye: datos del piso, lista de facturas con desglose por inquilino, estado de cada pago y total recaudado vs. pendiente. <br> 3. El PDF tiene encabezado con logo de ROOMA, datos del piso y fecha de generación. <br> 4. La descarga se inicia en menos de 10 segundos para informes de hasta 12 meses. |
| **Especificación** | Backend: Generación de PDF con librería (puppeteer/pdfkit). Endpoint: `GET /api/casero/exportar?vivienda={id}&desde={fecha}&hasta={fecha}&formato={pdf|csv}`. Límite: Máximo rango de 12 meses por exportación. |
| **Riesgos** | Informes muy grandes que tarden en generar (mitigar con generación asíncrona y notificación cuando esté listo). |


### HU17
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-18, RF-20 |
| **Historia** | Como Inquilino, quiero ver un dashboard con todas mis deudas pendientes ordenadas por urgencia y con colores claros, para identificar rápidamente lo que tengo que pagar. |
| **Criterios de aceptación** | 1. La pestaña 'Pendientes' muestra deudas ordenadas: Vencidas (rojo) > Próximas ≤ 3 días (amarillo) > Al día (verde). <br> 2. Cada tarjeta muestra: icono de concepto, importe, fecha límite, nombre de la vivienda y badge de estado. <br> 3. Los badges usan color + icono (accesibilidad daltónicos). <br> 4. La cabecera muestra el total pendiente acumulado con cifra destacada. <br> 5. Al pulsar una tarjeta, se muestra el detalle con la factura original adjunta y botón 'Pagar'. |
| **Especificación** | Lógica: Ordenación por `fecha_vencimiento ASC` con priorización de vencidas. |
| **Riesgos** | Daltónicos no distinguen rojo/verde (mitigado con iconos diferenciadores). Lista muy larga si hay muchas deudas acumuladas (mitigar con paginación). |


### HU18
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-18 |
| **Historia** | Como Inquilino, quiero consultar mi historial de pagos realizados filtrado por mes y concepto para llevar un control de mis gastos. |
| **Criterios de aceptación** | 1. La pestaña 'Historial' muestra una lista cronológica descendente de todos los pagos realizados. <br> 2. Filtros disponibles: mes (selector), concepto (desplegable), vivienda (desplegable si tiene varias). <br> 3. Cada elemento muestra: concepto, importe pagado, fecha de pago, método de pago (últimos 4 dígitos) y badge 'Pagado'. <br> 4. El inquilino puede pulsar sobre un pago para ver el recibo detallado con opción de descarga en PDF. |
| **Especificación** | Backend: `GET /api/inquilino/pagos?mes={MMYYYY}&concepto={enum}&vivienda={id}`. Paginación: 20 elementos por página, carga infinita. |
| **Riesgos** | Historial muy extenso afectando rendimiento (mitigar con paginación y caché). |


### HU19
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-19, RNF-11, RNF-12, RNF-16, RNF-17 |
| **Historia** | Como Inquilino, quiero pagar una deuda pulsando un solo botón y usando mi tarjeta guardada para completar el pago sin salir de la app. |
| **Criterios de aceptación** | 1. Al pulsar 'Pagar' se abre un modal con resumen del cargo (concepto, importe, vivienda). <br> 2. Se muestra la tarjeta predeterminada; si no tiene ninguna guardada, se muestra formulario para añadir. <br> 3. Al confirmar, se muestra un spinner de carga durante el procesamiento (máx. 5 segundos). <br> 4. Tras pago exitoso: animación de éxito, la deuda pasa a 'Pagado' y se ofrece descargar recibo. <br> 5. Tras error: mensaje descriptivo y botón 'Reintentar'. <br> 6. No se permiten cargos duplicados si el usuario pulsa varias veces. |
| **Especificación** | API: Stripe Payment Intents con idempotency key. Seguridad: HTTPS/TLS 1.2+, nunca se envía PAN completo al backend propio. Frontend: Modal con bloqueo de botón tras primer clic (prevent double-submit). Webhooks: Stripe webhook para confirmar estado final del pago. |
| **Riesgos** | Cierre de la app durante el pago (mitigar con recuperación de estado vía webhook). Doble cobro por doble clic (mitigar con idempotency key y bloqueo de UI). |


### HU20
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-21, RNF-11 |
| **Historia** | Como Inquilino, quiero activar el auto-pago con un interruptor para que las facturas recurrentes se cobren automáticamente de mi tarjeta. |
| **Criterios de aceptación** | 1. En la pantalla 'Métodos de Pago' hay un toggle switch 'Auto-Pago' claramente visible. <br> 2. Al activar, se muestra un popup con los términos legales del cobro recurrente que el usuario debe aceptar explícitamente. <br> 3. El usuario selecciona qué tarjeta asociar al auto-pago. <br> 4. Una vez activado, se muestra la tarjeta asociada y la fecha del próximo cargo previsto. <br> 5. Al desactivar, se pide confirmación. <br> 6. Si el auto-pago falla, el sistema notifica al inquilino y desactiva el toggle automáticamente. |
| **Especificación** | Backend: Stripe Customer con Setup Intent para tokenización. Cron: Job programado (diario a las 08:00) que procesa cobros pendientes con auto-pago activo. Reintentos: Máx. 3 intentos con backoff exponencial (1h, 6h, 24h). Legal: Texto de consentimiento LOPD/SEPA almacenado con timestamp de aceptación. |
| **Riesgos** | Tarjeta caducada sin aviso (mitigar con alerta 30 días antes). Cobro en fecha errónea (mitigar con logs detallados y reconciliación). |


### HU21
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-25, RNF-11, RNF-12 |
| **Historia** | Como Inquilino, quiero gestionar mis tarjetas guardadas (añadir, eliminar, establecer predeterminada) para tener control sobre mis métodos de pago. |
| **Criterios de aceptación** | 1. La pantalla 'Métodos de Pago' lista todas las tarjetas guardadas con: máscara (•••• 4242), logo de marca, fecha de caducidad. <br> 2. Un badge 'Predeterminada' marca la tarjeta principal. <br> 3. Al añadir nueva tarjeta, se muestra un formulario seguro embebido (Stripe Elements) validando en tiempo real. <br> 4. Al eliminar, se pide confirmación. No se puede eliminar la tarjeta predeterminada si el auto-pago está activo. <br> 5. Si una tarjeta caduca en ≤ 30 días, se muestra un aviso amarillo con enlace para actualizar. |
| **Especificación** | API: Stripe Setup Intents para tokenizar. Almacenamiento: Solo token + últimos 4 dígitos + marca + caducidad. UI: Stripe Elements embebido con estilos personalizados. |
| **Riesgos** | Tarjeta eliminada que estaba asociada al auto-pago (mitigar con validación previa). |


### HU22
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-24 |
| **Historia** | Como Inquilino, quiero exportar mi historial de pagos en PDF o CSV para tener un justificante de todos los pagos realizados en una vivienda. |
| **Criterios de aceptación** | 1. Botón 'Exportar' visible en la pestaña de Historial. <br> 2. Selector de formato: PDF (visual) o CSV (datos). <br> 3. Filtros opcionales: rango de fechas y vivienda. <br> 4. El documento incluye nombre del inquilino, vivienda, lista de pagos con fecha, concepto, importe y método de pago. <br> 5. Descarga inmediata o envío al email registrado si el archivo es grande. |
| **Especificación** | Backend: Generación de archivo con pdfkit/csv-writer. Endpoint: `GET /api/inquilino/exportar`. Límite: Máximo 24 meses por exportación. |
| **Riesgos** | Archivo muy grande en CSV (mitigar con límite de rango). |


### HU23
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-18, RF-23 |
| **Historia** | Como Inquilino, quiero recibir notificaciones cuando se registre un nuevo gasto y cuando esté a punto de vencer un pago, para no olvidarme de pagar a tiempo. |
| **Criterios de aceptación** | 1. Notificación push al registrarse un nuevo gasto asignado al inquilino con concepto e importe. <br> 2. Notificación 3 días antes del vencimiento. <br> 3. Notificación el día del vencimiento. <br> 4. Notificación diaria tras vencimiento (máx. 7 días). <br> 5. Todas las notificaciones son visibles en el centro de notificaciones in-app. <br> 6. Al pulsar la notificación, se navega directamente a la tarjeta de deuda correspondiente. |
| **Especificación** | Backend: Scheduler que evalúa fechas de vencimiento a las 09:00 cada día. Deep link: Navegación directa al detalle de la deuda desde la notificación. |
| **Riesgos** | Exceso de notificaciones molesta al usuario (mitigar con configuración de frecuencia en ajustes). Notificación llega tras haber pagado (mitigar con check de estado antes de enviar). |

---

# CU-11: Gestión de Incidencias en la Vivienda


## Requisitos Funcionales

### RF-27 — Formulario de Nueva Incidencia
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe ofrecer al Inquilino una pantalla de creación de tickets que incluya: título obligatorio (máx. 100 caracteres), descripción multilínea (máx. 1000 caracteres), selector desplegable de categoría (Fontanería, Electricidad, Electrodomésticos, Cerrajería, Pintura/Paredes, Climatización, Plagas, Otro), selector de urgencia con código de color (Baja, Media, Alta, Urgente), acceso a cámara del dispositivo para fotos (máx. 5), y selector de zona del piso. |

**Historias de usuario vinculadas:** [HU24](#hu24)


### RF-28 — Línea de Tiempo de Estado
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe mostrar en la vista de detalle de cada incidencia una barra de progreso o línea de tiempo vertical que indique la fase de la reparación, con los estados: Abierta → Recibida por el casero → En Proceso → Técnico Avisado (opcional) → Resuelta por Casero → Cerrada. Cada paso debe mostrar la fecha y hora en que se alcanzó. El Casero puede avanzar el estado; el Inquilino solo puede cerrar la incidencia tras la resolución. |

**Historias de usuario vinculadas:** [HU26](#hu26), [HU30](#hu30)


### RF-29 — Pestaña de Chat Técnico
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | El sistema debe incorporar dentro del detalle de cada incidencia una pestaña de conversación dedicada, separada del chat general. Esta conversación debe permitir: enviar mensajes de texto, adjuntar fotos adicionales, y mostrar mensajes con avatar, nombre, hora y estado de lectura (doble check). Solo participan el Inquilino que abrió el ticket y el Casero/Anunciante de la vivienda. |

**Historias de usuario vinculadas:** [HU28](#hu28)


### RF-30 — Botonera de Validación del Inquilino
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe mostrar al Inquilino dos botones de acción ('Confirmar Solución' / 'Rechazar Solución') únicamente cuando la incidencia alcance el estado 'Resuelta por Casero'. Al confirmar, pasa a 'Cerrada'. Al rechazar, vuelve a 'En Proceso' con campo obligatorio de motivo. Si el Inquilino no actúa en 72 horas, el sistema cierra automáticamente la incidencia como 'Cerrada por inactividad'. |

**Historias de usuario vinculadas:** [HU27](#hu27)


### RF-31 — Listado de Incidencias (Vista Inquilino)
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe presentar al Inquilino una pantalla con la lista de todas las incidencias reportadas en sus viviendas, filtrables por: estado (Abiertas / Cerradas), categoría y vivienda. Cada elemento mostrará: título, categoría (badge de color), urgencia (badge), fecha de apertura, estado actual y miniatura de la primera foto adjunta. |

**Historias de usuario vinculadas:** [HU25](#hu25)


### RF-32 — Panel de Incidencias (Vista Casero)
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe proporcionar al Casero un panel con todas las incidencias recibidas en sus viviendas, organizadas por defecto en columnas tipo Kanban: 'Nuevas', 'En Proceso', 'Resueltas', 'Cerradas'. El Casero podrá alternar esta vista a formato lista. Cada tarjeta mostrará título, urgencia, inquilino reportador, fecha y miniatura de foto. |

**Historias de usuario vinculadas:** [HU29](#hu29)


### RF-33 — Notificaciones de Incidencias
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe enviar notificaciones push automáticas en los siguientes eventos: nueva incidencia creada (al Casero), cambio de estado (al Inquilino reportador), nuevo mensaje en el chat técnico (al destinatario), incidencia próxima al auto-cierre — al Inquilino (24h antes del plazo de 72h), e incidencia cerrada (a ambas partes). |

**Historias de usuario vinculadas:** [HU26](#hu26), [HU30](#hu30), [HU32](#hu32)


### RF-34 — Historial de Incidencias por Vivienda
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe mantener un historial completo de todas las incidencias (abiertas y cerradas) asociadas a cada vivienda, accesible tanto para el Casero como para los Inquilinos actuales. El historial debe ser buscable por texto libre y filtrable por categoría, fecha y estado. |

**Historias de usuario vinculadas:** [HU32](#hu32)


### RF-35 — Adjuntar Presupuesto de Reparación
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | El sistema debe permitir al Casero adjuntar un documento (PDF/imagen, máx. 10 MB) con el presupuesto de reparación dentro de la vista de detalle de la incidencia. El Inquilino podrá visualizar dicho documento. Opcionalmente, el Casero puede indicar si el coste será compartido, en cuyo caso el sistema ofrecerá la opción de generar un gasto en el CU-10 vinculado a la incidencia. |

**Historias de usuario vinculadas:** [HU31](#hu31)


## Requisitos de Información

### RI-11 — Incidencia
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alto |

**Atributos:**
- `ID_Incidencia` (autogenerado, formato INC-XXXX)
- `ID_Vivienda` (FK a Vivienda)
- `ID_Inquilino_Reportador` (FK a Usuario)
- `ID_Casero` (FK a Usuario)
- `Titulo` — máx. 100 caracteres
- `Descripcion` — máx. 1000 caracteres
- `Categoria` — Enum: Fontanería / Electricidad / Electrodomésticos / Cerrajería / Pintura / Climatización / Plagas / Otro
- `Zona_Piso` — Enum: Cocina / Baño / Salón / Dormitorio / Zonas_Comunes / Exterior
- `Urgencia` — Enum: Baja (verde) / Media (amarillo) / Alta (naranja) / Urgente (rojo)
- `Estado` — Enum: Abierta / Recibida / En_Proceso / Tecnico_Avisado / Resuelta / Cerrada / Cerrada_Inactividad
- `Fotos` — array de URLs (máx. 5 elementos)
- `Presupuesto_URL` (opcional)
- `Coste_Compartido` (Boolean)
- `Fecha_Apertura`
- `Fecha_Ultima_Actualizacion`
- `Fecha_Cierre` — null si abierta
- `Historial_Estados` — array de {estado, fecha, usuario}


## Requisitos No Funcionales

### RNF-13 — Privacidad de Incidencias
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | Datos de incidencias solo accesibles para: Inquilino del ticket, Casero y administradores. Excepción: incidencias en zonas comunes → otros inquilinos ven estado pero no el chat. |


## Historias de Usuario

### HU24
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-27 |
| **Historia** | Como Inquilino, quiero abrir un ticket de incidencia describiendo la avería, seleccionando categoría, zona y urgencia, y adjuntando fotos, para que el Casero reciba toda la información necesaria para actuar. |
| **Criterios de aceptación** | 1. El formulario incluye campos obligatorios: título, descripción, categoría (desplegable) y urgencia (selector con colores). <br> 2. Campo opcional de zona del piso. <br> 3. Se pueden adjuntar hasta 5 fotos desde la cámara o galería, con previsualización y opción de eliminar cada una. <br> 4. Las fotos se comprimen en el cliente antes de subir (máx. 2 MB por foto tras compresión). <br> 5. Al enviar, se muestra confirmación con el número de ticket (INC-XXXX) y se notifica al Casero. <br> 6. Si la subida de fotos falla, el ticket se guarda como borrador con las fotos ya subidas. |
| **Especificación** | Permisos: Solicitar Camera/Storage Access en tiempo de ejecución. Compresión: Client-side resize a máx. 1920px de ancho manteniendo aspect ratio. Backend: `POST /api/incidencias` con multipart/form-data. |
| **Riesgos** | Fotos oscuras/borrosas inutilizables (mitigar con sugerencia de flash y encuadre). |


### HU25
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-31 |
| **Historia** | Como Inquilino, quiero ver un listado de todas mis incidencias con filtros por estado y categoría para hacer seguimiento fácilmente. |
| **Criterios de aceptación** | 1. Lista de incidencias ordenada por fecha descendente con tarjetas que muestran: título, categoría (badge color), urgencia (badge), fecha, estado actual y miniatura de primera foto. <br> 2. Filtros en la cabecera: estado (Abiertas/Cerradas/Todas), categoría (desplegable), vivienda (si tiene varias). <br> 3. Badge de contador en la pestaña de Incidencias del menú indicando número de tickets abiertos. <br> 4. Al pulsar una tarjeta, se navega al detalle completo de la incidencia. |
| **Especificación** | Backend: `GET /api/incidencias?estado={enum}&categoria={enum}&vivienda={id}`. UI: FlatList/RecyclerView con lazy loading de imágenes. Badge: Actualizado en tiempo real vía WebSocket o polling. |
| **Riesgos** | Lista vacía sin contexto (mitigar con empty state ilustrado y texto explicativo). |


### HU26
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-28, RF-33, RNF-13 |
| **Historia** | Como Inquilino, quiero ver la línea de tiempo de mi incidencia con fechas y estados para saber en qué punto está la reparación. |
| **Criterios de aceptación** | 1. Vista de detalle muestra una línea de tiempo vertical con los estados alcanzados resaltados y los pendientes en gris. <br> 2. Cada estado muestra la fecha y hora en que se alcanzó. <br> 3. El estado actual está destacado con indicador pulsante (dot animation). <br> 4. Si el Casero añade una nota al cambiar el estado, se muestra junto al paso correspondiente. <br> 5. Al cambiar de estado, el Inquilino recibe notificación push con el nuevo estado y nota del Casero. |
| **Especificación** | UI: Componente Stepper/Timeline vertical. Backend: Campo `historial_estados` (array de {estado, fecha, usuario, nota}). |
| **Riesgos** | Casero no actualiza el estado (mitigar con recordatorios automáticos tras 48h sin actividad). |


### HU27
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-30 |
| **Historia** | Como Inquilino, quiero confirmar o rechazar la solución propuesta por el Casero para cerrar la incidencia o reabrirla si el problema persiste. |
| **Criterios de aceptación** | 1. Los botones 'Confirmar Solución' y 'Rechazar Solución' aparecen solo cuando el estado es 'Resuelta por Casero'. <br> 2. Al confirmar, la incidencia pasa a 'Cerrada' con fecha de cierre y ambas partes reciben notificación. <br> 3. Al rechazar, se muestra un campo de texto obligatorio para indicar el motivo y la incidencia vuelve a 'En Proceso'. <br> 4. El Casero recibe notificación del rechazo con el motivo. <br> 5. Si el Inquilino no actúa en 72 horas, la incidencia se cierra automáticamente como 'Cerrada por inactividad'. <br> 6. 24 horas antes del auto-cierre, se envía un recordatorio push al Inquilino. |
| **Especificación** | Lógica: Renderizado condicional de botones basado en estado. Timeout: Job programado que revisa incidencias en 'Resuelta' > 72h. Push: Recordatorio a las 48h tras resolución. |
| **Riesgos** | Inquilino inactivo que no cierra ni rechaza (mitigar con auto-cierre de 72h). |


### HU28
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-29, RNF-13 |
| **Historia** | Como Inquilino, quiero enviar mensajes y fotos adicionales en el chat de la incidencia para proporcionar más información al Casero sobre la avería. |
| **Criterios de aceptación** | 1. La pestaña de chat dentro de la incidencia muestra los mensajes con avatar, nombre, hora y estado de lectura. <br> 2. El Inquilino puede escribir texto y adjuntar fotos. <br> 3. Los mensajes de sistema (cambios de estado) aparecen centrados con fondo diferente. <br> 4. El chat se actualiza en tiempo real sin necesidad de refrescar. <br> 5. Al recibir un nuevo mensaje del Casero, se muestra notificación push si la app está en segundo plano. |
| **Especificación** | Backend: WebSocket. |
| **Riesgos** | Mensajes perdidos por mala conexión (mitigar con cola de mensajes pendientes y reenvío). |


### HU29
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-32 |
| **Historia** | Como Casero, quiero ver todas las incidencias de mis viviendas organizadas en columnas Kanban (Nuevas, En Proceso, Resueltas, Cerradas) para gestionar las reparaciones de forma visual. |
| **Criterios de aceptación** | 1. Panel con columnas tipo Kanban donde cada tarjeta muestra: título, urgencia (color), inquilino (avatar + nombre), fecha, miniatura de foto. <br> 2. El Casero puede alternar entre vista Kanban y vista lista. <br> 3. Las incidencias 'Urgentes' aparecen con borde rojo y en la parte superior de su columna. <br> 4. Se muestra un contador de incidencias por columna. <br> 5. Al pulsar una tarjeta se accede al detalle completo con timeline, chat y acciones. |
| **Especificación** | UI: Componente Kanban con drag (opcional para cambiar estado) o vista lista alternativa. Backend: `GET /api/casero/incidencias?vivienda={id}`. Filtros: Por vivienda (si tiene varias). |
| **Riesgos** | Muchas incidencias acumuladas dificultan la gestión (mitigar con filtros y ordenación por urgencia). |


### HU30
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-28, RF-33 |
| **Historia** | Como Casero, quiero cambiar el estado de una incidencia (En Proceso, Técnico Avisado, Resuelta) para que el Inquilino vea el progreso de la reparación. |
| **Criterios de aceptación** | 1. En el detalle de la incidencia, el Casero dispone de un selector de estado que muestra solo las transiciones válidas desde el estado actual. <br> 2. Al cambiar estado, puede añadir una nota explicativa opcional. <br> 3. El cambio se refleja inmediatamente en la línea de tiempo con fecha y nota. <br> 4. Se envía notificación push al Inquilino con el nuevo estado y la nota. <br> 5. No se puede retroceder a un estado anterior (solo avanzar en la línea de tiempo). |
| **Especificación** | Backend: `PATCH /api/incidencias/{id}/estado` con validación de transiciones permitidas. Push: FCM con payload {titulo_incidencia, nuevo_estado, nota}. Auditoría: Cada cambio se registra en `historial_estados`. |
| **Riesgos** | Casero olvida actualizar el estado (mitigar con recordatorios automáticos). |


### HU31
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-35 |
| **Historia** | Como Casero, quiero adjuntar un presupuesto de reparación a una incidencia para que el Inquilino conozca el coste estimado. |
| **Criterios de aceptación** | 1. Botón 'Adjuntar Presupuesto' visible en el detalle de incidencias con estado 'En Proceso' o superior. <br> 2. Permite subir PDF o imagen (máx. 10 MB) con previsualización. <br> 3. El Casero puede indicar si el coste será compartido con los inquilinos mediante un checkbox. <br> 4. Si marca coste compartido, se ofrece un enlace para crear un gasto (CU-10) vinculado a la incidencia. <br> 5. El Inquilino recibe notificación de que hay un presupuesto adjunto. |
| **Especificación** | Backend: Endpoint `PATCH /api/incidencias/{id}/presupuesto`. Vinculación: Campo opcional `ID_Factura` en la incidencia. |
| **Riesgos** | Presupuesto confuso o incompleto (mitigar con preview y validación de formato). |


### HU32
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-33, RF-34 |
| **Historia** | Como Casero, quiero consultar el historial completo de incidencias de una vivienda para documentar el mantenimiento realizado. |
| **Criterios de aceptación** | 1. Pantalla de historial filtrable por categoría, rango de fechas y estado. <br> 2. Búsqueda por texto libre (busca en título y descripción). <br> 3. Cada entrada muestra: título, categoría, urgencia, fecha de apertura, fecha de cierre y duración total de resolución. <br> 4. Al pulsar, se accede al detalle completo (incluso de incidencias cerradas). <br> 5. Dato agregado en la cabecera: nº total de incidencias, tiempo medio de resolución, categoría más frecuente. |
| **Especificación** | Backend: `GET /api/casero/incidencias/historial?vivienda={id}&buscar={texto}&desde={fecha}&hasta={fecha}`. Cálculo: Tiempo medio = AVG(fecha_cierre - fecha_apertura) de incidencias cerradas. |
| **Riesgos** | Historial muy extenso (mitigar con paginación y filtros). |

---

# CU-12: Reseñas y Valoración de Convivencia

## Requisitos Funcionales

### RF-36 — Tarjeta de Valoración Pendiente
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe hacer aparecer una tarjeta de llamada a la acción ('Valora tu experiencia') en la pantalla principal (Home) del usuario una vez que se detecte la finalización del contrato o que el Casero marque el fin de la convivencia. La tarjeta debe incluir: foto y nombre de la persona/vivienda a valorar, un botón 'Valorar ahora' y un enlace 'Recordarme más tarde' que pospone la tarjeta 48 horas. Si el usuario ignora la tarjeta, se mostrarán recordatorios progresivos durante 30 días naturales. |

**Historias de usuario vinculadas:** [HU33](#hu33), [HU36](#hu36), [HU38](#hu38), [HU42](#hu42)


### RF-37 — Interfaz de Estrellas y Etiquetas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe presentar un formulario de reseña compuesto por: (a) puntuación global mediante componente de 5 estrellas interactivas (obligatorio, mínimo 1 estrella); (b) puntuaciones por categorías específicas (1–5 estrellas); (c) una nube de etiquetas pulsables (chips) positivas y negativas preconfiguradas; (d) un campo de texto libre opcional (máx. 500 caracteres). |

**Historias de usuario vinculadas:** [HU33](#hu33), [HU36](#hu36), [HU38](#hu38)


### RF-38 — Sistema de Ciego Mutuo
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe implementar un mecanismo de 'Ciego Mutuo': ambas partes podrán enviar su valoración de forma independiente, pero ninguna será visible hasta que ambas hayan sido enviadas (o hasta que expire el plazo de 30 días). Mientras la reseña esté oculta, el perfil público del valorado mostrará una tarjeta con efecto blur y el texto 'Reseña pendiente de reciprocidad'. |

**Historias de usuario vinculadas:** [HU34](#hu34)


### RF-39 — Hilo de Réplica
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe permitir al usuario valorado escribir una respuesta única a cada reseña recibida. La réplica (máx. 300 caracteres) se mostrará anidada visualmente debajo de la reseña original en el perfil público, con fondo de color diferenciado e indicación de 'Respuesta del propietario/inquilino'. Solo se permite una réplica por reseña, no editable una vez publicada. |

**Historias de usuario vinculadas:** [HU39](#hu39)


### RF-41 — Visualización de Reseñas en Perfil Público
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe mostrar en el perfil público de cada usuario una sección de 'Valoraciones' que incluya: puntuación media global, número total de reseñas, desglose visual por categoría (barras de progreso horizontales), etiquetas más frecuentes (nubes de tags con contador), y lista de reseñas individuales ordenadas por fecha (más reciente primero). |

**Historias de usuario vinculadas:** [HU35](#hu35), [HU37](#hu37)


### RF-42 — Moderación de Contenido
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe someter todas las reseñas y réplicas a un proceso de moderación automática antes de su publicación. El filtro debe detectar y bloquear: lenguaje ofensivo o discriminatorio, datos personales e información falsa manifiesta. Las reseñas rechazadas quedarán en estado 'En revisión' y se notificará al autor para que la edite. Si no se edita en 7 días, se descarta. |

**Historias de usuario vinculadas:** [HU41](#hu41)


### RF-43 — Reportar Reseña Inadecuada
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe incluir en cada tarjeta de reseña pública un botón o icono de 'Reportar' que permita a cualquier usuario registrado informar de contenido inapropiado. Al pulsar, se mostrará un selector con motivos predefinidos (Lenguaje ofensivo, Información falsa, Spam, Datos personales, Otro) y un campo de texto libre opcional. |

**Historias de usuario vinculadas:** [HU40](#hu40)


### RF-44 — Resumen de Reputación en Tarjetas de Swipe/Solicitud
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alta |
| **Descripción** | El sistema debe mostrar un resumen compacto de la reputación del usuario (puntuación media + nº de reseñas + 3 etiquetas más frecuentes) en: (a) las tarjetas de pisos durante el swipe (reputación del Casero); (b) las tarjetas de solicitudes que ve el Casero (reputación del Inquilino); (c) las tarjetas de búsqueda de compañeros. Al pulsar sobre el resumen se navega al perfil completo de reseñas. |

**Historias de usuario vinculadas:** [HU35](#hu35), [HU37](#hu37)


### RF-45 — Recordatorios de Valoración
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | El sistema debe enviar notificaciones push de recordatorio para valorar en los siguientes momentos: (a) al detectar fin de contrato o desvinculación; (b) a las 48h si se pospuso; (c) a los 7 días si no se ha valorado; (d) a los 21 días como último aviso. Tras 30 días sin acción, el periodo se cierra y se publica la reseña de la otra parte (si existe) unilateralmente. |

**Historias de usuario vinculadas:** [HU42](#hu42)


## Requisitos de Información

### RI-13 — Valoracion
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alto |

**Atributos:**
- `ID_Valoracion` (autogenerado)
- `ID_Autor` (FK a Usuario)
- `ID_Valorado` (FK a Usuario)
- `ID_Convivencia` (FK a Convivencia)
- `Puntuacion_Global` — número de estrellas (1–5, decimal con 1 posición)
{Limpieza: 4, Convivencia: 5, ...}
- `Comentario` — texto libre (máx. 500 caracteres, nullable)
- `Replica` — texto de respuesta (máx. 300 caracteres, nullable)
- `Fecha_Creacion`
- `Publicada`
- `Respuesta`


### RI-14 — ResumenReputacion
| Campo | Valor |
|-------|-------|
| **Prioridad** | Alto |

**Atributos:**
- `ID_Usuario`
- `Media_Global` — media aritmética de todas las puntuaciones globales recibidas (1 decimal)
- `Total_Resenas` — número total de reseñas publicadas
- `Medias_Categoria` — objeto con media por cada categoría valorada
- `Top_Etiquetas` — array de las 5 etiquetas más frecuentes con contador
- `Etiquetas_Positivas_Count`
- `Etiquetas_Negativas_Count`
- `Ultima_Resena_Fecha`


## Requisitos No Funcionales

### RNF-14 — Anonimización Parcial de Reseñas en Moderación
| Campo | Valor |
|-------|-------|
| **Prioridad** | Baja |
| **Descripción** | Revisores de moderación solo ven: ID anónimo, texto y puntuaciones. Sin acceso a datos personales completos. Previene sesgos. |


### RNF-15 — Inmutabilidad de Reseñas Publicadas
| Campo | Valor |
|-------|-------|
| **Prioridad** | Media |
| **Descripción** | Valoraciones no modificables ni eliminables tras publicación. Solo moderación puede ocultar si hay infracción confirmada. Autor puede solicitar eliminación vía soporte, no directamente. |


## Historias de Usuario

### HU33
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-36, RF-37 |
| **Historia** | Como Inquilino, quiero recibir un aviso al finalizar mi contrato y poder valorar al Casero con estrellas, etiquetas y un comentario, para que futuros inquilinos conozcan mi experiencia. |
| **Criterios de aceptación** | 1. Al detectarse fin de contrato, aparece una tarjeta 'Valora tu experiencia con [nombre Casero]' en el Home. <br> 2. La tarjeta incluye foto del Casero, nombre de la vivienda y botones 'Valorar ahora' / 'Recordarme más tarde'. <br> 3. 'Recordarme más tarde' pospone 48 horas. <br> 4. El formulario incluye: puntuación global (1–5 estrellas, obligatorio), puntuaciones por categoría (Mantenimiento, Comunicación, Resolución de incidencias, Honestidad, Relación calidad-precio), chips seleccionables (mín. 1 etiqueta) y comentario libre (máx. 500 caracteres, opcional). <br> 5. Antes de enviar se muestra una pantalla de confirmación/resumen. <br> 6. Tras enviar, se muestra mensaje: 'Tu valoración se publicará cuando ambas partes hayan valorado'. |
| **Especificación** | UI: Star Rating Component con feedback háptico. Chips: Array de strings predefinidos, seleccionables con toggle visual. Validación: Mín 1 estrella global + mín 1 etiqueta. Backend: `POST /api/valoraciones`. Estado inicial: 'Oculta_Ciego_Mutuo'. |
| **Riesgos** | Valoración accidental (mitigar con pantalla de confirmación). Usuario no valora nunca (mitigar con recordatorios progresivos y cierre a los 30 días). |


### HU34
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-38, RNF-15 |
| **Historia** | Como Inquilino, quiero que mi reseña permanezca oculta hasta que el Casero también valore, para evitar represalias y garantizar honestidad. |
| **Criterios de aceptación** | 1. Tras enviar la reseña, el perfil del Casero muestra una tarjeta borrosa (blur) con texto 'Reseña pendiente de reciprocidad'. <br> 2. El Inquilino ve en su historial de reseñas enviadas el estado 'Oculta — esperando a la otra parte'. <br> 3. Cuando ambas partes han valorado, las reseñas se publican simultáneamente y se notifica a ambos. <br> 4. Si el Casero no valora en 30 días, la reseña del Inquilino se publica unilateralmente y se notifica. <br> 5. Una vez publicada, la reseña no puede modificarse ni eliminarse por el autor. |
| **Especificación** | Frontend: `CSS filter: blur(8px)` sobre tarjeta de reseña oculta. Backend: Flag estado='Oculta_Ciego_Mutuo' → 'Publicada' cuando ambas existen o tras 30 días. Job: Scheduler diario que revisa reseñas pendientes > 30 días. |
| **Riesgos** | Confusión del usuario al ver 'Oculta' (mitigar con tooltip explicativo). Una parte nunca valora (mitigar con publicación unilateral tras 30 días). |


### HU35
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-41, RF-44 |
| **Historia** | Como Inquilino, quiero ver la reputación de un Casero (puntuación media, reseñas, etiquetas frecuentes) en su perfil y en las tarjetas de pisos durante el swipe, para tomar decisiones informadas. |
| **Criterios de aceptación** | 1. En las tarjetas de pisos (swipe) se muestra: puntuación media (X.X / 5.0), nº de reseñas y las 3 etiquetas más frecuentes del Casero. <br> 2. Al pulsar sobre la sección de reputación, se navega al perfil completo del Casero. <br> 3. El perfil muestra: media global (número + estrellas), nº total de reseñas, desglose por categoría (barras de progreso), nube de etiquetas con contador y lista de reseñas individuales paginadas. <br> 4. Cada reseña muestra: estrellas, etiquetas, comentario, fecha, y réplica del Casero (si existe). <br> 5. Ordenación por defecto: más recientes primero; opción de ordenar por puntuación. |
| **Especificación** | Backend: `GET /api/usuarios/{id}/reputacion` (datos agregados cacheados). Caché: Invalidar al publicar nueva reseña (Redis con TTL). UI: Barras de progreso horizontales por categoría, tag cloud. Paginación: 10 reseñas por página con scroll infinito. |
| **Riesgos** | Perfil sin reseñas da impresión de desconfianza (mitigar mostrando 'Nuevo en ROOMA' con icono amigable). |


### HU36
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-36, RF-37 |
| **Historia** | Como Casero, quiero valorar a un Inquilino al finalizar su estancia con puntuaciones específicas (Limpieza, Convivencia, Puntualidad en pagos, Respeto de normas, Comunicación), para ayudar a otros caseros. |
| **Criterios de aceptación** | 1. Al finalizar la convivencia, aparece tarjeta 'Valora a [nombre Inquilino]' en el panel del Casero. <br> 2. El formulario incluye: puntuación global (1–5), puntuaciones por categorías de inquilino, chips de etiquetas y comentario opcional. <br> 3. El Casero puede valorar a cada inquilino de la vivienda de forma individual. <br> 4. Si hay varios inquilinos que terminan a la vez, se presentan las tarjetas de valoración una detrás de otra. <br> 5. Mismas reglas de ciego mutuo que para el Inquilino. |
| **Especificación** | Backend: Misma entidad Valoracion con `Tipo_Relacion = 'Casero_Valora_Inquilino'`. UI: Mismo componente de formulario con categorías adaptadas al perfil. Validación: Mín 1 estrella + mín 1 etiqueta. |
| **Riesgos** | Casero con muchos inquilinos se satura de tarjetas de valoración (mitigar con cola secuencial y opción 'Valorar más tarde'). |


### HU37
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-41, RF-44 |
| **Historia** | Como Casero, quiero ver la reputación de un Inquilino en su solicitud de interés y en la lista de candidatos, para decidir si acepto su solicitud. |
| **Criterios de aceptación** | 1. En las tarjetas de solicitudes que ve el Casero se muestra: puntuación media, nº de reseñas y 3 etiquetas más frecuentes del Inquilino. <br> 2. Al pulsar se navega al perfil completo de reseñas del Inquilino. <br> 3. El perfil muestra las mismas secciones que el del Casero pero con categorías de inquilino. <br> 4. Si el inquilino no tiene reseñas, se muestra 'Nuevo en ROOMA — sin valoraciones aún'. |
| **Especificación** | Backend: Mismo endpoint `/api/usuarios/{id}/reputacion`. UI: Componente reutilizable de resumen de reputación. |
| **Riesgos** | Sesgo hacia usuarios nuevos sin reseñas (mitigar con badge 'Nuevo' que sea neutral). |


### HU38
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-36, RF-37 |
| **Historia** | Como Compañero de piso, quiero valorar a otro compañero con el que he convivido, para que la comunidad conozca su estilo de convivencia. |
| **Criterios de aceptación** | 1. Al finalizar la convivencia (desvinculación del piso), se habilita la opción de valorar a cada compañero por separado. <br> 2. Categorías específicas para compañeros: Limpieza, Convivencia, Ruido, Respeto de espacios comunes, Comunicación. <br> 3. Chips de etiquetas adaptados: 'Silencioso', 'Ordenado', 'Buen ambiente', 'Fiestero', 'Ruidoso', etc. <br> 4. Mismas reglas de ciego mutuo. <br> 5. Las valoraciones entre compañeros se distinguen visualmente en el perfil ('Valoración de compañero de piso'). |
| **Especificación** | Backend: `Tipo_Relacion = 'Compañero_Valora_Compañero'`. UI: Reutilización del componente de valoración con categorías personalizadas. |
| **Riesgos** | Compañeros que se ponen de acuerdo para valorarse positivamente sin honestidad (mitigar con moderación y detección de patrones). |


### HU39
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-39 |
| **Historia** | Como Usuario valorado, quiero poder escribir una réplica a una reseña que he recibido para dar mi versión de los hechos. |
| **Criterios de aceptación** | 1. Debajo de cada reseña recibida publicada aparece un botón 'Responder' (solo si no hay réplica previa). <br> 2. Al pulsar, se abre un campo de texto (máx. 300 caracteres) con contador de caracteres. <br> 3. Se muestra pantalla de confirmación antes de publicar. <br> 4. La réplica se muestra anidada visualmente debajo de la reseña con fondo diferenciado y etiqueta 'Respuesta de [rol]'. <br> 5. Solo se permite una réplica por reseña, no editable una vez publicada. <br> 6. La réplica pasa por el mismo filtro de moderación que las reseñas. |
| **Especificación** | Backend: `PATCH /api/valoraciones/{id}/replica`. Moderación: Mismo pipeline que las reseñas. UI: Card anidada con indent y fondo de color diferente. |
| **Riesgos** | Réplica ofensiva (mitigar con moderación automática antes de publicar). |


### HU40
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-43 |
| **Historia** | Como Usuario, quiero poder reportar una reseña que considero inapropiada o falsa para que el equipo de moderación la revise. |
| **Criterios de aceptación** | 1. Cada tarjeta de reseña pública incluye un icono de menú (tres puntos) con opción 'Reportar'. <br> 2. Al pulsar, se muestra un selector de motivos: Lenguaje ofensivo, Información falsa, Spam, Datos personales, Otro. <br> 3. Campo de texto libre opcional para detalles adicionales. <br> 4. Tras enviar, se muestra confirmación: 'Tu reporte ha sido recibido. Lo revisaremos en un plazo de 48 horas'. <br> 5. La reseña reportada permanece visible hasta que la moderación decida (excepto si acumula ≥ 3 reportes). <br> 6. El usuario reportador recibe notificación del resultado de la moderación. |
| **Especificación** | Backend: `POST /api/valoraciones/{id}/reportes`. Moderación: Cola de revisión con dashboard interno para moderadores. Umbral: Si una reseña acumula ≥ 3 reportes distintos, se oculta automáticamente hasta revisión. |
| **Riesgos** | Reportes falsos para ocultar reseñas legítimas (mitigar con umbral de múltiples reportes y revisión humana). |


### HU41
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-42, RNF-14 |
| **Historia** | Como Usuario, quiero que las reseñas pasen por un filtro de moderación automático antes de publicarse para evitar contenido ofensivo o datos personales expuestos. |
| **Criterios de aceptación** | 1. Al enviar una reseña, se procesa por un filtro automático que detecta: lenguaje ofensivo, datos personales (teléfonos, emails), URLs y contenido discriminatorio. <br> 2. Si el filtro detecta contenido problemático, la reseña queda en estado 'En revisión' y el autor recibe notificación con los fragmentos señalados. <br> 3. El autor puede editar y reenviar la reseña (solo en estado 'En revisión', antes de publicación). <br> 4. Si no edita en 7 días, la reseña se descarta y se notifica al autor. <br> 5. Las reseñas que pasan el filtro se publican según las reglas de ciego mutuo. |
| **Especificación** | Backend: Servicio de moderación con regex para PII + API de detección de lenguaje ofensivo (Perspective API o similar). Estados: Pendiente_Moderacion → Oculta_Ciego_Mutuo (si pasa) o Rechazada (si no pasa). Timeout: Job a los 7 días que descarta reseñas rechazadas sin editar. |
| **Riesgos** | Falsos positivos del filtro automático (mitigar permitiendo edición y reenvío). |


### HU42
| Campo | Detalle |
|-------|---------|
| **Requisitos** | RF-36, RF-45 |
| **Historia** | Como Usuario, quiero recibir recordatorios progresivos para valorar mi experiencia y que el sistema cierre el periodo si no actúo, para no quedar en un limbo. |
| **Criterios de aceptación** | 1. Recordatorio al detectar fin de convivencia (tarjeta en Home + push). <br> 2. Si pospone: push a las 48 horas. <br> 3. Si ignora: push a los 7 días. <br> 4. Último aviso: push a los 21 días. <br> 5. A los 30 días, el sistema cierra el periodo sin reseña y publica la de la otra parte (si existe). <br> 6. El usuario puede desactivar los recordatorios desde ajustes (pero el plazo de 30 días sigue vigente). |
| **Especificación** | Backend: Scheduler con tabla de `recordatorios_pendientes` y estados. Config: Flag en ajustes de usuario para silenciar recordatorios de valoración. |
| **Riesgos** | Exceso de notificaciones percibido como spam (mitigar con frecuencia progresiva y opción de silenciar). |




