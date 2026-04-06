# ZUGO Bike — Project Directives

> **On-demand docs — load when the task matches:**
> - `docs/INTEGRATIONS.md` — **load for:** Shopify, Google Sheets, shipping API work
> - `docs/SCHEMA.md` — **load for:** writing queries, modifying tables, debugging data
> - `docs/KEY-FILES.md` — **load for:** finding files, understanding project structure
> - `docs/DEPLOY.md` — **load for:** pushing, deploying, version questions

## Identity

You are helping Juls Bindi build ZUGO Bike — a premium electric fat tire e-bike company focused on performance, lifestyle, and all-terrain use. The goal is a complete digital operating system covering marketing, sales, customer support, inventory, fulfillment, and finance.

## Mandatory Behaviors

1. After code changes: end response with `vYYMMDD.NN H:MMa [model]` + affected URLs (read `version.json`)
2. Ask before making changes to any working system
3. Focus on real business impact: revenue, customer experience, operational efficiency
4. Prefer simple, scalable solutions over clever ones
5. Never rebuild what Shopify already handles

## Code Standards

- Mobile-first, fast, and accessible HTML/JS
- Tailwind v4 with design tokens from `styles/tokens.css`
- Run `npm run css:build` after adding new Tailwind classes
- `showToast()` not `alert()` for user feedback
- `openLightbox(url)` for images

## What to Avoid

- Rebuilding Shopify's storefront, cart, checkout, or product catalog
- Overengineering simple problems
- Breaking working systems without explicit approval
- Disconnected tools instead of integrated systems
- Generic outputs that don't add real business value

## Shopify Boundary

Shopify handles products, checkout, and orders. This system supports marketing, content, and internal tools. Do not duplicate Shopify's product catalog, cart, checkout, or payment processing. This repo may receive data from Shopify (webhooks, API) but never replaces it.

## Tech Stack

- **Frontend:** Vanilla HTML/JS + Tailwind v4
- **Backend:** Supabase (PostgreSQL + Edge Functions + Auth)
- **Hosting:** GitHub Pages (push to main = deployed, no build step)
- **Store:** Shopify (separate — not managed here)
- **Architecture:** Browser → GitHub Pages → Supabase (no server-side code)
- **Live:** https://YOUR_USERNAME.github.io/zugo-bike/
