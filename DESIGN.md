---
version: alpha
name: Async Digital Demos
description: Satellite property of async-digital.com hosting product demos. Inherits the Async Digital brand. Tokens and voice rules come from the canonical DESIGN.md at async-digital-site.
---

> **Read the canonical brand spec first:** [`async-digital-ltd/async-digital-site/blob/main/DESIGN.md`](https://github.com/async-digital-ltd/async-digital-site/blob/main/DESIGN.md). The full token list (colours, typography, components, voice rules) lives there.

## What this property is

`demo.async-digital.com` is a tiny GitHub Pages site that hosts product demos. Two pages today: a landing page (`/`) listing available demos, and the Speed to Lead demo (`/speed-to-lead/`) that Helen sends to dental clinics.

## How it inherits the brand

Both pages load `https://async-digital.com/assets/brand.css` directly over HTTPS. That gives them the canonical colour, typography, line-height, and weight tokens without local copies. When the main site's brand changes, this property follows automatically.

`brand.js` is loaded the same way. There is no local `brand/` folder, no local `BRAND.md`, no local foundation docs.

## Local additions

What this property has that the main site doesn't:

- **Single-column landing layout** on `/` — vertically centred, no `.wrap` multi-section pattern. The page is a list of demo links with a fixed legal footer. Use the `.demos` and `.demos a` patterns rather than `.card` / `.grid`.
- **Flow-step pattern** on `/speed-to-lead/` — a horizontal three-step diagram (`.flow`, `.flow-step`, `.flow-icon`, `.flow-connector`). Brick-coloured connectors and icons. This is a deliberate demo-page visualisation; it does not exist on the main site and **should not** be repeated there.
- **Uppercase tracked section labels** (`.section-label`) on the demo subfolder. Unusual for the brand but kept for the marketing-page idiom of demos. The main site uses sentence-case `<h2>` with the bar-stack accent instead.

## What stays out

The main site's voice rules and colour palette apply identically here. Specifically:

- **No em dashes anywhere**, including page titles, meta descriptions, Open Graph titles and descriptions, and Twitter Card titles and descriptions. Em dashes in meta tags appear in link previews and are the strongest LLM-generated tell.
- **No cyan, blue, or non-brand accent colours.** Earlier versions of these pages used a cyan accent palette (`#0aa5ff`, `#0077ff`); that has been removed. Anything that needs to draw attention uses `var(--primary)`.
- **No animation theatre** — pulsing dots, breathing gradients, glowing CTA backgrounds. The brand reads as calm and clinical-adjacent. An earlier version had a pulsing connector dot and a radial-gradient glow on the CTA section; both have been removed.
- **No black buttons.** The CTA button background is `var(--primary)`, not `#111` or `#000`.

## Updates

When `assets/brand.css` changes on the main site, this property picks it up on the next page load. Nothing to update here unless:

- A local layout pattern (flow-step, section-label, demos list) needs to change.
- A new voice rule lands in `brand/voice.md` on the main site that this file's "What stays out" section should mirror.
- A new demo subfolder is added — it should load `https://async-digital.com/assets/brand.css` as its first stylesheet, then any local `styles.css`.
