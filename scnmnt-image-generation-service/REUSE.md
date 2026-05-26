# scnmnt-image-generation-service — reusability notes

**Type:** `subsystem`

## What the consumer must change to use this elsewhere

This capsule is heavily dependent on the `CHATGPT2API_BASE_URL`, `CHATGPT2API_API_KEY`, `CHATGPT2API_IMAGE_MODEL`, and `CHATGPT2API_PROMPT_MODEL` environment variables. The `gox/openai` library is used for OpenAI API interactions. Constants like `maxMultipartMemory`, `maxReferenceUploadBytes`, `maxReferenceUploadSizeMB` define specific limits that might need adjustment for different contexts. The `taskAPIRoot` and `openAIBaseURL` are derived from `CHATGPT2API_BASE_URL`.

## Required environment variables

- `CHATGPT2API_BASE_URL`
- `CHATGPT2API_API_KEY`
- `CHATGPT2API_IMAGE_MODEL`
- `CHATGPT2API_PROMPT_MODEL`

## Required peer capsules

- `scnmnt-quota-service`

## Invariants you must not break

- All requests to the upstream AI API must be authenticated with the provided API key.
- Image generation tasks must correctly deduct quota credits, and refund on failure.
- Prompt enhancement must return a valid stream of text.
