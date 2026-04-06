# Key Files

> Load this file when looking for where something lives in the project.

---

## Root

| File | Purpose |
|---|---|
| `CLAUDE.md` | AI behavior rules and code standards |
| `CONTEXT.md` | Project goals, what good looks like, what to avoid |
| `REFERENCES.md` | Brand, design, and system references |
| `README.md` | Project overview and quick start |
| `version.json` | Current version number |
| `index.html` | Public homepage entry point |
| `.nojekyll` | Tells GitHub Pages not to process with Jekyll |

---

## Web — Public Pages (`web/`)

| Path | Purpose |
|---|---|
| `web/blog/` | SEO content hub — articles, guides, buying resources |
| `web/products/` | Product detail and education pages |
| `web/support/` | Self-service help center and troubleshooting guides |
| `web/compare/` | Bike comparison tool |
| `web/login/` | Customer login and account access |

---

## Admin — Internal Tools (`admin/`)

| Path | Purpose |
|---|---|
| `admin/inventory/` | Inventory tracking dashboard (Google Sheets sync) |
| `admin/orders/` | Order management and fulfillment workflow |
| `admin/customers/` | Customer records and history |
| `admin/content/` | Blog and content management |
| `admin/finance/` | Expense tracking, forecasting, cash flow |
| `admin/support/` | Support ticket management |
| `admin/fulfillment/` | Warehouse and shipping workflows |

---

## Shared Modules (`shared/`)

| File | Purpose |
|---|---|
| `shared/supabase.js` | Supabase client singleton |
| `shared/auth.js` | Authentication helpers (login, logout, role checks) |
| `shared/brand-config.js` | Brand colors, fonts, identity constants |
| `shared/admin-shell.js` | Admin page layout wrapper (auth gate + nav) |
| `shared/public-shell.js` | Public page layout wrapper (header + footer) |
| `shared/ui-components.js` | Shared UI — showToast(), openLightbox(), modals |

---

## Backend (`supabase/`)

| Path | Purpose |
|---|---|
| `supabase/functions/contact-form/` | Public contact form submission handler |
| `supabase/functions/support-ticket/` | Support ticket creation |
| `supabase/functions/inventory-sync/` | Syncs inventory data with Google Sheets |
| `supabase/functions/order-lookup/` | Customer-facing order status lookup |
| `supabase/migrations/` | Database schema migrations (run in order) |

---

## Integrations (`integrations/`)

| Path | Purpose |
|---|---|
| `integrations/shopify/` | Shopify webhook handlers and API helpers |
| `integrations/google-sheets/` | Google Sheets API sync for inventory and finance |
| `integrations/shipping/` | Shipping carrier API connectors |

---

## Styles (`styles/`)

| File | Purpose |
|---|---|
| `styles/tailwind.css` | Tailwind source file |
| `styles/tailwind.out.css` | Compiled CSS output (run `npm run css:build`) |
| `styles/tokens.css` | Design tokens — brand colors, spacing, typography |

---

## Assets (`assets/`)

| Path | Purpose |
|---|---|
| `assets/branding/` | Logos, wordmarks, brand kit files |
| `assets/images/` | Product and lifestyle photography |
| `assets/icons/` | UI icons |

---

## Documentation (`docs/`)

| File | Purpose |
|---|---|
| `docs/DEPLOY.md` | How to push and deploy |
| `docs/SCHEMA.md` | Database table definitions |
| `docs/INTEGRATIONS.md` | Third-party service setup (Shopify, Sheets, etc.) |
| `docs/KEY-FILES.md` | This file |
| `docs/CREDENTIALS.md` | API keys and secrets — NOT in git, create locally |
