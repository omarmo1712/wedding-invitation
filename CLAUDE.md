# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A static single-page wedding invitation template. No build step, no package manager, no test suite — open `index.html` directly in a browser or deploy via Netlify.

## Architecture

All content lives in a single `index.html`. Customization means editing inline text and placeholder values throughout that file.

**Key customization points in `index.html`:**
- `<title>` and Open Graph `<meta>` tags — couple names, date, venue
- Hero section — names, date, venue city
- Countdown script (inline `<script>` around line 129) — `harih` variable holds the target datetime in `MM/DD/YYYY HH:MM:SS` format; `offset` is the UTC offset
- Waktu section — ceremony/reception times and date display
- Google Calendar button `href` — pre-filled calendar event URL
- Lokasi section — venue name, address, embedded Google Maps `<iframe>` src, and Google Maps directions link
- Tentang section — photo captions (`.foto1`–`.foto6` tiles)
- RSVP section — WhatsApp API links with phone numbers and message text, Instagram handles

**Styling:**
- `css/menikah.css` — all custom styles; uses dusty-pink palette (`#996E6D`, `#BC8887`, `#D8A9A8`, `#EDD2D1`, `#F4E2E2`)
- `css/jquery.countdown.css` — countdown widget styles
- Bulma 0.8.x loaded from CDN for layout

**JavaScript:**
- `js/menikah.js` — Bulma mobile nav toggle, smooth scroll, scroll-to-top button, preloader fade
- `js/jquery.coundown.js` — countdown timer plugin (jQuery-based)
- AOS (Animate On Scroll) loaded from CDN for `data-aos="fade-up"` entrance animations

**Photos:**
- Couple/story photos referenced as CSS `background-image` in `.foto1`–`.foto6` classes in `menikah.css`
- Replace the `url(../image/...)` paths in those classes to swap photos

**Deployment:** Netlify (drag-and-drop or Git integration). No build command needed.
