# ZUGO Bike — Roadmap

> Build order based on business impact. Each phase unlocks the next.
> Current: **Phase 1**

---

## Phase 1 — Growth and Content
**Goal:** Drive traffic, build trust, support sales.

- [ ] SEO blog (articles, buying guides, how-to content)
- [ ] Video integration (YouTube embeds, product walkthroughs)
- [ ] Product education pages (feature breakdowns, riding guides)
- [ ] Bike comparison tool
- [ ] Basic homepage and site structure on GitHub Pages
- [ ] Social media content system (templates, posting cadence)

**Why first:** Nothing else matters if people can't find you. Content is the cheapest, most durable growth channel. Every article and video compounds over time.

---

## Phase 2 — Customer Support
**Goal:** Reduce support tickets, increase customer confidence, improve retention.

- [ ] Self-service help center (assembly, battery, maintenance, warranty)
- [ ] Troubleshooting guides with decision trees
- [ ] FAQ pages with schema markup
- [ ] Email response templates for common issues
- [ ] Contact form with Supabase edge function

**Why second:** Support volume scales with sales. If Phase 1 works and traffic grows, support requests grow with it. Build the help center before you need it, not after you're drowning in tickets.

---

## Phase 3 — Sales and Conversion
**Goal:** Turn traffic into customers. Shorten the path from interest to purchase.

- [ ] Lead capture forms (email signup, quiz, comparison tool exit intent)
- [ ] Email follow-up sequences (welcome, education, nudge)
- [ ] Customer reviews and testimonials system
- [ ] Landing pages for campaigns and ads
- [ ] Shopify webhook integration (order data into Supabase)

**Why third:** Phase 1 brings people in. Phase 2 keeps them confident. Phase 3 converts them. You need traffic and trust before conversion optimization matters.

---

## Phase 4 — Operations and Inventory
**Goal:** Know what you have, where it is, and when to reorder.

- [ ] Inventory dashboard (admin, connected to Google Sheets)
- [ ] Google Sheets API integration for stock levels
- [ ] Reorder alerts (low stock notifications)
- [ ] Order tracking dashboard (Shopify orders synced to Supabase)
- [ ] Warehouse and fulfillment workflows

**Why fourth:** Operations systems save time and prevent mistakes, but they don't generate revenue directly. Build them once sales volume justifies the investment.

---

## Phase 5 — Finance and Planning
**Goal:** See the money clearly. Budget, forecast, and plan purchasing.

- [ ] Expense tracking dashboard
- [ ] Revenue and cash flow visibility
- [ ] Inventory purchasing projections (what to buy, when, how much)
- [ ] Financial forecasting (monthly, quarterly)
- [ ] Google Sheets integration for finance data

**Why fifth:** Financial tools are most valuable when there's real data flowing through the business. Phases 1–4 generate that data. Building finance dashboards before that means staring at empty charts.

---

## Phase 6 — Team and Scaling
**Goal:** Delegate, systematize, and grow the team without losing quality.

- [ ] Admin dashboard with role-based access (Supabase Auth)
- [ ] Content management system (blog admin, draft/publish workflow)
- [ ] Support ticket management (assign, track, resolve)
- [ ] Team workflows and standard operating procedures
- [ ] Mobile app (Capacitor — if needed)

**Why last:** You can't systematize what doesn't exist yet. Build the systems first (Phases 1–5), then build the tools that let other people run them.

---

## How to use this roadmap

1. Stay in the current phase until its core items are done
2. It's fine to do small tasks from future phases if they're quick wins
3. Don't build Phase 4–6 infrastructure to avoid doing Phase 1 content work
4. Check off items as they ship. Update this file when priorities change
5. Every system should make the next phase easier to build
