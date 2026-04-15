# ROOMA
# Reporte de testing definitivo

## Alcance

- Backend unitarios e integracion: backend/src/test/java
- Frontend e2e con Playwright: frontend/tests

## Convenciones

- Estado Testeado:
  - Si: hay cobertura automatizada directa del RF.
  - Parcial: hay cobertura automatizada, pero incompleta para todas las reglas del RF.
  - No: no hay cobertura automatizada suficiente del RF.
- Tipos de test:
  - BU: Backend unitario (JUnit + Mockito).
  - BI: Backend integracion (Spring Test, DataJpaTest, WebMvcTest, etc.).
  - FU: Frontend unitario (Vitest).
  - FE: Frontend e2e (Playwright).

---

## Resumen global

| Tipo | Total tests |
|---|---:|
| Backend unitarios | 388 |
| Backend integracion | 218 |
| Frontend Playwright | 91 |
| **Total general** | **697** |

## Backend por modulo

| Modulo | Unitarios | Integracion | Total |
|---|---:|---:|---:|
| Apartment | 16 | 27 | 43 |
| ApartmentMatch | 72 | 45 | 117 |
| ApartmentPhoto | 13 | 0 | 13 |
| Auth | 12 | 6 | 18 |
| Billing | 27 | 20 | 47 |
| Chat | 36 | 16 | 52 |
| dummy | 1 | 0 | 1 |
| Favorite | 17 | 24 | 41 |
| Incident | 46 | 21 | 67 |
| Jwt | 20 | 0 | 20 |
| MemberApartment | 61 | 31 | 92 |
| Review | 34 | 10 | 44 |
| User | 33 | 18 | 51 |

## Frontend Playwright por modulo

| Modulo | Tests Playwright |
|---|---:|
| advertisements | 2 |
| apartments | 4 |
| candidates-visits | 4 |
| chats | 24 |
| deck-swipe | 5 |
| favourites | 2 |
| incidents | 25 |
| invoices | 6 |
| notifications | 9 |
| profile-accounts | 4 |
| reviews | 6 |

---

## Desglose detallado por CU y RF

### CU-01 - Descubrimiento de viviendas

| RF | Testeado | Tipo | Tests en repo (nombre y linea) | Pendiente |
| :--- | :---: | :--- | :--- | :--- |
| RF-46 | Si | BI, FE | backend/src/test/java/com/example/demo/Apartment/ApartmentRepositoryTest.java:75 - findDeckForCandidate_ReturnsOnlyActiveNotOwnedAndNotSwiped; frontend/tests/deck-swipe/deck-swipe.spec.ts:184 - El deck devuelve inmuebles elegibles... | Rendimiento del deck con carga alta. |
| RF-47 | Si | BI, FE | backend/src/test/java/com/example/demo/Apartment/ApartmentControllerTest.java:179 - getApartmentAndPhotos_ReturnsData; frontend/tests/deck-swipe/deck-swipe.spec.ts:362 - Al abrir detalle se muestran galeria... | Errores de datos incompletos y fallback UI. |
| RF-48 | Si | BI, FE | frontend/tests/deck-swipe/deck-swipe.spec.ts:232 - Like y dislike por botones...; frontend/tests/deck-swipe/deck-swipe.spec.ts:309 - El gesto horizontal... | Cobertura de botones + gesto en mas estados limite. |
| RF-49 | No | - | Sin test asociado en backend/src/test ni frontend/tests para rewind premium. | Pruebas BU/BI de regla premium y FE del flujo rewind. |
| RF-50 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/ApartmentMatch/ApartmentMatchServiceTest.java:64 - processSwipe_InterestTrue_CreatesActiveMatch; frontend/tests/deck-swipe/deck-swipe.spec.ts:232 - Like y dislike por botones... | Casos de idempotencia y doble click. |
| RF-51 | Parcial | FE | frontend/tests/deck-swipe/deck-swipe.spec.ts:214 - Sin resultados muestra mensaje personalizado... | Persistencia real offline/reconexion de posicion. |
| RF-52 | Si | FE | frontend/tests/deck-swipe/deck-swipe.spec.ts:214 - Sin resultados muestra mensaje personalizado... | Regla de sugerencia en backend con test BI/BU. |

---

### CU-02 - Gestion de candidatos y match

| RF | Testeado | Tipo | Tests en repo (nombre y linea) | Pendiente |
| :--- | :---: | :--- | :--- | :--- |
| RF-53 | Si | BI, FE | frontend/tests/candidates-visits/candidates-visits.spec.ts:301 - Muestra dashboard con tabs...; backend/src/test/java/com/example/demo/ApartmentMatch/ApartmentMatchControllerTest.java:258 - getInterestedCandidates_ReturnsOk | Paginacion y volumen alto. |
| RF-54 | Si | BI, FE | frontend/tests/candidates-visits/candidates-visits.spec.ts:356 - Abre ficha expandida del candidato...; backend/src/test/java/com/example/demo/ApartmentMatch/ApartmentMatchControllerTest.java:311 - getApartmentMatchDetailsForLandlord_ReturnsOk | Campos opcionales y privacidad fina. |
| RF-55 | Si | BU, BI, FE | frontend/tests/candidates-visits/candidates-visits.spec.ts:415 - Aceptar mueve la solicitud...; frontend/tests/candidates-visits/candidates-visits.spec.ts:439 - Rechazar archiva...; backend/src/test/java/com/example/demo/ApartmentMatch/ApartmentMatchServiceTest.java:190 - processLandlordAction_InterestTrue_SetsMatch | Reversibilidad controlada y anti doble accion. |
| RF-56 | Parcial | BI, FE | frontend/tests/apartments/apartments.spec.ts:363 - Permite pausar/reactivar...; frontend/tests/apartments/apartments.spec.ts:399 - Permite cerrar anuncio... | Cascada completa de cancelaciones de pendientes/en espera. |
| RF-74 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/ApartmentMatch/ApartmentMatchServiceTest.java:64 - processSwipe_InterestTrue_CreatesActiveMatch; backend/src/test/java/com/example/demo/ApartmentMatch/ApartmentMatchServiceTest.java:835 - legacyProcessSwipe_FirstCandidateInteraction_CreatesActiveMatch; frontend/tests/candidates-visits/candidates-visits.spec.ts:415 - Aceptar mueve la solicitud... | Casos de sincronizacion bilateral concurrente. |

---

### CU-03 - Sistema de chats

| RF | Testeado | Tipo | Tests en repo (nombre y linea) | Pendiente |
| :--- | :---: | :--- | :--- | :--- |
| RF-57 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Chat/ChatControllerTest.java:71 - getMessageHistory_ReturnsOkForTenant; backend/src/test/java/com/example/demo/Chat/ChatServiceTest.java:111 - getMessageHistory_shouldReturnMessages_forValidStatuses; frontend/tests/chats/ - 24 tests e2e de bandeja y chat | - |
| RF-58 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Chat/ChatServiceTest.java:393 - sendFileMessage_shouldSaveMessage_whenValid; backend/src/test/java/com/example/demo/Chat/ChatWebSocketControllerTest.java:38 - sendMessage_ReturnsMessageDTO; frontend/tests/chats/ - cobertura e2e de adjuntos | - |
| RF-59 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Chat/ChatServiceTest.java:597 - markMessagesAsRead_shouldMarkOtherUsersMessagesAsRead; backend/src/test/java/com/example/demo/Chat/ChatControllerTest.java:157 - markAsRead_ReturnsOkAndMessages; frontend/tests/chats/ - cobertura e2e de checks entregado/leido | - |
| RF-60 | No | - | Sin test asociado para gestion de citas en chat. | Crear casos de proponer/aceptar/contraoferta. |
| RF-61 | No | - | Sin test asociado para cancelacion de citas. | Cobertura de cancelacion y aviso a contraparte. |
| RF-62 | No | - | Sin test asociado para cierre/archivo de chat por estado del inmueble. | Cobertura de bloqueo y mensaje de no disponibilidad. |

---

### CU-04 - Gestion de notificaciones

| RF | Testeado | Tipo | Tests en repo (nombre y linea) | Pendiente |
| :--- | :---: | :--- | :--- | :--- |
| RF-01 | Si | FE | frontend/tests/notifications/ - 9 tests e2e cubriendo generacion y visualizacion de notificaciones | Cobertura BU/BI del motor de eventos. |
| RF-02 | Si | FE | frontend/tests/notifications/ - cobertura e2e de listado cronologico | Cobertura BU/BI de scoping por usuario. |
| RF-03 | Parcial | FE | frontend/tests/notifications/ - cobertura e2e del badge de pendientes | Indicador visual en boton + refresco en tiempo real. |
| RF-04 | Si | FE | frontend/tests/notifications/ - cobertura e2e de navegacion desde notificacion | Cobertura BU/BI de deep linking. |
| RF-05 | Si | FE | frontend/tests/notifications/ - cobertura e2e de marcado de lectura | Cobertura BU/BI de marcado masivo. |

---

### CU-05 - Sistema de favoritos

| RF | Testeado | Tipo | Tests en repo (nombre y linea) | Pendiente |
| :--- | :---: | :--- | :--- | :--- |
| RF-06 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Favorite/FavoriteServiceTest.java:56 - addFavorite_SavesWhenNotExisting; backend/src/test/java/com/example/demo/Favorite/FavoriteControllerTest.java:118 - addFavorite_ReturnsOk; frontend/tests/favourites/favourites.spec.ts:220 - Permite guardar vivienda como favorita... | Concurrencia/duplicidad bajo alta frecuencia. |
| RF-07 | Si | BI, FE | backend/src/test/java/com/example/demo/Favorite/FavoriteControllerTest.java:65 - getCurrentUserFavorites_ReturnsOk; frontend/tests/favourites/favourites.spec.ts:277 - Muestra seccion de favoritos... | Volumen alto y paginacion. |
| RF-08 | Parcial | BU, FE | backend/src/test/java/com/example/demo/Favorite/FavoriteServiceTest.java:221 - getCurrentUserFavorites_MapsAvailabilityState; frontend/tests/favourites/favourites.spec.ts:277 - Muestra seccion de favoritos... | Bloqueo de detalle para todos los estados no disponibles. |

---

### CU-06 - Gestion de inmuebles

| RF | Testeado | Tipo | Tests en repo (nombre y linea) | Pendiente |
| :--- | :---: | :--- | :--- | :--- |
| RF-09 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Apartment/ApartmentServiceTest.java:78 - createWithImages_SavesAndDelegatesPhotoSave; frontend/tests/apartments/apartments.spec.ts:286 - Registra inmueble con formulario guiado... | Casos limite de adjuntos (tamano/formato/error red). |
| RF-11 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Apartment/ApartmentServiceTest.java:146 - update_MutatesAndSavesExistingApartment; frontend/tests/apartments/apartments.spec.ts:363 - Permite pausar/reactivar...; frontend/tests/apartments/apartments.spec.ts:399 - Permite cerrar anuncio... | Permisos por rol en matriz completa. |
| RF-12 | No | - | Sin test asociado especifico de previsualizacion de anuncio. | Vista previa antes de publicar. |
| RF-13 | Parcial | BU, BI | backend/src/test/java/com/example/demo/Apartment/ApartmentServiceTest.java:181 - deleteById_WhenExists_Deletes; backend/src/test/java/com/example/demo/Apartment/ApartmentControllerTest.java:161 - deleteApartment_Success | Regla de bloqueo con inquilinos activos + confirmacion FE. |
| RF-14 | Si | BI, FE | backend/src/test/java/com/example/demo/MemberApartment/ApartmentMemberControllerTest.java:68 - listShouldReturnAListOfApartmentMembersDTOForAGivenApartment; frontend/tests/apartments/apartments.spec.ts:458 - Consulta miembros actuales del piso... | Privacidad fina por rol/campo sensible. |
| RF-72 | Parcial | BU, BI, FE | backend/src/test/java/com/example/demo/Apartment/ApartmentEditingIntegrationTest.java:79 - landlordCanEditOwnApartment; backend/src/test/java/com/example/demo/Apartment/ApartmentEditingIntegrationTest.java:107 - nonOwnerCannotEditApartment; frontend/src/__tests__/apartmentEditSchema.test.ts:15 - accepts a valid payload | Notificaciones por cambios relevantes y marca de ultima modificacion. |
| RF-73 | Si | BI, FE | frontend/tests/advertisements/advertisements.spec.ts:204 - HU-66: landlord pausa anuncio...; frontend/tests/advertisements/advertisements.spec.ts:237 - HU-67: landlord reactiva anuncio... | Aviso opcional a candidatos en espera. |

---

### CU-07 - Gestion de cuentas y perfil

| RF | Testeado | Tipo | Tests en repo (nombre y linea) | Pendiente |
| :--- | :---: | :--- | :--- | :--- |
| RF-63 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Auth/AuthControllerTests.java:67 - register_success; backend/src/test/java/com/example/demo/Auth/AuthServiceTest.java:85 - register_shouldReturnAuthResultWhenUserIsNew; frontend/tests/profile-accounts/register.spec.ts:126 - Registra inquilino con email... | Rate limit/captcha y mensajes localizados. |
| RF-64 | Parcial | BU, BI | backend/src/test/java/com/example/demo/Auth/AuthControllerTests.java:145 - validate_success; backend/src/test/java/com/example/demo/Auth/AuthControllerTests.java:159 - validate_invalid | Reenvio controlado y expiracion completa en FE/BI. |
| RF-65 | No | - | Sin test asociado para OAuth Google/Apple/Facebook. | Vinculacion/desvinculacion de proveedores. |
| RF-66 | No | - | Sin test asociado para recuperacion de contrasena por token. | Solicitud, token, cambio clave e invalidacion sesiones. |
| RF-67 | No | - | Sin test asociado para 2FA TOTP y codigos de backup. | Alta/baja 2FA y recuperacion por backup. |
| RF-68 | Parcial | BU, BI | backend/src/test/java/com/example/demo/User/UserServiceTest.java:70 - updateCurrentUserProfile_updatesFields; backend/src/test/java/com/example/demo/User/UserControllerTests.java:103 - updateUserProfile_UpdatesSuccessfully | Onboarding completo, validaciones multimedia y perfil minimo. |
| RF-69 | No | - | Sin test asociado para reportes de usuarios. | Formulario reporte, adjuntos y cola de moderacion. |
| RF-70 | No | - | Sin test asociado para sanciones administrativas. | Suspender/banear, auditoria y notificacion. |
| RF-71 | No | - | Sin test asociado para verificacion de identidad delegada. | Consentimiento + estados proveedor + badge verificado. |

---

### CU-08 - Filtros avanzados para arrendador

| RF | Testeado | Tipo | Tests en repo (nombre y linea) | Pendiente |
| :--- | :---: | :--- | :--- | :--- |
| RF-10 | Parcial | BU, BI, FU | backend/src/test/java/com/example/demo/MemberApartment/ReglaViviendaServiceTest.java:50 - updateRules_UpdatesExistingWhenLandlord; backend/src/test/java/com/example/demo/Apartment/ApartmentEditingIntegrationTest.java:79 - landlordCanEditOwnApartment; frontend/src/__tests__/apartmentEditSchema.test.ts:15 - accepts a valid payload | Cobertura FE del formulario avanzado completo y efecto en afinidad. |
| RF-75 | No | - | Sin test asociado de filtrado manual completo de solicitudes. | Filtros combinados edad/genero/ocupacion/habitos. |
| RF-76 | No | - | Sin test asociado de orden por fecha/reputacion/afinidad. | Ordenacion y desempate deterministico. |

---

### CU-09 - Gestion de facturas y pagos

| RF | Testeado | Tipo | Tests en repo (nombre y linea) | Pendiente |
| :--- | :---: | :--- | :--- | :--- |
| RF-15 | Si | BU, BI, FE | frontend/tests/invoices/invoices.spec.ts:286 - Formulario permite adjuntar archivo...; backend/src/test/java/com/example/demo/Billing/BillingServiceTests.java:404 - createBillAndSplit_CreatesBillAndSplitsIntoDebts | Adjuntos corruptos/borrador de recuperacion. |
| RF-16 | Si | BU, BI, FE | frontend/tests/invoices/invoices.spec.ts:364 - Recalcula reparto al seleccionar/desseleccionar...; backend/src/test/java/com/example/demo/Billing/BillingServiceTests.java:404 - createBillAndSplit_CreatesBillAndSplitsIntoDebts | Repartos extremos mixtos y redondeo fino. |
| RF-17 | Si | BU, BI, FE | frontend/tests/invoices/invoices.spec.ts:364 - Recalcula reparto...; backend/src/test/java/com/example/demo/Billing/BillingServiceTests.java:404 - createBillAndSplit_CreatesBillAndSplitsIntoDebts | Edicion manual avanzada de cuotas y redistribucion. |
| RF-18 | Si | BI, FE | frontend/tests/invoices/invoices.spec.ts:501 - Dashboard pendiente muestra prioridad...; frontend/tests/invoices/invoices.spec.ts:564 - Historial muestra pagos...; backend/src/test/java/com/example/demo/Billing/BillingControllerTests.java:67 - myDebts_ReturnsOkForTenant | Filtros avanzados y accesibilidad completa. |
| RF-19 | Parcial | BI, FE | frontend/tests/invoices/invoices.spec.ts:618 - Permite pagar con un clic...; backend/src/test/java/com/example/demo/Billing/BillingControllerTests.java:117 - payDebt_ReturnsOkForTenant | Pasarela real/sandbox, idempotencia y errores transitorios. |
| RF-20 | Si | BU, BI, FE | frontend/tests/invoices/invoices.spec.ts:564 - Historial muestra pagos...; backend/src/test/java/com/example/demo/Billing/BillingServiceTests.java:256 - payDebt_MarksDebtAsPaidAndUpdatesBillStatusIfAllDebtsArePaid | Verificacion sistematica de iconos y color por estado. |
| RF-21 | No | - | Sin test asociado de auto-pago (toggle + scheduler). | Cobertura cron/reintentos y consentimiento FE. |
| RF-22 | Si | BI, FE | frontend/tests/invoices/invoices.spec.ts:448 - Panel muestra facturas pendientes/pagadas...; backend/src/test/java/com/example/demo/Billing/BillingControllerTests.java:179 - billsForApartment_ReturnsOkForLandlord | Resumen mensual agregado y cooldown de recordatorios. |
| RF-23 | No | - | Sin test asociado para notificaciones de pagos. | Triggers nueva factura/vencimiento/pago/auto-pago. |
| RF-24 | No | - | Sin test asociado de exportacion PDF/CSV. | Exportacion por rango y validacion de contenido. |
| RF-25 | No | - | Sin test asociado de gestion de metodos de pago. | Alta/baja/predeterminada/caducidad/bloqueo por auto-pago. |
| RF-26 | Parcial | BI, FE | frontend/tests/invoices/invoices.spec.ts:286 - Formulario permite adjuntar archivo...; backend/src/test/java/com/example/demo/Billing/BillingServiceTests.java:572 - createBillAndSplitAndPayDebt_IntegrationTest | Edicion/anulacion con nota de credito y versiones. |

---

### CU-10 - Gestion de incidencias

| RF | Testeado | Tipo | Tests en repo (nombre y linea) | Pendiente |
| :--- | :---: | :--- | :--- | :--- |
| RF-27 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Incident/ - 46 BU + 21 BI; frontend/tests/incidents/ - 25 tests e2e | Adjuntos desde camara y borrador. |
| RF-28 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Incident/ - cobertura de transiciones de estado; frontend/tests/incidents/ - cobertura e2e de timeline | - |
| RF-29 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Incident/ - cobertura de chat tecnico; frontend/tests/incidents/ - cobertura e2e | - |
| RF-30 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Incident/ - cobertura de validacion de solucion; frontend/tests/incidents/ - cobertura e2e | Autocierre por timeout. |
| RF-31 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Incident/ - cobertura de listado; frontend/tests/incidents/ - cobertura e2e con filtros | - |
| RF-32 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Incident/ - cobertura de panel casero; frontend/tests/incidents/ - cobertura e2e | - |
| RF-33 | No | - | Sin test asociado para notificaciones de incidencias. | Triggers por eventos de incidencia. |
| RF-34 | Si | BU, BI, FE | backend/src/test/java/com/example/demo/Incident/ - cobertura de historial; frontend/tests/incidents/ - cobertura e2e | Busqueda y filtros avanzados. |
| RF-35 | No | - | Sin test asociado para presupuesto adjunto. | Presupuesto adjunto y enlace con pagos. |

---

### CU-11 - Resenas y valoracion de convivencia

| RF | Testeado | Tipo | Tests en repo (nombre y linea) | Pendiente |
| :--- | :---: | :--- | :--- | :--- |
| RF-36 | Si | BI, FE | frontend/tests/reviews/reviews.spec.ts:276 - Muestra aviso de valoracion en Home...; backend/src/test/java/com/example/demo/Review/ReviewServiceTest.java:397 - getPendingReviewApartments_landlordPath | Recordatorios escalonados completos. |
| RF-37 | Si | BI, FE | frontend/tests/reviews/reviews.spec.ts:311 - Formulario de inquilino valida categorias...; frontend/tests/reviews/reviews.spec.ts:406 - Casero puede valorar a inquilino... | Casos limite de validacion por rol. |
| RF-38 | Si | BI, FE | frontend/tests/reviews/reviews.spec.ts:357 - aparece estado pendiente con candado...; backend/src/test/java/com/example/demo/Review/ReviewServiceTest.java:103 - makeReviewByLandlord_success_withMutualPublish | Ventana temporal exacta de 30 dias. |
| RF-39 | Si | BI, FE | frontend/tests/reviews/reviews.spec.ts:487 - Usuario valorado puede responder...; backend/src/test/java/com/example/demo/Review/ReviewServiceTest.java:321 - respondToReview_success | Moderacion de replica y no-edicion posterior. |
| RF-41 | Parcial | BI, FE | backend/src/test/java/com/example/demo/Review/ReviewControllerTest.java:116 - getReceivedReviews_ok; frontend/tests/reviews/reviews.spec.ts:311 - Formulario de inquilino valida categorias... | Ordenacion, paginacion y resumen agregado por categorias. |
| RF-42 | No | - | Sin test asociado para moderacion automatica de contenido. | Filtro automatico + estado en revision + descarte a 7 dias. |
| RF-43 | No | - | Sin test asociado para reporte de resenas inadecuadas. | Flujo reportar, motivos y umbral de ocultacion. |
| RF-44 | No | - | Sin test asociado para resumen reputacional en tarjetas. | Resumen reputacion en swipe/solicitud + navegacion a perfil. |
| RF-45 | Parcial | BI, FE | frontend/tests/reviews/reviews.spec.ts:276 - Muestra aviso de valoracion en Home...; backend/src/test/java/com/example/demo/Review/ReviewServiceTest.java:297 - publishOldReviews_publishesAll | Hitos completos 48h/7d/21d/30d y publicacion unilateral. |

---
