# Copilot Instructions

## Project Overview

This is a personal portfolio site for Mantas (Software Engineer & Creative Developer), deployed via GitHub Pages. It is a single-page static website using only HTML and CSS — no JavaScript frameworks or build tools are required.

## Tech Stack

- **Semantic HTML5** — single `index.html` file
- **Modern CSS** — all styles are embedded in `<style>` inside `index.html`
  - CSS Custom Properties (variables)
  - OKLCH color system
  - CSS Grid and Flexbox for layout
  - `clamp()` for fluid typography and spacing
  - Container queries where appropriate
- **Google Fonts** — Playfair Display (headings/display) and Urbanist (body)
- **No JavaScript frameworks or build steps** — progressive enhancement only

## Design Principles

This site follows the [pbakaus/impeccable](https://github.com/pbakaus/impeccable) frontend-design skill principles:

### Colors
- Use **OKLCH** for all colors (e.g. `oklch(75% 0.18 85)`)
- Palette uses warm-toned neutrals with a golden accent
- **Never use pure black (`#000`) or pure white (`#fff`)**
- Avoid generic blue/gray color schemes

### Typography
- Display headings: `Playfair Display`, serif, weight 700–900
- Body / UI text: `Urbanist`, sans-serif, weight 300–600
- **Never use generic fonts** like Inter, Roboto, or Arial
- All font sizes use `clamp()` for fluid scaling across screen sizes

### Layout & Aesthetics
- Art deco geometric aesthetic with intentional visual rhythm
- Asymmetric layout — **avoid centered-everything layouts**
- Geometric decorative accents (circles, lines) as background elements
- **No glassmorphism** (backdrop-filter blur cards)
- **No nested cards** — keep layout hierarchy flat and direct
- Use purposeful whitespace and fluid spacing via CSS custom properties

### Animation
- Exponential/quint easing: `cubic-bezier(0.22, 1, 0.36, 1)` or `cubic-bezier(0.16, 1, 0.3, 1)`
- Always include `@media (prefers-reduced-motion: reduce)` overrides
- Slow decorative animations (rotate-slow: 45–60s) for background elements

## CSS Conventions

- All design tokens are defined as CSS custom properties in `:root`
- Spacing scale: `--space-xs`, `--space-sm`, `--space-md`, `--space-lg`, `--space-xl`, `--space-2xl`
- Typography scale: `--text-xs` through `--text-3xl`
- Color tokens: `--color-base`, `--color-surface`, `--color-elevated`, `--color-text-primary`, `--color-text-secondary`, `--color-accent`, `--color-accent-vivid`, `--color-border`
- Use existing tokens rather than hardcoding values

## Accessibility

- WCAG 2.1 compliant — maintain sufficient color contrast
- Support keyboard navigation (`:focus-visible` styles)
- Include `aria-label` / `aria-hidden` where appropriate
- All interactive elements must be reachable via keyboard

## Deployment

The site deploys automatically to GitHub Pages on every push to `main` via the workflow in `.github/workflows/deploy.yml`. No build step is required — the entire repository root is uploaded as the Pages artifact.

## What to Avoid

- Do **not** introduce JavaScript frameworks (React, Vue, etc.) or npm dependencies
- Do **not** add a build pipeline unless explicitly requested
- Do **not** use generic "AI-aesthetic" design patterns (glassmorphism, gradient blobs, inter font, excessive shadows)
- Do **not** use pure `#000` or `#fff` — use the OKLCH-based color tokens
- Do **not** center every element — respect the asymmetric layout intent
