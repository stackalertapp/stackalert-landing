# StackAlert Landing Page

## Project Overview

Static landing page for **StackAlert** — an AWS cost spike alert service for small/mid-sized teams. No framework, no build step — pure HTML + Tailwind CSS (CDN) + vanilla JS.

## Tech Stack

- **HTML** — single-page static site (`index.html`)
- **Tailwind CSS** — loaded via CDN (`cdn.tailwindcss.com`), config embedded inline
- **Feather Icons** — via unpkg CDN
- **Fonts** — Space Grotesk (body), JetBrains Mono (data/code)
- **Deployment** — GitHub Pages via GitHub Actions (`.github/workflows/deploy.yml`)
- **Analytics** — Cloudflare Web Analytics

## File Structure

```
index.html          # Main landing page
datenschutz.html    # Privacy policy (German)
impressum.html      # Legal notice (German)
favicon.svg         # Site favicon
```

## Design System

- **Theme**: Dark (#080808 background), orange (#f97316) and red (#ef4444) accents
- **Style**: Minimalist, glassmorphism cards, animated hero glow
- **Tailwind config**: Inline `<script>` block in index.html (custom colors, fonts)
- **Responsive**: Mobile-first with Tailwind breakpoints

## Development

No build step required. Open `index.html` in a browser or use a local server:

```bash
npx serve .
# or
python3 -m http.server 8000
```

## UI/UX Design Principles

When working on visual or design tasks, always use the `/frontend-design` skill.

- **Visual hierarchy**: Hero → value props → social proof → CTA. Every section must have a clear focal point
- **Spacing**: Use generous whitespace. Sections separated by `py-20` minimum. Cards use `p-6` or `p-8`
- **Typography**: Headlines in Space Grotesk (semibold/bold), body in Space Grotesk (regular), data/metrics in JetBrains Mono
- **Color usage**: Orange (#f97316) for primary CTAs and highlights. Red (#ef4444) for alerts/warnings. White text on dark bg. Muted text uses `text-gray-400`/`text-gray-500`
- **Glassmorphism cards**: `bg-white/5 backdrop-blur border border-white/10 rounded-2xl`
- **Hover states**: Subtle transitions (`transition-all duration-300`), slight scale or border glow on interactive elements
- **Accessibility**: Minimum contrast ratio for text. Focus-visible states on interactive elements. Semantic HTML
- **Animations**: Subtle and purposeful — entry animations, hover transitions. No excessive motion
- **Mobile-first**: Design for mobile, enhance for desktop. Test at 375px, 768px, 1024px, 1440px breakpoints
- **CTA pattern**: Primary buttons use `bg-orange-500 hover:bg-orange-400` with rounded-full, secondary use ghost/outline style
- **Trust signals**: Badges, icons, and micro-copy near CTAs to reduce friction

## Guidelines

- Keep it as a static site — no bundler, no framework
- All styling via Tailwind utility classes (CDN)
- Maintain GDPR compliance (EU data residency messaging)
- Legal pages (datenschutz, impressum) must stay in German
- Test visual changes with Playwright MCP (`browser_navigate` to local server)
- When editing the landing page, preserve the dark theme and glassmorphism aesthetic
- Keep page load fast — no heavy JS frameworks, minimize external requests
- Use `/frontend-design` skill for any UI/UX work (component creation, page redesign, visual improvements)
- Use Playwright MCP to visually verify changes after editing HTML/CSS
