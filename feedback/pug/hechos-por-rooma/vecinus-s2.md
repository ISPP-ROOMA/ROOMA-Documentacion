# Informe de Revisión PUG -(ISPP 2025-2026)

**Fecha de revisión:** 7 de abril de 2026  
**Procedimiento aplicado:** PILOT USER GROUP PROCEDURE (V1.0)

---

## 1. Gestión Multipropiedad (Multi-Property Management)
**Estado:** 🔴 **FALLIDO (Parcial)**

### Hallazgo 1: Inconsistencia de Permisos en el Rol "Presidente"
* **Descripción:** Se ha detectado una restricción de acceso indebida para el rol de Presidente.
* **Rol Utilizado:** Presidente.
* **Resultado Esperado:** Según la especificación funcional, tanto el Administrador como el Presidente deben tener capacidad para invitar personas.
* **Resultado Obtenido:** El sistema deniega la acción al Presidente, indicando que el permiso es exclusivo del Administrador.
* **Condición de Fallo Aplicada:** **(T-12)** Una interacción legal con el sistema no tiene el comportamiento esperado.

### Hallazgo 2: Funcionamiento Correcto del Rol "Administrador"
* **Descripción:** Se ha verificado que la funcionalidad de invitación está operativa bajo el rol jerárquico superior.
* **Rol Utilizado:** Administrador.
* **Resultado:** El Administrador puede enviar invitaciones sin errores.

---

## 2. Chatbot de la Comunidad (Community Chatbot)
**Estado:** 🟢 **CORRECTO**

### Verificación 1: Subida de Documentos
* **Descripción:** Comprobación de carga de actas y estatutos.
* **Rol Utilizado:** Administrador.
* **Resultado:** El sistema procesa la carga de archivos PDF sin errores de servidor y confirma la disponibilidad para el chatbot.

### Verificación 2: Consultas (UX/UI)
* **Descripción:** Los usuarios realizan preguntas basadas en el contenido subido.
* **Roles Utilizados:** Vecino / Presidente.
* **Resultado:** El comportamiento es el esperado, proporcionando respuestas coherentes.

---

## 3. Transcripciones de Reuniones (Meeting Transcriptions)
**Estado:** 🟢 **CORRECTO**

### Verificación 1: Gestión de Errores (Alertas)
* **Descripción:** Estabilidad ante eventos inesperados durante la transcripción.
* **Resultado:** Las alertas no gestionadas han sido solventadas; el sistema no lanza errores **T-10** (HTTP) ni **T-11** (pánico/crash).

### Verificación 2: Integridad y Edición
* **Descripción:** La lógica de edición se aplica exclusivamente al resumen.
* **Resultado:** Al modificar, el sistema actualiza el resumen manteniendo la transcripción original intacta.

### Verificación 3: Formato del Documento Final
* **Descripción:** Inspección del archivo exportado.
* **Resultado:** El documento generado incluye correctamente el espacio para firmas solicitado.

---

## 4. Zonas Comunes (Common Areas)
**Estado:** 🟢 **CORRECTO**

### Verificación 1: Gestión y Administración
* **Descripción:** Capacidad de gestión de infraestructuras comunes.
* **Rol Utilizado:** Administrador.
* **Resultado:** El Administrador puede gestionar zonas comunes sin restricciones técnicas.

### Verificación 2: Reserva e Invitaciones
* **Descripción:** Prueba de flujo desde reserva hasta generación de credenciales.
* **Resultado:** El sistema permite realizar reservas de forma efectiva y genera invitaciones funcionales con la información necesaria.

---

## 5. Gestión de Incidencias (Incident Management)
**Estado:** 🔴 **FALLIDO**

### Hallazgo 1: Denegación de Acceso a Roles Autorizados
* **Descripción:** Incapacidad para actualizar estados de incidencias con roles de gestión.
* **Roles Utilizados:** Administrador y Presidente.
* **Resultado Esperado:** El sistema debe permitir que tanto el administrador como el presidente actualicen el estado de una incidencia.
* **Resultado Obtenido:** El sistema bloquea la acción para ambos, impidiendo la gestión del ciclo de vida de la incidencia.
* **Condición de Fallo Aplicada:** **(T-12)** Una interacción legal con el sistema no tiene el comportamiento esperado.

### Hallazgo 2: Inconsistencia en Lógica de Autorización (Error 403)
* **Descripción:** El backend devuelve un error de prohibición (403) que contradice su propio mensaje de detalle.
* **Evidencia Técnica (Consola):** `{"detail":"Admin, president or employee access required for this action"}`.
* **Análisis:** El sistema rechaza la petición a pesar de que el usuario logueado cumple con los requisitos del mensaje.
* **Condición de Fallo Aplicada:** **(T-10)** Una interacción legal con el sistema resulta en un error HTTP percibido por el usuario.

### Hallazgo 3: Ausencia de Feedback en Interfaz (Silent Fail)
* **Descripción:** El error 403 y el mensaje de detalle no se muestran en pantalla.
* **Resultado:** El usuario no recibe notificaciones sobre el fallo, percibiendo que la funcionalidad simplemente no responde.
