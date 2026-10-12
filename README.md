# uhb217 - Personal Website

Personal portfolio website for **uhb217** — 18-year-old hobbyist developer building Android apps and Python tools.

## Live Site

**https://uhb217.github.io/personal-site/**

## Tech Stack

- **Framework:** Svelte 5 + Vite
- **Styling:** Vanilla CSS with Expo design system tokens
- **Fonts:** Inter (display/body) + JetBrains Mono (code)
- **Deployment:** GitHub Pages via `gh-pages` branch

## Features

- Dark/light mode toggle with localStorage persistence & system preference detection
- Fixed top navigation with smooth-scroll anchor links
- Hero section with sky-blue gradient atmospheric wash + device mockup (MacBook code + phone with PlayerTracker compass)
- About section with GitHub profile picture, bio, and badges
- Skills tags (Kotlin, Java, Python, JavaScript, Android, Svelte)
- Featured projects: PlayerTracker (Java), Airdrop (Python), chess0.2 (Java)
- CTA band + footer with project links
- Fully responsive (1024px / 768px / 640px breakpoints)
- Accessibility: ARIA labels, focus-visible, semantic HTML, reduced motion support

## Design System

Based on the **Expo design system** — pure white canvas, black primary CTAs (8px radius), blue inline links only, Inter 600/400, JetBrains Mono, 96px section rhythm, hairline borders, soft shadows.

## Development

```bash
# Install dependencies
npm install

# Start dev server (http://localhost:5173)
npm run dev

# Production build (outputs to dist/)
npm run build

# Preview production build
npm run preview
```

## Deploy

```bash
# Build and push to gh-pages branch
npm run build && npx gh-pages -d dist --branch gh-pages
```

GitHub Pages is configured to serve from the `gh-pages` branch at `/personal-site/` (set via `base` in `vite.config.js`).

## Project Structure

```
personal-site/
├── src/
│   ├── App.svelte      # Single-file component with all sections + styles
│   ├── main.js         # Entry point
│   └── app.css         # Global base styles (minimal)
├── index.html          # HTML template with font preconnect + meta
├── public/favicon.svg  # Custom "u" favicon
├── vite.config.js      # Vite config with base path
└── package.json
```

## License

MIT — feel free to use as a template for your own site.