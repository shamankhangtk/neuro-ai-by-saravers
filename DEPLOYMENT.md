# NEURO AI — Deployment & Verification Guide

The original Expo/React Native UI is retained. The Express server serves the exported web app and `/api/neuro/*` endpoints from one origin.

## 1. Requirements and local setup

- Node.js 22
- pnpm 9

```bash
pnpm install
cp .env.example .env
```

Set at least `GEMINI_API_KEY`, `NEURO_ADMIN_USERNAME`, and a unique `NEURO_ADMIN_PASSWORD` (16+ characters). Add `HUGGINGFACE_API_TOKEN` to enable image generation. Then run:

```bash
pnpm dev
```

Production build and run:

```bash
pnpm build
pnpm start
```

The production server listens on `PORT` (defaults to 3000). Health endpoint: `/api/health`.

## 2. AI provider setup

- **Chat, Study Tools, CreateLab and Coding Help:** Gemini via `GEMINI_API_KEY`, default model `gemini-2.5-flash`.
- **Web search:** Gemini Google Search grounding is used when the existing live-search toggle is enabled. This depends on model/API availability and quota.
- **Image generation:** Hugging Face Inference Providers via `HUGGINGFACE_API_TOKEN`, default model `black-forest-labs/FLUX.1-schnell`. Free access is limited and can change; it is not unlimited or guaranteed to be available at all times.
- **Optional paid override:** `OPENAI_API_KEY` takes priority for chat/search/image. OpenAI API billing is separate from ChatGPT subscriptions.

Create keys only on the providers' official dashboards:
- Google AI Studio: https://aistudio.google.com/apikey
- Hugging Face: https://huggingface.co/settings/tokens

Never put API keys in `EXPO_PUBLIC_*`, frontend code, source control, or chat messages. Store them only in the hosting provider's server-side environment variables. `.env` is ignored by Git; `.env.example` contains placeholders only.

## 3. Deploy to Render (free plan, where available)

1. Push this project to a GitHub repository.
2. In Render, choose **New → Blueprint** and connect the repository. Render reads `render.yaml`.
3. Enter the secret values requested by the blueprint:
   - `GEMINI_API_KEY`
   - `HUGGINGFACE_API_TOKEN` (optional if you want image generation)
   - `NEURO_ADMIN_USERNAME`
   - `NEURO_ADMIN_PASSWORD` (unique, random, at least 16 characters)
4. Deploy and wait for the build to finish.
5. Open `https://YOUR-SERVICE.onrender.com/api/health`; expect JSON with `ok: true`.
6. Open the root service URL to use the website.

Render free services may sleep after inactivity, have resource limits, and change availability/terms. First request after sleep can be slow. AI provider free quotas are separate from hosting quotas.

## 4. Post-deploy test checklist

- `/api/health` returns `{ "ok": true }`.
- `/api/neuro/status` lists which providers are configured. It does not validate keys, remaining quota, or successful inference.
- Send a normal question in Neuro Chat.
- Enable live web search and ask for a current fact; confirm sources are returned.
- Generate an image in AI Image Studio.
- Test Study Tools, CreateLab and Coding Help.
- Test admin login/logout with the credentials set in Render.
- Check browser console and Render logs for errors.

## 5. Honest readiness notes

A configured key is not proof that the provider accepts it or has quota. Validate each feature using real credentials after deployment. This repository cannot create API keys, add them to your hosting account, connect a GitHub repository, or publish a service without the account owner's explicit access and action. No deployment can promise zero errors on every device/provider; report and fix any reproducible issue found during the checklist.
