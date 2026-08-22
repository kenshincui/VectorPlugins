# Third-Party Notices

This repository redistributes selected Agent Skills under their original
licenses. The adapted packages retain their upstream copyright, license, and
repository metadata.

## Impeccable

- Upstream: https://github.com/pbakaus/impeccable
- Imported revision: `56f44523f76efdcec813e67b38ee550e49b16f48`
- Upstream version: `4.1.1`
- License: Apache License 2.0
- Local package: `plugins/impeccable/skills/impeccable`

The package contains the upstream Codex-compatible Skill distribution. Vector
adds only its plugin manifest, marketplace metadata, provenance record, and UI
metadata.

## PPT Master

- Upstream: https://github.com/hugohe3/ppt-master
- Imported revision: `613e0d12a1ee4df1fa487f743fd23445cb7169b6`
- Upstream version: `4.8.0`
- License: MIT
- Local package: `plugins/ppt-master/skills/ppt-master`

Vector redistributes the upstream skill runtime with all workflows, references,
scripts, structural templates, and attribution files. To remain under Vector's
4,000-file plugin limit, the adapted package omits the optional bundled sound
effect library and reduces the optional icon catalog to the complete
`chunk-filled`, `tabler-filled`, and `phosphor-duotone` collections plus a
commonly used subset of `simple-icons` brand marks. Projects may provide
additional SVG icons and audio files locally as documented by PPT Master.
