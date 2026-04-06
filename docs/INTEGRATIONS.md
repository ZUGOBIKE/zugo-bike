# Integrations

## Shopify

ZUGO Bike's store runs on Shopify at https://www.zugobike.com. This repo does NOT manage the storefront, product catalog, or checkout.

**What we integrate with Shopify:**
- Order webhooks (new orders, fulfillment status updates)
- Inventory sync (stock levels → Google Sheets)
- Customer data sync (for support tickets and follow-up)

**Do not rebuild:** cart, product pages, checkout, payments, product catalog. Shopify owns these.

**Setup (Phase 2):**
- Create a Shopify private app or custom app in the Shopify admin
- Request scopes: `read_orders`, `read_inventory`, `read_customers`
- Store the Admin API access token in `docs/CREDENTIALS.md` (not in git)
- Configure webhooks in Shopify Admin → Settings → Notifications

---

## Google Sheets

Used for inventory tracking and financial forecasting. Google Sheets is the source of truth for operational data before a full database is needed.

**Sheets in use:**
- **Inventory Master** — SKU, stock levels, reorder points, supplier info, cost per unit
- **Order Tracking** — Orders, fulfillment status, shipping carriers, tracking numbers
- **Finance Dashboard** — Revenue, expenses, cash flow projections, purchasing forecasts

**Integration method:** Google Sheets API v4 via a Supabase Edge Function or direct browser fetch using a service account.

**Setup (Phase 2):**
- Create a Google Cloud project
- Enable the Google Sheets API
- Create a service account and download the JSON key
- Share each sheet with the service account email address
- Store credentials in `docs/CREDENTIALS.md` (not in git)

---

## Supabase

Backend for database, auth, and edge functions.

- Project URL: stored in `docs/CREDENTIALS.md`
- Anon key: safe to expose in `shared/supabase.js`
- Service role key: never in frontend code — edge functions only

**Setup:** See Phase 2 setup plan. Project not yet created.

---

## Email

**Planned:** Resend or Postmark for transactional email.

Use cases:
- Order confirmation follow-ups
- Support ticket acknowledgements
- Lead capture and follow-up sequences
- Internal alerts (low inventory, new support ticket)

---

## Shipping

**Planned integrations:**
- **ShipStation** or **EasyPost** — label generation and tracking
- **AfterShip** — branded order tracking pages for customers
- Note: Shopify Shipping may cover basic needs initially — evaluate before building custom

---

## SMS / WhatsApp

**Planned:** Telnyx or Twilio.

Use cases:
- Order shipment notifications
- Support ticket updates
- High-priority customer follow-up

---

## Analytics

**Planned:**
- Google Analytics 4 (website traffic, conversions)
- Shopify Analytics (sales, revenue — built in)
- Google Search Console (SEO performance)

---

## Credentials

All API keys, tokens, and secrets are stored in `docs/CREDENTIALS.md`.
That file is listed in `.gitignore` and must never be committed.
