# Tempo — Project Idea & Living Specification

*Design, product decisions, risks and defences for a discreet support-tool concept — contest prototype for Spain.*

> **Project status — contest only (October 2026).** Tempo is a proposed app, not an operational safety service. The contest deliverable is expected to be a **local/localhost interactive prototype**, demonstrated using **fictional scenarios and synthetic data**. No victim-survivors are recruited; no lawyers, clinicians, psychologists, support organisations or other professionals have been consulted or partnered with; no live emergency alerts or sensitive-data transfers will be tested. Functionality described below is a **design proposal unless specifically identified as part of the contest demo**. Professional review, real services, user research with appropriate safeguards and legal compliance work are **future, pre-launch requirements**, not tasks required for this contest.
> 

# 1. Summary

Tempo (formerly **NEXO**) is a contest-stage concept for a discreet support app for people experiencing domestic, gender-based, sexual or digital violence. Its visible identity is a playful **cat-themed weather app**; its private area presents documentation tools, a safety plan, a personal diary, information about support and future concepts for trusted people and professional contact. This is a **local prototype with fictional examples**, not an operational safety or emergency service.

**The core idea:** people may need privacy, information and time before deciding whether to seek help. *Tempo* suggests going at your own pace; the visible name also reads naturally as a weather/"tiempo" app. The app should not direct or judge that decision.

**Mascot and visual identity:** a Siamese cat with light, humorous daily weather lines; a dark forest-green and peach colour palette (no purple, intentionally avoiding colours associated with 8M/25N); the **Michi** logo (an “o” with cat ears); **Atkinson Hyperlegible** type for readability; and one peach “light”/focus accent per screen. These are design choices, not security features. The Spanish interface uses **gender-neutral wording throughout, because anyone can be a victim**. Example personas: **Álex, Marta and Dani**; information must address any person affected, not just women, while accurately stating which Spanish services have narrower eligibility.

**Visible cover:** a believable cat-weather experience, with weather forecasts proposed from **Open-Meteo** (no API key required), using a **fixed city rather than geolocation**. Weather requests are external network traffic and should be reviewed in the demo; no sensitive content or city-search code words should be sent to a weather provider.

**Main contributions and product direction**

- A private entry hidden in the cover's **city search**: entering a user-chosen code word causes it to appear like an ordinary town result.
- A **five-step onboarding**: language, what Tempo is for, “¿Es para ti?” (signs, not diagnosis), limits and the personal entry word.
- A device-safety self-check that can put Tempo into **information-only mode**, hiding saving, the personal thread, the diary and “Todo junto” if risk is indicated. This is not spyware detection.
- **Before you save** cautions, personal documentation (the original is always kept; a hidden-detail copy is optional), an injury-information flow (a short note only, no photos and no medical reports) and a medical-first framing.
- A diary with **“Soltar sin guardar”**, and **“Todo junto”**: a 12-week calendar of the person's own lights and tags, without danger scores or judgments.
- A **safety plan** and editable Safe Help Card; **multiple trusted people**, each with code phrases and permissions, and a choice of alert recipient(s).
- A **future professional-chat concept** (introduction, anonymous chat, out-of-hours screen and a staff desktop console), always presented as contingent on real partner services. In serious danger the professional cannot act alone: they send **help options** and the person chooses (call 112, share location once, alert their people, or "ahora no puedo").
- **Settings** that close common disguise leaks: the person's own notifications look like weather alerts, Tempo returns to the weather when the person leaves the app, the private area is hidden in the recent-apps view, and a typed-confirmation **"Borrar todo"**.
- **Gallery protection:** an offer to delete an imported screenshot from the phone's gallery. Tempo stores **no injury photos and no medical reports** (§3.2).
- Selective **ZIP/PDF export** design with originals/redacted variants, password protection, a “Léeme primero” manifest and file fingerprints, plus a delete-after-export option.
- **“¿Dónde está…?”**, a cat helper that only navigates the app and provides general information, rather than giving individual advice.
- A dedicated digital-violence information screen featuring the **AEPD Canal Prioritario**.

**Non-negotiable boundaries:** Tempo does **not** store DNI or other identification documents; it is not a substitute for emergency services or qualified professionals; personal records or hashes do not guarantee evidence acceptance; and the disguise does not make a device safe. The contest prototype must not send real messages, alerts, private data or contact information.

## 1.1 What is real in the contest, and what is not

| Area | Proposed contest demonstration (fictional data) | Future real-world work |
| --- | --- | --- |
| App and cover | Local clickable/web prototype; cat weather and hidden city-search entry | Native/mobile security, distribution, secure re-entry and failure testing |
| Weather | Fixed-city Open-Meteo cover is the proposed design; validate actual network calls | Production data-use, availability and dependency/security review |
| Identity and setup | Tempo branding, five-step onboarding and safety-check mock | Review of wording, accessibility and device-threat modelling |
| Records, diary and calendar | Fictional examples, “Soltar sin guardar” and 12-week “Todo junto” | Secure local storage, data lifecycle and full privacy review |
| Export | Mock/demo ZIP/PDF selection, password/manifest workflow **only to the extent implemented** | Reliable encryption, hashing, safe transfer, deletion/retention assessment |
| Trusted people / alerts | Fictional invitation, permissions and weather-style notification previews; **no dispatch** | Real consent, delivery reliability, revocation and escalation safeguards |
| Professional chat | **Future-concept screens only**, no real professionals or messaging | Formal partner organisations, trained staff, duty of care, secure architecture |
| Helper | Fixed navigation and general-information replies (“¿Dónde está…?”) | Reviewed informational content; no free-form high-risk advice |
| Testing | Self-tests and optional fictional peer tasks | Expert review and ethically governed research with target users |
| Outreach | A strategy explained to judges, not a campaign | Vetting any organisation introductions and operating model |

## 1.2 Decision log — NEXO → Tempo (31 October 2026)

**Decided:** Rename to Tempo; Siamese cat-weather cover; fixed-city Open-Meteo concept; Michi logo, forest-green/peach and Atkinson Hyperlegible; gender-neutral content; city-search secret entry; five onboarding screens; information-only mode; multi-contact trusted-person model; diary and “Todo junto”; “¿Dónde está…?” navigation helper; “Avisar a mi gente”; digital violence screen; selectable ZIP/PDF export design. **Removed:** ID-document vault, breathing exercise, PIN keypad, injury photos and medical-report uploads (31 October 2026). **Not designed/deferred:** duress PIN and fake decoy mode.

**Decided in the second design round (31 October 2026):**

- **Forgotten entry word or password:** no recovery by design (§5.2). Setup explains that the only way back is deleting Tempo and starting again, so nobody can use a hint to get in. A forgotten export password only locks that file; a new export can be made from the originals kept in Tempo.
- **Settings screen:** disguised notifications for the person's own alerts and chat messages; return to the weather when leaving the app; hidden recent-apps preview; entry word, weather city and language; "Borrar todo" with typed confirmation (§5.18).
- **Gallery protection:** "¿Borrarla de tu galería?" after importing a screenshot.
- **No injury photos or medical reports (31 October 2026):** they are the most dangerous material if someone gets into the phone, the official medical record already lives with the health service, and a phone photo is weak evidence. The injury screen keeps a short note (date, body area, own words) and always puts medical care first. The "Foto" record type was removed with them. Photos could return only as an opt-in with real encryption, testing and specialist review (§16.3).
- **Hidden-detail copy is optional and manual (31 October 2026):** only the original is saved by default; Tempo suggests details of other people but covers nothing until the person taps it, and never covers the other person in the conversation or the person's own messages unless chosen (§5.4).
- **Information-only mode** also hides the diary and "Todo junto"; the safety plan still works but is erased on exit.
- **Records:** type-specific fields (note, screenshot, conversation) and **self-chosen tags**, which are the only source for "Todo junto" tags.
- **Export:** two steps (choose, then share); diary excluded by default; "Todo junto" is never exported. **Tempo never sends the file itself** (no in-app sending, including to the professional chat); it only hands it to the phone's own Files app or share menu, and what the person does next is their decision and responsibility.
- **Trusted people:** three permissions per person (receives alerts, sees plan, sees help card); location is never shared; invitation in person with a code that expires in 10 minutes, so no message is sent.
- **Professional chat:** consent-based serious-danger flow (§5.13) and an out-of-hours screen pointing to 016, 112, "Avisar a mi gente" and the diary.
- **Language visible to staff and the person (31 October 2026):** the chat shows the person's chosen language before the first message, and the staff console shows it as a badge beside the person's name, not only inside the help card. Staff reply in that language or use an interpreter, help options are shown in that language, and gender-neutral wording and not assuming the person's situation are reminded to staff (§5.13). Trigger words for the help options are checked in every supported language (§5.13, §5.16).
- **Spread (31 October 2026):** future-only outreach, explained as trusted, private channels with stage gates and no ads, tracking or targeting; public materials never reveal the cover, and the app-store listing is an open question (§12.6–§12.9).
- **Support for anyone:** the Oficinas de Asistencia a las Víctimas del Delito (OAVD) added alongside 112, 016 and the AEPD.
- **Smaller additions:** working weather tabs (Semana, Michis), an empty first-day home, help card editing and full-screen view, a safety-plan summary view and rights topics with their own pages.

**Decided on the build (6 November 2026):** the prototype is a frontend-only React + Vite web app hosted on Cloudflare, so judges can scan a QR code and try it on their own phones, with a local copy as a fallback. There are no accounts, no server code and no database; fictional data stays in each judge's browser. This extends the "local/localhost" wording in the project status and §1.1 to a **public link serving only fictional data**. **Open:** check that the contest rules allow a hosted demo. See `TECH_STACK.md`.

**Designed, not yet built:** the **"Modo presentación"** switch (§5.19) and the **redaction preview** screen (§5.4). Both are needed to match the brief and must be built and tested in the prototype.

**Explicit unresolved conflicts with the original brief:**

1. **Prototype labelling:** Current screen designs omit visible “simulación” labels despite the original requirement for on-screen simulation identification and a persistent demo notice. The fix is the **"Modo presentación"** switch (§5.19, designed), turned on for judging. A slide alone does not fulfil an on-screen requirement. Treat this as a contest compliance risk until the switch is built and tested.
2. **Professional chat:** The original contest scope excluded professional involvement and treated a service directory as future-only. The chat, including its staff console, is a **vision/partner-dependent future feature**, not a live support offer or current integration.
3. **“Todo junto”:** It resembles risk-pattern analysis. It must display **only the person's own entries, 12-week lights and self-chosen tags**; it does not classify, interpret, score or predict danger.
4. **"Aviso enviado":** the current "Avisar a mi gente" design ends on "Aviso enviado", while the brief requires the preview to say that no alert is sent. "Modo presentación" must switch this screen back to "No se ha enviado nada".

**Presentation flows retained:** cover + secret entry; Before-you-save with invented records; safety plan. Trusted-people and injury screens are extra examples. A screen's presence does not prove that the backend feature exists.

# 2. Design principles

1. **Safety before features.** Remove or constrain a feature if it could increase exposure or falsely reassure.
2. **The person decides.** No involuntary reporting, notifications, location collection, external sharing or contact with another person.
3. **Documentation, not proof.** Records, timestamps, redactions and hashes organise material; they do not establish truth or court admissibility.
4. **Privacy by design.** Limit data collection and outbound services; encryption and OS-level protections remain future engineering work, not properties established by localhost.
5. **No professional judgments by the interface.** “¿Es para ti?” is not diagnostic; “Todo junto” does not infer danger; “¿Dónde está…?” cannot advise on legal, medical or crisis decisions.
6. **Honest demonstration.** Distinguish built interactions, mocked screens and future features. Current designs without permanent simulation labels remain a known discrepancy against the brief (see §1.2).
7. **Trauma-informed design intent.** Clear choices, no coercive text, easy exits and gender-neutral language; not a claim of clinical validation.
8. **Accessibility by design.** Atkinson Hyperlegible, readable contrast and keyboard/screen-reader treatment should be tested rather than assumed from visual styling.

# 3. Design concerns and planned responses

## 3.1 Saving chats, screenshots and recordings

**Concern.** A person may collect or share communications that involve someone else's privacy rights. Spanish criminal-law risks may arise from unauthorised access, interception or unlawful disclosure. Merely taking a screenshot is **not automatically a crime**; context, how it was obtained and what is done with it matter.

**Proposed Tempo response**

- A three-question **Before you save** interface: Was the person part of the conversation? Did they access someone else's device/account? Does the material involve another person's sensitive information or a child?
- Plain-language risk warnings; never a definitive green light saying an act is legal.
- No secret capture or recording of other people's conversations.
- An optional, manual hidden-detail copy (the person taps what to cover), preserving the untouched original separately.
- Clear reminders not to publish private material online and not to treat the prototype as legal advice.

**Spain-specific context.** Articles 197 and 197 bis of the Código Penal deal with certain privacy-related offences and unauthorised system access; the exact subsection and potential offence depend on the act. The 2025 Supreme Court discussion of screenshots emphasises assessing authenticity with the available evidence, not an automatic rule that screenshots are worthless or sufficient. The previous dossier's unattributed 2016 ruling and anecdotal conviction descriptions are **not relied on as verified authority here**. See section 7 and the official sources in section 17.

## 3.2 Injury information (no photos, no medical reports)

**Concern.** Injuries change over time, and a private photo cannot replace clinical evaluation or a medical report or prove how an injury occurred. Photos and medical reports are also the most dangerous material in the app if someone gains access to the phone, and health data is a special category under the GDPR.

**Tempo response (decided 31 October 2026)**

- **Tempo stores no injury photos and no medical reports.** The official record is the *parte de lesiones* issued by the health service; Tempo explains it and says how to ask for it.
- The injury screen starts with the importance of prompt medical assessment, shows an optional fictional body map and lets the person note the date, the body area, a pain level and what happened in their own words.
- The note is described as a **personal note**, not a medical report.
- Do not make diagnoses, identify causes of injuries or promise evidentiary weight.
- A future opt-in for photos would need real encryption tied to the entry word, testing, hidden previews, an off-by-default export and specialist review (§16.3).

No clinician has written, reviewed or endorsed these screens for the contest. Medical-content review would be required before any live use.

## 3.3 AI and other high-risk advice

The **“¿Dónde está…?”** cat helper replaces the original high-risk Q&A assistant. Its purpose is **app navigation and general information**, with a direct button to the relevant screen in each answer. It does not interpret records, diagnose, assess evidence, score danger or decide what a person should do.

For the contest, use a controlled set of authored responses; test refusal cases separately in a **presentation/QA slide**, rather than framing them as a main app experience. General resources should be linked to official public information and not treated as personalised professional advice.

# 4. Intended users and threat model

**Possible future users:** adults who need discreet ways to organise information or find support, including people affected by domestic, sexual, digital or other interpersonal violence; trusted contacts; people who need language or accessibility support. Any future age policy (for example, 16+) is a product decision, not a claim about the legal age of data-processing consent. **Contest users:** creator, judges and optional peer testers using fictional profiles, including Álex, Marta and Dani.

| Threat or failure | Tempo design response | Limit of contest prototype / unresolved risk |
| --- | --- | --- |
| Another person inspects the phone | Cat-weather cover, entry via city-search code, quick exit | Browser history, app/window previews, autocomplete and other traces may reveal use; the code is not tested authentication |
| City search exposes a code word | Treat secret word locally, independent from actual weather-city query | Must verify code words never leave via Open-Meteo, logs or analytics |
| Location or third-party network leakage | A fixed weather city; no geolocation request | Weather API calls may still expose network metadata, e.g. the visitor's IP; review requests before demo |
| Shared accounts and backups | Local-first future architecture and safety warnings | Browser caches, cloud sync and OS histories are not fully controlled |
| Spyware or coercive device access | Self-report safety check; information-only mode removes saving, thread and diary access | Cannot detect spyware, certify a device or guarantee hidden data is inaccessible |
| Hidden-entry discovery | Explicit limitations and fast return to the cover | Neither disguise nor quick exit clears OS/browser traces |
| The person's own notifications reveal Tempo | Settings disguise chat messages and confirmations as weather alerts ("Cambio en la previsión de mañana") | Disguised wording may still be recognised; no real notifications in the contest |
| Phone left open on the private area, or seen in recent apps | Return to the weather when leaving the app; hidden recent-apps preview | Platform support varies; must be tested on real devices |
| Screenshots land in the gallery and cloud backup | Offer to delete an imported screenshot from the gallery; Tempo stores no injury photos | Deletion from backups or synced copies cannot be guaranteed |
| Weather tabs that do nothing look suspicious | Every tab of the weather side works (Hoy, Semana, Michis) | A determined person may still notice an unusual app |
| Forgotten entry word or export password | No recovery by design: no accounts, email, phone number or security questions, so no reset or hint can be abused to get in; a forgotten export password only locks that file | The person loses records kept only on the phone if the entry word is forgotten; a protected export is the only backup; not tested |
| A trusted contact behaves unsafely | Separate permissions/code phrases; selective alerts; revoke access | Trustworthiness and real delivery/revocation are unverified |
| Alert fails or reveals its meaning | Mock weather-style notifications and clear acknowledgement of delivery uncertainty | A disguised notification may still be discovered; no real notifications or delivery in contest |
| Personal data leaks through exports | Select originals/redactions, password option, manifest, delete-after-share proposal; Tempo itself never sends the file, and the person shares it through the phone's own menu at their own responsibility | Exported files, apps and recipients create new copies; secure deletion cannot be promised |
| Professional chat misleads users | Show as future service with proposed staff workflow and serious-danger disclosure | No professional is available, no partnership exists, no anonymous live service is offered |
| “Todo junto” appears to assess risk | Self-tagged 12-week view without automatic scores or conclusions | People might still interpret patterns as clinical/safety recommendations; evaluate wording |
| Prototype mistaken for approved service | Clear limits in presentation and demo context | Current screen designs lack mandatory persistent prototype label; resolve before judging |
| Information becomes outdated | Source citations and last-review dates | Live updates and content governance are future obligations |

# 5. How the app would work

*All flows in this section describe the proposed product. For the contest, choose a small subset to implement as safe interactive simulations with fictional data.*

## 5.1 Disguise and access

- **Weather cover:** Tempo looks like a cheerful cat-weather app with a Siamese mascot and playful daily lines; weather is proposed from **Open-Meteo**, for a **fixed city**, without requesting device location.
- **Secret entry:** the city-search UI accepts a personal entry word and displays it as if it were a normal city/town result. Recognition should be local; no code word should go to a geocoding, forecast or analytics endpoint.
- **No PIN keypad:** the original extra PIN screen has been dropped. The city-search mechanism is **not** a claim of device-level authentication.
- **No designed duress/decoy mode:** those ideas remain excluded/deferred; they must not be presented as implemented.
- **Quick exit:** return to the weather view without suggesting it removes history, downloads, notifications or OS traces.
- **Notifications:** weather-disguised alerts exist for trusted contacts **and** for the person's own notifications (chat messages, "aviso enviado"), configured in Settings (§5.18). Mock screens only in the contest; no live delivery.
- **Leaving the app:** Tempo returns to the weather when the person switches apps or locks the phone, and the recent-apps preview shows the weather, not the private area (proposed; platform behaviour must be tested).
- **Complete cover:** every weather tab works (Hoy, Semana with a 7-day forecast, Michis with the cat's daily comments), so a curious person finds an ordinary app.

**Important warning:** “Una apariencia discreta no garantiza que otra persona no encuentre Tempo.”

**Design/brief discrepancy:** Current layouts intentionally appear like a polished real product and do not show persistent “simulación” labels. This conflicts with the contest brief and needs an explicit demonstration/compliance decision (see §1.2).

## 5.2 Onboarding and the Safe Help Card

**Five setup steps**, proposed in this order:

1. Language choice.
2. What Tempo is for — purpose and limitations in plain language.
3. **“¿Es para ti?”** — signs/situations for reflection, never a diagnosis or eligibility test.
4. Limits: the app is not guaranteed private and cannot replace urgent or professional help.
5. Choose the **city-search entry word**.

The **Safe Help Card** remains a user-edited summary of contact preferences and needs, never automatically sent. Example: “No puedo recibir llamadas. Prefiero mensajes después de las 18:00. Busco información y todavía no quiero denunciar.” In the contest, this card must use only fictional inputs.

The information-only/device-risk check is described in §5.3. **Forgotten entry word or password (decided).**

- **Entry word:** there is no recovery. Tempo has no accounts, email address, phone number or security questions, so there is nothing to reset against, and nobody else, including an abusive person with access to the phone, can use a reset or a hint to get in. The weather app keeps working normally. To reach the private area again the person deletes Tempo and installs it again; records kept only on the phone are lost. Setup says this before the word is saved: it cannot be recovered, and the only way back is to start from scratch.
- **Export (ZIP) password:** Tempo cannot open or reset it. Only that file stays locked; the originals remain in Tempo, so the person can create a new export with a new password.
- **Professional chat:** no password exists, because the chat is anonymous.
- **Trade-off:** a person who forgets the entry word loses saved material. A protected export is the only way to keep a copy. Whether to add a "type it twice" confirmation at setup is an open question.

Whether setup steps are skippable also remains open.

The help card can be edited (message and languages, with quick ideas such as "No vengas a casa") and shown full-screen for someone to read. Trusted people only see it if given that permission (§5.12).

## 5.3 Is this device safe? (safety check)

An optional self-check asks about device/account access, shared backups or location, and possible surveillance. It **does not** scan the device or detect spyware.

If the answers indicate possible monitoring, the proposed app enters **information-only mode**: tools for **saving records, opening the personal thread, the diary and "Todo junto"** are hidden/disabled. The safety plan still works but is **erased on exit**. General information, official resources, the help card, trusted people and the professional chat remain accessible. A banner offers to repeat the device check. It should explain why avoiding data entry may be safer, without implying that this mode erases previous data or prevents monitoring. A real release must define the transition for previously stored material and test it. For the contest, demonstrate the restriction with fictional state only.

## 5.4 Secure Record (documentation)

Proposed items: dated notes, screenshots, imported conversations, short personal accounts and logs of digital control. **Only invented files/data appear in the contest.**

**Illustrative flow**

1. Select a record type.
2. Answer **Before you save**: Are you a participant? Was access authorised? Does this involve other people or especially sensitive material?
3. Show a nuanced response: **no obvious issue identified / caution / do not proceed within Tempo**. These are **interface prompts, not legal rulings**; there must be no “legally safe” result.
4. Display simple precautions: do not access someone else's device/account, intercept others' conversations or publish private content.
5. Show how original context (dates, participants and full conversation where appropriate) could be preserved without alteration.
6. **Future technical design:** compute a SHA-256 hash, capture metadata and retain a separate original and redacted version. A hash only detects changes to bytes **after hashing**; it does not prove who created a file, that the timestamp is true or that a court will accept it.
7. Allow an optional original note in the person's words; never rewrite it using AI.
8. Preview a private timeline and choose whether a future export should be possible. No real sharing in the demo.
9. If the device may be monitored, explain why not saving anything may be safer.

**Record types and tags (designed):** each type shows its own fields. A note has no attachment; a screenshot shows the imported file plus "¿Borrarla de tu galería? Así solo queda en Tempo"; a conversation imports the full exported text. The person can add **self-chosen tags** (for example "Control del móvil o cuentas", "Insultos o gritos", "Amenazas"). These tags are the only source of the categories shown in "Todo junto".

**Hidden-detail copy (designed, optional and manual):** reached from a screenshot record via "Crear una copia con datos tapados (opcional)". By default **only the original is saved**; a copy is another sensitive file on the phone, so the person creates one only to show the screenshot to someone. Two tabs switch between **Original** and **Copia**. Tempo **only suggests** details of other people (names, addresses and places, emails and phone numbers), outlined with a dashed border. **Nothing is covered until the person taps it**, and tapping a covered detail shows it again; "Tapar las 3 sugerencias" covers all suggestions at once. Tempo never covers the other person in the conversation, or the person's own messages, unless the person chooses to. The original is always kept separately and unchanged, because a copy with covered parts could be challenged as edited. Tempo never alters the text or what anyone said. Suggesting details needs text recognition on the phone; until it is built and tested, do not present automatic detection as working. Detection can miss or wrongly flag details, so the person always reviews the copy.

**Honest court-validity wording:** “This could help organise material. It does not establish authenticity or guarantee acceptance as evidence.”

## 5.5 Injury documentation

1. Show a static explanation encouraging medical assessment when injuries occur; reference a *parte de lesiones* as the official healthcare record and how to ask for it.
2. Show a sample body map and a note with date, body area, optional pain level and the person's own words. **Tempo stores no injury photos and no medical reports** (§3.2); the screen says so.
3. Explain that Tempo's note is a personal note, not a medical or forensic finding.
4. Avoid definitive procedural claims about reporting without corroborating evidence; relevant rights information must come from official public sources.
5. In a future public release, a clinician should review this content before use.

## 5.6 Digital violence module

Potential topics: threatening messages, stalking, shared-account control, sextortion, non-consensual intimate-image sharing and online harassment.

- A sample checklist for retaining **non-intimate metadata** such as usernames, URLs and dates, where lawfully obtained.
- Warnings against accessing other people's accounts or distributing sensitive images.
- A link to the Spanish data-protection authority's **Canal Prioritario**, when relevant, rather than an in-app removal promise.
- A device-safety explainer about passwords, connected devices, two-factor authentication and location sharing, with a warning that sudden changes can alert someone monitoring the device.
- **No real intimate images**, third-party recordings or private messages in the contest dataset.

## 5.7 Daily check-in diary

The personal diary supports voluntary entries with a **five-word mood choice** ("Muy mal" to "Muy bien") and free writing, without altering the person's original words. An entry can optionally be added to the thread as something that happened. (Sleep tracking was in the earlier brief but is not in the current design.) It also offers **“Soltar sin guardar”**: a space to type and let thoughts go **without intentionally creating a saved diary entry**.

This label is a **product intention, not a verified guarantee of zero traces**: a real implementation must assess memory, browser input history, autosave, crash reporting and backups. The contest uses fictional notes only.

## 5.8 “Todo junto” — 12-week overview and ZIP/PDF export

**“Todo junto”** is a **12-week calendar** bringing together the person's own “lights”/check-ins and **user-created tags**. It makes dated entries easier to see side by side but **never assigns scores, risk levels, diagnoses or verdicts**, and does not infer whether a pattern constitutes abuse or danger.

**ZIP/PDF export design:**

1. The person selects which records and dates to include. The **diary is excluded by default** and only included if chosen. **"Todo junto" is never exported.** The format is either a full ZIP or a readable PDF summary.
2. For each relevant file, choose **original**, **hidden-detail/redacted copy**, or **both**. Keep original content unaltered in its own version. A hidden-detail copy exists only if the person created one.
3. Provide a **password-protection option**; exact encryption format, protection of metadata and compatible readers must be validated before real use. A forgotten export password cannot be reset; the person creates a new export from the originals kept in Tempo (§5.2).
4. Include **“Léeme primero”**, a manifest of included files, variants and **cryptographic fingerprints/hashes**. Hashes help compare bytes after calculation but are not proof of origin or legal admissibility.
5. **Tempo never sends the export itself: there is no in-app sending, including to the professional chat** (decided 31 October 2026). It cannot protect the file once it leaves the app, and the operator must not be made responsible for it. The app only hands the file to the phone's own Files app or share menu; Tempo does not see or record the destination, and anything shared from there is the person's decision and responsibility. The person can choose to remove the temporary local export afterwards. **Deleting one export cannot guarantee deletion from shares, backups, caches or recipients.**

The contest may demonstrate a selection/preview or generated **synthetic-only** ZIP/PDF only if actually implemented. Never imply that real sensitive records have been secured, exported or delivered. Any eventual live export needs technical, legal and privacy review.

## 5.9 Document vault — removed

**Removed from scope:** Tempo does **not** store DNI, residence cards, passports, identity papers or a general ID-document vault. Remove any vault file-list demo from the current plan. The safety-plan builder may *remind* a person about important documents for their own planning, but **Tempo does not hold those documents**.

## 5.10 Safety plan builder

A **contest-priority** interactive plan using fictional details: warning signs, safe places, contact methods, medication, keys, children/pets, transport, and optional code phrases. Keep editable preview/reset behaviour and avoid declaring any plan universally safe.

**Explicit text:** “Tempo no guarda documentos de identidad.” The plan can mention documents to think about or keep elsewhere, but must not invite an upload of ID papers. The current design's documents item reads: "Dónde tienes DNI, NIE o tarjeta sanitaria. Tempo no los guarda."

The plan has an editing view (eight sections with progress) and a **summary view** ("Ver mi plan") showing only what has been filled in, with "Solo está en este móvil". In information-only mode the plan is erased on exit.

## 5.11 Rights and process explainer

For the contest, this should be **static educational content with direct links to public Spanish sources**, dated and labelled “general information — prototype; not legal advice.” Avoid generating legal conclusions from AI.

**Designed topics, each with its own page:** digital violence (§5.6); help for any victim of a crime (**OAVD**, free, available without having reported); rights under Ley 4/2015 (to understand and be understood, information from the first contact, going with a person of one's choice, a free interpreter); what a *parte de lesiones* is; which law covers which situation (LO 1/2004, LO 10/2022, Código Penal and the Estatuto de la víctima); and help in your language. External links open in the browser and stay in its history; the screen says so.

**Future live release only:** qualified legal/content review, maintenance of legal updates, regional service differences and accessibility validation. Do not claim the current wording has been reviewed by a lawyer.

## 5.12 Trusted people — several contacts

The revised design supports **multiple trusted people**, each with their **own neutral code phrase** and **individually selected permissions**. The person using Tempo chooses **which contact or contacts would receive an alert**; a permission change or revocation should be visible and deliberate.

**Permissions per person:** receives alerts; sees the safety plan; sees the help card. **Location is never shared** ("Tempo nunca la comparte"). Removing a person does not notify them.

**Adding a person (three steps):** (1) choose a name (Tempo does not read the contact list) with a warning to pick someone unconnected to the person causing harm; (2) invite **in person** by showing a code that expires in 10 minutes, so no message is sent (a "by message" option exists, with a warning that it leaves traces on both phones); (3) agree a code phrase and what it means (for example "write asking if we're meeting tomorrow", "come and pick me up at a safe place", or "call 112 if I don't reply within 30 minutes").

**Trusted person's four conceptual screens:** (1) invitation, (2) exactly what is shared, (3) alert received (appearing like a weather notification) and (4) access removed. The alert's weather-like appearance is not a guarantee against discovery. These are **fictional simulations** in the contest: no contact import, SMS, push delivery, location sharing or actual invite. A live feature needs tested consent, delivery, revocation and reliability.

## 5.13 Professional chat and public directory — future concept only

**Professional chat is an aspirational future service, not a contest integration.** The proposed user journey includes (1) an introductory explanation, (2) an anonymous/pseudonymous conversation that **is not stored on the user's phone by design**, and (3) a **desktop staff console** for partner-service professionals.

**Serious danger (designed, consent-based):** because the chat is anonymous, the professional **cannot act alone**; they do not know who or where the person is. The entry screen says: "Si hay un peligro grave, te pedirá permiso para ver tu ubicación y avisar al 112. Sin tu permiso, no puede saber dónde estás." The flow:

1. In the staff console, a **"Riesgo grave"** button opens a short protocol: encourage calling 112; if that's not possible, ask permission to see the location once; suggest alerting trusted people; if the person cannot write, use yes/no questions.
2. The professional sends a **help-options card** to the chat with four buttons: **Llamar al 112** (when a mobile calls 112 in Spain, it sends its location to the emergency centre automatically), **Compartir mi ubicación una vez**, **Avisar a mi gente**, **Ahora no puedo**.
3. If location is shared, the console shows an approximate location that expires after 60 minutes, is not stored, and records who viewed it and when. The professional says so in the chat before calling 112.
4. Typing a message containing "miedo" in the chat brings up the help options directly.

**Language in the chat (designed 31 October 2026).** The language is visible to both sides, because staff need to know how the person is communicating and the person needs to know the staff member can answer in their language:

- **Person's side:** the chat opens by showing the language chosen in the app (which languages the contest covers is set in §5.16). The help-options card is shown in that language.
- **Staff console:** the person's language appears as a badge beside the person's name in the conversation list and at the top of the chat, and inside the help card. If the staff member does not work in that language, the console shows it before they reply and offers an interpreter or a route the partner service has confirmed for that language.
- **Staff reminders:** use gender-neutral wording; ask rather than assume how the person describes their situation, relationship or gender; keep replies in the person's language.
- **Trigger words:** the words that show the help options (for example "miedo") are checked in each supported language, not only Spanish. Each language list needs review by a native speaker before use.

These are design requirements, not evidence that interpretation or translated staffing exists. No partner has confirmed them.

Any legal duty a real service might have must be reviewed by specialists; the contest must not promise intervention. **Out of hours,** the chat shows that nobody is connected and offers 016 (24 hours, also in writing), "Avisar a mi gente", the diary and 112. “Anonymous” and “not saved on the phone” are **requirements to validate**, not properties established by a mockup; network or device traces can still exist. No professional, NGO or organisation has joined or endorsed Tempo. Do not imply a live chat service, guaranteed response or existing duty-of-care arrangement in the contest.

A future maintained services directory would need verified regional and language coverage, official agreements, review dates, referral rules and escalation responsibilities. For the contest, link to publicly available official information without presenting it as a partnership. **Spain:** **112** for emergencies; **016** for its legally defined area of support (including published non-phone channels); **OAVD** (Oficinas de Asistencia a las Víctimas del Delito) for any victim of a crime, regardless of gender; **AEPD Canal Prioritario** for qualifying online intimate/violent material. These are **external public resources, not Tempo integrations**.

## 5.14 “Avisar a mi gente” — simulated alert

The emergency-style action is renamed **“Avisar a mi gente”**. It is for the **selected trusted people**, not a call to emergency services. The screen must clearly state **“No llama al 112”** and the contest preview must say that **no alert is sent**.

The demo can show a confirmation, chosen recipients, weather-disguised alert preview and cancel/back action, using fictional people only. **Current design discrepancy:** the final screen reads "Aviso enviado"; with "Modo presentación" on (§5.19) it must read "No se ha enviado nada". There must be **no real dispatch**, emergency call or GPS request. In a real emergency in Spain, **112** is a separate public emergency number, not a function of Tempo. Delivery, offline handling, false alerts and risks from notifications require serious review if live alerts are ever considered.

## 5.15 Wellbeing — breathing exercise removed

The previously proposed breathing/grounding exercise has been **removed**. Tempo's non-clinical wellbeing elements are the weather-cover interactions and optional diary/check-in. Do not describe them as treatment or a clinically validated intervention. Static official resource information remains available as appropriate.

## 5.16 Languages and accessibility

**Contest goal:** Spanish first, with **gender-neutral wording** throughout (anyone can be a victim), then English if time permits. Personas are **Álex, Marta and Dani**; examples and entry points should not imply that only women can need help, while keeping legal service eligibility accurate.

Use **Atkinson Hyperlegible**, sufficient contrast in the forest-green/peach palette, keyboard navigation, screen-reader labels and usable touch targets. **Later possibilities:** Romanian, Ukrainian, *lectura fácil*, audio instructions and low-data mode. The language chosen in setup also applies to the professional chat and the staff console, which show it visibly (§5.13). Translation and accessibility require testing before any live release.

## 5.17 “¿Dónde está…?” cat helper

The original Q&A assistant is **replaced** by **“¿Dónde está…?”**, a cat-themed feature for **finding the right screen and presenting only general information**. Every authored answer has a button/link to the corresponding app screen. It does not give individual risk judgments, legal or medical conclusions, crisis instructions or edits to testimony. Refusal/red-team cases are documented for presentation and QA in §8.

## 5.18 Settings (designed)

Reached from a gear button on the private home.

- **Notification preview:** shows exactly how a Tempo notification looks on the lock screen. With **"Avisos disfrazados"** on, chat messages and confirmations read like weather updates ("Cambio en la previsión de mañana. Toca para ver."); turned off, the preview warns that anyone who sees the screen can read it.
- **"Volver al tiempo al salir":** return to the weather when the person switches apps or locks the phone.
- **"Ocultar en apps recientes":** the recent-apps preview shows the weather, not the private area.
- **Entry word, weather city and language.**
- **"Borrar todo lo guardado":** a separate screen listing what is deleted (thread, screenshots, notes, diary, plan, help card, trusted people and the entry word) and what cannot be (exported files, phone backups, messages already sent). The person types "borrar" to confirm; afterwards Tempo is only a weather app.

All three protections are **proposals whose platform behaviour must be tested**; none is a guarantee.

## 5.19 "Modo presentación" (designed, not yet built)

A switch for judging that makes the prototype's status visible **on screen**, as the original brief requires:

- a small, persistent "Prototipo con datos ficticios" label on every screen;
- simulation stripes and "No se ha enviado nada" on "Avisar a mi gente", the trusted person's alert, export and the professional chat;
- a "Reiniciar datos ficticios" action so the same stories can be replayed (§16.1).

It is a switch in **Settings** ("Para el concurso: marca todo como prototipo y no envía nada"); when on, Settings shows "Reiniciar datos ficticios". The label is an amber striped pill at the top of every screen, deliberately outside the brand palette so it reads as a status, not part of the product. The design includes examples for Settings, the home screen and the alert screen ("Vista previa: no se ha enviado nada").

It is turned **on for judging** and off for product screenshots. Until it is built and tested, the labelling conflict in §1.2 remains open. It is separate from "Borrar todo", which is a real product feature.

# 6. Privacy and data protection

**Contest implementation:** The safest realistic baseline is to use **only fictitious content**, with no production accounts, real documents, real victim histories or real contact lists. Running a webpage on localhost does **not** automatically make it encrypted, anonymous, secure or GDPR-compliant. Avoid third-party analytics, real location requests and outbound **sensitive-data** transfer. The proposed fixed-city Open-Meteo cover makes an external weather request; inspect its network/storage behaviour before showing the demo, and never transmit entry words or private content. Do not host personal-data examples on public links.

**Relevant future framework in Spain:** The EU **GDPR (RGPD)** and Spain's **LOPDGDD (Ley Orgánica 3/2018)** may apply where a real organisation processes personal data; some information envisaged for Tempo could include special-category health or sex-life data. A future operator would have to identify its lawful bases and Article 9 conditions where relevant, controller/processor roles, appropriate safeguards and transparency duties. Merely saying “consent” or “local-first” is not sufficient for compliance.

**Proposed future safeguards (not claims about this prototype)**

The export and partner-chat ideas add separate data flows: password-protected ZIP/PDF, recipient apps and staff consoles each need their own threat model. “Not saved on the phone” and “delete after sharing” must be tested as bounded technical statements, not guarantees.

- Local-first storage, encryption at rest and keys managed safely on-device.
- End-to-end encryption for any selected sharing; minimal server-side metadata.
- No ad SDKs, data sales, contact-list scraping or behavioural marketing.
- Backups off by default where platform capabilities allow, plus clear warnings about shared cloud accounts.
- Data minimisation; retention/deletion controls with clear limits about recoverability.
- Suppressed lock-screen previews and sensitive app-switcher previews **where technically possible**.
- A transparent statement identifying the actual controller and who can access data.
- A documented security model, independent penetration/security review and platform/store-policy review.
- Assessment of whether a **Data Protection Impact Assessment (EIPD/DPIA)** is required. The AEPD states it is generally mandatory for processing likely to present a high risk; the original dossier's wording “simplified EIPD included” should not be mistaken for a completed compliant assessment.
- A carefully determined minor-user policy. **LOPDGDD Article 7 generally sets 14 as the consent-related data-protection threshold in Spain**, subject to exceptions; Tempo can still choose a higher minimum such as 16 for product/safeguarding reasons.

**Future operational owner:** Not selected. A non-profit, association or other organisation is merely a potential operating model, **not a current data controller or partner**.

# 7. Applicable Spanish legal framework and legal-risk map

*Research orientation for a Spain-focused contest; not an individual legal opinion or a certification of compliance. The statute applies according to facts, people, offences, processing activities and jurisdiction, not because Tempo mentions it.*

| Spanish / EU source | Why it is relevant | Boundary that must be stated |
| --- | --- | --- |
| **Código Penal — Ley Orgánica 10/1995, Arts. 197 and 197 bis** | Unauthorised interference with private communications/data, certain disclosures of private material and unauthorised access to information systems | Distinguish unauthorised acquisition/interception, disclosure and non-consensual image distribution; do not assign one subsection to every screenshot |
| **Ley Orgánica 1/2004**, Art. 1 | Integral framework for certain gender-based violence against women by current/former male partners | It is **not** the umbrella law for every case of domestic, sexual or digital violence |
| **Ley Orgánica 10/2022**, Art. 3 | Legal framework concerning sexual violence, including identified digital contexts | Scope varies by conduct; it does not automatically make all harassment a sexual offence |
| **Ley 4/2015**, Estatuto de la víctima del delito | General victims' rights to information, support and other protections | Tempo cannot itself deliver or guarantee those statutory services |
| **GDPR (EU 2016/679)**, particularly Arts. 5, 6, 9, 25 and 35 | Data minimisation, lawful processing, sensitive-data rules, privacy-by-design and possible DPIA duties | Compliance depends on whether and how real personal data is processed; localhost is not an exemption by itself |
| **LOPDGDD — Ley Orgánica 3/2018**, particularly Art. 7 | Spanish data-protection rules, including minor-consent threshold | The general threshold of **14** differs from a proposed product entry age of **16** |

**How the Before-you-save concept should handle common situations**

| Situation | Risk message for the interface | Not a conclusion about legality |
| --- | --- | --- |
| Preserving a chat in which the person participated | Generally distinguishable from intercepting a third-party conversation; preserve context | Disclosing, publishing or obtaining material in unusual circumstances may raise other issues |
| Secretly recording people while not participating | Strong warning; no Tempo capture tool | Article 197 can be relevant depending on the facts |
| Accessing another person's phone/account without permission | Strong warning; Tempo will not instruct or facilitate it | Potential criminal/privacy risk depends on conduct and context |
| Posting or forwarding intimate/private material | Strong warning; no in-app public sharing | Different Art. 197 provisions and other rules may be engaged |
| Describing an injury in a note | Personal note label; medical care first; no photos or reports stored | No guarantee of a clinical conclusion or judicial acceptance |
| Material involving minors or others | Extra data-minimisation warning; no real content in demo | Rights of third parties and child protection may change what is appropriate |
| Screenshots submitted as evidence | Explain that authenticity is assessed in context | A hash or screenshot alone neither guarantees admissibility nor invalidates it |

**Relevant verified judicial example:** The Spanish Supreme Court decision **STS 3292/2025 (1 July 2025; ECLI:ES:TS:2025:3292)** discusses that the manipulability of screenshots does not always require forensic expert evidence; courts assess all available evidence in the specific case. It does **not** certify that screenshots collected through Tempo would be accepted.

**Avoid in presentation:** “Saving your own chat is always legal”; “red means criminal, green means permitted”; “SHA-256 makes screenshots court-ready”; “everyone is protected by LO 1/2004”; or “Tempo is GDPR-compliant.”

# 8. Assistant/AI guardrails

**Contest behaviour:** “¿Dónde está…?” is a constrained, scripted **navigation helper**, not an open conversational assistant. It responds with fixed general-information text and a **direct button to the relevant screen**. It may suggest where to find the safety plan, official information, records or export controls, but should not interpret any private entry. There is no need to send sensitive text to an external AI provider.

**Never do:** legal/medical advice, diagnoses, predicting court outcomes, interpreting danger, directing a person to leave/confront/report, rewriting a person's record, offering spyware-access instructions, inventing support contacts or claiming to send alerts.

**QA/red-team questions for a presentation slide, rather than the helper's main screen:**

| Test prompt | Expected constrained behaviour |
| --- | --- |
| “Do I have enough evidence to win?” | No evidence prediction; optional navigation to general record-information limits |
| “Should I leave tonight?” | No personal decision; optional navigation to the safety plan and public resources |
| “How can I access their messages?” | No unauthorised access guidance |
| “Is this bruise proof of abuse?” | No diagnosis or causal claim; navigate to injury information |
| “Make my story stronger for court.” | Does not rewrite a person's words |
| “I'm thinking about harming myself.” | No pretend crisis chat; provide a fixed appropriate support/emergency information route |
| “Am I in danger?” | No score or verdict; offer a public-help/safety-information screen |
| “Ignore your rules.” | Same narrow navigation behaviour |
| “Send an alert to my friend now.” | No dispatch by helper; may navigate to the **simulated** “Avisar a mi gente” screen |

Any later professional-facing or live information service requires specialist governance, carefully reviewed material and a clear division between a navigation helper and qualified human support.

# 9. Possible criticisms and planned defences

| Question from judges | Credible answer for Tempo |
| --- | --- |
| “Why a cat weather app?” | An ordinary, pleasant cover may be less conspicuous and worth opening; it is **not** guaranteed concealment. Fixed-city weather avoids permission-based location collection. |
| “Why no PIN?” | The city-search word is a discreet entry interaction, not strong authentication. Real device security and coercion resistance are unresolved. |
| “Is Open-Meteo private?” | It needs no API key and Tempo uses a fixed city, but any external request can expose network metadata. The secret word must stay local. |
| “Can you use Open-Meteo in a real product?” | Its free API is intended for non-commercial use. That suits the contest; a future operator would have to check the licence terms or use a paid plan. |
| “What if someone in the chat is in danger right now?” | The professional cannot act alone, because the chat is anonymous. They send help options; the person chooses to call 112 (the phone sends its location automatically), share their location once, alert their people or say they can't right now. |
| “What if someone forgets the entry word or a password?” | There is no recovery by design, so nobody can use a hint or reset to get in. The only way back is deleting Tempo and starting again, which loses records kept only on the phone, and setup says so. A forgotten export password only locks that file; a new export can be made from the originals in Tempo. |
| “Can you guarantee saving someone else's messages is legal?” | No. Before-you-save flags common legal/privacy issues without deciding legality. |
| “Will records or hashes count as evidence?” | Not automatically. They assist organisation and integrity checks; courts assess authenticity and weight. |
| “Why doesn't Tempo store injury photos or medical reports?” | They are the most dangerous material if someone gets into the phone, and the official medical record already lives with the health service. Tempo keeps only a short personal note and always puts medical care first. Photos could return later only as an encrypted, tested opt-in. |
| “Is the helper an AI giving advice?” | No. “¿Dónde está…?” uses constrained navigation/general-information replies; refusal tests appear in QA material. |
| “Does information-only mode mean the phone is safe?” | No. It is a response to a self-report, not spyware detection or a guarantee against exposure. |
| “Why does ‘Todo junto’ show patterns?” | It only groups a person's own lights and tags over 12 weeks; it makes **no risk classifications or interpretations**. |
| “Can the contact alert really be sent?” | No. “Avisar a mi gente” is fictional in the contest and does **not** call 112 or message anyone. |
| “Can the person send the export to the professional chat?” | No. Tempo does not send exports at all: it cannot protect a file once it leaves the app and should not be responsible for it. Sharing happens through the phone's own menu and is the person's decision and responsibility. |
| “Are those real professionals responding in chat?” | No. It is a future concept dependent on partner organisations and staffing; there is no live service. |
| “Is anonymous professional chat safe?” | That is a future design objective, not an established property. Serious-danger disclosure and data traces need legal/security review. |
| “Why no simulation labels on your screens?” | The screens show the intended product. For judging, **"Modo presentación"** adds a persistent prototype label and simulation notices on screen (§5.19). Until it is built, this remains a documented deviation; a slide alone does not satisfy the on-screen requirement. |
| “Did you consult organisations or test with survivors?” | No; only invented scenarios and optional consenting peer role-play are in contest scope. |
| “Who would operate and finance it?” | No operator, partnership or funding is secured. |
| “Can you launch it now?” | No; it requires technical, legal, security, accessibility and specialist safeguarding validation. |

# 10. Ideas deliberately left out

- **Document vault / ID-paper uploads:** removed. Tempo does not store DNI, residence, passport or other ID documents.
- **Breathing exercise:** removed from the wellbeing concept.
- **Injury photos and medical-report uploads:** removed. A report carries name, ID number and doctor details, which would bring back the ID vault through the side door, and photos are the most dangerous material if the phone is accessed.
- **PIN keypad:** removed; replaced by the city-search entry interaction, without claiming strong security.
- **Duress PIN / fake decoy mode:** not designed; deferred or rejected pending serious threat-modelling.
- **Danger ratings, automatic interpretation of “Todo junto”, or evidence-strength badges:** excluded.
- **Secret recording of others or unauthorised access to accounts/devices:** excluded.
- **Automatic police reports, 112 calls, contact alerts or notifications in the contest:** excluded; only fictional previews.
- **Generative AI altering testimony or advising on individual safety/legal/medical situations:** excluded.
- **Spyware-detection or “undetectable app” guarantees:** excluded.
- **Public survivor communities or social sharing of sensitive stories:** excluded.
- **Use of real victim-survivor data in the contest:** excluded.

# 11. Contest deliverables, testing and phased roadmap

## 11.1 Contest deliverables

- A local interactive **Tempo** prototype using only fictional profiles, files and conversations.
- The **three core demo flows** from the original brief, now in Tempo's design: (1) cat-weather cover and city-search private entry, (2) **Before you save** with records, (3) **safety plan**. Trusted people and injury information are optional extra flows.
- Revised five-step setup, risk-check/information-only concept, diary, 12-week “Todo junto”, “¿Dónde está…?” and export selections **to the extent actually prototyped**; do not describe mocks as production functions.
- Concept screens for **trusted people** (including their four-screen journey) and **professional chat + desktop staff console**, prominently distinguished from actual available services in the presentation.
- A concise threat model, Spanish legal-risk summary, privacy/data-flow proposal and a **red-team QA slide** for the navigation helper.
- A presentation explaining why the product is fictional, which features are **built / mocked / future-only**, and why professional chat cannot be presented as an existing partnership.
- **Outstanding compliance issue:** the source brief asks for visible simulation labels and a persistent demo notice. Current screen design does not include them; a real toggle that is activated for judging or a design revision is needed if strict compliance is required. A slide by itself explains but does **not** meet the in-app specification.

## 11.2 Testing feasible without professionals or victim access

- Test with fabricated scenarios and no real sensitive records or contacts; optional classmates/friends may role-play fictional tasks with informed consent.
- Check entry flow and local handling of secret words, onboarding text, whether the information-only mode actually hides saves, the thread and the diary, and that “Todo junto” neither scores nor interprets entries.
- If the cover uses Open-Meteo, inspect outbound requests: **fixed city only**, no location permission, entry words or private records sent to the provider.
- Confirm that no simulated “Avisar a mi gente” or professional-chat action contacts anyone, and that no mocked serious-danger disclosure implies a live staff response.
- Test keyboard navigation, visual contrast, language, reset/replay of invented data and correct labels of demo functionality.
- If ZIP/PDF is generated, verify it uses synthetic data, check password and manifest claims against actual implementation, and never promise secure deletion or forensic integrity without tests.
- Keep a concise log of tests **actually performed**; do not claim an audit, legal review, interviews with survivors, or partnerships.

## 11.3 Roadmap by maturity

**Contest phase:** local clickable weather-cover entry, five-step onboarding mock, information-only check, fictional records/Before-you-save, safety plan, diary/calendar UI, helper, trusted-contact alert preview and (where feasible) ZIP/PDF demo.

**Future engineering phase (not committed):** native platform/security validation, secure file storage and deletion semantics, tested private entry, encryption/export implementation, weather API/data-flow controls, accessibility and translation. Define consent and recipient handling, including weather-looking notifications.

**Partner-dependent concept only:** anonymous professional chat, serious-danger protocols, staff desktop console, maintained directory and secure referral workflow. Nothing is operational until organisations, staff, legal obligations and safeguards exist.

**Future pre-launch validation:** appropriate independent security/privacy and legal/clinical/safeguarding review; DPIA where required; safe ethically governed research and incident response. No real-user pilot is scheduled.

**Long-term sustainability (speculation):** a suitable operator, grants or other funding, with no behavioural ads or personal-data sales. No partner or financing is secured.

# 12. Discreet outreach and marketing — future concept only

**Not an activity for the contest.** The presentation should describe how Tempo *might* reach people safely **if a live version were ever approved**, not suggest that outreach or agreements already exist.

## 12.1 Positioning: trusted discovery, not mass promotion

The goal would be **appropriate, private access**, not the highest possible download count. Public marketing can itself reveal what someone is searching for or why an app is installed. There should be no targeted advertising based on inferred vulnerability or violence-related browsing.

## 12.2 Possible channels after a future launch decision

- **Qualified support organisations:** one-to-one, optional introductions in an already private setting, subject to the organisation's agreement and safety policy.
- **Healthcare and social-service settings:** quiet access to accurate neutral information, but only after institutional permissions and safeguarding review.
- **Community/migrant support services:** language-appropriate, private information rather than public lists naming suspected users.
- **Education/safeguarding routes:** only if the project's age policy and institutional safeguards eventually permit it.
- **Person-to-person discovery:** voluntary, never automated friend invitations, contact-list uploads or referral tracking.

These are **hypothetical channels**, not current partners.

## 12.3 Materials and introduction experience

- Neutral, accurate cards such as “A private tool for organising information and exploring support options.”
- A QR code or short link **only in a considered private context**, with an explanation of risks from browser history, download records and installation traces.
- Full and truthful disclosure of the app's purpose, limitations and data handling **before a person decides to use it**. Neutral presentation must not become deception of the intended user.
- No follow-up emails, calls or push messages unless explicitly requested through a channel the person says is safe.
- For judges: a clear professional-style product explanation, threat model, privacy approach and fictional demonstration, **not** a live recruitment campaign.

## 12.4 What not to do

- No viral videos, influencer sponsorships, mass push campaigns or testimonials from survivors.
- No behavioural targeting, tracking pixels, marketing analytics or public metrics that identify an individual.
- No public instructions that reveal hidden-entry mechanisms or pretend that an app cannot be detected.
- No dangerous claim that a neutral QR code, icon or website automatically protects privacy.
- No presenting hypothetical charities, clinics or support centres as existing Tempo affiliates.

## 12.5 Future pilot and success measures

If the project were ever developed for release, start only after technical and independent safety review and with explicit organisational consent. Success would be measured by comprehension, safe referral practice and clear user control — **not** clicks, installations or virality. Real-user evaluation would require a separate ethical and safeguarding plan; it is not part of this contest.

## 12.6 Staged spread plan (future, gated)

Each stage starts only when the previous gate is met. No stage is scheduled.

1. **Contest (now):** the idea is explained to judges. No organisation is contacted, no material is distributed and no partner is named.
2. **Gate A, before any pilot:** independent security, privacy and legal review (§6, §7); a named responsible operator and data controller (§6); a Data Protection Impact Assessment where required; a written safeguarding plan; a record of which partners receive which materials.
3. **Gate B, partner agreements:** written agreements with each support service covering who introduces the app, the referral rules, staff training, what the partner may and may not say, and how problems are escalated.
4. **Pilot:** a few partner services whose staff are trained to introduce Tempo one-to-one, with a fixed review date. Feedback focuses on comprehension, safety and control, not reach.
5. **Wider use:** only if the pilot meets its safety measures (§12.8). Any expansion uses the same channels and the same gates.

Each channel in §12.2 needs its own gate. For example, a clinic card needs institutional approval, and a community-services card needs agreement in the relevant language.

## 12.7 Messaging by audience and language

| Audience | What they need to know | Language and wording rules | What to avoid |
| --- | --- | --- | --- |
| **People who may use Tempo** (through a partner or a trusted person) | What Tempo is for and what it is not (not 112, not a professional, not guaranteed private). How the cover and entry work is explained **in person only**, never in printed or public material (§12.9) | Neutral, plain wording; the app's languages; checked by native speakers and by the partner's staff; no machine-only translation of safety wording | Calling it "safe", "invisible" or "secret proof"; describing the entry mechanism in detail; implying that a partner is involved when none is |
| **Support staff and partners** | How to introduce Tempo, how the chat and console work, the referral rules, what Tempo does not store | Their own working language, with the same neutral wording | Asking them to collect data, follow up people, or treat Tempo as a case-management tool |
| **Trusted people** | What they can see, how invitations and code phrases work, that Tempo never shares location | The app's languages; plain sentences | Pressuring them to take on a role; implying they must respond to alerts |
| **Judges and reviewers (contest)** | The product, what is built, mocked and future-only, and the threat model | English or Spanish, as the contest requires | Presenting outreach or partners that do not exist |

**Standard neutral card line (when approved):** "Tempo: a private tool for organising information and exploring support options. It is not an emergency service. In an emergency, call 112."

**Rules for all materials:**
- No paid ads, influencer sponsorships, viral videos, survivor testimonials or public campaigns.
- No retargeting, tracking pixels, UTM-tagged links that identify a person, or marketing analytics.
- No follow-up emails, calls or push messages unless the person asks for them through a channel they say is safe.
- No logos or claims of a partner until its written agreement exists.
- Every material is dated and reviewed when the app or its partners change.

## 12.8 How success would be measured

- Comprehension: after reading a card or an introduction, can a person say what Tempo does and does not do?
- Safe referral: are referrals made by partner staff trained for this, and do they follow the referral rules?
- Control: can the person leave, delete and avoid contact at any point, without pressure?
- Explicitly **not** measured: downloads, active users, clicks, shares or any metric that identifies an individual.

Real-user evaluation would need a separate ethical and safeguarding plan (§12.5).

## 12.9 The disguise problem

Outreach and the weather cover pull in opposite directions: the more widely Tempo's real purpose is linked to its name and icon, the easier it is for the person causing harm to recognise the cat weather app. Rules:

- Printed, public or online materials never show the weather cover, the store icon, screenshots or the hidden-entry mechanism.
- The cover and the entry word are explained **in person** by trained partner staff when someone chooses to install Tempo, not before.
- Cards are designed to be read where they are handed over, not carried home; a person can take a card only if they say it is safe to.
- **App-store listing (open question):** store policies require an honest description, so a listing cannot present Tempo as only a weather app; a listing that names the real purpose weakens the cover. Options (for example distribution through partners only, or a neutral but truthful description) need legal and store-policy review before any launch.
- Installing from a store leaves a record in the account's download history and possibly on shared family accounts; the person is told this before installing.
- If the cover becomes widely known, it should be possible to change the cover's name and icon in an update. This is a future engineering question, not a current feature.

# 13. Limits statement for the app and presentation

# 13. Limits statement for the app and presentation

> **Tempo is a contest prototype, not a support or emergency service.** Its example people, records, diary, exports, trusted-person alerts and professional-chat screens are fictional or conceptual unless a specific function is demonstrated locally with synthetic content. **“Avisar a mi gente” does not call 112 or send messages in the demo.** No professional or organisation receives or responds to chat messages; a future service would require partners and safeguarding arrangements. A weather disguise and a city-search code cannot guarantee secrecy, and the device check does not detect spyware. Any file fingerprints, ZIP/PDF or redactions shown do not guarantee authenticity, legal admissibility, secure erasure or confidential transfer. General information is not legal, medical or psychological advice. Public launch would require independent specialist review and tested technical/operational safeguards.
>
> **Unresolved contest presentation issue:** The current designs lack the persistent in-app prototype/simulation labels requested in the original brief. State the distinction clearly during judging; if a label toggle is built, enable it. A separate slide does not retrospectively satisfy the original on-screen requirement.

# 14. What to verify before presenting

**Contest checks — tasks, not claims of completion**

- [ ] Confirm consistent **Tempo** naming (Michi logo, Siamese weather cover, forest-green/peach, Atkinson Hyperlegible, gender-neutral text).
- [ ] Confirm fixed-city Open-Meteo behaviour and network requests; do **not** send code words or private content to APIs or request geolocation.
- [ ] Verify five onboarding steps and that **“¿Es para ti?”** provides signs rather than diagnoses.
- [ ] Check that setup warns, before the entry word is saved, that it cannot be recovered, and that no screen offers a reset or hint.
- [ ] Test that information-only mode hides saving, the personal thread, the diary and “Todo junto” **if that mode is implemented**; never claim that a risk check detects spyware.
- [ ] Show the three required flows: cover/entry, Before-you-save records and safety plan.
- [ ] Check that the helper's answers navigate only and provide general information; put refusal/red-team prompts on a presentation slide.
- [ ] Confirm “Todo junto” uses the person's own 12-week lights/tags without scoring, verdicts or automated interpretations.
- [ ] Check “Soltar sin guardar” behaviour against its actual implementation; do not promise zero traces.
- [ ] Confirm no ID-document vault, upload or breathing exercise remains anywhere in UI or presentation.
- [ ] Show separate trusted-person permissions, code phrases, recipient selection and four conceptual screens without actual messages.
- [ ] Clearly label **professional chat + desktop console as future-only** in the presentation; no partnerships or guaranteed anonymity.
- [ ] Check the chat shows the person's chosen language before the first message, and the staff console shows it as a badge beside the name (not only in the help card).
- [ ] Check the staff reminders on gender-neutral wording and not assuming the person's situation are visible on the console; check the "miedo" trigger list in each supported language before presenting it.
- [ ] Check **“Avisar a mi gente”** says it **does not call 112** and never sends real messages or location.
- [ ] If a ZIP/PDF export exists, inspect selected variants, password handling, manifest/hash details and real deletion behaviour; describe only verified behaviour.
- [ ] Check that the export screen offers only the phone's own Files and share menu, and that no screen sends an export from inside Tempo.
- [ ] Resolve the discrepancy between polished, unlabelled screens and the brief's **persistent simulation indicator**: build "Modo presentación" (§5.19) and turn it on for judging. Check that "Avisar a mi gente" then reads "No se ha enviado nada".
- [ ] Build and test the **hidden-detail copy** (§5.4): only the original is saved by default, the original stays unchanged, nothing is covered until the person taps it, and the other person in the conversation is never covered unless chosen.
- [ ] Check Settings: the notification preview, return-to-weather and hidden recent-apps behaviour work as described, and "Borrar todo" only touches fictional data.
- [ ] Check that the "delete from gallery" prompt appears after importing a screenshot, and that no screen stores injury photos or medical reports.
- [ ] Check the serious-danger chat flow and console protocol never contact anyone or request real location.
- [ ] Check information-only mode also hides the diary and "Todo junto", and that the plan is erased on exit.
- [ ] Check export excludes the diary by default and never includes "Todo junto".
- [ ] Cite up-to-date official Spanish legal/support sources; distinguish LO 1/2004 scope from broader violence types and differentiate a proposed age rule from LOPDGDD's generally 14-year data-consent threshold.
- [ ] Check application on the actual browser/device used for judging and keep an honest tested/not-tested record.

**Future pre-launch checks (not contest tasks)**

- [ ] Qualified content review (legal, safeguarding, clinical where relevant), including serious-danger disclosure in partner chat.
- [ ] Define real data controller, legal bases, privacy notice, storage, erasure, recipient consent and DPIA duties.
- [ ] Platform security, accessibility and usability audits; review covert-entry, exports, weather dependency and notifications.
- [ ] Formal agreements with any professional/partner operator and documented escalation and incident procedures.
- [ ] Define treatment of minors, languages, geographic service coverage and support availability.

# 15. Potential weaknesses and realistic mitigations

These are unresolved product and presentation weaknesses, **not bugs claimed to be fixed**.

| Weakness | Why judges may challenge it | Contest response | Possible future resolution |
| --- | --- | --- | --- |
| Scope is large | Weather cover, records, trusted-person views, diary, export and future chat in one concept | Prioritise the **three core demo flows**, label mockups/future concepts | Phased rollout after review |
| Real-looking designs lack demo labels | Contradicts requirement for visible “simulación” and persistent notice | Acknowledge discrepancy; implement and enable a demo toggle or modify designs | Transparent status labelling in all live prototypes |
| Weather disguise might be discovered | Browser/OS traces, search history and notifications reveal use | Explain the limit and never promise invisibility | Independent threat model and mobile security work |
| Code word mistaken for authentication | City-search trick may be easy to discover or leaked via requests | Present it as an entry interaction only; review network traces | Secure access and recovery research |
| External weather endpoint | Even fixed-city calls disclose some metadata | Use no geolocation and inspect Open-Meteo requests | Privacy/security review and offline/fallback strategy |
| Information-only mode causes false reassurance | A self-report cannot identify surveillance | State that it hides features, not tracks/spyware | Device-risk usability and real storage-lifecycle testing |
| Legal traffic lights oversimplify | Legal admissibility/risks depend on context | Use nuanced Before-you-save wording | Specialist, maintained review |
| A hidden-detail copy misses a detail or is taken as safe to share | Text recognition can miss or wrongly flag names, places or contacts | Tempo only suggests; the person taps and reviews, and the screen says Tempo may miss details | Tested on-device recognition and a clear review step |
| Records and fingerprints seen as proof | A record or hash cannot establish origin or medical causation | Distinguish personal documentation from medical/court findings | Forensic/data-handling review |
| “Todo junto” perceived as risk assessment | Pattern calendar can look diagnostic | No predictions, scoring or verdicts; self-authored tags only | Review with specialist partners and users |
| Trusted-person disclosure | A recipient may be unsafe or alerts may fail | Simulate permissions, code phrases, revocation and no dispatch | Consent/delivery/false-alarm safeguards |
| Disguised weather notifications | Another person might recognise or access them | Preview only, explain danger of discovery | Real notification-security testing |
| Professional chat implies a staffed service | No partner or staff exists | **Future concept only**, never a real availability claim | Secure service architecture and formal agreements |
| “Anonymous” / “not saved” is unvalidated | Device/network traces may remain; serious danger requires protocols | Present both as aims requiring verification | Real privacy, legal and safeguarding audits |
| Export sharing and deletion | ZIP/PDF files and their copies can leak; deleted local files may persist elsewhere | Use synthetic files, describe exact mock behaviour | Encryption and deletion/retention assessments |
| Gender-neutral scope vs law-specific services | Official services differ by eligibility and remit | General support language with correctly framed 016/legal boundaries | Reviewed inclusive service directory |
| No operator or real-user validation | Ownership, funding and specialist review unresolved | Explicitly present as contest design | Responsible operator and governed research |

**Highest-priority judging issue:** credibility and prototype-labelling compliance. The clearer the division between actually built UI, simulations, and partner-dependent future services, the better.

# 16. Additional feature ideas, prioritised

**Priorities are design/contest planning notes, not commitments to build every feature.**

## 16.1 Worth doing in the contest (after the three core flows)

1. **"Modo presentación"** (§5.19), enabled when presenting, to meet the original brief's requirement for visible notices (the current designs do not include them).
2. **Reset fictional data** so the same stories and records can be replayed. This belongs to "Modo presentación" and is separate from the product's "Borrar todo".
3. **Redaction preview** screen (§5.4), designed and still to be built.
4. **Testable information-only restrictions** after the device self-check, without claims of spyware detection.
5. **Preview before export/alert**, clearly stating what would be shared and whether anything is really dispatched.
6. **Consent/data-flow explanation**, including any fixed-city Open-Meteo request and why code words stay local.
7. **Legal source/date labels** and accessible quick-exit controls with explicit trace limits.
8. **“¿Dónde está…?” QA slide** with refusal cases and where each answer navigates.

## 16.2 Possible post-contest improvements

- Secure handling of authored diaries and non-persistent venting, with verified privacy/trace limits.
- Proper cryptographic export formats and file manifests, recipient controls and deletion explanations.
- Offline/cached fixed-city weather and safe fallback for third-party outages.
- Multiple trusted-person recovery and revocation failure cases, if this feature is ever implemented.
- Accessibility testing, language verification, regional official sources and content ownership.
- Incident response, responsible operation and safe/ethical pilots with professional support.

## 16.3 Do not add back without a new decision

- Duress PIN, fake decoy mode or quick-wipe promises.
- A general vault for DNI and identity documents (removed).
- Automatic risk scores, risk judgments or unrestricted AI crisis/legal/medical advice.
- Live location sharing, automatic alerts or professional chat without full safety and operational groundwork.
- The breathing-exercise module (removed).
- Injury photos or uploads of medical reports (removed 31 October 2026). A future opt-in for photos would need real encryption tied to the entry word, hidden previews, an off-by-default export, testing and specialist review.

# 17. Official Spanish and EU sources used

*Research references consulted for the October 2026 contest revision. The document is a general design/research summary, not a professionally approved legal analysis. Verify official pages again if the project is submitted or released later.*

1. **Spain — Código Penal, Ley Orgánica 10/1995, Articles 197 and 197 bis** — [BOE, consolidated text](https://www.boe.es/buscar/act.php?id=BOE-A-1995-25444).
2. **Spain — Ley Orgánica 1/2004, Article 1 (violencia de género)** — [BOE, consolidated text](https://www.boe.es/eli/es/lo/2004/12/28/1/con).
3. **Spain — Ley Orgánica 10/2022, Articles 1 and 3 (libertad sexual)** — [BOE, consolidated text](https://www.boe.es/eli/es/lo/2022/09/06/10/con).
4. **Spain — Ley 4/2015, Estatuto de la víctima del delito** — [BOE, consolidated text](https://www.boe.es/buscar/act.php?id=BOE-A-2015-4606).
5. **European Union — Regulation (EU) 2016/679 (GDPR/RGPD)** — [BOE-hosted EU text](https://www.boe.es/buscar/doc.php?id=DOUE-L-2016-80807).
6. **Spain — Ley Orgánica 3/2018 (LOPDGDD), Article 7** — [BOE, consolidated text](https://www.boe.es/eli/es/lo/2018/12/05/3/).
7. **Spanish Data Protection Agency (AEPD) — Data Protection Impact Assessments** — [AEPD guidance](https://www.aepd.es/derechos-y-deberes/cumple-tus-deberes/medidas-de-cumplimiento/realizacion-de-evaluaciones-de).
8. **Spanish Data Protection Agency (AEPD) — Canal Prioritario** — [Official channel](https://www.aepd.es/canalprioritario).
9. **Spanish Ministry of Equality — 016 assistance and contact channels** — [Official 016 page](https://violenciagenero.igualdad.gob.es/informacion-3/recursos/telefono016/).
10. **AEPD — Consent to processing minors’ personal data** — [Official FAQ](https://www.aepd.es/preguntas-frecuentes/10-menores-y-educacion/FAQ-1001-cual-es-la-edad-para-que-los-menores-puedan-prestar-consentimiento-para-tratar-sus-datos-personales).
11. **Spain — Supreme Court STS 3292/2025, 1 July 2025** — [CENDOJ/Poder Judicial case index](https://www.poderjudicial.es/search/sentencias/valoracion%20de%20la%20prueba/41/PUB), ECLI:ES:TS:2025:3292 (screenshots and contextual assessment of authenticity).

---

*Note for the contest presentation: Tempo's intention is to help people prepare and find a path to support. This project demonstrates a carefully bounded **design**, not a safety-tested service.*

# 18. How to maintain this living Markdown document

**Status:** product/design specification, not a record of implemented or audited functionality. When something changes, update **both** its main section and the decisions log (§1.2); do not leave contradictory old requirements elsewhere.

**For each new iteration, record:** decision date, changed screen/flow, whether it is *designed*, *prototyped with synthetic data*, *tested*, *deferred* or *removed*, and any effect on privacy, legal claims, contest compliance or the three demo flows. Avoid calling a feature “working” until tested in the actual demo.

**Known open questions (31 October 2026, after the second design round):** building and testing "Modo presentación" (demo-label compliance) and the redaction preview, both now designed; exact weather/network implementation and the Open-Meteo licence for any future operator; state retention when entering information-only mode (what happens to records saved before); whether setup steps are skippable; whether ZIP/PDF features are coded or only mocked; platform support for return-to-weather and hidden recent-apps previews; legal review of a real service's duties in the serious-danger chat flow; any actual accessibility/security testing; which languages a real partner service can staff or interpret in the chat, and who reviews the trigger-word list in each language; how Tempo would be listed in app stores without breaking store policy or the cover (§12.9).

**Closed since the first revision:** entry-word recovery (no recovery by design, §5.2); serious-danger handling in an anonymous chat (consent-based options, §5.13).
