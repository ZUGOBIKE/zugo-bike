# ZUGO Bike — Digital Operating System

ZUGO Bike is a premium electric fat tire e-bike company focused on performance, lifestyle, and all-terrain use. This repo is the digital operating system for the business — covering marketing, sales, customer support, inventory, fulfillment, and finance.

## What this is

This is not the Shopify storefront. This is the internal and public-facing infrastructure that surrounds the store.

| Area | What's here |
|---|---|
| Marketing | SEO blog, content hub, product education |
| Sales | Comparison tools, lead capture, product pages |
| Customer Support | Help center, troubleshooting guides, support tickets |
| Operations | Inventory tracking, warehouse workflows, order management |
| Finance | Expense tracking, purchasing projections, cash flow |

## Tech stack

- **Frontend:** Vanilla HTML/JS + Tailwind CSS v4
- **Backend:** Supabase (database, auth, edge functions)
- **Hosting:** GitHub Pages (push to main = live, no build step)
- **Store:** Shopify — separate, not managed here

## Project structure

```
web/              Public-facing pages (products, blog, support, compare)
admin/            Internal business tools (inventory, orders, finance)
shared/           Reusable JS modules (auth, supabase, ui components)
supabase/         Backend functions and database migrations
integrations/     Shopify, Google Sheets, and shipping connectors
styles/           Tailwind CSS source and design tokens
assets/           Brand files, product images, icons
docs/             Documentation (deploy, schema, integrations, key files)
mobile/           Future mobile app (placeholder)
scripts/          Utility and deployment scripts
```

## Quick start

```bash
git clone https://github.com/ZUGOBIKE/zugo-bike.git
cd zugo-bike
npm install
npm run css:build
```

Open `index.html` in a browser or use a local server (e.g. `npx serve .`).

## AI assistant

This project uses Claude Code. Context files are loaded automatically when you run `claude` from the project root:

- `CLAUDE.md` — behavior rules and code standards
- `CONTEXT.md` — project goals and what good looks like
- `REFERENCES.md` — brand, design, and system references

## Deployment

Push to `main` → live on GitHub Pages in ~60 seconds. See `docs/DEPLOY.md`.
