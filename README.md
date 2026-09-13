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
  VIDEO_URL:    "./assets/video-leidy.mp4",  // video real de Leidy, autohospedado
  CHECKOUT_URL: "https://almaeimagen.com/finalizar-compra/?add-to-cart=169",
  INSTAGRAM_URL: "",  // opcional
  WHATSAPP_URL:  "",  // opcional
};
```

- **VIDEO_URL** — acepta `youtube.com`, `youtu.be`, `vimeo.com` o un archivo
  `.mp4` propio. Se carga de forma diferida (no afecta la velocidad inicial):
  solo se descarga cuando la visitante le da play. Vacío = muestra el póster
  con el botón de play y el texto "Muy pronto".
- **CHECKOUT_URL** — el enlace de pago/entrega (hoy: carrito de WooCommerce en
  almaeimagen.com, producto #169, $17, entrega automática del PDF vía Stripe).
  Todos los botones de compra apuntan al mismo lugar. Vacío = los botones
  quedan en `#comprar`.
- El **precio** se actualiza en toda la página desde `PRICE`.

## Recursos

Los `assets/` (logo transparente, portada, páginas interiores, fotos de Leidy
y el video) se generaron a partir del material real de la marca y del PDF de
la guía. El PDF del producto **no** se incluye en el repositorio (`.gitignore`).

**Video** (`assets/video-leidy.mp4` + `assets/video-poster.webp`): el archivo
crudo de la grabación vive en `_src/video/` (gitignored, pesa >200MB) y se
comprimió con ffmpeg a 720p H.264/AAC (`-crf 25 -preset medium +faststart`,
~20MB) para que cargue rápido en móvil/Instagram. El póster es un fotograma
real extraído del propio video (sin subtítulo incrustado encima), no una
foto genérica.

## Publicar

Es un sitio estático: sirve la carpeta con cualquier host estático
(Vercel, Netlify, GitHub Pages, Hostinger…) o incrústalo donde ya vive la marca.
