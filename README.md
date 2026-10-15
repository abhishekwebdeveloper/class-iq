# ClassIQ

A responsive landing page for an online learning platform, built from a Figma design with **Tailwind CSS v4** and **Vite**.

Pages: `index.html` (home), `login.html`, `signup.html`.

## Getting started

Requires [Node.js](https://nodejs.org/) 18 or newer.

```bash
# 1. Install dependencies
npm install

# 2. Start the dev server (opens at http://localhost:5173)
npm run dev

# 3. Create a production build in /dist
npm run build

# 4. (Optional) Preview the production build locally
npm run preview
```

To open the built site without a server, run `npm run build` and open `dist/index.html` in a browser.

## Tech stack

| Tool | Purpose |
| --- | --- |
| [Vite](https://vite.dev/) | Dev server and production bundler (`vite.config.ts`) |
| [Tailwind CSS v4](https://tailwindcss.com/) | Utility-first styling, configured in CSS with `@theme` (no `tailwind.config.js`) |
| Google Fonts | Poppins and Inter |

## Project structure

```
src/
  css/
    base/          Tailwind theme tokens and base styles (tailwind.css)
    components/    Reusable component classes (ap-button, ap-container, ...)
    index.css      CSS entry point
  img/             SVG icons and images
  js/              Page scripts
  main.js          JS entry point
index.html
login.html
signup.html
vite.config.ts
```

## Design tokens (`src/css/base/tailwind.css`)

- **Breakpoints:** `md` 768px, `lg` 1280px, `xl` 1366px, `2xl` 1640px. These are custom values, not Tailwind's defaults.
- **Colors:** `ap-gray-400` to `ap-gray-800`, `ap-lime-400`, `ap-neutral-100`, `ap-slate-300` to `ap-slate-500`.
- **Fonts:** `font-inter`, `font-poppins`.
- **Shadow:** `shadow-ap-card`.

## Conventions and shortcuts

- **`ap-` prefix** is used for custom component and theme names (`ap-container`, `ap-button`, `ap-title`, `ap-about__item`, ...), with BEM-style `__` elements. This keeps them separate from Tailwind's own utilities.
- **Mobile-first:** base styles are for phones, with larger breakpoints layered on top.
- **Theme variables:** colors, fonts and shadows are defined once in `@theme`, so Tailwind generates utilities like `bg-ap-lime-400` and `text-ap-gray-700` automatically.
- **SVG icons** are used as images or CSS masks (`mask-image-*` utilities), so their color can follow the theme.
- **Tailwind v4 shorthands:** spacing and sizing accept any number (`w-137`, `gap-26`), and aspect ratios can be written inline (`aspect-548/517`).
