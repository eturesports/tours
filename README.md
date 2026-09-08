# ETURE Spain Tours — Catálogo general

Catálogo general de tours de ETURE Sports. Deck horizontal de 25 secciones en un
único `index.html` sin dependencias ni build: se abre tal cual, o se sirve como
estático desde cualquier hosting.

Está construido sobre el sistema de diseño del deck de [`eturesports/PDA`](https://github.com/eturesports/PDA)
(paleta, tipografías, rail lateral, HUD, navegación, carruseles), pero con el
contenido generalizado: donde el de PDA es una propuesta cerrada para un cliente
—fechas, plantilla, precio—, este describe la oferta completa y el histórico de
experiencias realizadas.

## Propuestas por cliente

Además del catálogo general, el repo aloja propuestas cerradas para un cliente
concreto en su propia carpeta, reutilizando el material de la raíz:

- [`st-marks-high-school/`](st-marks-high-school/) — St Mark's High School ·
  Barcelona, Vinaròs y Valencia · 2.500 &euro; por jugador.

En esta rama, el `vercel.json` de la raíz sirve esa propuesta en `/` para poder
desplegarla como proyecto propio; el catálogo general sigue en `/index.html`.

## Estructura del deck

| # | Sección | # | Sección |
|---|---|---|---|
| 01 | Portada | 14 | Sample Itinerary |
| 02 | ETURE Spain Tours — qué hacemos | 15 | Football Program |
| 03 | Destinations | 16 | Friendly Opponents |
| 04 | Teams We Have Hosted | 17 | ETURE Soccer Fields |
| 05 | Previous Experiences (collage) | 18 | Training Facilities |
| 06–13 | Una sección por tour realizado | 19 | Accommodation |
| | (St. Louis City SC, ODP USYS, Creighton, | 20 | Cultural Program |
| | Clemson, Mustang, Clarkson, Bayside, | 21 | Services |
| | San Francisco Glens) | 22 | Tour Formats |
| | | 23 | How Pricing Works |
| | | 24 | Payment & Cancellation |
| | | 25 | How It Works |
| | | 26 | Contact |

## Cómo se edita

Todo el contenido variable vive en cinco arrays al principio del `<script>`:

- **`TOURS`** — los tours realizados. Cada entrada genera **a la vez** su tarjeta
  en *Teams We Have Hosted*, sus dos fotos del collage de *Previous Experiences*,
  su sección de galería propia y su recuento en *Destinations*. Añadir un tour =
  añadir un objeto al array y su carpeta en `Tours/<slug>/`.
- **`DESTINATIONS`** — las ciudades. El número de tours de cada una se cuenta solo
  a partir de `TOURS`, no se escribe a mano.
- **`HOTELS`** — los hoteles de muestra.
- **`OPPONENTS`** — los clubes contra los que se han organizado amistosos. Solo
  nombres: si algún día se tiene el set completo de escudos, se añade el campo y
  se pintan todos a la vez, en lugar de mezclar unos con escudo y otros sin él.
- **`ITINERARY`** — el itinerario modelo de 9 días. Los días marcados
  `tag:'Match Day'` se resaltan en rojo solos, y los contadores de la cabecera
  (entrenamientos, partidos) se cuentan desde las propias filas.

El índice de secciones (`TOTAL`, `NAMES`, qué secciones son claras) se deriva del
DOM leyendo el atributo `data-name` de cada `<section class="slide">`, así que
reordenar o añadir secciones no obliga a tocar el motor de navegación.

## Rendimiento

Hay ocho galerías en la página. Cada carrusel monta sus imágenes solo cuando su
sección entra en la ventana de navegación (`updateFar` → `ensureCarousel`), y las
secciones lejanas se saltan con `content-visibility`. Sin eso, las ~150 fotos se
cargarían de golpe al abrir.

## Origen del material

- **Fotos de los tours** (`Tours/`): galerías de `eturesports.com/eture-tours/<tour>`.
- **Logos y fotos de portada de clientes** (`Clientes/`), **hoteles** (`Hoteles/`),
  **escudos** (`Escudos/`), **campos** (`assets/img/`), **vídeos**: repo `eturesports/PDA`.
- **Datos de cada tour** (ciudades, fechas): página `eturesports.com/tours`.
- **Itinerario modelo**: `itinerario_tour.xlsx`, traducido al inglés del deck.
