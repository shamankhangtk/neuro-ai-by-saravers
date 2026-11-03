# NEURO AI by Saravers

NEURO AI is an Expo Router / React Native app with a web export and Express API. The current UI is intentionally preserved; the backend supports Gemini free-tier chat/search, optional Hugging Face image generation, and optional OpenAI overrides.

## Quick start

1. Install Node.js 22 and pnpm 9.
2. Run `pnpm install`.
3. Copy `.env.example` to `.env`, set `GEMINI_API_KEY`, and choose a strong `NEURO_ADMIN_USERNAME` and `NEURO_ADMIN_PASSWORD`. Add `HUGGINGFACE_API_TOKEN` if you want to enable image generation.
4. Run `pnpm dev` for local development.
5. Run `pnpm build && pnpm start` for production.

See [DEPLOYMENT.md](./DEPLOYMENT.md) for hosting and environment configuration.

## AI provider setup

For a free-tier-first setup, configure `GEMINI_API_KEY` for AI chat and optional Google Search grounding. Image generation can use `HUGGINGFACE_API_TOKEN`, subject to the provider's small free monthly credit allowance. See [DEPLOYMENT.md](./DEPLOYMENT.md) for setup and limits. Do not commit secrets.


## Provider diagnostics

`GET /api/neuro/status` reports whether chat, web search and image generation providers are configured. It never returns API keys. A configured provider does not guarantee a valid key, remaining quota, or successful live request.
