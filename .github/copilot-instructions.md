# Copilot instructions for Mona Mayhem

## Project overview

This repository is a workshop starter for a retro arcade-themed GitHub contribution battle app built with Astro. The app is intentionally scaffolded, not fully implemented: the main product work happens in the Astro app under `src/`, while the workshop materials live in `workshop/` and the static docs site in `docs/`.

The core feature is a comparison page that lets two GitHub usernames battle by fetching contribution data and rendering contribution graphs side by side. The current starter includes a minimal landing page in `src/pages/index.astro` and a placeholder API route in `src/pages/api/contributions/[username].ts`.

## Commands

Install dependencies:

```bash
npm install
```

Run the app in development mode:

```bash
npm run dev
```

Build the site for production:

```bash
npm run build
```

Preview the built site:

```bash
npm run preview
```

There is no dedicated test script or lint script configured in `package.json` yet. Treat `npm run build` as the primary validation command after code changes. For focused verification of the API route during development, use the app locally and hit endpoints such as:

```bash
curl http://localhost:4321/api/contributions/octocat
```

## Architecture and file responsibilities

- `src/pages/index.astro` is the main battle page and contains the UI scaffold for the game.
- `src/pages/api/contributions/[username].ts` is the server-side API proxy that should fetch GitHub contribution data for a given username and avoid browser CORS restrictions.
- `astro.config.mjs` configures Astro with the Node adapter and server output (`output: 'server'`).
- `workshop/` contains the guided Copilot workshop steps and task prompts; this content is instructional, not the app itself.
- `docs/` and `workshop/` are used for the GitHub Pages deployment workflow in `.github/workflows/deploy.yml`.

Keep the app implementation centered on Astro page + route patterns. Do not re-architect the repo around a different framework or build tool unless the task explicitly requires it.

## Conventions specific to this repo

- This project uses Astro pages and file-based routing under `src/pages`.
- Prefer server-side data fetching for GitHub contribution requests instead of client-side fetches to the GitHub domain, because the route is meant to proxy cross-origin data.
- The repo is a workshop and starter scaffold; implement the missing features incrementally and keep changes aligned with the workshop flow.
- The default dev server runs on port `4321`, matching the workshop examples and the local API check commands.
- The project is TypeScript-first and inherits Astro's strict TypeScript config from `tsconfig.json`.
- The existing API stub uses `export const prerender = false` for a runtime route; keep this pattern for routes that need live data or runtime request handling.
- The GitHub Pages deployment workflow copies static site content from `docs/` and `workshop/` rather than building the Astro app. If you change deployment assumptions, update the workflow and docs together.

## Working expectations

- Prefer surgical edits in the relevant Astro page or API route instead of broad rewrites.
- When building the battle app, keep the UI simple and match the workshop's progression: basic page scaffold first, then API integration, then interactive battle logic.
- Treat the `workshop/` docs as the design reference for how the app is meant to evolve; they explain the intended architecture and workflow.
- Keep any new code consistent with Astro conventions and the current repository's lightweight setup.
