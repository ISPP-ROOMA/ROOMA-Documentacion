# Plan de SEO — ROOMA

**Proyecto:** ROOMA — App para encontrar compañero de piso sin agencia + gestionar gastos compartidos  
**Fase:** Pre-lanzamiento, lanzamiento y crecimiento orgánico  
**Pre-lanzamiento público:** 13/05/2026 - 20/05/2026  
**Lanzamiento oficial:** 21/05/2026  
**Vinculado a:** [`plan-marketing-pre-lanzamiento.md`](plan-marketing-pre-lanzamiento.md)  
**Objetivo:** mejorar la visibilidad orgánica de ROOMA, preparar la web para indexación, reforzar la marca en buscadores y reducir progresivamente la dependencia de Ads.

---

## 1. Diagnóstico actual

### Estado técnico de la web

| Aspecto | Estado actual | Impacto SEO | Prioridad |
|:---|:---|:---|:---:|
| **`<title>`** | Genérico: `Rooma` | No comunica propuesta de valor ni keywords principales | 🔴 Alta |
| **Meta description** | No existe | Google genera un snippet automático poco controlado | 🔴 Alta |
| **Open Graph / Twitter Cards** | No existen | Al compartir la URL en redes no se muestra preview optimizado | 🔴 Alta |
| **Idioma del HTML** | `lang="en"` | Incoherente con público objetivo español | 🔴 Alta |
| **robots.txt** | No existe | Falta control explícito de rastreo | 🟠 Media |
| **sitemap.xml** | No existe | Google no recibe estructura básica de URLs | 🔴 Alta |
| **Heading structure (H1)** | Gestionado por React en cada vista | Puede ser inconsistente entre páginas | 🟠 Media |
| **Renderizado** | SPA con React + Vite | Riesgo de indexación si el contenido depende de JavaScript | 🔴 Alta |
| **PWA manifest** | Descripción genérica: `"A room booking application"` | No representa la propuesta real de ROOMA | 🟠 Media |
| **Canonical URL** | No definida | Riesgo de duplicidad si existen varias rutas o dominios | 🟠 Media |
| **Velocidad de carga** | No medida | Pendiente de auditoría Lighthouse | 🟠 Media |
| **Datos estructurados** | No existen | Oportunidad perdida para mejorar comprensión por buscadores | 🟠 Media |
| **Landing indexable** | No confirmada | Riesgo de que Google no entienda la propuesta de valor | 🔴 Alta |

### Conclusión del diagnóstico

La web actual de ROOMA necesita una optimización SEO básica antes del lanzamiento. El principal riesgo es que, al tratarse de una SPA renderizada en cliente, Google pueda indexar una página con poco contenido visible o sin entender correctamente la propuesta de valor.

Las acciones prioritarias son:

- optimizar el `index.html`;
- corregir el idioma del documento;
- añadir meta tags SEO y sociales;
- crear `robots.txt` y `sitemap.xml`;
- preparar una landing indexable;
- configurar Search Console y Analytics;
- alinear SEO con el plan de marketing, redes sociales y análisis económico.

---

## 2. Objetivos SEO

### Objetivos a corto plazo: antes del lanzamiento

| Objetivo | Indicador de cumplimiento |
|:---|:---|
| Que al buscar "ROOMA app" aparezca la web oficial | Indexación correcta en Google |
| Que la URL compartida en WhatsApp, LinkedIn, Instagram o X muestre preview atractivo | Open Graph configurado |
| Que la web tenga una puntuación Lighthouse SEO ≥ 80 | Auditoría Lighthouse |
| Que Google pueda rastrear la web correctamente | `robots.txt` y `sitemap.xml` activos |
| Que la propuesta de valor sea entendible sin navegar por la app | Landing clara e indexable |
| Que el idioma esté alineado con España | `lang="es"` |

### Objetivos a medio plazo: meses 1-6 post-lanzamiento

| Objetivo | Indicador |
|:---|:---|
| Posicionar búsquedas de marca | "rooma app", "rooma piso", "rooma compañero de piso" |
| Captar búsquedas locales | "buscar compañero de piso Sevilla", "piso compartido Sevilla" |
| Generar tráfico orgánico cualificado | 10% de registros mensuales desde orgánico |
| Conseguir autoridad externa | 5-10 backlinks de calidad |
| Crear contenido indexable | mínimo 1-2 piezas mensuales |

### Objetivos a largo plazo: meses 6-12

| Objetivo | Indicador |
|:---|:---|
| Posicionar keywords transaccionales | "app compañero de piso", "alquilar habitación sin agencia" |
| Reducir dependencia de Ads | 20-30% de registros desde orgánico |
| Aumentar autoridad del dominio | DA/DR ≥ 15 como referencia externa |
| Crear páginas locales | Sevilla, Madrid, Barcelona y otras ciudades objetivo |
| Escalar contenido evergreen | guías, comparativas y consejos de vivienda compartida |

---

## 3. Investigación de palabras clave

### 3.1. Keywords de marca

| Keyword | Volumen estimado | Dificultad | Prioridad |
|:---|:---:|:---:|:---:|
| rooma app | Bajo | Muy baja | 🔴 Alta |
| rooma compañero de piso | Bajo | Muy baja | 🔴 Alta |
| rooma pisos | Bajo | Muy baja | 🔴 Alta |
| rooma alquiler compartido | Bajo | Muy baja | 🟠 Media |
| rooma gastos compartidos | Bajo | Muy baja | 🟠 Media |

**Acción:** estas keywords deben estar presentes en el título, descripción, H1, contenido inicial de la landing y perfiles sociales.

---

### 3.2. Keywords informacionales

| Keyword | Volumen estimado | Dificultad | Segmento objetivo |
|:---|:---:|:---:|:---|
| cómo buscar compañero de piso | Medio | Media | Estudiante, joven profesional |
| consejos para compartir piso | Medio | Media | Estudiante |
| cómo dividir gastos del piso | Medio-bajo | Baja | Inquilinos |
| qué preguntar antes de compartir piso | Bajo-medio | Baja | Estudiante, joven profesional |
| derechos del inquilino piso compartido | Medio | Media-alta | Inquilinos |
| cómo evitar estafas alquiler | Medio | Media | Estudiante, trabajador desplazado |
| cómo saber si un compañero de piso es compatible | Bajo | Baja | Estudiante, joven profesional |
| cómo organizar gastos compartidos | Bajo-medio | Baja | Inquilinos |

---

### 3.3. Keywords transaccionales

| Keyword | Volumen estimado | Dificultad | Segmento objetivo |
|:---|:---:|:---:|:---|
| app buscar compañero de piso | Bajo-medio | Media | Estudiante, joven profesional |
| buscar compañero de piso Sevilla | Medio | Media-alta | Estudiante local |
| buscar habitación sin agencia | Medio | Media | Demanda |
| alquilar habitación a estudiantes | Medio | Media-alta | Propietario |
| app gestión gastos piso compartido | Bajo | Baja | Inquilinos |
| alquiler piso compartido sin comisión | Bajo-medio | Media | Estudiante, joven profesional |
| app para compartir piso | Bajo-medio | Media | Demanda |
| encontrar compañero de piso compatible | Bajo | Baja | Demanda |

---

### 3.4. Keywords por segmento

| Segmento | Keywords principales | Keywords long-tail |
|:---|:---|:---|
| **Estudiante 18-25** | compañero de piso universidad, habitación estudiantes | buscar compañero piso Erasmus, piso compartido cerca campus |
| **Joven profesional 25-35** | piso compartido jóvenes profesionales, alquilar habitación | compartir piso con desconocidos opiniones, piso compartido teletrabajo |
| **Trabajador desplazado** | habitación temporal, alquiler corta estancia | habitación amueblada por meses, piso temporal por trabajo |
| **Propietario particular** | alquilar habitación particular, buscar inquilino | cómo alquilar habitación legalmente, app gestión inquilinos |
| **Agencia / residencia** | llenar habitaciones estudiantes, captar inquilinos | software captación estudiantes vivienda, publicar habitaciones estudiantes |

---

## 4. Acciones técnicas SEO On-Page

El objetivo de esta fase es preparar la web para que Google y las redes sociales entiendan correctamente qué es ROOMA antes del lanzamiento. No se trata de desarrollar nuevas funcionalidades, sino de ajustar la capa pública de la aplicación para que sea rastreable, comprensible y compartible.

### 4.1. Optimización del documento principal

El documento principal de entrada de la aplicación debe dejar de ser genérico y pasar a comunicar claramente la propuesta de valor de ROOMA.

Acciones necesarias:

- cambiar el idioma principal de la web a español;
- sustituir el título genérico por un título descriptivo;
- añadir una descripción breve orientada a conversión;
- definir la URL principal del proyecto como referencia canónica;
- preparar la vista previa al compartir el enlace en redes sociales;
- añadir una imagen específica para previews en WhatsApp, LinkedIn, Facebook, Instagram y X;
- incluir un texto alternativo básico para usuarios o bots que no ejecuten JavaScript;
- evitar depender únicamente del contenido cargado por React para explicar qué es ROOMA.

### 4.2. Título y descripción recomendados

| Elemento | Contenido recomendado |
|:---|:---|
| Título SEO | ROOMA — Encuentra compañero de piso sin comisión |
| Descripción SEO | ROOMA te ayuda a encontrar compañero de piso compatible, sin agencia y sin comisión. Gestiona gastos compartidos, incidencias y pagos de forma sencilla. |
| Idioma | Español |
| URL canónica | Dominio principal de producción |
| Rastreo | Permitir indexación de páginas públicas |

### 4.3. Archivos técnicos básicos

Se deben añadir o revisar los siguientes archivos públicos:

| Archivo | Función |
|:---|:---|
| `robots.txt` | Indicar a los buscadores qué zonas pueden rastrear |
| `sitemap.xml` | Facilitar a Google las URLs principales del proyecto |
| `og-image.jpg` | Mejorar la vista previa al compartir la web en redes |
| `manifest.json` | Ajustar nombre, idioma y descripción de la PWA |

### 4.4. Recomendaciones para `robots.txt`

El archivo debe permitir la indexación de la web pública y bloquear rutas internas que no aportan valor SEO.

| Ruta | Tratamiento recomendado |
|:---|:---|
| Página principal | Permitir |
| Registro | Permitir |
| Login | Permitir |
| Panel interno | Bloquear si no aporta contenido público |
| API | Bloquear |
| Administración | Bloquear |

### 4.5. Recomendaciones para `sitemap.xml`

El sitemap debe incluir únicamente URLs públicas relevantes.

| URL | Prioridad |
|:---|:---:|
| Página principal | Alta |
| Registro | Alta |
| Login | Media |
| Futuras páginas locales | Alta |
| Futuro blog | Media |

### 4.6. Manifest PWA

La descripción actual de la PWA debe sustituirse por una descripción alineada con el producto real.

| Campo | Recomendación |
|:---|:---|
| Nombre | ROOMA — Compañero de piso sin comisión |
| Nombre corto | ROOMA |
| Descripción | Encuentra compañero de piso compatible, sin agencia y sin comisión. Gestiona gastos compartidos y alquila con confianza. |
| Idioma | Español |
| Display | Standalone |

### 4.7. Imagen Open Graph

Crear una imagen de 1200 × 630 px para previews en redes sociales.

Debe incluir:

- logo de ROOMA;
- mensaje principal: "Encuentra compañero de piso. Sin comisión. Sin fraudes.";
- mockup simple de la app;
- diseño limpio y legible en móvil.

Ubicación recomendada:

`frontend/public/og-image.jpg`

### 4.8. Datos estructurados

A medio plazo se recomienda añadir datos estructurados para que Google interprete ROOMA como una aplicación web. Esta mejora no es crítica para el lanzamiento, pero sí recomendable para reforzar SEO técnico en la fase de crecimiento.

---

## 5. Estrategia de contenidos SEO

### 5.1. Landing indexable

Para el lanzamiento, ROOMA debe contar con una landing indexable que pueda entenderse sin iniciar sesión.

La landing debe incluir:

- H1 claro con keyword principal;
- explicación breve de la propuesta de valor;
- beneficios para inquilinos;
- beneficios para propietarios;
- bloque de confianza;
- CTA de registro;
- texto visible con keywords naturales;
- enlaces a login y registro;
- preview correcto en redes.

### Estructura recomendada de la landing

| Bloque | Contenido |
|:---|:---|
| Hero | "Encuentra compañero de piso sin comisión" |
| Problema | Grupos caóticos, agencias, poca confianza |
| Solución | Matching, perfiles verificados y gestión de gastos |
| Beneficios demanda | Afinidad, ahorro, claridad |
| Beneficios oferta | Publicación, control, filtrado |
| Funciones clave | Match, chat, incidencias, facturas |
| CTA | Registrarse gratis |
| Confianza | Usuarios piloto, feedback, seguridad |

---

### 5.2. Blog / páginas de contenido

| Opción | Ventaja | Desventaja | Recomendación |
|:---|:---|:---|:---|
| Blog en subdirectorio `/blog` | Aporta autoridad al dominio principal | Requiere implementación técnica | Mejor opción a medio plazo |
| Blog externo | Rápido y simple | No transmite tanta autoridad al dominio | Útil como solución temporal |
| Landing estática | Rápida, indexable y enfocada | Limitada a pocas keywords | Mínimo necesario para lanzamiento |
| Páginas locales | Captan búsquedas por ciudad | Requieren contenido específico | Alta prioridad post-lanzamiento |

---

### 5.3. Calendario de contenidos SEO

| Mes | Contenido | Keyword objetivo | Formato |
|:---|:---|:---|:---|
| 1 | Cómo encontrar compañero de piso sin agencia | buscar compañero de piso sin agencia | Artículo blog |
| 1 | 5 errores al buscar piso compartido | errores buscar piso compartido | Artículo blog |
| 2 | Guía para dividir gastos del piso compartido | dividir gastos piso compartido | Guía |
| 2 | ROOMA vs Idealista vs grupos de Facebook | alternativa idealista piso compartido | Comparativa |
| 3 | Cómo alquilar tu habitación de forma segura | alquilar habitación particular | Artículo propietario |
| 3 | Derechos del inquilino en piso compartido | derechos inquilino piso compartido | Artículo informacional |
| 4 | Buscar piso compartido en Sevilla | piso compartido Sevilla | Landing local |
| 5 | Buscar piso compartido en Madrid | piso compartido Madrid | Landing local |
| 6 | Buscar piso compartido en Barcelona | piso compartido Barcelona | Landing local |

---

## 6. Linkbuilding y autoridad

### 6.1. Backlinks prioritarios

| Fuente | Tipo de enlace | Dificultad | Prioridad |
|:---|:---|:---:|:---:|
| Prensa universitaria | Nota de prensa / entrevista | Baja | 🔴 Alta |
| Blogs universitarios | Artículo o mención | Baja | 🔴 Alta |
| Directorios de startups | Perfil de empresa | Muy baja | 🔴 Alta |
| Product Hunt | Lanzamiento de producto | Baja | 🔴 Alta |
| Medios locales | Nota de prensa | Media | 🟠 Media |
| Blogs de vivienda / proptech | Guest post o mención | Media | 🟠 Media |
| Redes sociales | Perfil con enlace | Muy baja | 🔴 Alta |
| Reddit / foros | Participación orgánica | Baja | 🟠 Media |
| Influencers universitarios | Mención con enlace | Media | 🟠 Media |

### 6.2. Mensaje base para outreach

> Somos el equipo de ROOMA, una app creada para ayudar a estudiantes y jóvenes profesionales a encontrar compañero de piso sin agencia ni comisión, con perfiles verificados y gestión de gastos compartidos.
>
> Lanzamos públicamente el 21 de mayo y estamos buscando medios universitarios, blogs o comunidades interesadas en proyectos tecnológicos orientados a vivienda joven y convivencia.
>
> Podemos facilitar una breve nota de prensa, capturas de la app y contexto del proyecto.

---

## 7. SEO local

### 7.1. Google Business Profile

Crear un perfil de Google Business para ROOMA.

| Campo | Contenido |
|:---|:---|
| **Nombre** | ROOMA — App compañero de piso |
| **Categoría** | Aplicación móvil / Servicio inmobiliario |
| **Descripción** | ROOMA es una app para encontrar compañero de piso sin comisión y gestionar gastos compartidos. Perfiles verificados, matching por compatibilidad y sin intermediarios. |
| **Sitio web** | https://www.rooma.app |
| **Horario** | Servicio digital 24/7 |
| **Zona de servicio** | Sevilla inicialmente, con expansión progresiva |

### 7.2. Páginas locales futuras

| Ciudad | Keyword principal | Objetivo |
|:---|:---|:---|
| Sevilla | buscar compañero de piso Sevilla | Captar demanda universitaria local |
| Madrid | piso compartido Madrid | Captar volumen alto |
| Barcelona | piso compartido Barcelona | Captar volumen alto y estudiantes desplazados |
| Valencia | habitación estudiantes Valencia | Captar demanda universitaria |
| Granada | piso estudiantes Granada | Captar mercado universitario |

---

## 8. SEO y redes sociales

### 8.1. Optimización de perfiles sociales

Cada perfil social debe funcionar como una micro-landing.

| Red social | Estado actual | Acción SEO |
|:---|:---|:---|
| Instagram | Activo | Bio con keywords + enlace a web + CTA |
| YouTube | Activo | Descripción del canal con keywords + enlaces |
| LinkedIn | Activo | Descripción de empresa con keywords + enlace |
| TikTok | Pendiente / en preparación | Bio optimizada + enlace a web |
| X / Twitter | Opcional | Perfil de marca y enlace a landing |

### 8.2. Bio optimizada para Instagram / TikTok

> 🏠 Encuentra compañero de piso sin comisión  
> ✅ Perfiles verificados · Gestión de gastos  
> 📱 Disponible ya — link en bio  
> 🇪🇸 Sevilla · expansión progresiva  
> 👇 Regístrate gratis

### 8.3. SEO en vídeos

| Elemento | Recomendación |
|:---|:---|
| Título | Incluir keyword: "Cómo encontrar compañero de piso sin agencia | ROOMA" |
| Descripción | 150+ palabras con keywords, enlace y CTA |
| Hashtags | #compañerodepiso #alquiler #pisocompartido #sincomision #rooma |
| Subtítulos | Activar subtítulos para mejorar comprensión e indexación |
| Miniatura | Texto claro, logo y beneficio principal |
| Primeros segundos | Explicar problema y solución de forma directa |

---

## 9. Métricas SEO y seguimiento

### 9.1. Herramientas

| Herramienta | Propósito | Coste |
|:---|:---|:---:|
| Google Search Console | Indexación, keywords, errores | 0 € |
| Google Analytics 4 | Tráfico, comportamiento, conversiones | 0 € |
| Google Lighthouse | Auditoría técnica y SEO | 0 € |
| Ubersuggest / Ahrefs Free | Keywords y backlinks | Gratis / Freemium |
| PageSpeed Insights | Rendimiento y Core Web Vitals | 0 € |

---

### 9.2. KPIs SEO

| KPI | Objetivo Mes 1 | Objetivo Mes 6 | Objetivo Mes 12 |
|:---|:---:|:---:|:---:|
| Páginas indexadas | ≥ 3 | ≥ 15 | ≥ 30 |
| Impresiones en Google Search | 500+ | 10.000+ | 50.000+ |
| Clics orgánicos | 30+ | 800+ | 5.000+ |
| CTR medio en búsqueda | ≥ 3% | ≥ 5% | ≥ 6% |
| Posición media keywords de marca | Top 5 | Top 3 | Top 1 |
| Posición media keywords genéricas | Top 50 | Top 20 | Top 10 |
| Backlinks | 3+ | 15+ | 30+ |
| DA/DR orientativo | 5+ | 10+ | 15+ |
| Tráfico orgánico → registros | 5+ | 80+ | 500+ |
| % registros desde orgánico | 5% | 10% | 20-30% |

---

### 9.3. Relación con impresiones de redes y Ads

El tráfico SEO complementa y amplifica la inversión en Ads. Mientras los Ads generan impresiones pagadas inmediatas, el SEO genera impresiones orgánicas crecientes y acumulativas.

| Fuente SEO | Mes 1 | Mes 6 | Mes 12 |
|:---|:---:|:---:|:---:|
| Impresiones Google Search | ~500 | ~10.000 | ~50.000 |

### Lectura económica

El SEO reduce la dependencia de Ads a medio plazo. En el presupuesto económico, el CAC combinado se estima en **0,80 €/usuario** gracias a la mezcla de canales: Ads, orgánico, referidos, usuarios piloto y captación directa.

Una mejora SEO permite:

- captar usuarios sin pagar cada impresión;
- mejorar el CAC efectivo;
- aumentar registros orgánicos;
- reforzar marca;
- generar tráfico acumulativo;
- reducir riesgo de inflación publicitaria.

---

## 10. Cronograma de implementación

### Fase 1: Pre-lanzamiento

| Acción | Responsable | Prioridad |
|:---|:---|:---:|
| Actualizar `index.html` con meta tags SEO y Open Graph | Desarrollador frontend | 🔴 Crítica |
| Cambiar `lang="en"` a `lang="es"` | Desarrollador frontend | 🔴 Crítica |
| Crear `robots.txt` | Desarrollador frontend | 🔴 Alta |
| Crear `sitemap.xml` | Desarrollador frontend | 🔴 Alta |
| Crear imagen Open Graph | Diseñador / CM | 🔴 Alta |
| Actualizar descripción del manifest PWA | Desarrollador frontend | 🟠 Media |
| Registrar web en Google Search Console | CM / Marketing | 🔴 Alta |
| Configurar Google Analytics 4 | CM / Marketing | 🔴 Alta |
| Optimizar bios sociales | CM | 🔴 Alta |
| Crear perfil en TikTok | CM | 🟠 Media |

---

### Fase 2: Lanzamiento

| Acción | Responsable | Prioridad |
|:---|:---|:---:|
| Verificar indexación en Google Search Console | CM / Marketing | 🔴 Alta |
| Ejecutar auditoría Lighthouse SEO ≥ 80 | Frontend | 🔴 Alta |
| Registrar ROOMA en Product Hunt | Marketing | 🔴 Alta |
| Registrar en directorios de startups | Marketing | 🟠 Media |
| Publicar primer contenido indexable | CM | 🟠 Media |
| Crear Google Business Profile | CM | 🟠 Media |
| Enviar nota de prensa a medios universitarios | CM / Marketing | 🟠 Media |

---

### Fase 3: Crecimiento

| Acción | Responsable | Prioridad |
|:---|:---|:---:|
| Publicar 2 artículos SEO al mes | CM | 🔴 Alta |
| Crear landing pages locales | Frontend + CM | 🔴 Alta |
| Outreach para backlinks | Marketing | 🟠 Media |
| Optimizar titles y descriptions con datos reales | CM | 🟠 Media |
| Implementar Schema.org | Frontend | 🟠 Media |
| Evaluar SSR / SSG | Equipo técnico | 🟢 Baja |

---

## 11. Presupuesto SEO

| Partida | Coste | Frecuencia | Tratamiento económico |
|:---|---:|:---|:---|
| Google Search Console | 0 € | Continuo | Gratuito |
| Google Analytics 4 | 0 € | Continuo | Gratuito |
| Lighthouse / PageSpeed | 0 € | Puntual | Gratuito |
| Creación de contenidos | Incluido en CM | Mensual | Incluido en los 1.000 €/mes de Community Manager |
| Imagen Open Graph | 0-50 € | Una vez | Incluido en recursos creativos |
| Registro en directorios | 0 € | Una vez | Gratuito |
| Product Hunt | 0 € | Una vez | Gratuito |
| Linkbuilding orgánico | Incluido en marketing | Mensual | Tiempo de equipo |
| **Total coste adicional SEO** | **0-50 €** | — | Apoyado en recursos ya presupuestados |

---

## 12. Riesgos SEO

| Riesgo | Impacto | Mitigación |
|:---|:---|:---|
| Google no indexa bien la SPA | Baja visibilidad orgánica | Landing estática, sitemap, Search Console y contenido visible |
| Contenido demasiado genérico | No posiciona en keywords relevantes | Crear artículos y landings con intención clara |
| Falta de backlinks | Baja autoridad de dominio | Outreach a medios, universidades y directorios |
| Mala velocidad de carga | Peor experiencia y menor rendimiento SEO | Optimización de imágenes, bundles y Lighthouse |
| Duplicidad de URLs | Riesgo de contenido duplicado | Canonical URLs y sitemap controlado |
| Bajo CTR en resultados | Pocos clics aunque haya impresiones | Mejorar titles y meta descriptions |
| Dependencia excesiva de Ads | CAC más alto | SEO, referidos, orgánico y contenido evergreen |

---

## 13. Conclusión económica y estratégica

El SEO es una de las palancas con mejor retorno a medio y largo plazo para ROOMA, porque genera tráfico acumulativo y reduce la dependencia de campañas pagadas.

En el corto plazo, el objetivo no es competir de inmediato por keywords muy difíciles, sino asegurar que:

- la marca ROOMA se indexa correctamente;
- el enlace compartido en redes se ve profesional;
- Google entiende la propuesta de valor;
- los usuarios encuentran la web al buscar el proyecto;
- el canal orgánico empieza a aportar registros sin coste publicitario directo.

A medio plazo, el SEO debe apoyar tres objetivos del modelo económico:

1. Reducir el CAC efectivo.
2. Aumentar registros orgánicos.
3. Mejorar la confianza de usuarios, propietarios y medios.

Por tanto, este plan SEO complementa el plan de marketing, el presupuesto de lanzamiento y el análisis de riesgos, especialmente en lo relativo a adquisición de usuarios, inflación del CAC y sostenibilidad del crecimiento.
