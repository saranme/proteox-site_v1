# proteox.com

Sitio estático de Proteox Ltd. HTML, CSS y JS propios; sin dependencias externas, sin analítica, sin cookies.

## Estructura

- `index.html` — la web (una sola página)
- `privacy.html` — aviso de privacidad (enlazado como `/privacy`)
- `404.html` — página de error (Cloudflare Pages la sirve automáticamente)
- `img/` — ilustraciones de fondo
- `fonts/` — Inter e Instrument Serif, autoalojadas (licencia OFL incluida)
- `favicon.ico`, `og-image.png`, `robots.txt`, `sitemap.xml`
- `_headers` — cabeceras de seguridad y caché (formato Cloudflare Pages)
- `_redirects` — `proteox.com` → `www.proteox.com` y `/privacy` → `privacy.html`

## Despliegue en Cloudflare Pages

1. Crea un repositorio en GitHub (por ejemplo `proteox-site`) y sube el contenido de esta carpeta a la raíz (no dentro de una subcarpeta).
2. En Cloudflare: **Workers & Pages → Create → Pages → Connect to Git** → elige el repositorio.
3. Configuración del build:
   - Framework preset: **None**
   - Build command: *(vacío)*
   - Build output directory: `/`
4. Deploy. Cloudflare te da una URL `*.pages.dev` para comprobarlo.
5. **Custom domains**: añade `www.proteox.com` y `proteox.com`. Si el DNS de proteox.com ya está en Cloudflare, los registros se crean solos; si no, apunta `www` con un CNAME a `<proyecto>.pages.dev` y sigue las instrucciones para el dominio raíz.
6. HTTPS se activa solo. La redirección de `proteox.com` a `www.proteox.com` la hace `_redirects`.

Cada `git push` a la rama principal vuelve a desplegar la web.

## Antes de publicar (del brief)

- Pedir reindexación en Google Search Console tras el primer despliegue.
- Comprobar la vista previa del enlace en LinkedIn y WhatsApp (OG image).
- Revisar en móvil real.
- Lighthouse > 90 en rendimiento y accesibilidad.
