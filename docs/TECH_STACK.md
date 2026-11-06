# Tempo: tech stack

*Decided 6 November 2026. Free-tier details were checked against Cloudflare and Open-Meteo documentation that day. Check them again before judging.*

## The short version

Tempo is a **frontend-only web app**. Judges scan a QR code, a link opens, and the app runs in their browser. Their data stays in that browser. There are no accounts, no server code and no database.

```
Judge scans QR
   → Cloudflare serves the app's files
   → the app runs in the judge's browser
   → records stay in that browser's storage
   → the only outside request is the Open-Meteo forecast
```

## Choices

| Need | Choice | Why |
|---|---|---|
| Interface | **React + Vite** | Normal React, HTML and CSS, with a very simple setup |
| Language | **JavaScript** | The owner doesn't know TypeScript, and it isn't needed at this size |
| Hosting | **Cloudflare Workers static assets** | Free, stays on, neutral link, custom security headers, and room for a live chat in the same deploy |
| Saved data | **Browser storage**: `localStorage` first, IndexedDB if screenshots outgrow it | Matches the spec's local-first design |
| Navigation | **In-app state, no router** | Private screens never appear in the URL or browser history |
| Weather | **Open-Meteo**, fixed city, called from the browser | No API key and no location permission |
| Font | **Atkinson Hyperlegible, self-hosted** via `@fontsource` | The spec's font, with no request to Google Fonts |
| Translations | Simple JSON files per language | Spanish first, then English. Add a library only if this becomes painful |
| Install on phone | **PWA** via `vite-plugin-pwa` (optional, later) | Home-screen icon and offline use |
| Helper "¿Dónde está…?" | Scripted answers | No AI, and no text leaves the device (spec §8) |

Libraries for specific features are added only when that feature is built:

| Feature | Likely tool |
|---|---|
| ZIP export with a real password | `@zip.js/zip.js` |
| PDF export | `pdf-lib` |
| SHA-256 file fingerprints | Web Crypto (built into browsers) |
| Encrypting saved data | Web Crypto (built into browsers) |
| Checking outbound requests | Playwright |

## Why not the alternatives

| Option | Why not |
|---|---|
| **Next.js** | Built around a server, and Tempo has no server code |
| **Supabase or another hosted database** | Tempo has nothing to store centrally, and a central database would contradict the local-first design |
| **Expo / React Native** | Requires learning a different component model, with no benefit for a web demo |
| **GitHub Pages** | Works, but the link would be `katelynshapoval.github.io/survivor-safety-app`, which reveals the purpose. It also can't set custom security headers, and free accounts need a public repo |

## Security headers

`public/_headers` makes the browser enforce the privacy claims:

- The app can only connect to itself and `api.open-meteo.com`. If a future change tried to send data elsewhere, the browser would block it.
- Location, camera and microphone access are switched off.
- Search engines are told not to index the site.

The Open-Meteo **geocoding** host is deliberately not allowed. City search stays local, so typed text, including entry words, can't reach it.

This limits what the app's code can do. It does not make the device safe, and it doesn't remove browser history or other traces.

## Limits of the web version

These parts of the design can't work properly in a browser, so they stay **designed, not built** and must be presented that way:

- Hiding the app in the recent-apps view
- Real disguised lock-screen notifications
- Reliable return to the weather when the phone locks (the app can only react when the page is hidden)
- Deleting a screenshot from the phone's gallery

Browser storage also isn't strongly protected: clearing site data erases it, and anyone with access to the unlocked browser may be able to read it. That's acceptable for fictional data only.

## Free-tier limits

| Service | Limit | Risk for the contest |
|---|---|---|
| Open-Meteo | Under 10,000 calls a day, 5,000 an hour, 600 a minute, per IP. Non-commercial use only | None for judging. A real product may need a paid plan |
| Open-Meteo data licence | CC BY 4.0 | **Requires attribution**, so show credit in the app |
| Durable Objects (only if chat is built) | 100,000 requests and 13,000 GB-s a day, SQLite-backed objects only | None at demo scale |

## If a live chat demo is added

This is optional, and only comes after the core flows work.

- A small Cloudflare Worker with **Durable Objects** relays messages between the phone and the staff console over WebSockets, using the Hibernation API to stay within the free tier.
- **No database** and no saved history. The spec says the chat is anonymous and not stored.
- It stays clearly labelled as a fictional demo, with no real professionals.
- `public/_headers` doesn't apply to responses from Worker code, so the Worker must set its own security headers.

This adds real server code and real network traffic, so the spec's statement that only the weather request leaves the device would have to change. Record that decision in the spec first.

## Later: public release

A browser isn't enough for a real release, because the protections listed above need native access. The likely path is wrapping the app with **Capacitor** for iOS and Android, and reassessing storage and encryption. Spec §11.3 and §14 list the required reviews, and none of this is committed.
