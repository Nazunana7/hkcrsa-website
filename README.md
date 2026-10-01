# HKCRSA Website

Official website of the **Hong Kong China Radiation Safety Association (香港中國輻射安全協會)**.

[![Static Site](https://img.shields.io/badge/site-static-1e91c7.svg)](#file-structure)
[![No Build Step](https://img.shields.io/badge/build-none-1aaa6e.svg)](#editing-content)
[![Languages](https://img.shields.io/badge/languages-EN%20%7C%20%E7%AE%80%20%7C%20%E7%B9%81-c8860a.svg)](#features)
[![Hosted on Cloudflare Pages](https://img.shields.io/badge/host-Cloudflare%20Pages-F38020?logo=cloudflare&logoColor=white)](#deployment)

🌐 Live site: [hkcrsa.org](https://hkcrsa.org) *(pending domain registration)*

---

## Overview

A single-page static website for HKCRSA, a professional association for medical physicists and radiation safety practitioners across Hong Kong and Mainland China.

**Built with:** plain HTML + CSS + vanilla JavaScript — no frameworks, no build tools, no dependencies.

> **Related repository:** [`hkcrsa-register`](https://github.com/Nazunana7/hkcrsa-register) is a **reduced copy of this site**, prepared for the Association's Hong Kong government registration submission. It is not a duplicate to be merged or deleted — it will be archived once registration completes. **Develop here, not there.**

---

## File Structure

All site files live in the `hkcrsa-website/` directory:

```
hkcrsa-website/
├── index.html                          # Main site (single page, all sections)
├── constitution.html                   # Association constitution
├── privacy-policy.html                 # Privacy policy
└── events/
    └── 2025-calibration-visit.html     # Sample event article (template)
```

Every page is self-contained: styles are inlined in a `<style>` block, and language switching is handled by a small inline script.

---

## Features

- **Trilingual** — English / 简体中文 / 繁體中文， switchable via the top bar
- **Sections:** About · Focus Areas · Standards · Our Team · Membership · Recent Events · Contact
- **Responsive** — works on mobile and desktop
- **No dependencies** — no npm, no build step; open `hkcrsa-website/index.html` directly in a browser to preview
- **Fonts** via Google Fonts (Source Serif 4 / Source Sans 3 / Noto Sans + Serif SC & TC)

---

## Editing Content

All text content uses a `data-en` / `data-zh` / `data-tc` attribute system. To update any visible text, edit all three language versions on the same element:

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
| Focus area descriptions | Search `<!-- FOCUS AREAS -->` in `index.html` |
| Contact email / address | Search `<!-- CONTACT -->` in `index.html` |
| Recent events (news cards) | Search `<!-- RECENT EVENTS -->` in `index.html` |
| Standards section | Search `<!-- STANDARDS -->` in `index.html` |
| Adding a new event article | Copy `events/2025-calibration-visit.html` and fill in the content |

### Adding a photo to an event card

In the news card, replace:

```html
<div class="ncard-img-ph">📷</div>
```

with:

```html
<img src="photos/your-photo.jpg" alt="Brief description">
```

### ⚠️ About the inline images

`index.html` currently embeds **3 JPEG images as base64 data URIs**, which account for roughly **436 KB of the file's ~500 KB**. Before adding more imagery, prefer moving photos into a `photos/` folder and referencing them normally:

```html
<img src="photos/hero.jpg" alt="…">
```

This keeps the HTML small, makes the browser cache images separately, and lets you swap a photo without editing a 500 KB file.

---

## Deployment

Hosted on **Cloudflare Pages** (free tier). No `CNAME` file is needed.

**To deploy an update:**

1. Push changes to this repository (`main` branch)
2. Cloudflare Pages automatically rebuilds and deploys within about 1 minute

**Contact:** the site uses direct `mailto:` links (`info@hkcrsa.org` and `hkc.radsa@gmail.com`). There is no contact form backend or third-party form service wired up yet.

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
- [x] Constitution and privacy policy pages published
- [ ] Real contact email configured
- [ ] Domain `hkcrsa.org` registered
- [ ] Real event content added to Recent Events section
- [ ] Event photos added (and inline base64 images moved to `photos/`)
- [ ] License decided (site content belongs to the Association)

---

*Website built and maintained by the HKCRSA web team. For content questions, contact the Association at hkc.radsa@gmail.com*
