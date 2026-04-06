# Database Schema

> This file describes the Supabase (PostgreSQL) database for ZUGO Bike.
> Update this file whenever tables are created or modified via migrations.
> All migrations live in `supabase/migrations/`.

## Status

Supabase project not yet created. This file documents the planned schema for Phase 2.

---

## Planned Tables

### `customers`
Customer records synced from Shopify.

```sql
id                uuid PRIMARY KEY DEFAULT gen_random_uuid()
shopify_id        text UNIQUE
email             text NOT NULL
first_name        text
last_name         text
phone             text
created_at        timestamptz DEFAULT now()
updated_at        timestamptz DEFAULT now()
```

---

### `orders`
Orders synced from Shopify for internal tracking and fulfillment.

```sql
id                uuid PRIMARY KEY DEFAULT gen_random_uuid()
shopify_order_id  text UNIQUE NOT NULL
customer_id       uuid REFERENCES customers(id)
status            text DEFAULT 'pending'
  -- pending | processing | shipped | delivered | cancelled
total_amount      numeric(10,2)
line_items        jsonb
shipping_address  jsonb
tracking_number   text
carrier           text
notes             text
created_at        timestamptz DEFAULT now()
updated_at        timestamptz DEFAULT now()
```

---

### `inventory`
Internal inventory tracking. Synced with Google Sheets Inventory Master.

```sql
id                uuid PRIMARY KEY DEFAULT gen_random_uuid()
sku               text UNIQUE NOT NULL
product_name      text NOT NULL
variant_name      text
quantity_on_hand  integer DEFAULT 0
quantity_reserved integer DEFAULT 0
reorder_point     integer DEFAULT 0
supplier          text
cost_per_unit     numeric(10,2)
notes             text
last_synced_at    timestamptz
updated_at        timestamptz DEFAULT now()
```

---

### `support_tickets`
Customer support requests submitted via the help center.

```sql
id                uuid PRIMARY KEY DEFAULT gen_random_uuid()
customer_email    text NOT NULL
customer_name     text
subject           text NOT NULL
message           text NOT NULL
status            text DEFAULT 'open'
  -- open | in_progress | resolved | closed
priority          text DEFAULT 'normal'
  -- low | normal | high | urgent
order_id          uuid REFERENCES orders(id)
assigned_to       text
created_at        timestamptz DEFAULT now()
updated_at        timestamptz DEFAULT now()
resolved_at       timestamptz
```

---

### `blog_posts`
SEO content hub — articles, guides, and buying resources.

```sql
id                uuid PRIMARY KEY DEFAULT gen_random_uuid()
slug              text UNIQUE NOT NULL
title             text NOT NULL
meta_description  text
content           text  -- markdown
author            text DEFAULT 'ZUGO Bike'
status            text DEFAULT 'draft'
  -- draft | published | archived
published_at      timestamptz
created_at        timestamptz DEFAULT now()
updated_at        timestamptz DEFAULT now()
```

---

### `leads`
Email captures from website forms, comparison tools, and landing pages.

```sql
id                uuid PRIMARY KEY DEFAULT gen_random_uuid()
email             text NOT NULL
first_name        text
source            text  -- homepage | comparison | blog | support
interest          text  -- product or topic they engaged with
status            text DEFAULT 'new'
  -- new | contacted | qualified | converted | unsubscribed
notes             text
created_at        timestamptz DEFAULT now()
```

---

## Auth System

Uses Supabase Auth (built-in). Roles:

- `admin` — Juls and internal team (full access)
- `staff` — Support and operations staff (limited access)

Row-level security (RLS) will be enabled on all tables.

---

## Conventions

- All IDs are `uuid` using `gen_random_uuid()`
- All tables have `created_at` and `updated_at` timestamps
- Soft deletes use an `is_archived boolean DEFAULT false` column where needed
- Status fields use plain text enums documented inline
- Secrets and credentials never stored in the database — use `docs/CREDENTIALS.md`
