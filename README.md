# 🎈 First Birthday Party Website

A fun, mobile-friendly birthday party website built with [Astro](https://astro.build/) and ready to deploy to Cloudflare Pages.

## Features

- **Animated Hero** with floating balloons, falling confetti, and a birthday cake
- **Live Countdown Timer** to the party date
- **Party Details Cards** — date, time, venue, dress code, and RSVP
- **Embedded Map** via OpenStreetMap (no API key needed) with a Google Maps directions link
- **Fully Responsive** — looks great on phones, tablets, and desktops
- **Static Output** — fast, secure, zero JavaScript frameworks at runtime (just a tiny countdown script)

## Quick Start

```bash
npm install
npm run dev       # local dev server at localhost:4321
npm run build     # produces static files in dist/
npm run preview   # preview production build locally
```

## Customization

All party details are configured in a single `config` object at the top of `src/pages/index.astro`. Update these values to match your event:

| Field | Description |
|-------|-------------|
| `childName` | Name displayed in the hero (e.g. `"Emma's"`) |
| `tagline` | Subtitle under the main heading |
| `partyDate` | ISO date string for the countdown (e.g. `"2026-03-15T14:00:00"`) |
| `date` / `time` | Human-readable date and time strings |
| `venue` / `address` | Venue name and full address |
| `lat` / `lng` | Coordinates for the map marker |
| `dressCode` | Dress code message |
| `rsvpEmail` | Email address for the RSVP mailto link |
| `familyName` | Name shown in the footer |

## Deploy to Cloudflare Pages

1. Push this repo to GitHub/GitLab
2. In the [Cloudflare Pages dashboard](https://dash.cloudflare.com/), create a new project
3. Connect your repository
4. Set build settings:
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
   - **Node.js version:** `18` (or higher)
5. Deploy!

Alternatively, deploy directly via Wrangler:

```bash
npx wrangler pages deploy dist
```

## Adding Dynamic Components

Since this is Astro, you can add interactive islands with React, Svelte, Vue, etc.:

```bash
npx astro add react    # or svelte, vue, solid, etc.
```

Then create `.tsx` components and use them with `client:load` or `client:visible` directives in your `.astro` pages.

## Project Structure

```
src/
├── components/
│   ├── Hero.astro         # Animated hero with balloons & confetti
│   ├── Countdown.astro    # Live countdown timer
│   ├── Details.astro      # Party info cards
│   ├── Map.astro          # OpenStreetMap embed + directions
│   └── Footer.astro       # Footer
├── layouts/
│   └── Layout.astro       # Base HTML layout & global styles
└── pages/
    └── index.astro        # Main page (edit config here)
```
