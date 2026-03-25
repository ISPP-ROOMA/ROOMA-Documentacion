# ROOMA
# Requisitos de información

## CU-01: Descubrimiento de Viviendas

### RI-03: Vivienda
**Descripción:** El sistema debe almacenar para cada inmueble los siguientes datos obligatorios:
- **Título:** Nombre descriptivo del anuncio para atraer buscadores.
- **Descripción:** Texto detallado con las características e condiciones del piso.
- **Precio:** Valor numérico del alquiler mensual.
- **Gastos:** Especificación de suministros incluidos o adicionales.
- **Ubicación:** Coordenadas e zona para el filtrado en el mapa.
- **Estado:** Indicador de disponibilidad (Activo | Pausado | Cerrado).
- **Nº máximo de inquilinos.**

### RI-04: FotosViviendas
**Descripción:** El sistema debe gestionar la información individual de cada archivo visual:
- **ID_Vivienda:** Referencia al inmueble al que pertenece el archivo.
- **URL_Imagen:** Enlace directo al almacenamiento del recurso visual.
- **Orden:** Posición numérica del archivo dentro de la galería.
- **Portada:** Indicador binario para definir la imagen principal del deck.

### RI-06: ReglasVivienda
**Descripción:** El sistema debe almacenar las normas de convivencia mediante indicadores booleanos para facilitar el filtrado:
- **ID_Vivienda:** Referencia al inmueble al que se aplican estas normas.
- **Permite_Mascotas:** Indicador booleano (Sí | No) sobre la aceptación de animales.
- **Permite_Fumadores:** Indicador booleano (Sí | No) sobre el consumo de tabaco en el inmueble.
- **Fiestas_Permitidas:** Indicador booleano (Sí | No) sobre la realización de eventos sociales.

---

## CU-02: Gestión de Candidatos y Match

### RI-21: Match
**Descripción:** El sistema debe guardar los datos relacionados con el match:
- **ID:** Identificador único.
- **ID_Usuario (candidato):** Referencia al perfil (FK).
- **ID_Apartamento:** Referencia al inmueble (FK).
- **InteresCasero:** Indicador de interés por parte del anunciante.
- **InteresInquilino:** Indicador de interés por parte del buscador.
- **Fecha del Match:** Timestamp del momento del interés mutuo.
- **Estado del Match:** (Activo | Match | Rechazado | Exitoso).

---

## CU-03: Sistema de Chats

### RI-12: Mensaje
**Descripción:** Datos para la vista de cualquier chat dentro del sistema:
- **ID_Mensaje:** Identificador único (autogenerado).
- **ID_Incidencia:** Ticket asociado (FK) si el mensaje es de soporte técnico.
- **ID_Remitente:** Usuario que envía (FK).
- **Nombre_Remitente:** Nombre para mostrar en la burbuja de chat.
- **Tipo (Enum):** Texto | Imagen | Sistema.
- **Contenido:** Texto del mensaje o URL de la imagen adjunta.
- **Fecha_Envio:** Timestamp de envío.
- **Leido (Boolean):** Indicador de lectura.
- **Fecha_Lectura:** Timestamp de cuando fue leído (null si no leído).

### RI-15: Citas | Visitas
**Descripción:** Datos a almacenar para cada visita que se concrete:
- **ID_Usuario1:** Usuario que crea la cita.
- **ID_Usuario2:** Usuario que acepta la cita.
- **Fecha:** Fecha e hora de la cita acordada.
- **Ubicación:** Lugar de enlace que impone quien crea la cita.

---

## CU-04: Gestión de notificaciones

### RI-01: Notificación
**Descripción:** El sistema debe almacenar e mostrar para cada notificación los siguientes datos obligatorios:
- **Identificador de origen:** Usuario que originó el mensaje o evento.
- **Tipo de evento:** Categoría (Match | Mensaje | Pago pendiente).
- **Fecha e hora:** Momento exacto del evento.
- **Descripción:** Mensaje breve sobre el contenido.
- **Leido:** Indicador binario de estado.
- **Enlace directo:** URL para acceder rápidamente al evento.

---

## CU-05: Sistema de favoritos

### RI-02: Elemento Guardado
**Descripción:** Entidad relacional que vincula de forma única a un Usuario con una Vivienda específica:
- **ID_Usuario:** Referencia al buscador.
- **ID_Vivienda:** Referencia al inmueble.
- **Favorito:** Indicador booleano de guardado.

---

## CU-06: Gestión de inmuebles

### RI-05: MiembrosViviendas
**Descripción:** El sistema debe almacenar los datos de los usuarios que ya habitan el inmueble:
- **ID_Vivienda:** Vínculo con el inmueble específico.
- **ID_Usuario:** Referencia al perfil conviviente.
- **Rol:** Tipo de habitante (Propietario | Inquilino principal | Compañero).
- **Fecha_Ingreso:** Fecha de vinculación del miembro.
- **Fecha de salida:** Fecha de abandono prevista (puede ser null).

---

## CU-07: Gestión de cuentas y perfil

### RI-16: Usuario
**Descripción:** Datos maestros del perfil e cuenta:
- **ID_Usuario:** (PK autogenerada).
- **Email:** (único e indexado).
- **PasswordHash:** Contraseña cifrada.
- **Nombre e Apellido:** Datos personales.
- **Fecha_Nacimiento | Telefono | Foto_Perfil_URL.**
- **Estado_Cuenta (Enum):** Pendiente_Verificacion | Activa | Suspendida | Banneada.
- **Fecha_Alta | Fecha_Ultima_Conexion.**
- **Etiquetas de información | Género | Fumador (Boolean).**
- **Rol en la aplicación:** (Casero | Inquilino).

### RI-17: Tokens de Seguridad
**Descripción:** Gestión de tokens para procesos críticos:
- **ID_Token | ID_Usuario | Token_Hash.**
- **Tipo:** (EmailVerification | PasswordReset).
- **Fecha_Expiracion | Usado (Boolean) | Intentos.**

### RI-18: ProveedorOAuth
**Descripción:** Registro de vinculaciones con terceros:
- **ID_Usuario | Proveedor (Google | Apple | Facebook) | Proveedor_UserID.**
- **Email_Proveedor | Email_Verificado (Boolean) | Fecha_Vinculacion.**

### RI-19: Seguridad 2FA
**Descripción:** Datos para doble factor e recuperación:
- **TwoFactor:** Secret_Encrypted | Activo (Boolean).
- **RecoveryCodes:** Lista hashed de códigos de un solo uso.

### RI-20: Audit Log
**Descripción:** Registro inmutable de eventos críticos:
- **ID_Evento | ID_Usuario | Tipo_Evento | Timestamp | IP | Agent | Detalle (JSON).**

---

## CU-08: Filtros avanzados para arrendador

Este caso de uso utiliza principalmente los datos definidos en RI-03, RI-06 y el algoritmo de afinidad basado en los perfiles RI-16.

---

## CU-09: Gestión de facturas y pagos

### RI-07: FacturaGasto
**Descripción:** Datos de la cabecera del gasto registrado:
- **ID_Factura | ID_Vivienda | ID_Casero.**
- **Concepto (Enum):** Alquiler | Luz | Agua | Gas | Internet | Comunidad | Otro.
- **Importe_Total (Decimal) | Moneda (EUR).**
- **Periodo_Consumo_Inicio | Periodo_Consumo_Fin | Fecha_Vencimiento.**
- **Modo_Reparto (Enum):** Partes_Iguales | Porcentaje | Importe_Fijo.
- **Estado_Global:** Pendiente | Parcialmente_Cobrado | Cobrado | Anulado.
- **Archivo_URL | Archivo_Nombre | Archivo_Tamaño.**

### RI-08: DeudaInquilino
**Descripción:** Datos para la tarjeta de deuda individual:
- **ID_Deuda | ID_Factura | ID_Usuario.**
- **Cuota (Decimal) | Porcentaje.**
- **Estado (Enum):** Pendiente | Procesando | Pagado | Vencido | Rechazado.
- **ID_Transaccion | Fecha_Pago.**
- **Semaforo (Derivado):** Verde | Amarillo | Rojo | Gris.

### RI-09: TransaccionPago
**Descripción:** Registro de cada operación financiera:
- **ID_Transaccion | ID_Deuda | ID_Usuario.**
- **Importe | Metodo_Pago_ID | Codigo_Pasarela.**
- **Estado (Enum):** Pendiente | Exitoso | Fallido | Reembolsado.
- **Es_AutoPago (Boolean).**

### RI-10: MetodoPago
**Descripción:** Gestión de tarjetas tokenizadas:
- **ID_Usuario | Token_Pasarela | Mascara_Tarjeta (•••• 4242).**
- **Logo_Marca | Titular | Caducidad_Mes | Caducidad_Año.**
- **Es_Predeterminada | AutoPago_Activo (Boolean).**

---

## CU-10: Gestión de incidencias

### RI-11: Incidencia
**Descripción:** Datos del ticket de soporte técnico:
- **ID_Incidencia:** (INC-XXXX).
- **ID_Vivienda | ID_Inquilino_Reportador | ID_Casero.**
- **Titulo | Descripcion.**
- **Categoria (Enum) | Zona_Piso (Enum) | Urgencia (Enum).**
- **Estado (Enum):** Abierta | Recibida | En_Proceso | Tecnico_Avisado | Resuelta | Cerrada.
- **Fotos (Array) | Presupuesto_URL | Coste_Compartido (Boolean).**
- **Historial_Estados:** Array de {estado, fecha, usuario}.

---

## CU-11: Reseñas y valoración de convivencia

### RI-13: Reseña
**Descripción:** Datos para la valoración pública:
- **ID_Valoracion | ID_Autor | ID_Valorado | ID_Convivencia.**
- **Puntuacion_Global (1-5 estrellas) | Comentario | Respuesta.**
- **Estado_Visibilidad (Boolean: published) | Fecha_Creacion.**

### RI-14: ResumenReputacion
**Descripción:** Datos agreg