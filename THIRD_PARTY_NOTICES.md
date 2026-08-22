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

## Internal Comms

- Upstream: https://github.com/anthropics/skills
- Imported revision: `3b3fad96af16a10759d930941b4520ba0c40edae`
- Imported path: `skills/internal-comms`
- License: Apache License 2.0
- Local package: `plugins/internal-comms/skills/internal-comms`

Vector adapts triggering and UI metadata while retaining the upstream workflow
and examples.

## Diagram Maker

- Upstream: https://github.com/openclaw/openclaw
- Imported revision: `ea1cd39d6c9ac880eaa531e57c98219d8c559e57`
- Imported path: `skills/diagram-maker`
- License: MIT
- Local package: `plugins/diagram-maker/skills/diagram-maker`

Vector normalizes host-specific frontmatter and adds plugin metadata.

## Deep Research

- Upstream: https://github.com/daymade/claude-code-skills
- Imported revision: `52afafe78646b82ef228819d3e5acc8684943502`
- Imported path: `deep-research`
- Upstream release line: V6.1
- License: MIT
- Local package: `plugins/deep-research/skills/deep-research`

Vector replaces product-specific tool and team commands with capability-based
browser, retrieval, file, and optional parallel-worker instructions.

## Anthropic document Skills not redistributed

Anthropic's `skills/docx`, `skills/xlsx`, and `skills/pdf` were inspected at
revision `3b3fad96af16a10759d930941b4520ba0c40edae`. Their `LICENSE.txt` files
state that users may not retain copies outside Anthropic Services, reproduce or
copy the materials, create derivative works, or distribute them to third
parties. They are therefore deliberately excluded from this public repository.

## Frontend Design

- Upstream: https://github.com/anthropics/skills
- Imported revision: `3b3fad96af16a10759d930941b4520ba0c40edae`
- Imported path: `skills/frontend-design`
- License: Apache License 2.0
- Local package: `plugins/frontend-design/skills/frontend-design`

Vector adapts the upstream Skill for its Codex-compatible runtime and plugin
catalog. The adaptation preserves the upstream visual-design principles while
replacing Claude-specific host assumptions with Vector tool, implementation,
verification, and bounded screenshot-QA instructions.
