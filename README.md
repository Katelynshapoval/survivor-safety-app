# Tempo

Contest prototype of a discreet support app that looks like a cat weather app. It uses fictional data only and is **not** an operational safety or emergency service. In an emergency in Spain, call 112.

**Status:** project base only. No features are built yet.

## Run it locally

You need [Node.js](https://nodejs.org) installed.

```bash
npm install
```

```bash
npm run dev
```

Then open the link it prints.

## Commands

| Command | What it does |
|---|---|
| `npm run dev` | Runs the app locally and reloads as you edit |
| `npm run build` | Creates the production version in `dist/` |
| `npm run preview` | Runs the production version locally |
| `npm run deploy` | Builds and publishes to Cloudflare (see `docs/DEPLOY.md`) |

## Where things are

| Path | Contents |
|---|---|
| `src/` | The app |
| `public/` | Files copied as they are, including security headers (`_headers`) and `robots.txt` |
| `wrangler.jsonc` | Cloudflare settings |
| `docs/Tempo_Project_Specification.md` | Product spec, the source of truth |
| `docs/Tempo_Overview.md` | Plain-language overview |
| `docs/TECH_STACK.md` | Tools and why they were chosen |
| `docs/ROADMAP.md` | Build order and status |
| `docs/DEPLOY.md` | Publishing the app and making the QR code |
| `AGENTS.md` | Rules for anyone (or any AI) working on the code |
