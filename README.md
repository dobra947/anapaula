# Ana Paula Barahona - Portfolio

Web corporativa/portfolio desarrollada en **Astro** con enfoque extremo en rendimiento, SEO, accesibilidad y usabilidad.

## 🎨 Características principales

- **Rendimiento optimizado**: Diseñada para obtener 100/100/100/100 en Lighthouse
- **SEO avanzado**: Metadatos completos, JSON-LD, sitemap automático
- **Accesibilidad WCAG 2.2 AA**: HTML semántico, navegación por teclado, contraste AA
- **Diseño responsive**: Sistema de grid de 8pt, mobile-first
- **Estética única**: Blanco y negro con efectos de dibujo a lápiz

## 🚀 Stack tecnológico

- **Astro 5.x** - Framework principal
- **CSS moderno** - Variables, Grid, Flexbox, prefers-reduced-motion
- **@astrojs/sitemap** - Generación automática de sitemap
- **HTML semántico** - Estructura accesible y SEO-friendly

## 📁 Estructura del proyecto

```
/
├── public/
│   ├── favicon.svg
│   ├── manifest.webmanifest
│   ├── robots.txt
│   └── images/
├── src/
│   ├── components/
│   │   ├── SEO.astro
│   │   ├── Hero.astro
│   │   ├── Gallery.astro
│   │   └── PencilDivider.astro
│   ├── content/
│   │   └── obras/
│   │       ├── retrato-grafito.md
│   │       ├── paisaje-urbano.md
│   │       ├── estudio-botanico.md
│   │       └── abstraccion-geometrica.md
│   ├── layouts/
│   │   └── BaseLayout.astro
│   └── pages/
│       ├── index.astro
│       ├── sobre.astro
│       ├── contacto.astro
│       └── obras/
│           ├── index.astro
│           └── [slug].astro
├── astro.config.mjs
├── package.json
└── README.md
```

## 🛠️ Instalación y desarrollo

### Prerrequisitos

- Node.js 18+ 
- npm o yarn

### Instalación

```bash
# Clonar el repositorio
git clone [URL_DEL_REPO]
cd ana-paula-portfolio

# Instalar dependencias
npm install

# Iniciar servidor de desarrollo
npm run dev
```

### Scripts disponibles

```bash
# Desarrollo
npm run dev          # Servidor de desarrollo en http://localhost:4321

# Construcción
npm run build        # Construir para producción
npm run preview      # Vista previa de la build

# Utilidades
npm run astro        # CLI de Astro
```

## 🎯 Páginas implementadas

### Página principal (/)
- Hero con nombre y claim
- Galería de obras destacadas
- Sección "sobre mí" resumida
- Call-to-action para contacto
- JSON-LD: Person + WebSite

### Obras (/obras)
- Galería completa con filtros
- Lightbox accesible con `<dialog>`
- Navegación por teclado
- JSON-LD: CollectionPage

### Detalle de obra (/obras/[slug])
- Imagen optimizada con lazy loading
- Descripción completa y ficha técnica
- Navegación anterior/siguiente
- Breadcrumbs
- JSON-LD: CreativeWork

### Sobre mí (/sobre)
- Biografía completa
- Skills y especialidades
- Timeline de formación
- Filosofía artística
- JSON-LD: AboutPage

### Contacto (/contacto)
- Múltiples formas de contacto
- Servicios disponibles
- FAQ expandible
- JSON-LD: ContactPage

## 🎨 Sistema de diseño

### Paleta de colores
```css
--color-black: #000000
--color-white: #ffffff
--color-gray-light: #f8f8f8
--color-gray: #666666
```

### Sistema de espaciado (8pt grid)
```css
--space-1: 8px    --space-6: 48px
--space-2: 16px   --space-8: 64px
--space-3: 24px   --space-10: 80px
--space-4: 32px   --space-12: 96px
--space-5: 40px
```

### Tipografía
- **UI/Texto**: system-ui, Inter (sistema)
- **Decorativa**: Títulos con fuente display
- **Tamaños responsive** con clamp()

## ♿ Accesibilidad

### Implementado
- ✅ HTML semántico (header, nav, main, section, footer)
- ✅ Contraste AA en toda la interfaz
- ✅ Focus visible personalizado
- ✅ Alt descriptivo en todas las imágenes
- ✅ Aria-labels en iconos y controles
- ✅ Navegación por teclado completa
- ✅ Skip links para contenido principal
- ✅ Respeto a prefers-reduced-motion
- ✅ Estructura de headings jerárquica

### Testing
```bash
# Validar HTML
https://validator.w3.org/

# Verificar contraste
https://webaim.org/resources/contrastchecker/

# Lighthouse
npm run build && npm run preview
# Abrir DevTools > Lighthouse > Generar reporte
```

## 🔍 SEO

### Meta tags implementados
- Title único por página
- Meta description específica
- Canonical URLs
- Open Graph completo
- Twitter Cards
- Meta viewport y theme-color

### JSON-LD schemas
- **HomePage**: Person + WebSite
- **ObrasPage**: CollectionPage + ItemList
- **ObraDetail**: CreativeWork
- **AboutPage**: AboutPage + Person
- **ContactPage**: ContactPage + ContactPoint

### Sitemap y robots
- Sitemap automático con @astrojs/sitemap
- robots.txt optimizado
- URLs limpias sin .html

## 🚀 Rendimiento

### Optimizaciones implementadas
- **Imágenes**: Lazy loading, dimensiones fijas (previene CLS)
- **CSS**: Variables nativas, sin frameworks pesados
- **Fonts**: System fonts o autoalojadas con font-display: swap
- **JS**: Mínimo JS, solo para funcionalidades esenciales
- **Build**: CSS crítico inline, compresión HTML

### Objetivo Lighthouse
- Performance: 100/100
- Accessibility: 100/100  
- Best Practices: 100/100
- SEO: 100/100

## 🔒 Seguridad

### Headers recomendados (configurar en hosting)
```
X-Content-Type-Options: nosniff
Referrer-Policy: strict-origin-when-cross-origin
Permissions-Policy: geolocation=(), camera=(), microphone=()
Content-Security-Policy: default-src 'self'; img-src 'self' data: https:; script-src 'self'; style-src 'self' 'unsafe-inline'
```

## 📱 Responsive Design

### Breakpoints
- Mobile: < 768px
- Tablet: 768px - 1024px  
- Desktop: > 1024px

### Grid system
- CSS Grid para layouts principales
- Flexbox para componentes
- Sistema mobile-first

## 🎛️ Configuración

### astro.config.mjs
```javascript
export default defineConfig({
  site: 'https://anapaulabarahona.com',
  integrations: [sitemap()],
  output: 'static',
  build: {
    inlineStylesheets: 'auto',
  },
  compressHTML: true,
});
```

### Variables de entorno
Crear `.env` para configuración específica:
```env
SITE_URL=https://anapaulabarahona.com
```

## 🚀 Despliegue — Pasos prácticos para producción

A continuación tienes instrucciones claras y ejemplos prácticos para desplegar el sitio en diferentes plataformas. Copia y pega los snippets según la opción que elijas.

Requisito previo: sube el código a un repositorio remoto (GitHub, GitLab o similar) y verifica que la rama principal esté preparada (por ejemplo `main`).

A) Netlify (fácil, CI automático)

1. Subir el repo a GitHub y empujar la rama principal:

```bash
git add .
git commit -m "Prepara despliegue"
git push origin main
```

2. En Netlify: New site -> Import from Git -> conecta GitHub -> selecciona repo.
3. Configura los settings de build:
   - Build command: `npm run build`
   - Publish directory: `dist`
4. (Opcional) Añade variables de entorno en Site settings → Build & deploy → Environment.
5. Despliega. Netlify hará builds automáticos en cada push a la rama configurada.
6. Para cabeceras/redirects, crea `public/_headers` o `_redirects` si necesitas reglas personalizadas.

Ejemplo rápido de `_headers` (opcional):

```
/*
  X-Content-Type-Options: nosniff
  Referrer-Policy: strict-origin-when-cross-origin
  Permissions-Policy: geolocation=(), camera=(), microphone=()
  Cache-Control: public, max-age=31536000, immutable
```

B) Vercel (preview + deploy automático)

1. En vercel.com -> Import Project -> From Git -> selecciona tu repo.
2. Si es necesario, configura:
   - Build command: `npm run build`
   - Output directory: `dist`
3. Añade variables de entorno en Project Settings -> Environment Variables.
4. Push a `main` y Vercel hará el build y deploy.

También puedes usar la CLI:
```bash
npm i -g vercel
vercel # sigue el asistente
```

C) Cloudflare Pages

1. En Cloudflare Pages -> Create a project -> conecta tu repo.
2. Configura:
   - Framework preset: None
   - Build command: `npm run build`
   - Build output directory: `dist`
3. Añade variables en Settings -> Environment variables.
4. Deploy.

D) GitHub Pages con GitHub Actions (ejemplo automatizado)

1. Añade este workflow en `.github/workflows/deploy.yml` (ejemplo básico usando `peaceiris/actions-gh-pages`):

```yaml
name: Deploy to GitHub Pages
on:
  push:
    branches: [ main ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 18
      - run: npm ci
      - run: npm run build
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./dist
```

2. Push el workflow y el repo; la Action hará build y publicará `dist/` en la rama `gh-pages`.
3. Activa GitHub Pages en Settings si necesitas servir desde `gh-pages`.

E) Despliegue manual (S3, FTP, servidor estático)

1. Construye localmente:
```bash
npm ci
npm run build
```
2. Sube el contenido de `dist/` al hosting (S3 bucket, FTP, servidor estático).
3. Asegura que `index.html` esté en la raíz pública.

F) Comprobaciones post-despliegue (imprescindible)

- Abrir el dominio público y verificar que carga correctamente.
- DevTools → Network: comprobar que `/fonts/Handodle.woff2` devuelve 200 y otras fuentes/imagenes no 404.
- Lighthouse (Prod): revisar Performance, Accessibility, Best Practices y SEO.
- Verificar sitemap en `/sitemap-index.xml` y `robots.txt`.
- Comprobar Open Graph / JSON-LD con https://metatags.io/.

G) Recomendaciones de headers y caché

- Añade headers de seguridad y caché en tu CDN/hosting:
  - X-Content-Type-Options: nosniff
  - Referrer-Policy: strict-origin-when-cross-origin
  - Permissions-Policy: geolocation=(), camera=(), microphone=()
  - Cache-Control: `public, max-age=31536000, immutable` para fonts/images versionadas
  - Content-Security-Policy: ajusta según recursos usados

H) ¿Necesitas que lo configure por ti?

Puedo generar automáticamente:
- El archivo `.github/workflows/deploy.yml` para GitHub Pages
- Un ejemplo de `_headers` (Netlify)
- Un script de deploy para Vercel/Netlify

Dime cuál prefieres y lo añado al repo (commit + push si quieres). 

## 📝 Contenido

### Agregar nuevas obras
1. Crear archivo .md en `src/content/obras/`
2. Usar el frontmatter requerido:
```yaml
---
title: "Título de la obra"
date: "2024-MM-DD"
technique: "Técnica utilizada"
summary: "Resumen breve"
image: "/images/obra.jpg"
alt: "Descripción de la imagen"
slug: "url-slug"
featured: true/false
---
```

### Imágenes
- Colocar en `public/images/`
- Formatos recomendados: WebP, AVIF, JPEG
- Tamaños optimizados para web
- Alt text descriptivo obligatorio

## 🐛 Troubleshooting

### Problemas comunes

**Build falla**
```bash
rm -rf node_modules package-lock.json
npm install
npm run build
```

**Imágenes no cargan**
- Verificar rutas en `public/images/`
- Comprobar nombres de archivo exactos
- Verificar permisos de archivos

**Lighthouse bajo rendimiento**
- Optimizar imágenes (tamaño y formato)
- Verificar que no hay JS innecesario
- Comprobar fonts autoalojadas

## 📄 Licencia

Este proyecto está bajo licencia MIT. Ver `LICENSE` para más detalles.

## 🤝 Contribución

1. Fork del proyecto
2. Crear branch para features (`git checkout -b feature/AmazingFeature`)
3. Commit cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push al branch (`git push origin feature/AmazingFeature`)
5. Abrir Pull Request

## 📞 Soporte

Para consultas sobre el desarrollo de este portfolio:
- Email: [tu-email]
- GitHub Issues: [link-al-repo]

---

**Desarrollado con ❤️ usando Astro**
