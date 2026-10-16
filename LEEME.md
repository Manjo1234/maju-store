# MAJU STORE — tienda lista para publicar

Abrí `index.html` para ver la tienda. Es una página estática (HTML + fotos): no necesita servidor ni base de datos.

## Cómo publicarla y obtener un enlace para tus clientes

Subí **toda la carpeta** (no solo `index.html`: tiene que ir con `imagenes_tienda/`).

**Opción más simple — Netlify Drop (gratis, sin instalar nada)**
1. Entrá a https://app.netlify.com/drop (creá una cuenta gratuita si te la pide).
2. Arrastrá la carpeta `maju-store` completa a la zona indicada.
3. En unos segundos te da un enlace público del estilo `https://nombre-aleatorio.netlify.app`. Podés cambiar el nombre en *Site configuration → Change site name* y, más adelante, conectar un dominio propio (por ejemplo `majustore.com.ar`).

**Alternativas gratuitas:** Cloudflare Pages (subida directa de carpeta) o GitHub Pages (subir los archivos a un repositorio y activar Pages).

Para actualizar la tienda: modificá los archivos y volvé a subir la carpeta (en Netlify, *Deploys → Drag and drop*).

## Configurar el WhatsApp (pendiente)

Abrí `index.html` con un editor de texto y buscá, al comienzo del bloque `<script>`:

    const WHATSAPP_NUMBER = '';

Escribí el número con código de país, sin `+` ni espacios. Ejemplo (celular de Buenos Aires): `'5491122334455'`.
Mientras esté vacío, el botón "Pedir por WhatsApp" copia el pedido al portapapeles y avisa que falta el número. No inventé ningún número.

## Qué hay en la carpeta

- `index.html` — la tienda (diseño, productos, precios, carrito, ventana de detalle).
- `imagenes_tienda/card/` — miniaturas 600×800 (se usan en la grilla).
- `imagenes_tienda/full/` — fotos 900×1200 (se usan en la ventana de detalle).
- Las fotos de BURO hombre y mujer se recortaron en alta resolución desde los catálogos PDF de Gitti.

## Cómo agregar una foto o cambiar un precio

- **Precio / talles / nombre:** están en la lista `products` dentro de `index.html` (una línea por producto).
- **Foto nueva:** guardala en 3:4 (ideal 900×1200) como `imagenes_tienda/full/NOMBRE.jpg` y una versión de 600×800 en `imagenes_tienda/card/NOMBRE.jpg`; después poné `"imagen":"NOMBRE"` en el producto.
- **Variante de color con foto real:** agregá una entrada en `colorVariants` con el id del producto, el nombre del color y la foto. Los colores del selector salen solo de ahí (no se inventan).
