# Tempo: instructions for working in this repo

Tempo is a contest prototype of a discreet support app disguised as a cat weather app. It is not an operational safety service.

Read before changing anything:

- `docs/Tempo_Project_Specification.md`: what the product is and its decisions. This is the source of truth.
- `docs/TECH_STACK.md`: the tools, and why.
- `docs/ROADMAP.md`: build order and status.
- `docs/DEPLOY.md`: how the app reaches the public link.

## Stack

React + Vite in plain JavaScript (`.jsx`), normal HTML and CSS, deployed on Cloudflare Workers static assets. The owner is learning, so prefer simple, readable code and don't add TypeScript or a library without a clear need.

## Rules that must not be broken

1. **Nothing private leaves the device.** The only outbound request is the fixed-city Open-Meteo forecast. Entry words and records are never sent anywhere.
2. **No analytics, trackers, ads, or third-party scripts or fonts.** Host every asset ourselves. `public/_headers` enforces this, so don't loosen it without recording a decision in the spec.
3. **No real dispatch.** Alerts, invitations, chat and exports to other people are fictional. Nothing contacts anyone, calls 112 or requests location.
4. **Fictional data only.** Personas are Álex, Marta and Dani.
5. **Private screens stay out of the URL.** The private area uses in-app state, not routes, so browser history shows nothing but the cover.
6. **No judgments by the interface.** No danger scores, verdicts, diagnoses or "this is legal" results. "¿Dónde está…?" is a scripted navigation helper with no AI.
7. **Removed features stay removed:** ID-document vault, injury photos, medical reports, breathing exercise, PIN keypad, duress or decoy modes (spec §16.3).
8. **Gender-neutral wording** throughout the interface and examples.
9. **Be honest about status.** Don't call something working until it has been tested. Use the spec's terms: designed, prototyped, tested, deferred, removed.

## Keeping docs current

When a decision changes, update the relevant section of the spec and its decision log (§1.2, see §18), plus `docs/TECH_STACK.md` or `docs/ROADMAP.md` where affected.
