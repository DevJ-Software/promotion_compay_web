# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev        # start dev server (localhost:4321)
npm run build      # production build → dist/
npm run preview    # preview the built site locally
```

No linter or test suite is configured.

## Architecture

Single-page Astro 6 static site deployed to GitHub Pages at `https://DevJ-Software.github.io/promotion_compay_web/`.

**Key config:** `astro.config.mjs` sets `site` and `base: '/promotion_compay_web/'`. All internal asset URLs must use the `BASE_URL` prefix — see how `import.meta.env.BASE_URL` is used in `Welcome.astro` for image paths.

**File layout:**
- `src/layouts/Layout.astro` — HTML shell, all global CSS variables and utility classes (`.card`, `.btn`, `.chip`, `.container`, etc.), font import (Inter via Google Fonts)
- `src/components/Welcome.astro` — the entire landing page in one component: topbar, hero, sections (cómo funciona, apps, herramientas, features, planes, contacto, FAQ), footer + all scoped styles
- `public/images/compay/` — 13 screenshots referenced directly in `Welcome.astro`

**CSS approach:** Global utility classes defined in `Layout.astro` via `:global()`. Component-specific styles are scoped inside `<style>` in `Welcome.astro`. No CSS framework or preprocessor.

**No JavaScript** — the site is fully static with zero client-side JS. Responsive breakpoint at `980px` (media query in `Welcome.astro`).

**Content language:** Spanish (Cuban market focus). Keep all user-facing text in Spanish.
