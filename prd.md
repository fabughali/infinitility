# Product Requirements Document: Infinitility Website

**Version:** 2.2.0 · **Date:** 2026-11-19 · **Owner:** Infinitility Tech Ltd
**Live:** https://fabughali.github.io/infinitility/ · **Repo:** https://github.com/fabughali/infinitility

## 1. Purpose
Infinitility's public website presents the company as a premium, all-in-one digital partner. It turns visitors (small and mid-sized businesses in the Arabic-speaking market and beyond) into leads through a memorable, bilingual experience.

## 2. Goals
1. Communicate the full service range clearly within 10 seconds.
2. Feel unique and premium: a signature "Phoenix ∞" motion identity, not a template.
3. Give Arabic-speaking visitors a first-class experience (RTL by default), with English equal in quality.
4. Make contact effortless: a contact form, phone, WhatsApp and e-mail on every page.

### Non-goals (this version)
- Client login or a hosting control panel (planned next)
- E-commerce or online payments
- Adding or removing portfolio, team or article items from the admin panel (existing items are editable)

## 3. Audience
- Business owners looking for hosting, a website, an app or marketing
- Companies wanting AI, API or cloud work
- Arabic-first visitors, with English for regional and international clients

## 4. Functional requirements
| ID | Requirement |
|---|---|
| F1 | Pages: Home, About, Services, Service detail (×8), Work, Insights, Contact, and a 404 page |
| F2 | Services: Hosting & Domains, Development, Design, Marketing, AI, Social Media, APIs, Cloud |
| F3 | Language switch AR ⇄ EN anywhere. Arabic is the default and right-to-left. |
| F4 | Clean, shareable URLs for every page (e.g. `/services/ai`), including deep links |
| F5 | Contact form with validation, spam protection (honeypot) and rate limiting; messages are stored and read in the admin inbox. Demo mode when no backend is connected. |
| F6 | Quick-contact buttons (WhatsApp, call) and a call-to-action band on every page |
| F7 | Animated ∞ loading screen until the app's first frame |
| F8 | **Admin panel** (`/admin`, done in 2.1.0): staff sign-in with 2-step verification; roles (support, editor, admin) |
| F9 | **Content editing** (done): every text in Arabic and English, article and team photos, contact details and home-page numbers; draft → preview → publish, with full version history and restore |
| F10 | **Messages inbox** (done): contact-form messages with unread filter, mark read/unread, one-tap e-mail, call and WhatsApp |
| F11 | **Always on** (done): if the backend is slow or unreachable, visitors get the built-in content within 3 seconds |
| F12 | **Admin by service** (done in 2.2.0): menu grouped as Overview, Website, Services (one section per service), Business and System. Each service lists what is managed there, and unbuilt parts are marked "Coming soon". |
| F13 | **Section permissions** (done): admins grant each staff member only the sections they need, invite people by e-mail, and the panel always keeps at least one admin |
| F14 | **Integrations without hardcoded keys** (done): every API key and setting is entered in Admin → Settings → Integrations, stored encrypted, can never be read back, and can be checked with "Test connection" |

## 5. Experience and motion requirements
| ID | Requirement |
|---|---|
| M1 | Hero: a self-drawing infinity (lemniscate) with flowing particles, star field and mouse parallax |
| M2 | Header figure-eight wave, scroll reveals, count-up stats, rotating headline word, technology marquee, service-card border trace, process line draw |
| M3 | Every animation honours "reduce motion" |
| M4 | Endless loops pause when off screen or when the tab is hidden |
| M5 | Responsive breakpoints at 600, 900 and 1100 px. No horizontal scroll on phones. |

## 6. Visual identity
- Palette: deep navy `#0A0F2C`, brand indigo `#1F2A7A`, ember `#FF7A3D` → `#FFB547`, cyan `#38D5F5`
- Typeface: Readex Pro (Arabic and Latin), 400–700, bundled locally

## 7. Technical
- Flutter web (Dart 3), go_router, flutter_localizations/ARB, url_launcher, visibility_detector, supabase_flutter, qr_flutter
- Supabase: Auth (with TOTP 2-step), Postgres with row-level security, Storage for images
- Static hosting on GitHub Pages under `/infinitility/`
- Automated tests: geometry, navigation and locale, contact form, content overrides and fallback, admin guard, editors, publish/preview, inbox, sections, staff, integrations (108 app tests + 8 server-function tests)

## 8. Open items before public launch
- Connect the Supabase project and create the first admin account
- Real phone, WhatsApp, e-mail, statistics, team members and articles (now set from the admin panel)
- Real portfolio projects
- Custom domain (optional)

## 9. Success metrics
- Contact-form submissions and WhatsApp clicks per month
- Bounce rate on Home below 50%
- Lighthouse accessibility score of 90 or higher
