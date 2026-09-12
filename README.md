# Perderte a ti, fue encontrarme a mí — Landing

Landing de venta de la guía digital **«Perderte a ti, fue encontrarme a mí»** de
**Leidy Sepúlveda · Alma e Imagen**.

Página estática, sin build. Un solo `index.html` + la carpeta `assets/`.
Diseño 100% propio (sin frameworks ni CDN), optimizado para móvil y para
verse bien incluso en el navegador interno de Instagram/Facebook.

## Configuración rápida

Todo se cambia desde el objeto `CONFIG` que está al inicio del `<script>` en
`index.html`:

```js
const CONFIG = {
  BRAND_NAME:   "Alma e Imagen",
  AUTHOR_NAME:  "Leidy Sepúlveda",
  PRICE:        "$17",
  CURRENCY:     "USD",
  VIDEO_URL:    "",   // YouTube, Vimeo o .mp4 — vacío = muestra el placeholder
  CHECKOUT_URL: "",   // link de compra (Hotmart, Payhip, Wompi, WhatsApp, etc.)
  INSTAGRAM_URL: "",  // opcional
  WHATSAPP_URL:  "",  // opcional
};
```

- **VIDEO_URL** — pega el link del video de Leidy cuando esté listo. Acepta
  `youtube.com`, `youtu.be`, `vimeo.com` o un archivo `.mp4`. Se carga de forma
  diferida (no afecta la velocidad inicial). Vacío = muestra el póster con el
  botón de play y el texto “Muy pronto”.
- **CHECKOUT_URL** — el enlace de pago/entrega. Todos los botones de compra
  apuntan al mismo lugar automáticamente. Vacío = los botones quedan en `#comprar`.
- El **precio** se actualiza en toda la página desde `PRICE`.

## Recursos

Los `assets/` (logo transparente, portada, páginas interiores y fotos de Leidy)
se generaron a partir del material real de la marca y del PDF de la guía.
El PDF del producto **no** se incluye en el repositorio (`.gitignore`).

## Publicar

Es un sitio estático: sirve la carpeta con cualquier host estático
(Vercel, Netlify, GitHub Pages, Hostinger…) o incrústalo donde ya vive la marca.
