# Shahid Aman — Minimal Portfolio (Astro)

A single‑page, minimalist portfolio inspired by the simplicity of davis7.sh.

- Built with Astro (no JS frameworks, no extra dependencies)
- Monospace-first typography, subtle grid/baseline, soft radial gradients
- Data-driven from `src/data/cv.ts`
- One page only: `src/pages/index.astro`

## Quick start

```bash
npm install
npm run dev
```

- Dev server: http://localhost:4321
- Production build: `npm run build` (outputs to `dist/`)
- Preview production build: `npm run preview`

## Project structure

```text
/
├── public/
│   └── assets/
│       └── cv.pdf           # Place your resume here (optional)
├── src/
│   ├── data/
│   │   └── cv.ts            # Profile, links, projects, skills
│   └── pages/
│       └── index.astro      # Minimal single-page site
├── package.json
└── README.md
```

## Customize

Most content and links are driven by `src/data/cv.ts`.

- profile.name, location, email, github, linkedin
- profile.projects[] (name, url, description)
- profile.skills (languages, frontend, backend, databases, tools, others)

Header + nav

- Email, GitHub, LinkedIn are rendered from your `cv.ts` links
- CV link points to `/assets/cv.pdf` and triggers a download (`download="Shahid_Aman.pdf"`)
  - To enable: place your file at `public/assets/cv.pdf`

Design knobs (in `src/pages/index.astro`)

- Typography: monospace by default (body). Change the `font` declaration on `body { ... }`
- Lowercase heading: `header h1 { text-transform: lowercase; }`
- Gradient heading: tweak the color stops in `linear-gradient(90deg, ...)`
- Subtle grid/baseline: adjust `--grid` variable and the `body::before` overlay
- Section label: “Stuffs I’ve built” can be renamed in the Projects section header

## Scripts

| Command           | Description                          |
| ----------------- | ------------------------------------ |
| `npm install`     | Install dependencies                 |
| `npm run dev`     | Start dev server                     |
| `npm run build`   | Build static site to `./dist/`       |
| `npm run preview` | Preview the production build locally |

## Deployment

The site is fully static. Deploy the contents of `dist/` to any static host.

- Vercel / Netlify / Cloudflare Pages: set build command to `npm run build`, output dir `dist/`
- GitHub Pages or any static host: run `npm run build` and upload `dist/`

## Tech

- Astro ^5 — no client-side frameworks, no extra packages
- Inline CSS for minimal footprint and fast first paint

## Notes

- Dark mode supported via `prefers-color-scheme`
- No analytics, no fonts loaded from the network by default
- Keep it minimal; add sections/components only if you need them
