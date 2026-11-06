# Tempo: roadmap

Build order for the contest prototype. Section numbers (§) refer to `Tempo_Project_Specification.md`.

**Status terms** (from §18): not started, prototyped, tested, deferred. Mark something tested only after trying it on a real phone.

## Before any features

| Task | Status |
|---|---|
| Project base, docs and security headers | Done |
| Check the contest rules allow a hosted public link (§1 describes a local prototype) | **Open: owner to check** |
| Publish to Cloudflare and test the QR on a phone (`DEPLOY.md`) | Not started |

## Step 1: Foundations

| Task | Spec | Status |
|---|---|---|
| Brand colours, Atkinson Hyperlegible, phone-sized layout | §1 | Not started |
| In-app screen navigation, with no private URLs | §4 | Not started |
| Local storage helper and fictional seed data (Álex, Marta, Dani) | §1.1 | Not started |
| Spanish text kept in a language file, in gender-neutral wording | §5.16 | Not started |
| **Modo presentación**, on by default in the contest build: persistent label, "Reiniciar datos ficticios" | §5.19 | Not started |

## Step 2: Core demo flows (required)

| Task | Spec | Status |
|---|---|---|
| Weather cover: Hoy, Semana, Michis, fixed city, Open-Meteo credit | §5.1 | Not started |
| Hidden entry through city search, and "Salir" on every private screen | §5.1 | Not started |
| Five-step onboarding, including the no-recovery warning | §5.2 | Not started |
| Private home | §5 | Not started |
| Before you save, records, tags and the dated thread | §5.4 | Not started |
| Safety plan: eight sections plus summary view | §5.10 | Not started |

**Stop here and test on a real phone.** This is the minimum demo.

## Step 3: Priority additions

| Task | Spec | Status |
|---|---|---|
| Device check and information-only mode | §5.3 | Not started |
| Diary and "Soltar sin guardar" | §5.7 | Not started |
| "Todo junto" 12-week view, with no scoring | §5.8 | Not started |
| Help card, editable and full-screen | §5.2 | Not started |
| Information and rights pages, with sources and dates | §5.11 | Not started |
| Digital violence page | §5.6 | Not started |
| "¿Dónde está…?" scripted helper | §5.17 | Not started |
| Settings and "Borrar todo" | §5.18 | Not started |

## Step 4: Extras, if time allows

| Task | Spec | Status |
|---|---|---|
| Injury note, with no photos | §5.5 | Not started |
| Hidden-detail copy, redaction preview | §5.4 | Not started |
| ZIP and PDF export with synthetic data | §5.8 | Not started |
| Trusted people and the "Avisar a mi gente" preview, with no dispatch | §5.12, §5.14 | Not started |
| Trusted person's four screens | §5.12 | Not started |
| Professional chat and staff console as scripted mocks, labelled future-only | §5.13 | Not started |
| English | §5.16 | Not started |
| PWA install and offline use | `TECH_STACK.md` | Not started |

## Step 5: Optional stretch

| Task | Spec | Status |
|---|---|---|
| Live chat demo between a phone and the staff console (`TECH_STACK.md`) | §5.13 | Deferred |

## Before judging

- [ ] Work through the contest checks in §14 and keep an honest tested/not-tested log (§11.2).
- [ ] Use Playwright or browser dev tools to confirm the only outside request is the Open-Meteo forecast, and that entry words never appear in it.
- [ ] Test on the actual phones and browsers you expect, including iPhone Safari and Android Chrome.
- [ ] Put the QR code and a fictional demo entry word on the slide or a handout, so judges can get in unaided.
- [ ] Keep a local copy running on your laptop in case the venue Wi-Fi fails.
- [ ] Re-check the free-tier limits in `TECH_STACK.md`.
