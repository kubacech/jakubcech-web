# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal website for Jakub Čech (jakubcech.cz) — a static site built with Astro 5, using a terminal/code-editor aesthetic with Fira Code monospace font and a dark color palette.

## Commands

- `npm run dev` — Start dev server
- `npm run build` — Type-check with `astro check`, then build to `dist/`
- `npm run preview` — Preview the production build locally
- `npm run check` — Run TypeScript/Astro type checking only

## Architecture

This is a minimal Astro site with no UI framework (no React/Vue/Svelte). Pages are pure `.astro` components.

- `src/layouts/BaseLayout.astro` — Single layout containing the full HTML shell (head, header, nav, footer) and **all global CSS** (defined in a `<style is:global>` block at the bottom of the file)
- `src/pages/index.astro` — The only page; a single-page personal site with hero, focus areas, and about sections
- `public/` — Static assets (favicon, Fira Code font)
- `astro.config.mjs` — Configures the site URL (`https://jakubcech.cz`) and the sitemap integration

## Styling Conventions

All styles live in `BaseLayout.astro` as global CSS. The design uses CSS custom properties defined in `:root`:
- `--background`, `--foreground`, `--accent`, `--secondary`, `--muted` for the color scheme
- `--border`, `--border-subtle`, `--code-bg` for structural elements
- `--font` and `--max-width` for typography and layout
- BEM-style class naming (e.g., `.header__title`, `.focus-card__desc`, `.btn--ghost`)

## TypeScript

Strict mode via `astro/tsconfigs/strict`. Component props use Astro's `interface Props` pattern in the frontmatter.
