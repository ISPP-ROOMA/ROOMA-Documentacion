# Plan de SEO — ROOMA

**Proyecto:** ROOMA — App para encontrar compañero de piso sin agencia + gestionar gastos compartidos  
**Fase:** Pre-lanzamiento y lanzamiento (mayo 2026)  
**Vinculado a:** `plan-marketing-pre-lanzamiento.md`

---

## 1. DIAGNÓSTICO ACTUAL

### Estado técnico de la web

| Aspecto | Estado actual | Impacto SEO |
|:---|:---|:---|
| **`<title>`** | Genérico: `Rooma` | Negativo — no comunica propuesta de valor |
| **Meta description** | No existe | Negativo — Google genera snippet automático |
| **Open Graph / Twitter Cards** | No existen | Negativo — al compartir en redes no muestra imagen ni descripción |
| **Idioma del HTML** | `lang="en"` | Negativo — el público objetivo es español |
| **robots.txt** | No existe | Neutro — Google indexa todo por defecto, pero sin control |
| **sitemap.xml** | No existe | Negativo — Google no conoce la estructura de URLs |
| **Heading structure (H1)** | Gestionado por React en cada vista | Variable — depende del componente |
| **Renderizado** | SPA (React + Vite) | Riesgo — los bots pueden no ejecutar JS; el contenido puede no indexarse |
| **PWA (manifest.json)** | Existe pero con descripción genérica: `"A room booking application"` | Negativo — no refleja la propuesta de valor |
| **Canonical URL** | No definida | Riesgo de contenido duplicado |
| **Velocidad de carga** | No medida | Pendiente de auditoría con Lighthouse |
| **Datos estructurados (Schema.org)** | No existen | Oportunidad perdida de rich snippets |

### Conclusión del diagnóstico

La web actual de ROOMA no tiene prácticamente ninguna optimización SEO. Al ser una SPA renderizada en el cliente (CSR), Google puede tener dificultades para indexar el contenido. Las acciones prioritarias son: mejorar el `index.html`, crear una landing page estática indexable, y configurar los archivos técnicos básicos.

---

## 2. OBJETIVOS SEO

### Objetivos a corto plazo (antes del lanzamiento — 13 mayo)
- Que al buscar "ROOMA app" en Google aparezca la web en el primer resultado
- Que al compartir la URL en redes sociales se muestre un preview atractivo con imagen, título y descripción
- Que la web tenga una puntuación Lighthouse ≥ 80 en SEO
- Configurar los archivos técnicos básicos: `robots.txt`, `sitemap.xml`, meta tags

### Objetivos a medio plazo (meses 1–6 post-lanzamiento)
- Posicionar para búsquedas de marca: "rooma app", "rooma piso", "rooma compañero de piso"
- Aparecer en las primeras 3 páginas para búsquedas genéricas locales: "buscar compañero de piso [ciudad]"
- Generar tráfico orgánico que represente al menos el 10% de los registros mensuales
- Conseguir 5–10 backlinks de calidad (prensa universitaria, blogs de vivienda, directorios de apps)

### Objetivos a largo plazo (meses 6–12)
- Posicionar en primera página para keywords transaccionales: "app compañero de piso", "alquilar habitación sin agencia"
- Tráfico orgánico que represente el 20-30% de los registros mensuales
- Domain Authority (DA) ≥ 15

---

## 3. INVESTIGACIÓN DE PALABRAS CLAVE

### 3.1. Keywords de marca (brand)

| Keyword | Volumen estimado | Dificultad | Prioridad |
|:---|:---:|:---:|:---:|
| rooma app | Bajo (nuevo) | Muy baja | **Alta** |
| rooma compañero de piso | Bajo (nuevo) | Muy baja | **Alta** |
| rooma pisos | Bajo (nuevo) | Muy baja | **Alta** |

> **Acción:** Estas keywords deben estar controladas desde el día 1. El título, la descripción y el contenido de la landing deben contenerlas.

### 3.2. Keywords informacionales (awareness / top-of-funnel)

| Keyword | Volumen estimado | Dificultad | Segmento objetivo |
|:---|:---:|:---:|:---|
| cómo buscar compañero de piso | Medio | Media | Estudiante, joven profesional |
| consejos para compartir piso | Medio | Media | Estudiante |
| cómo dividir gastos del piso | Medio-bajo | Baja | Todos los inquilinos |
| qué preguntar antes de compartir piso | Bajo-medio | Baja | Estudiante, joven profesional |
| derechos del inquilino piso compartido | Medio | Media-alta | Todos |
| cómo evitar estafas alquiler | Medio | Media | Estudiante, trabajador desplazado |

### 3.3. Keywords transaccionales (conversión / bottom-of-funnel)

| Keyword | Volumen estimado | Dificultad | Segmento objetivo |
|:---|:---:|:---:|:---|
| app buscar compañero de piso | Bajo-medio | Media | Estudiante, joven profesional |
| buscar compañero de piso Sevilla | Medio | Media-alta | Estudiante (local) |
| buscar habitación sin agencia | Medio | Media | Todos demanda |
| alquilar habitación a estudiantes | Medio | Media-alta | Propietario particular |
| app gestión gastos piso compartido | Bajo | Baja | Todos |
| alquiler piso compartido sin comisión | Bajo-medio | Media | Estudiante, joven profesional |

### 3.4. Keywords por segmento (alineadas con plan de marketing §3)

| Segmento | Keywords principales | Keywords long-tail |
|:---|:---|:---|
| **Estudiante (18-25)** | compañero de piso universidad, habitación estudiantes | buscar compañero piso Erasmus, piso compartido cerca campus |
| **Joven profesional (25-35)** | piso compartido jóvenes profesionales, alquilar habitación | compartir piso con desconocidos opiniones, piso compartido teletrabajo |
| **Trabajador desplazado** | habitación temporal, alquiler corta estancia | habitación amueblada meses, piso temporal por trabajo |
| **Propietario** | alquilar habitación particular, buscar inquilino | cómo alquilar habitación legalmente, app gestión inquilinos |

---

## 4. ACCIONES TÉCNICAS (SEO On-Page)

### 4.1. Mejoras en `index.html` (PRIORITARIO)

El archivo `index.html` actual es la base de toda la aplicación. Se deben añadir las siguientes meta tags:

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <!-- SEO básico -->
    <title>ROOMA — Encuentra compañero de piso sin comisión | App de alquiler compartido</title>
    <meta name="description" content="ROOMA te ayuda a encontrar compañero de piso compatible, sin agencia y sin comisión. Gestiona gastos compartidos y alquila con confianza. Disponible en España." />
    <meta name="keywords" content="compañero de piso, alquiler compartido, buscar habitación, sin comisión, app piso compartido, gestión gastos piso" />
    <meta name="author" content="ROOMA" />
    <link rel="canonical" href="https://www.rooma.app/" />

    <!-- Open Graph (Facebook, LinkedIn, WhatsApp) -->
    <meta property="og:type" content="website" />
    <meta property="og:title" content="ROOMA — Encuentra compañero de piso sin comisión" />
    <meta property="og:description" content="App para encontrar compañero de piso compatible y gestionar gastos compartidos. Sin agencia. Sin fraudes." />
    <meta property="og:image" content="https://www.rooma.app/og-image.jpg" />
    <meta property="og:url" content="https://www.rooma.app/" />
    <meta property="og:locale" content="es_ES" />
    <meta property="og:site_name" content="ROOMA" />

    <!-- Twitter Cards -->
    <meta name="twitter:card" content="summary_large_image" />
    <meta name="twitter:title" content="ROOMA — Encuentra compañero de piso sin comisión" />
    <meta name="twitter:description" content="App para encontrar compañero de piso compatible y gestionar gastos compartidos." />
    <meta name="twitter:image" content="https://www.rooma.app/og-image.jpg" />

    <!-- Favicon e iconos -->
    <link rel="icon" type="image/jpeg" href="/Logo Rooma.jpeg" />
    <link rel="apple-touch-icon" href="/icons/rooma_192.png" />

    <!-- Verificación Google Search Console (sustituir con código real) -->
    <!-- <meta name="google-site-verification" content="CÓDIGO_VERIFICACIÓN" /> -->

    <script src="https://accounts.google.com/gsi/client" async defer></script>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.tsx"></script>
  </body>
</html>
```

### 4.2. Crear `robots.txt`

Ubicación: `frontend/public/robots.txt`

```
User-agent: *
Allow: /
Disallow: /admin/
Disallow: /api/

Sitemap: https://www.rooma.app/sitemap.xml
```

### 4.3. Crear `sitemap.xml`

Ubicación: `frontend/public/sitemap.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaporg/schemas/sitemap/0.9">
  <url>
    <loc>https://www.rooma.app/</loc>
    <lastmod>2026-05-13</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://www.rooma.app/login</loc>
    <lastmod>2026-05-13</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.6</priority>
  </url>
  <url>
    <loc>https://www.rooma.app/register</loc>
    <lastmod>2026-05-13</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
</urlset>
```

### 4.4. Corregir el manifest de la PWA

En `vite.config.ts`, actualizar la descripción del manifest:

```typescript
manifest: {
  name: 'ROOMA — Compañero de piso sin comisión',
  short_name: 'ROOMA',
  description: 'Encuentra compañero de piso compatible, sin agencia y sin comisión. Gestiona gastos compartidos y alquila con confianza.',
  theme_color: '#ffffff',
  // ...iconos existentes
}
```

### 4.5. Imagen Open Graph

Crear una imagen de 1200×630 px para previews en redes sociales con:
- Logo de ROOMA
- Tagline: "Encuentra compañero de piso. Sin comisión. Sin fraudes."
- Mockup simplificado de la app
- Guardar como `frontend/public/og-image.jpg`

---

## 5. ESTRATEGIA DE CONTENIDOS (SEO Off-Page + Content Marketing)

### 5.1. Blog / Landing pages de contenido

Para posicionar en keywords informacionales y transaccionales, se recomienda crear contenido indexable fuera de la SPA. Opciones:

| Opción | Ventaja | Desventaja | Recomendación |
|:---|:---|:---|:---|
| **Blog en subdirectorio** (`rooma.app/blog`) | Mejor para SEO (autoridad del dominio) | Requiere SSR o generación estática | Ideal a medio plazo |
| **Blog externo** (Medium, Substack) | Rápido de montar, sin desarrollo | No aporta autoridad al dominio principal | Aceptable como inicio |
| **Landing estática** (`rooma.app/`) | Indexable, rápida, con meta tags | Solo una página | Mínimo viable para el lanzamiento |

**Recomendación para el lanzamiento:** Crear al menos una landing page estática (HTML puro o pre-renderizada) en la raíz de la web que sea indexable por Google sin necesidad de ejecutar JavaScript. Esta página debe contener el mensaje principal, los beneficios, un CTA de registro y las keywords objetivo.

### 5.2. Calendario de contenidos SEO (post-lanzamiento)

| Mes | Contenido | Keyword objetivo | Formato |
|:---|:---|:---|:---|
| 1 | "Cómo encontrar compañero de piso sin agencia" | buscar compañero de piso sin agencia | Artículo blog / post |
| 1 | "5 errores al buscar piso compartido" | errores buscar piso compartido | Artículo blog / post |
| 2 | "Guía para dividir gastos del piso compartido" | dividir gastos piso compartido | Artículo guía |
| 2 | "ROOMA vs Idealista vs grupos Facebook: comparativa" | alternativa idealista piso compartido | Artículo comparativo |
| 3 | "Cómo alquilar tu habitación de forma segura" | alquilar habitación particular | Artículo (segmento propietario) |
| 3 | "Derechos del inquilino en piso compartido" | derechos inquilino piso compartido | Artículo informacional |
| 4 | "Buscar piso compartido en Sevilla: guía completa" | piso compartido Sevilla | Landing local |
| 5 | "Buscar piso compartido en Madrid: guía completa" | piso compartido Madrid | Landing local |
| 6 | "Buscar piso compartido en Barcelona: guía completa" | piso compartido Barcelona | Landing local |

### 5.3. Linkbuilding (backlinks)

| Fuente | Tipo de enlace | Dificultad | Prioridad |
|:---|:---|:---:|:---:|
| **Prensa universitaria** (periódicos de facultad, blogs de universidad) | Nota de prensa / entrevista | Baja | **Alta** |
| **Directorios de startups** (StartupXplore, Crunchbase, AngelList) | Perfil de empresa | Muy baja | **Alta** |
| **Product Hunt** | Lanzamiento de producto | Baja | **Alta** |
| **Blogs de vivienda / proptech** | Guest post o mención | Media | **Media** |
| **Medios locales** (periódicos digitales de Sevilla, etc.) | Nota de prensa | Media | **Media** |
| **Redes sociales** (Instagram, TikTok, LinkedIn, YouTube) | Perfil con enlace a web | Muy baja | **Alta** |
| **Reddit / foros** | Participación orgánica con enlace contextual | Baja | **Media** |
| **Colaboraciones con influencers universitarios** | Mención en vídeo/post con enlace | Media | **Media** |

---

## 6. SEO LOCAL

### 6.1. Google Business Profile

Crear un perfil de Google Business (anteriormente Google My Business) para ROOMA:

| Campo | Contenido |
|:---|:---|
| **Nombre** | ROOMA — App compañero de piso |
| **Categoría** | Servicio de alquiler de inmuebles / Aplicación móvil |
| **Descripción** | ROOMA es una app para encontrar compañero de piso sin comisión y gestionar gastos compartidos. Perfiles verificados, matching por compatibilidad y sin intermediarios. |
| **Sitio web** | https://www.rooma.app |
| **Horario** | No aplica (servicio digital 24/7) |
| **Zona de servicio** | Sevilla (expandir a otras ciudades progresivamente) |

### 6.2. Fichas en directorios locales

- Páginas Amarillas digital
- Yelp (categoría servicios)
- Directorios de startups españolas (StartupXplore, SeedRocket, etc.)

---

## 7. SEO Y REDES SOCIALES (alineado con plan de marketing §5 y §6)

### 7.1. Optimización de perfiles sociales

Cada perfil social debe funcionar como un micro-landing page con SEO básico:

| Red social | Estado actual | Acción SEO |
|:---|:---|:---|
| **Instagram** (@roomaapp) | Activo | Bio con keywords + enlace a web + CTA claro |
| **YouTube** | Activo | Descripción del canal con keywords + enlaces + tags en vídeos |
| **LinkedIn** | Activo | Descripción de empresa con keywords + enlace a web |
| **TikTok** | Pendiente | Crear perfil con bio optimizada + enlace Linktree/web |

### 7.2. Ejemplo de bio optimizada (Instagram)

```
🏠 Encuentra compañero de piso sin comisión
✅ Perfiles verificados · Gestión de gastos
📱 Disponible ya — link en bio
🇪🇸 Sevilla · Madrid · Barcelona
👇 Regístrate gratis
[enlace a rooma.app]
```

### 7.3. SEO en vídeos (YouTube y TikTok)

Para que los vídeos aparezcan en búsquedas de Google y dentro de cada plataforma:

| Elemento | Recomendación |
|:---|:---|
| **Título** | Incluir keyword principal: "Cómo encontrar compañero de piso sin agencia \| ROOMA" |
| **Descripción** | Texto de 150+ palabras con keywords, enlace a la web y CTAs |
| **Tags / Hashtags** | #compañerodepiso #alquiler #pisocompartido #sincomision #rooma |
| **Subtítulos** | Activar subtítulos automáticos (mejora indexación) |
| **Miniatura** | Atractiva, con texto legible y branding ROOMA |

---

## 8. MÉTRICAS SEO Y SEGUIMIENTO

### 8.1. Herramientas a configurar

| Herramienta | Propósito | Coste |
|:---|:---|:---:|
| **Google Search Console** | Monitorizar indexación, keywords, errores | Gratis |
| **Google Analytics 4** | Tráfico, comportamiento de usuario, conversiones | Gratis |
| **Google Lighthouse** | Auditoría de rendimiento, accesibilidad y SEO | Gratis |
| **Ubersuggest / Ahrefs (free)** | Investigación de keywords y backlinks | Gratis / Freemium |

### 8.2. KPIs de SEO

| KPI | Objetivo Mes 1 | Objetivo Mes 6 | Objetivo Mes 12 |
|:---|:---:|:---:|:---:|
| **Páginas indexadas** | ≥ 3 | ≥ 15 | ≥ 30 |
| **Impresiones en Google Search** | 500+ | 10.000+ | 50.000+ |
| **Clics orgánicos** | 30+ | 800+ | 5.000+ |
| **CTR medio en búsqueda** | ≥ 3% | ≥ 5% | ≥ 6% |
| **Posición media (keywords de marca)** | Top 5 | Top 3 | Top 1 |
| **Posición media (keywords genéricas)** | Top 50 | Top 20 | Top 10 |
| **Backlinks** | 3+ | 15+ | 30+ |
| **Domain Authority** | 5+ | 10+ | 15+ |
| **Tráfico orgánico → registros** | 5+ | 80+ | 500+ |
| **% registros desde orgánico** | 5% | 10% | 20-30% |

### 8.3. Relación con impresiones de redes sociales (plan de marketing §5)

El tráfico SEO complementa y amplifica la inversión en Ads. Mientras los Ads generan impresiones pagadas inmediatas, el SEO genera impresiones orgánicas crecientes y acumulativas:

| Fuente | Mes 1 | Mes 6 | Mes 12 |
|:---|:---:|:---:|:---:|
| **Impresiones Ads (TikTok + Meta)** | ~13.400 | ~119.000 | ~1.415.000 |
| **Impresiones orgánicas RRSS** | ~1.300 – 12.000 | ~15.000 – 50.000 | ~80.000 – 200.000 |
| **Impresiones Google Search (SEO)** | ~500 | ~10.000 | ~50.000 |
| **Total impresiones** | **~15.200 – 25.900** | **~144.000 – 179.000** | **~1.545.000 – 1.665.000** |

> **Ventaja clave del SEO:** El coste marginal por impresión orgánica tiende a 0 €. Mientras que cada impresión en Ads cuesta ~0,005 – 0,006 €, las impresiones SEO son gratuitas una vez posicionado el contenido. A medida que la autoridad del dominio crece, el SEO se convierte en el canal más rentable.

---

## 9. CRONOGRAMA DE IMPLEMENTACIÓN

### Fase 1: Antes del lanzamiento (semanas 3-4 pre-lanzamiento)

| Acción | Responsable | Prioridad |
|:---|:---|:---:|
| Actualizar `index.html` con meta tags SEO y Open Graph | Desarrollador frontend | **Crítica** |
| Cambiar `lang="en"` a `lang="es"` | Desarrollador frontend | **Crítica** |
| Crear `robots.txt` | Desarrollador frontend | **Alta** |
| Crear `sitemap.xml` | Desarrollador frontend | **Alta** |
| Crear imagen Open Graph (1200×630) | Diseñador / CM | **Alta** |
| Actualizar descripción del manifest PWA | Desarrollador frontend | **Media** |
| Registrar web en Google Search Console | CM / Marketing | **Alta** |
| Configurar Google Analytics 4 | CM / Marketing | **Alta** |
| Optimizar bios de redes sociales (Instagram, LinkedIn, YouTube) | CM | **Alta** |
| Crear perfil en TikTok | CM | **Media** |

### Fase 2: Lanzamiento (semanas 1-4 post-lanzamiento)

| Acción | Responsable | Prioridad |
|:---|:---|:---:|
| Verificar indexación correcta en Google Search Console | CM / Marketing | **Alta** |
| Auditoría Lighthouse (score SEO ≥ 80) | Desarrollador frontend | **Alta** |
| Registrar ROOMA en Product Hunt | Marketing | **Alta** |
| Registrar en directorios de startups (StartupXplore, Crunchbase) | Marketing | **Media** |
| Publicar primer artículo de blog / contenido indexable | CM | **Media** |
| Crear Google Business Profile | CM | **Media** |
| Enviar nota de prensa a medios universitarios | CM / Marketing | **Media** |

### Fase 3: Crecimiento (meses 2-6)

| Acción | Responsable | Prioridad |
|:---|:---|:---:|
| Publicar 2 artículos de blog al mes (keywords informacionales) | CM | **Alta** |
| Crear landing pages locales (Sevilla, Madrid, Barcelona) | Desarrollador + CM | **Alta** |
| Outreach para backlinks (blogs, prensa, colaboraciones) | Marketing | **Media** |
| Optimizar títulos y meta descriptions según datos de Search Console | CM | **Media** |
| Implementar datos estructurados (Schema.org) | Desarrollador frontend | **Media** |
| Evaluar implementación de SSR/SSG para mejorar indexación | Equipo técnico | **Baja** |

---

## 10. PRESUPUESTO SEO

| Partida | Coste | Frecuencia | Notas |
|:---|:---:|:---|:---|
| Herramientas (Search Console, GA4, Lighthouse) | 0 € | — | Todas gratuitas |
| Creación de contenidos (blog) | Incluido en CM | Mensual | El CM dedica ~20% de su tiempo a contenido SEO |
| Imagen Open Graph | ~50 € | Una vez | Diseño profesional o herramienta tipo Canva |
| Registro en directorios | 0 € | Una vez | La mayoría son gratuitos |
| Product Hunt launch | 0 € | Una vez | Solo requiere preparación |
| **Total coste adicional SEO** | **~50 €** | — | El SEO se apoya en recursos ya presupuestados (CM, desarrollo) |

> **Conclusión económica:** El SEO es la estrategia de marketing con mejor ROI a medio-largo plazo. Con un coste adicional prácticamente nulo (se apoya en el CM y el equipo de desarrollo ya presupuestados), genera impresiones y tráfico orgánico creciente que reduce progresivamente la dependencia de la inversión en Ads.
