# Decomposition

**Source:** `https://github.com/sunls24/scenemint`

**Plan summary.** This repository, SceneMint, is decomposed into a Go HTTP backend and an Astro/React frontend for AI image generation. The decomposition aims to separate core application logic, domain-specific services (image generation, quota), security concerns, and the frontend application into reusable capsules. Generic UI components are also extracted as a separate library.

## Capsules produced (7)

- [`scnmnt-app-core`](scnmnt-app-core/) — see [REUSE.md](scnmnt-app-core/REUSE.md)
- [`scnmnt-image-generation-service`](scnmnt-image-generation-service/) — see [REUSE.md](scnmnt-image-generation-service/REUSE.md)
- [`scnmnt-quota-service`](scnmnt-quota-service/) — see [REUSE.md](scnmnt-quota-service/REUSE.md)
- [`scnmnt-security-middleware`](scnmnt-security-middleware/) — see [REUSE.md](scnmnt-security-middleware/REUSE.md)
- [`scnmnt-api-router`](scnmnt-api-router/) — see [REUSE.md](scnmnt-api-router/REUSE.md)
- [`scnmnt-web-ui-components`](scnmnt-web-ui-components/) — see [REUSE.md](scnmnt-web-ui-components/REUSE.md)
- [`scnmnt-web-app-core`](scnmnt-web-app-core/) — see [REUSE.md](scnmnt-web-app-core/REUSE.md)

## Leftover files: 0

All files in the source repository have been assigned to one of the defined reusable capsules. General project configuration, build scripts, and documentation files are included in the `scnmnt-app-core` capsule as they pertain to the overall application's setup and lifecycle.

## Next steps

```bash
# Validate every produced capsule
capsule validate .

# Reconstruct the whole composition into a runnable site
capsule reconstruct --from . --out ./out
```
