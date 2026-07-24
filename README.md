# Maruf Ahmed Siam — Portfolio

A React + Vite + Tailwind CSS v4 developer portfolio, built in a deep wine-red / black theme with
glassmorphism, scroll reveals, magnetic buttons, a tilt-hover tech stack, and a live-fetching
Codeforces + GitHub stats section.

## Run it locally

```bash
npm install
npm run dev
```

Open the printed local URL (usually `http://localhost:5173`).

## Build for production

```bash
npm run build
npm run preview   # to test the production build locally
```

The output goes to `dist/` — deploy that folder to Vercel, Netlify, GitHub Pages, or any static host.

## Project structure

```
src/
  components/
    NodeBackground.jsx   – ambient canvas network-node background
    CursorGlow.jsx        – mouse-follow spotlight glow (desktop only)
    Navbar.jsx
    Hero.jsx              – headline + terminal boot-sequence signature element
    About.jsx
    Education.jsx
    TechStack.jsx         – tilt-hover language cards
    CodingProfiles.jsx    – GitHub (live stats image) + Codeforces (live API) + LinkedIn + HackerRank
    Contact.jsx           – copy-email button, mailto CTA
    Footer.jsx
    Reveal.jsx            – scroll-in-view wrapper (Framer Motion)
    MagneticButton.jsx    – buttons that pull toward the cursor
  assets/img/maruf.png    – profile photo
  index.css               – Tailwind v4 theme tokens (colors, fonts)
```

## Notes on live data

- **GitHub stats** render via `github-readme-stats.vercel.app` — no key needed, but the free
  service can rate-limit occasionally; if the image fails to load, the card gracefully falls back
  to a text note.
- **Codeforces rating** is fetched client-side from the public Codeforces API
  (`codeforces.com/api/user.info`) on page load. No key required.
- **HackerRank and LinkedIn** don't offer public embeddable stats APIs, so those are clean link-out
  cards.

## Customizing

- **Colors / fonts**: edit the `@theme` block in `src/index.css`.
- **Content**: each section is a single component in `src/components/` — copy is inline in the JSX.
- **Adding sections later** (Projects, Experience, Achievements, etc.): create a new component
  following the pattern of the existing ones and drop it into `src/App.jsx`.

## Deploying

The quickest path is [Vercel](https://vercel.com): import the repo (or drag-and-drop the folder),
it auto-detects Vite, and ships it in under a minute. Netlify works the same way — build command
`npm run build`, publish directory `dist`.
