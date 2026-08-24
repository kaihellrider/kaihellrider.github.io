# Richter Rare Guitars — Catálogo de colección

Página web de una sola pieza (`index.html`, sin dependencias externas salvo Google Fonts) que presenta un catálogo personal de 19 guitarras — Fender, PRS, G&L, Washburn, Gibson, Takamine, Yamaha, Squier, Fernandes y Music Man — con estética de tienda de guitarras vintage (inspirada en Norman's Rare Guitars): fichas técnicas, filtro por categoría, y una reseña de la historia de cada modelo.

Cada ficha incluye año y fábrica de origen **estimados a partir del número de serie** grabado en el instrumento, según los esquemas de numeración publicados por cada fabricante:

- **Serie verificada** (verde): el prefijo/formato del número de serie fecha el año con buena confianza.
- **Serie estimada** (ámbar): el esquema de esa marca no codifica el año de forma exacta (p. ej. G&L "CLF" o Yamaha) — el año es una aproximación por comparación con otros ejemplares documentados.
- **Sin serie** (gris): el instrumento no tiene número de serie registrado en el inventario, así que solo se indica el rango de producción del modelo.

Las guitarras sin foto propia usan un **diagrama de silueta** (estilo dibujo técnico/patente) como marcador de posición. La Yamaha Pacifica 1221 ya lleva una foto real: se le quitó el fondo original (una alfombra) y quedó, como el resto de las tarjetas, sobre el mismo fondo crema con textura diagonal de la tarjeta — así todas las guitarras se ven parte de un mismo catálogo aunque las fotos originales tengan fondos distintos. Ver "Personalizar" para agregar más fotos siguiendo el mismo criterio.

## Cómo publicarla en GitHub Pages

1. Crea un repositorio nuevo en GitHub (por ejemplo `mis-guitarras`). Puede ser público o privado (Pages con repos privados requiere plan de pago; si quieres que sea gratis, hazlo público).
2. Sube el archivo `index.html` de esta carpeta a la raíz del repositorio (arrastrándolo en la interfaz web de GitHub, o con `git add`, `git commit`, `git push` desde tu computador).
3. En el repositorio, ve a **Settings → Pages**.
4. En "Build and deployment", selecciona **Deploy from a branch**.
5. En "Branch", elige `main` (o `master`) y la carpeta `/ (root)`, luego guarda.
6. Espera uno o dos minutos. GitHub te mostrará la URL pública, con el formato:
   `https://TU-USUARIO.github.io/NOMBRE-DEL-REPOSITORIO/`

Cada vez que quieras actualizar el contenido, edita `index.html` y vuelve a subir el archivo (o haz `git push`); GitHub Pages se actualiza solo en un par de minutos.

## Personalizar

- Todo el contenido y los estilos están en `index.html` — no hay archivos CSS o JS separados.
- Los colores principales están definidos como variables CSS al inicio del `<style>` (`--paper`, `--red`, `--ink`, `--tag`, etc.) si quieres cambiar la paleta.
- El nombre "Richter Rare Guitars" está en el `<div class="logo-lockup">` del `<header>` — cámbialo por el nombre que prefieras.
- **Para poner fotos reales** (siguiendo el mismo criterio que la foto de la Yamaha): cada tarjeta tiene un bloque `<div class="plate">...<svg><use href="#shape-..."/></svg></div>`. Para que la foto quede "sobre el mismo fondo" que el resto del catálogo:
  1. Quítale el fondo original a la foto (deja el fondo transparente) — con una app como remove.bg, la herramienta de objeto/fondo de Photos/Preview, o Photoshop.
  2. Recorta el sobrante transparente alrededor de la guitarra para que ocupe el máximo posible del encuadre.
  3. Guarda el resultado como PNG con transparencia dentro de la carpeta `/img` de este repositorio (por ejemplo `img/les-paul-classic.png`).
  4. En la tarjeta correspondiente, reemplaza la línea `<svg viewBox="..."><use href="#shape-..."/></svg>` por: `<img class="photo" src="img/les-paul-classic.png" alt="Nombre del modelo">` — y opcionalmente agrega justo antes `<span class="photo-tag">Foto real</span>` (así se ve la misma etiqueta que lleva la Yamaha).
  Como el fondo de la tarjeta (`.plate`) ya es el mismo para todas, cualquier foto con transparencia queda automáticamente sobre ese mismo fondo crema — sin necesidad de editar nada más.
- Los números de serie y años son los que aportaste; si corriges alguno (o confirmas los que quedaron marcados con `*` o `**` como estimados), solo edita el texto dentro de `.spec-ticket` en la tarjeta correspondiente.

## Notas sobre los datos

- **Washburn PS500** y **G&L ASAT Bluesboy Classic**: sus esquemas de numeración no fechan el año con precisión oficial; los años mostrados son estimaciones por comparación con otros ejemplares documentados.
- **Fernandes ZO-3 "UBB"**: no fue posible confirmar con certeza a qué acabado/edición exacta corresponde el código "UBB" — se indica como dato no confirmado en la reseña.
- **Music Man Axis Super Sport**: el prefijo "G" de Ernie Ball Music Man se usó de forma continua entre 1997 y 2021 sin relación estricta con la fecha real de fabricación, así que el año no pudo acotarse más que ese rango.
