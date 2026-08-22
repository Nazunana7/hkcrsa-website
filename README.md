# HKCRSA Website

Official website of the **Hong Kong China Radiation Safety Association (香港中國輻射安全協會)**.

🌐 Live site: [hkcrsa.org](https://hkcrsa.org) *(pending domain registration)*

---

## Overview

A single-page static website for HKCRSA, a professional association for medical physicists and radiation safety practitioners across Hong Kong and Mainland China.

**Built with:** Plain HTML + CSS + vanilla JavaScript — no frameworks, no build tools.

---

## File Structure

```
hkcrsa-website/
├── index.html                        # Main website (single page)
├── events/
│   ├── 2025-calibration-visit.html   # Sample event article (template)
│   ├── event-02.html                 # Placeholder
│   └── event-03.html                 # Placeholder
└── README.md
```

---

## Features

- **Trilingual** — English / 简体中文 / 繁體中文, switchable via top bar
- **Sections:** About · Focus Areas · Standards · Our Team · Recent Events · Contact
- **Responsive** — works on mobile and desktop
- **No dependencies** — no npm, no build step; open `index.html` directly in browser to preview

---

## Editing Content

All text content uses a `data-en` / `data-zh` / `data-tc` attribute system. To update any visible text, find the relevant element and edit all three language versions:

```html
<h2 data-en="English text"
    data-zh="简体中文"
    data-tc="繁體中文">
</h2>
```

### Common edits

| What to change | Where to find it |
|----------------|-----------------|
| Team member info | Search `<!-- TEAM -->` in `index.html` |
| Focus area descriptions | Search `<!-- FOCUS AREAS -->` |
| Contact email / address | Search `<!-- CONTACT -->` |
| Recent Events (news cards) | Search `<!-- RECENT EVENTS -->` |
| Adding a new event article | Copy `events/2025-calibration-visit.html`, fill in content |

### Adding a photo to an event card

In the news card, replace:
```html
<div class="ncard-img-ph">📷</div>
```
with:
```html
<img src="photos/your-photo.jpg" alt="Brief description">
```

---

## Deployment

Hosted on **Cloudflare Pages** (free tier).

**To deploy an update:**
1. Push changes to this repository (`main` branch)
2. Cloudflare Pages automatically rebuilds and deploys within ~1 minute

**Contact form:** Powered by [Formspree](https://formspree.io) — configure the endpoint in the `<form action="...">` tag inside `index.html`.

---

## Team

| Name | Role |
|------|------|
| Anson Cheung Ho-yin | Chairman & Founder |
| Andy Lai Yin Cheung | Honorary Secretary & Treasurer |
| Dr. Di Zhang | Vice Chairman |

---

## Status

- [x] Website v1 complete (trilingual, all sections)
- [x] Team info updated from CVs
- [ ] Real contact email configured (Formspree)
- [ ] Domain `hkcrsa.org` registered
- [ ] Constitution link added to footer (pending registration)
- [ ] Real event content added to Recent Events section
- [ ] Photos added

---

*Website built and maintained by the HKCRSA web team. For content questions, contact the Association at hkc.radsa@gmail.com*
