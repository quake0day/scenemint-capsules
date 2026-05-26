# scnmnt-app-core — reusability notes

**Type:** `subsystem`

## What the consumer must change to use this elsewhere

The Dockerfile is a multi-stage build that includes both Go backend and Bun/Astro frontend. For reuse, it would need to be split or adapted to only build the Go backend. The `quota.DefaultPath` (`data/quota.db`) is hardcoded. The `gox/server` dependency is specific and might need replacement if moving to a different HTTP framework. Environment variable names like `CHATGPT2API_BASE_URL` are specific to the upstream API.

## Required environment variables

- `HOST`
- `PORT`
- `CHATGPT2API_BASE_URL`
- `CHATGPT2API_API_KEY`
- `CHATGPT2API_IMAGE_MODEL`
- `CHATGPT2API_PROMPT_MODEL`
- `SECURITY_SECURE_COOKIES`

## Required peer capsules

- `scnmnt-image-generation-service`
- `scnmnt-quota-service`
- `scnmnt-security-middleware`
- `scnmnt-api-router`

## Invariants you must not break

- All required environment variables must be present and valid at startup.
- The HTTP server must start successfully and serve static files from 'web/dist'.
