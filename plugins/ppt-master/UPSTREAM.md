# Upstream provenance and Vector adaptation

- Repository: https://github.com/hugohe3/ppt-master
- Revision: `613e0d12a1ee4df1fa487f743fd23445cb7169b6`
- Version: `4.8.0`
- License: MIT
- Imported path: `skills/ppt-master`

The Vector package retains the complete workflow, references, scripts,
structural templates, attribution guard, license, and sponsor files.

To meet Vector's 4,000-file plugin limit, this package adapts only optional
asset catalogs:

- Keeps the complete `chunk-filled`, `tabler-filled`, and
  `phosphor-duotone` generic icon sets.
- Keeps a curated subset of common `simple-icons` brand marks.
- Omits the large optional `tabler-outline` icon library.
- Omits the optional bundled sound-effect files.

Users can add project-local SVG icons or audio assets when a deck needs a
missing resource. The core PPTX generation, editing, template, chart, table,
animation, narration, conversion, and QA scripts remain included.
