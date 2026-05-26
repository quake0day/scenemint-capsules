# scnmnt-api-router — reusability notes

**Type:** `adapter`

## What the consumer must change to use this elsewhere

This capsule is an adapter for the Echo HTTP framework. The specific API paths (`/api/session`, `/api/status`, `/api/quota/status`, `/api/quota/check-in`, `/api/prompts/enhance`, `/api/images/generate`, `/api/images/tasks/:id`, `/api/images/tasks/:id/image`) are hardcoded and specific to the SceneMint application. The `security.BodyLimit()` middleware is also applied here.

## Required peer capsules

- `scnmnt-image-generation-service`
- `scnmnt-quota-service`
- `scnmnt-security-middleware`

## Invariants you must not break

- All sensitive API routes must be protected by CSRF and source guard middleware.
- API paths must be consistent and follow the defined `/api/*` prefix.
