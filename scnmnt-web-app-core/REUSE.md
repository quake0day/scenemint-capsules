# scnmnt-web-app-core — reusability notes

**Type:** `template`

## What the consumer must change to use this elsewhere

This capsule is marked as `template` due to its heavy project-specific branding and content. `BrandHeader.tsx` contains the 'SceneMint' brand name, 'Codex App' attribution, and a hardcoded `githubUrl`. `copy.ts` contains all hardcoded UI text, storage keys (`scenemint:language`, `scenemint:size`, `scenemint:enhanceDirection`), and constants like `maxReferenceSizeMB`. Public assets (`brand-logo.png`, `favicon.ico`, etc.) are also specific. The `astro.config.mjs` includes a proxy for `/api` which is specific to the backend integration. The `fingerprint.ts` utility is tied to the quota system's use of browser fingerprints.

## Required peer capsules

- `scnmnt-web-ui-components`

## Invariants you must not break

- The application must correctly display image generation status and history.
- Quota information must be accurately reflected from the backend.
- All user interactions must be responsive and provide appropriate feedback.
