# ROOMA - Pagos: planteamiento, arquitectura, objetivo y selección de PSP

## Planteamiento del problema y alcance

Rooma necesita un módulo de **facturas y pagos** que funcione como un mini sistema financiero dentro de la app:

- **Registro de factura/gasto por el casero**: El sistema debe disponer de una interfaz de formulario para el casero con concepto, importes, vencimiento y adjunto PDF/imagen. **RF 15**.
- **Reparto de la factura entre participantes**: partes iguales, % personalizado, o importe fijo por persona recalculado en tiempo real y control de redondeos. **RF 16, RF 17**.
- **Checkout embebido (sin salir de la PWA)**: el inquilino paga desde un modal/pantalla, usando método guardado o añadiendo uno nuevo con “Elements/Components” del PSP. **RF 19**.
- **Estados visibles y consistentes (inquilino y casero)**:
	- Por deuda individual: Pendiente, Procesando, Pagado, Vencido, Rechazado. **RF 20**.
	- Por factura global: Pendiente, Parcialmente cobrado, Cobrado, Anulado. **RF 22 y modelo RI 07/RI 08**.
- **Autopago (cobro automático)**: toggle para activar/desactivar, selección de tarjeta asociada y gestión de fallos. **RF 21**.
- **Notificaciones**: push e in-app para nueva factura, recordatorios, pago recibido, pago vencido y autopago ejecutado. **RF 23**.
- **Reembolso / anulación**: si hay pagos parciales, solo se permite anular la factura completa, generando nota de crédito y gestionando reembolsos de pagos ya realizados. **RF 26**.
- **Exportación**: PDF/CSV del historial (filtrable por fechas/vivienda/concepto) para casero e inquilino. **RF 24**.
- **Idempotencia (sin dobles cobros)**: **RNF 17**.
- **PCI (no tocar PAN)**: **RNF 11**.

## Seguridad, cumplimiento y marco legal en UE y España

### ¿Qué es un PSP?

Un **PSP (Payment Service Provider)** es un proveedor de servicios de pagos que ofrece la infraestructura y los servicios necesarios para aceptar pagos electrónicos en una aplicación o web. Es el intermediario que conecta la aplicación con el ecosistema de pagos (bancos, redes de tarjetas y métodos locales como Bizum), aportando además componentes de seguridad, cumplimiento y operación (SCA/3DS, tokenización, webhooks, reembolsos, etc.).

### ¿Por qué se necesita un PSP?

#### 1) Integración con métodos bancarios

Un PSP trae integrado diferentes métodos de pago y acuerdos montados con distintas entidades bancarias y métodos de pago, como:

- Redes de pago (Visa, Mastercard, etc.).
- Bancos emisores (el banco del usuario, que autoriza o rechaza).
- Bancos adquirentes / acquiring (quien acepta pagos por parte del comercio).
- Sistemas antifraude, liquidación, reversos y disputas.

Por tanto, crear un PSP desde cero en Rooma es inviable por la complejidad de estas integraciones.

#### 2) Regulaciones y seguridad

Si quisiéramos cobrar por nuestra cuenta, habría que cumplir normas en la UE como la directiva **PSD2**, que regula los servicios de pago para hacer las transacciones electrónicas más seguras, competitivas e innovadoras, e impone la autenticación reforzada **SCA** en pagos online.

Además, si quisiéramos almacenar datos sensibles para no depender de proveedor externo, deberíamos cumplir requisitos estrictos de **PCI DSS** (auditorías, controles, hardening, monitorización). Con un PSP, se usa tokenización y/o componentes de pago del proveedor, de modo que:

- La aplicación no ve ni guarda el número real de tarjeta (solo tokens).
- El diseño es más seguro y mantenible.

Por último, un PSP ofrece mecanismos estándar ya preparados para actualizar estados y notificar al usuario, evitando construir una funcionalidad compleja y propensa a fallos.

## PSPs analizados

## Stripe

### ¿Qué es?

Stripe es el PSP más fácil de configurar para sacar un sistema de pagos rápido y bien montado. Proporciona checkout embebido (dentro de Rooma), APIs para cobros, reembolsos y gestión de métodos de pago, y además (si operamos como plataforma) Stripe Connect para gestionar comisiones y pagos a terceros.

### Ventajas

- Checkout embebido muy directo en React (Payment Element + React Stripe.js), con mucha documentación y comunidad.
- Autopago bien soportado: guardar método de pago y hacer cobros “off-session” con flujos preparados para SCA cuando aplique.
- Webhooks sólidos: Stripe avisa del resultado real del pago y tiene reintentos si el servidor no responde.
- Idempotencia: evita dobles cobros usando Idempotency-Key en operaciones críticas.
- Bizum: guía oficial para aceptar Bizum.

### Desventajas

- Si Rooma es plataforma con muchos caseros y payouts frecuentes, Connect puede elevar el coste total (costes por cuenta activa y por payout).
- El flujo del dinero (quién cobra, quién recibe y cómo se aplica comisión) debe diseñarse bien para encajar con anulación/reembolso y la lógica de estados.

### Recursos (docs/SDK) y compatibilidad con stack

- Frontend React (Vercel): Stripe React SDK + Payment Element.
- Backend Java/Spring Boot (Render/DO): Stripe API + webhooks (con verificación de firma) + idempotencia.
- PostgreSQL: facturas, deudas, intentos, eventos y reembolsos. Stripe actúa como motor de cobro y devuelve estado final.

### Precios (públicos)

- Tarjeta EEE España: **1,5% + 0,25€** por pago exitoso (tarjetas estándar EEE).
- Connect (si hay payouts a caseros): **2€ por cuenta activa mensual** (cuando se envían payouts ese mes) y **0,25% + 0,10€** por payout (puede variar por país/moneda).

### Referencias

- https://docs.stripe.com/sdks/stripejs-react
- https://docs.stripe.com/payments/payment-element
- https://docs.stripe.com/webhooks
- https://docs.stripe.com/webhooks/signature
- https://docs.stripe.com/api/idempotent_requests
- https://docs.stripe.com/payments/setup-intents
- https://docs.stripe.com/payments/save-and-reuse
- https://docs.stripe.com/payments/bizum/accept-a-payment
- https://stripe.com/en-ES/pricing/local-payment-methods
- https://stripe.com/connect/pricing

---

## Adyen

### ¿Qué es?

Adyen es un PSP muy fuerte en entornos enterprise. Proporciona checkout web (Drop-in/Components), APIs de pagos, reembolsos y notificaciones (webhooks) muy robustas. Para modelo de plataforma con reparto de importes, también ofrece opciones potentes, aunque con configuración más corporativa.

### Ventajas

- Muy robusto para operar a escala: buena trazabilidad de pagos y eventos.
- Webhooks seguros: verificación con HMAC.
- Idempotencia: soporte Idempotency-Key para evitar pagos duplicados por reintentos.
- Tokenización / guardar tarjeta para cobros futuros (autopago).
- Buen encaje con Java/Spring: librería oficial Java y patrones server-side claros.

### Desventajas

- Suele requerir más gestión contractual y configuración (más lento para un MVP).
- Bizum: normalmente exige contrato con banco adquirente local y MID/Terminal ID, añadiendo pasos externos.
- Precio real variable por país, método, volumen y acuerdo.

### Recursos (docs/SDK) y compatibilidad con stack

- Frontend React (Vercel): Web Drop-in/Components integrado en React.
- Backend Java/Spring Boot: SDK Java oficial + webhooks HMAC + idempotencia.
- PostgreSQL: Rooma guarda estados e histórico; Adyen ejecuta cobro y notifica.

### Precios (públicos)

- Parte variable según tarjeta + **0,11€** por procesamiento (más detalle en su web).
- Bizum puede implicar costes y requisitos adicionales según contrato y banco adquirente.

### Referencias

- https://docs.adyen.com/payment-methods/cards/web-drop-in
- https://github.com/Adyen/adyen-web
- https://docs.adyen.com/development-resources/api-idempotency
- https://docs.adyen.com/development-resources/webhooks/secure-webhooks/verify-hmac-signatures
- https://docs.adyen.com/payment-methods/bizum
- https://docs.adyen.com/online-payments/tokenization
- https://docs.adyen.com/online-payments/refund
- https://www.adyen.com/pricing
- https://github.com/Adyen/adyen-java-api-library

---

## Lemonway

### ¿Qué es?

Lemonway está orientado a plataformas/marketplaces. Permite cobrar a usuarios (pay-in) y, si aplica, hacer pagos a terceros (pay-out), con procesos de identificación cuando hay receptores (KYC/KYB). Es bastante estructurado y predecible en precios/documentación, útil para estimación de costes.

### Ventajas

- Tarifas públicas detalladas para calcular coste total desde el inicio.
- Pago embebido sin tocar datos sensibles (hosted fields / iframe).
- API con OAuth 2.0 (buen encaje con Spring).
- Webhooks con reintentos y comportamiento documentado.
- Pagos recurrentes (autopago) documentados.

### Desventajas

- Costes fijos (set-up + soporte mensual) altos para un MVP.
- Si Bizum es imprescindible, no aparece claramente como método estándar en la parte pública (a confirmar con ellos).
- Al ser muy marketplace, suele requerir más modelado (verificación, cuentas internas, etc.).

### Recursos (docs/SDK) y compatibilidad con stack

- Frontend React (Vercel): hosted fields/iframe integrables en UI React.
- Backend Java/Spring Boot: API REST + OAuth2 + webhooks para sincronizar estados.
- PostgreSQL: Rooma guarda facturas/deudas/intentos/eventos y valida estado final con webhooks.

### Precios (públicos)

- Tarjeta (pay-in): **1,10% + 0,25€**.
- Identificación KYC: **0,40€/mes** (persona) y **0,80€/mes** (empresa).
- Pay-out: **0,50€** Europa / **9€** internacional.
- Set-up: **5.490€**.
- Soporte: **840€/mes**.
- Chargeback: **35€**.

### Referencias

- https://www.lemonway.com/en/pricing
- https://documentation.lemonway.com/docs/embedded-card-payment
- https://documentation.lemonway.com/docs/how-to-access-lemonway-tools-and-services
- https://documentation.lemonway.com/reference/authentication-oauth
- https://documentation.lemonway.com/docs/developer-documentation
- https://documentation.lemonway.com/

---

## Mangopay

### ¿Qué es?

Mangopay está pensado para plataformas con varios actores (por ejemplo, inquilinos que pagan y caseros que reciben), con enfoque tipo wallet.

### Ventajas

- Enfoque plataforma alineado para comisiones, transferencias internas y payouts.
- Bizum soportado, con guías/endpoints.
- Webhooks con reglas claras y comportamiento predecible.
- Idempotencia con Idempotency-Key.
- Soporte para cobro recurrente/autopago y estados con re-autenticación.
- SDK Java para facilitar integración con Spring Boot.

### Desventajas

- Requiere más trabajo de integración que un PSP centrado solo en checkout.
- Precios no cerrados en tabla pública completa (requiere contacto comercial).
- Webhooks exigentes: requiere responder rápido y procesar eventos de forma ordenada.

### Recursos (docs/SDK) y compatibilidad con stack

- Frontend React (Vercel): UI propia, conectando flujo según método y evitando tocar datos sensibles.
- Backend Java/Spring Boot: SDK Java + webhooks + idempotencia.
- PostgreSQL: lógica de negocio (facturas/deudas/estados) y conciliación por eventos PSP.

### Precios (públicos)

- Pricing flexible/a medida (sin tabla pública cerrada de todos los importes).

### Referencias

- https://docs.mangopay.com/guides/payment-methods
- https://docs.mangopay.com/api-reference/bizum/create-bizum-payin
- https://docs.mangopay.com/webhooks
- https://docs.mangopay.com/api-reference/overview/idempotency
- https://docs.mangopay.com/guides/fees
- https://docs.mangopay.com/sdks/java
- https://mangopay.com/pricing
- https://mangopay.com/
