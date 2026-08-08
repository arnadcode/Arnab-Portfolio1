# Portfolio Website

A single-file, dependency-free portfolio website with an animated tech background, scroll reveals, and a one-click resume download.

## Core structure

- **HTML5** — single self-contained file, semantic tags (`<nav>`, `<header>`, `<section>`, `<footer>`)
- **CSS3** — no framework (no Bootstrap/Tailwind); hand-written with:
  - CSS custom properties (`:root` variables) for the color system, so the whole black/red palette is driven from one place
  - CSS Grid & Flexbox for layout (skills grid, cards, hero meta)
  - `@media` queries for responsiveness down to mobile
  - `prefers-reduced-motion` media query for accessibility (kills animation for users who've disabled motion)

## Fonts

- **Google Fonts** — IBM Plex Mono (headings, labels, technical/blueprint feel) + IBM Plex Sans (body text), loaded via `@import`

## JavaScript (vanilla — no libraries or frameworks)

- **Canvas API** — powers the animated tech background: particle nodes drifting across the screen, connecting lines drawn based on proximity, all recalculated every frame
- **`requestAnimationFrame`** — drives the animation loop efficiently (pauses automatically if reduced-motion is on)
- **Mouse event listeners** (`mousemove`/`mouseleave`) — make the particle network react to cursor position
- **`IntersectionObserver`** — powers the scroll-reveal effect (sections fade/slide in as you scroll to them)
- **`window.devicePixelRatio`** — used for canvas sharpness on high-DPI/retina screens

## Assets

- The resume PDF, copied alongside the HTML so the "Download Resume" button works via the native `download` attribute — no backend or server needed

## No dependencies, no build step

Everything runs from one `.html` file — you can open it directly in a browser or drop it onto any static host (GitHub Pages, Netlify, Vercel) with zero configuration, no `npm install`, no bundler.
