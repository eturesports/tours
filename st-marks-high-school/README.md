# St Mark's High School — Spain Tour

Propuesta de tour para **St Mark's High School**, montada por ETURE Sports.

Deck horizontal de 15 secciones en un único `index.html`, sin dependencias ni build:
se abre tal cual o se sirve como estático. Vive dentro del repo del catálogo general
y **reutiliza sus carpetas de material** (`../Fotos/`, `../Escudos/`, `../Hoteles/`,
`../Clientes/`, `../Tours/`, `../assets/img/`, los dos vídeos), así que hay que servir
la raíz del repo y entrar por `/st-marks-high-school/`.

Estructura y sistema de diseño copiados del deck de
[`eturesports/minervaacademyfc`](https://github.com/eturesports/minervaacademyfc)
(paleta, tipografías, rail lateral, HUD, navegación, carruseles, las 15 secciones).

## Resumen del tour

| | |
|---|---|
| Cliente | St Mark's High School |
| Fechas | Por confirmar · 9 días / 8 noches |
| Grupo | Por confirmar (jugadores + cuerpo técnico) |
| Llegada | **Barcelona** (BCN) |
| Ciudades | **3** — Barcelona · Vinaròs · Valencia |
| Fútbol | 2 amistosos · nivel academia española |
| Entrenamiento | ETURE FC (Vinaròs / Peñíscola) · cámaras VEO · material |
| Cultura | Sagrada Família · Mercat de la Boqueria · Ciutat de les Arts i les Ciències · La Albufera · Castillo de Peñíscola (Papa Luna) · LaLiga · **abiertos a sugerencias** |
| Precio | **2.500 € por jugador**, vuelos no incluidos |
| Contacto | Ivan Gaseni — ivangaseni@eturesports.com — +34 671 75 54 03 |

## Secciones

| # | Sección | # | Sección |
|---|---|---|---|
| 01 | Portada | 09 | Accommodation |
| 02 | Trip Overview | 10 | Cultural Program |
| 03 | Teams We Have Hosted | 11 | Services |
| 04 | Previous Experiences | 12 | Pricing |
| 05 | Creighton University · Spain Tour | 13 | Payment & Cancellation |
| 06 | Football Program | 14 | Contact |
| 07 | Possible Friendly Games | | |
| 08 | ETURE Soccer Fields / Training Facilities | | |

## Pendiente de material

- **Escudo de St Mark's High School.** No hay logo del centro en el repo, así que
  portada y contacto llevan de momento el nombre en tipografía del deck. En cuanto
  llegue el archivo, sustituye ese bloque por un `<img>` como el del deck de Minerva.
- **Escudos de Alboraya UD y Tabernes Blanques.** `../Escudos/` solo tiene Vinaròs CF,
  Torrent CF y CD Castellón. Los dos clubes nuevos salen con un monograma tipográfico
  (`.sm-mono`) del mismo tamaño que los escudos, para que la fila quede uniforme;
  al añadir los PNG basta cambiar el `<span class="sm-mono">` por el `<img>`.
- **Fechas y tamaño del grupo** están como *To Be Confirmed* en Trip Overview: no venían
  definidos en el encargo.
