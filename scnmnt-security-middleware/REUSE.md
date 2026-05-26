# scnmnt-security-middleware — reusability notes

**Type:** `adapter`

## What the consumer must change to use this elsewhere

The `csrfCookieName` (`_scenemint_csrf`), `csrfTokenBytes`, and `maxBodyBytes` constants are hardcoded. Error messages returned by the middleware are hardcoded in Chinese and would need localization or generalization. The capsule is tightly coupled with the Echo HTTP framework.

## Required environment variables

- `SECURITY_SECURE_COOKIES`

## Invariants you must not break

- CSRF tokens must be unique, securely generated, and correctly validated.
- Cross-site requests (except safe methods) must be rejected.
- Secure headers must be consistently applied to all responses.
