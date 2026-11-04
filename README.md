# RN Command Pro — AI Copilot Edition

**An AI copilot for home-health nurses: dictate the visit, review the chart.**

*Built for the Meta AI Developer Hackathon (Cerebral Valley) — Indie track, theme "Build for Your World."*

## What it is

Home-health nurses work alone in patients' homes — no charge nurse down the hall, no IT department, often no reliable signal — and then spend their evenings finishing the documentation (OASIS-E2 assessments, visit notes) that determines whether their agency gets paid and their patients stay safe.

RN Command Pro — AI Copilot Edition extends **RN Command Pro**, an already-shipped, selling app for field nurses, with one well-scoped AI layer:

- **Voice-to-charting (the flagship).** The app captures the visit by voice and transcribes it **100% on-device with Whisper** — the audio never leaves the nurse's device. The Copilot layer adds the structuring step: the transcript is shaped into a clean, OASIS-E2-aligned draft note that the nurse reviews, edits, and approves. Nothing is ever auto-filed; the nurse is always the last set of eyes. An on-device check then verifies every drafted value against the nurse's own words before review.
- **"For the Nurse" affirmations.** The Copilot tab opens with a card of twelve short affirmations drawn from the builder's own devotional book for nurses, *Refreshed for the Calling: 365 Days of Inspiration, Poems, and Scripture for Nurses* — lines for charting fatigue, the visit nobody saw, the shift that asks more than you have. (Full set and sourcing: [rn-affirmations.md](rn-affirmations.md).)
- **The shipped base around it:** clinical documentation templates (SBAR, handoff, psych/mental status), 8 clinical calculators with dual verification on high-risk math, GCS / burn Rule of 9s / ACLS rapid reference, consent-gated telehealth, OASIS-E2 and hospice HOPE modules, six specialty add-ons, and a 10-language interface including Arabic RTL.

## How to test it

**Live app (GitHub Pages):** https://tinglott.github.io/rn-command-pro-copilot/

1. **Open the live URL above** in a desktop browser (Chrome recommended — the on-device Whisper model downloads from a CDN on first use and needs a network connection once).
2. **Transcribe tab — no key needed.** Record or play a short visit dictation (fictional patient, initials only). Transcription runs entirely in your browser via Whisper (Transformers.js); no audio is uploaded anywhere.
3. **Copilot tab — bring your own key.** Send the transcript to the Copilot panel and paste **your own Groq or OpenRouter API key** into the panel's key field. The panel structures the transcript into an OASIS-E2-aligned draft (demonstrated live on Groq, `openai/gpt-oss-120b`; OpenRouter works the same way), then an on-device pass checks every drafted value against the transcript and flags anything not addressed. **Use a test key with no patient data — fictional dictation only.**
   - The build also includes an endpoint slot for the Meta Model API (Muse Spark). That slot is **unverified, and no Meta integration is claimed** — it is present so the same BYO-key panel can be pointed at Meta's endpoint.
4. **"For the Nurse" card — no key needed.** In the Copilot tab, use the "Another one" button to rotate through the 12 affirmation cards.

No backend, no account, nothing to install: the whole app is this repo's `index.html` plus its bundled Whisper worker (`assets/voice-whisper.js`).

## Privacy, by design

- Patient **initials only** — the app is built so real identifiers are never needed.
- Transcription is on-device; all app data lives in the browser's on-device storage.
- The only data that ever leaves the device is the transcript text a nurse deliberately sends to the AI provider **under her own API key**, for structuring — and the draft always comes back to the nurse for review and approval before any use.

## Builder

**Ting Lott, RN** — psychiatric nurse of 17 years, RN Supervisor in home care, solo founder of T. Lott Creative / ARTISY, building with AI engineering assistance.

## The shipped product

This hackathon edition is a separate build of a product that already sells:

- **RN Command Pro on Gumroad ($29.99):** https://tlott12.gumroad.com/l/gtanuu
