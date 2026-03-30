# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Tyme Boxed marketing website — a static HTML/CSS/JS site for a physical NFC product that helps manage phone distractions. Deployed on Netlify.

## Development

- **No build step** — open HTML files directly or use VS Code Live Server (port 5502)
- **Deployment:** Netlify serves from root directory (`.`), configured in `netlify.toml`
- **Redirects:** `_redirects` file maps `/` → `/index.html`

## Architecture

Single-level static site with no frameworks or dependencies:

- **Pages:** `index.html` (landing), `science.html` (educational content with sticky sidebar), `quiz.html` (interactive PFC fatigue assessment), `preorder.html` (Shopify embed), `app.html`, `privacy.html`, `terms.html`, `support.html`
- **`style.css`** (~3500 lines) — Complete design system using CSS custom properties. Color palette is warm/natural (beige `#F5F0EB` backgrounds, gold `#C4933F` accents). Typography: DM Serif Display (headings) + Hanken Grotesk (body) via Google Fonts.
- **`script.js`** (~364 lines) — All interactivity: navbar scroll effects, mobile hamburger menu, scroll-reveal animations (Intersection Observer), FAQ accordion, quiz scoring logic.

## Key Patterns

- **Scroll reveals:** Elements with `.reveal` class animate in via Intersection Observer with staggered delays
- **Quiz system:** 4-step multi-select quiz with point-based scoring bucketed into High/Moderate/Mild PFC fatigue tiers, each showing different improvement percentages
- **Navbar:** Fixed with backdrop blur on scroll, shared across pages
- **Responsive:** Mobile-first with hamburger menu; flexbox/grid layouts
- **External integrations:** Shopify product embed for ordering, App Store links
