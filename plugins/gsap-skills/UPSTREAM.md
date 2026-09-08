# Upstream provenance and Vector packaging

- Repository: https://github.com/greensock/gsap-skills
- Reference revision: `aed9cfd3277740755f6bfc1155c7aa645403b760`
- Imported path: `skills/` (eight skill directories and `llms.txt`)
- License: MIT; original copyright and permission notice retained in `LICENSE`.
- Package version: `1.0.1` (Vector packaging version, not an upstream release).

The complete upstream skill directory is copied with trailing whitespace normalized. These
are portable Agent Skills, not a separate product-specific edition. Vector adds
only the plugin manifest, catalog entry, README and provenance metadata. No MCP
server, authentication, install hook or executable script is bundled. The GSAP
runtime and framework packages are installed in a target project only as needed;
they are not vendored here and retain their own applicable license terms.
