# SVG Icon Library — Vector Distribution

This Vector distribution provides a compact subset of PPT Master's icon assets
that stays below Vector's 4,000-file plugin limit while preserving three visual
weights. Additional SVG icons may be placed under the active project's
`icons/<library>/` directory.

Upstream versions, licenses, attribution, and trademark boundaries are recorded
in [THIRD_PARTY_NOTICES.md](./THIRD_PARTY_NOTICES.md).

## Bundled libraries

| Library | Style | Count | Prefix |
| --- | --- | ---: | --- |
| `chunk-filled` | Heavy, compact filled silhouettes | 641 | `chunk-filled/` |
| `tabler-filled` | Smooth, rounded filled forms | 1,055 | `tabler-filled/` |
| `phosphor-duotone` | Layered duotone forms | 1,518 | `phosphor-duotone/` |
| `simple-icons` | Curated common brand marks | Curated subset | `simple-icons/` |

The large optional `tabler-outline` library is not included in the Vector
package. Do not reference it unless the user provides matching project-local
assets.

## Per-project icons

Copy selected bundled icons into the deck project before authoring SVG:

```bash
python3 "${SKILL_DIR}/scripts/icon_sync.py" <project_path> \
  tabler-filled/home tabler-filled/chart simple-icons/github
```

Choose at most one bundled stylistic library per selection batch;
`simple-icons` may accompany it for real company or product marks. If a needed
icon is missing, choose the nearest semantic alternative in the selected
library or add a coherent custom SVG under `<project>/icons/<library>/`.

Imported template vectors use `<workspace>/icons/imported/<name>.svg` and
`data-icon="imported/<name>"`.

## Usage

```xml
<use data-icon="chunk-filled/home" x="100" y="200" width="48" height="48" fill="#0076A8"/>
<use data-icon="tabler-filled/home" x="100" y="200" width="48" height="48" fill="#0076A8"/>
<use data-icon="phosphor-duotone/house" x="100" y="200" width="48" height="48" fill="#0076A8"/>
<use data-icon="simple-icons/github" x="100" y="200" width="48" height="48" fill="#181717"/>
```

`data-icon` values are case-sensitive. `finalize_svg.py embed-icons` resolves
project-local icons first and uses the bundled library only as a fallback.

For uncertain names, search only the chosen library:

```bash
rg --files "${SKILL_DIR}/templates/icons/tabler-filled" -g '*chart*.svg'
rg --files "${SKILL_DIR}/templates/icons/simple-icons" -g '*github*.svg'
```

Do not enumerate or load a full icon index into model context.

## Selection guidance

- `chunk-filled`: maximum small-size legibility and visual weight.
- `tabler-filled`: approachable, rounded product and business visuals.
- `phosphor-duotone`: contemporary layered depth.
- `simple-icons`: real brand recognition only, never generic concepts.

Project-local custom and imported assets are already prepared resources and are
not subject to the bundled-library mixing restriction.
