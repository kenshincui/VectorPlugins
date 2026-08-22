# Sound Effects — Vector Distribution

The upstream PPT Master distribution includes an optional global sound-effect
library. The Vector marketplace package omits those binary assets to remain
compact and installable.

Sound remains opt-in, and silence is valid. When the user requests audio:

1. Use supplied or independently sourced audio with known provenance and a
   compatible license.
2. Store it under the active project's `sounds/custom/` directory.
3. Reference only project-relative paths from animation or transition config.
4. Verify the deck in the target PowerPoint environment.

Example layout:

```text
projects/deck/sounds/custom/transition.wav
projects/deck/sounds/custom/notification.wav
```

Do not invoke the upstream global-library sync workflow: this Vector package
does not ship those source WAV files. The retained vocabulary and notice files
are provenance and planning references, not proof that a referenced audio asset
exists locally.

Prefer PowerPoint-compatible PCM signed 16-bit little-endian WAV files at
44.1 kHz.
