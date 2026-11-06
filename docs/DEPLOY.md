# Tempo: publishing and the QR code

The app is published with Cloudflare Workers static assets. `wrangler.jsonc` holds the settings and `public/_headers` holds the security headers.

## Pick a neutral link first

The public link is `<worker-name>.<account-subdomain>.workers.dev`, and it stays in browser history.

- **Worker name:** currently `tempo-weather`, set in `wrangler.jsonc`.
- **Account subdomain:** Cloudflare asks you to choose it the first time. Pick something neutral, not your name and nothing about safety or survivors.

## First publish

You need a free [Cloudflare account](https://dash.cloudflare.com/sign-up). The login step opens a browser window for you to approve.

```bash
npx wrangler login
```

```bash
npm run deploy
```

The command prints the public link when it finishes.

## After that

Run `npm run deploy` whenever you want to publish the latest version. Publishing is manual, so unfinished work never goes live by accident.

Cloudflare can also publish automatically on every push to GitHub, including from a private repo. You can turn that on from the Worker's settings in the dashboard.

## Check it worked

1. Open the link on your phone, on mobile data as well as Wi-Fi.
2. In a terminal, confirm the security headers are present:

```bash
curl -I https://YOUR-LINK.workers.dev
```

You should see `content-security-policy` and `x-robots-tag` in the output.

## Make the QR code

Generate the code **only from the final link**, using an offline tool or one that doesn't track scans. Avoid "dynamic QR" services, because they route scans through their own servers and log them. The spec rules out tracking (§6, §12.4).

Test the printed code with several phones before judging.

## Is the repo public?

The repo name and its docs explain exactly what the cover hides, including the hidden entry. That's harmless for a contest. Before any real release, make the repo private, or rename it and move the docs (§12.9).
