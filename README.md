# KYN Family Pharmacy website

**Know Your Numbers. Own Your Health.** · www.kynpharmacy.com

A single-page website for KYN Family Pharmacy. It includes the KYN Health Passport, the Nurse Doris virtual assistant, prescriptions by WhatsApp or email, alerts sign-up, a weekly health tip and accessibility features.

## What's in this folder
| File | Purpose |
|---|---|
| `index.html` | The whole website: HTML, CSS and JavaScript in one file |
| `docs/mockups/` | Windows, phone and braille Passport card mockups |

## Deploying
This is a static site, so it needs no PHP, Python or database. Upload `index.html` to any web host, for example:
- **cPanel or shared hosting:** upload to `public_html/`.
- **GitHub Pages:** go to Settings → Pages → Deploy from branch → `main` / root.
- **Netlify or Cloudflare Pages:** drag and drop the folder.

Then point the domain `kynpharmacy.com` at the host and turn on HTTPS.

## Settings to confirm before launch
Find these at the top of the `<script>` in `index.html`:
- `PHONE = '12462300322'` is used for WhatsApp links.
- `EMAIL = 'rx@kynpharmacy.com'` is a **placeholder**. Change it to the real address.

Also confirm opening hours and the services list.

## Features
- **Prescriptions:** WhatsApp or email message builder, with parish dropdown and the delivery fee shown ($15 BBD for Passport holders, $20 BBD for others).
- **KYN Health Passport:** why you need it, benefits, how it works, a sample record, the price ($94.20 BBD per year) and a "Check your numbers" tool.
- **Nurse Doris:** built-in answers on about 30 topics, voice input where the browser supports it, and an optional AI connection (see below).
- **Weekly health tip:** a pop-up that rotates through 26 tips each ISO week.
- **Accessibility:**
  - Easy view for low vision (press E)
  - optional read-aloud, text size, high contrast, easy-read spacing and stopping animations
  - screen-reader and braille-display friendly
  - keyboard shortcuts 1 to 6
- **Menus:** drop-down menus that fill in from data, plus site search.
- **Alerts:** opt-in by WhatsApp or email.

## Limitations of the static version
- Alerts and prescription forms open WhatsApp or email with a pre-written message. Nothing is stored on a server.
- Nurse Doris uses her built-in answers. Free-form AI answers need a small back end (see below).
- Read-aloud and voice input use the browser's own speech features.

## Recommended back end (phase 2)
| Need | Suggested |
|---|---|
| Store alert opt-ins with double opt-in | Python (FastAPI) + PostgreSQL, or PHP (Laravel) + MySQL |
| WhatsApp Business API messages and reminders | Python service using Meta Cloud API |
| Nurse Doris AI answers | Python endpoint calling the Anthropic API; keep the API key on the server |
| Passport records (sensitive health data) | Python + PostgreSQL with encryption, audit log and consent records, compliant with the Barbados Data Protection Act 2019 and GDPR |

## Disclaimer
Content is general health information and not a substitute for professional medical advice. Prescriptions are dispensed only against a valid prescription after review by a registered pharmacist.
