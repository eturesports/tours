# ETURE Spain Tours — Catálogo general

Catálogo general de tours de ETURE Sports. Deck horizontal de 25 secciones en un
único `index.html` sin dependencias ni build: se abre tal cual, o se sirve como
estático desde cualquier hosting.

Está construido sobre el sistema de diseño del deck de [`eturesports/PDA`](https://github.com/eturesports/PDA)
(paleta, tipografías, rail lateral, HUD, navegación, carruseles), pero con el
contenido generalizado: donde el de PDA es una propuesta cerrada para un cliente
—fechas, plantilla, precio—, este describe la oferta completa y el histórico de
experiencias realizadas.

## Estructura del deck

| # | Sección | # | Sección |
|---|---|---|---|
| 01 | Portada | 14 | Football Program |
| 02 | ETURE Spain Tours — qué hacemos | 15 | Possible Friendly Games |
| 03 | Destinations | 16 | ETURE Soccer Fields |
| 04 | Teams We Have Hosted | 17 | Training Facilities |
| 05 | Previous Experiences | 18 | Accommodation |
| 06–13 | Una sección por tour realizado | 19 | Cultural Program |
| | (St. Louis City SC, ODP USYS, Creighton, | 20 | Services |
| | Clemson, Mustang, Clarkson, Bayside, | 21 | Tour Formats |
| | San Francisco Glens) | 22 | **Sample Itinerary** |
| | | 23 | How Pricing Works |
| | | 24 | Payment & Cancellation |
| | | 25 | How It Works |
| | | 26 | Contact |

## Cómo se edita

Todo el contenido variable vive en cuatro arrays al principio del `<script>`:

- **`TOURS`** — los tours realizados. Cada entrada genera **a la vez** su tarjeta
  en *Teams We Have Hosted*, su sección de galería propia y su recuento en
  *Destinations*. Añadir un tour = añadir un objeto al array y su carpeta en
  `Tours/<slug>/`.
- **`DESTINATIONS`** — las ciudades. El número de tours de cada una se cuenta solo
  a partir de `TOURS`, no se escribe a mano.
- **`HOTELS`** — los hoteles de muestra.
- **`ITINERARY`** — el itinerario modelo de 9 días. Los días marcados
  `tag:'Match Day'` se resaltan en rojo solos, y los contadores de la cabecera
  (entrenamientos, partidos) se cuentan desde las propias filas.

El índice de secciones (`TOTAL`, `NAMES`, qué secciones son claras) se deriva del
DOM leyendo el atributo `data-name` de cada `<section class="slide">`, así que
reordenar o añadir secciones no obliga a tocar el motor de navegación.

## Rendimiento

Hay nueve galerías en la página. Cada carrusel monta sus imágenes solo cuando su
sección entra en la ventana de navegación (`updateFar` → `ensureCarousel`), y las
secciones lejanas se saltan con `content-visibility`. Sin eso, las ~150 fotos se
cargarían de golpe al abrir.

## Origen del material

- **Fotos de los tours** (`Tours/`): galerías de `eturesports.com/eture-tours/<tour>`.
- **Logos y fotos de portada de clientes** (`Clientes/`), **hoteles** (`Hoteles/`),
  **escudos** (`Escudos/`), **campos** (`assets/img/`), **vídeos**: repo `eturesports/PDA`.
- **Datos de cada tour** (ciudades, fechas): página `eturesports.com/tours`.
- **Itinerario modelo**: `itinerario_tour.xlsx`, traducido al inglés del deck.
