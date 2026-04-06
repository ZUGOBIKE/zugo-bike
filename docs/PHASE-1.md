# Phase 1 — Growth and Content

> Drive traffic. Build trust. Support sales.
> This phase is complete when ZUGO has a working content engine that brings qualified visitors to the site every week.

---

## What gets built

### 1. SEO Blog
The highest-leverage asset in this phase. Every article is a permanent traffic source.

**Tasks:**
- [ ] Build blog index page (`web/blog/index.html`) — lists all posts, sorted by date, filterable by category
- [ ] Build blog post template (`web/blog/post.html`) — clean reading experience, mobile-first, schema markup
- [ ] Write 10 foundational articles covering the topics people search before buying an e-bike:
  - [ ] "What is a fat tire e-bike and who is it for?"
  - [ ] "Electric bike classes explained (Class 1, 2, 3)"
  - [ ] "How far can an electric bike go on one charge?"
  - [ ] "Fat tire vs. regular tire e-bikes: which is right for you?"
  - [ ] "How to choose your first electric bike"
  - [ ] "E-bike battery care: how to make it last"
  - [ ] "Are electric bikes worth it? Cost breakdown"
  - [ ] "Best e-bikes for off-road and trails"
  - [ ] "E-bike maintenance: what you need to know"
  - [ ] "How fast do electric bikes go?"
- [ ] Add Article and FAQ schema markup to every post
- [ ] Add internal links from each article to relevant product pages on zugobike.com
- [ ] Set up Google Search Console and submit sitemap

**Prompt to use:** `prompts/seo-content.md`

---

### 2. Video Integration
Video builds trust faster than text. Embed YouTube content across the blog and product education pages.

**Tasks:**
- [ ] Create a YouTube content plan (12 videos mapped to the 10 blog topics + 2 product walkthroughs)
- [ ] Script the first 3 videos:
  - [ ] "What makes a fat tire e-bike different?" (educational, 4-5 min)
  - [ ] "ZUGO [model] — full walkthrough" (product, 6-8 min)
  - [ ] "First ride setup: unboxing to riding in 15 minutes" (how-to, 4-5 min)
- [ ] Build a video embed component for blog posts (responsive YouTube iframe, no autoplay)
- [ ] Embed videos in matching blog articles (each article should have a companion video where possible)
- [ ] Add VideoObject schema markup to pages with embedded videos

**Prompt to use:** `prompts/video-content.md`

---

### 3. Product Education Pages
Help customers understand what they're buying. These pages sit between the blog and the Shopify product pages.

**Tasks:**
- [ ] Build bike comparison page (`web/compare/index.html`) — side-by-side specs, "choose this if..." recommendations
- [ ] Build a "How to choose your ZUGO" guide page — interactive or structured walkthrough based on rider type
- [ ] Build individual feature explainer sections (battery tech, motor types, tire specs) — reusable across pages
- [ ] Link comparison and education pages from blog articles and from zugobike.com product pages

**Prompt to use:** `prompts/product-copy.md`

---

### 4. Homepage and Site Structure
The skeleton that holds everything together. Keep it simple.

**Tasks:**
- [ ] Replace the stub `index.html` with a real homepage:
  - Hero section with brand message and CTA to shop
  - Featured blog articles (latest 3)
  - Featured video embed
  - Link to comparison tool
  - Footer with social links and contact
- [ ] Build shared navigation component (`shared/public-shell.js`) — logo top-left, links to blog, compare, support, shop
- [ ] Build shared footer component — social links, contact email, copyright
- [ ] Create `styles/tokens.css` with ZUGO brand colors and typography from `docs/BRAND-SYSTEM.md`
- [ ] Run initial Tailwind build and verify styling
- [ ] Create `package.json` with Tailwind CSS as a dev dependency and `css:build` script

---

### 5. Social Media Foundation
Content from the blog and videos gets repurposed for social. This is distribution, not a separate content stream.

**Tasks:**
- [ ] Define posting cadence (e.g., 3x/week Instagram, 2x/week YouTube, 1x/week email)
- [ ] Create 5 social post templates using the ZUGO 24x24 grid system (4:5 and 1:1 ratios)
- [ ] Repurpose each blog article into 2-3 social posts (quote card, tip carousel, video clip)
- [ ] Write social captions for the first 10 blog articles

**Prompt to use:** `prompts/social-media.md`

---

## What success looks like

| Metric | Target | How to measure |
|---|---|---|
| Blog articles published | 10 | Count pages in `web/blog/` |
| Articles indexed in Google | 10 | Google Search Console |
| Organic search impressions | 1,000+/month within 90 days | Google Search Console |
| YouTube videos published | 3+ | YouTube Studio |
| Comparison tool live | Yes | Page loads at `/web/compare/` |
| Site loads on mobile in under 3 seconds | Yes | Google PageSpeed Insights |
| Every page has working internal links to zugobike.com | Yes | Manual check |

---

## What we are NOT doing in Phase 1

- Inventory dashboards or Google Sheets integrations
- Finance tracking or forecasting
- Supabase database setup beyond what's needed for a contact form
- Admin dashboards or role-based access
- Mobile app development
- Paid advertising systems (write the content first, then amplify it)

---

## Build order within Phase 1

```
1. package.json + Tailwind setup + tokens.css     (everything else needs CSS)
2. shared/public-shell.js (nav + footer)           (every page needs layout)
3. Blog template + first 3 articles                (start indexing immediately)
4. Video scripts + embeds in blog posts            (compound the blog content)
5. Homepage with featured content                  (give the site a front door)
6. Comparison tool                                 (conversion support)
7. Remaining 7 blog articles                       (fill out the content hub)
8. Social media templates and repurposed posts     (distribute what you built)
```

Start at the top. Ship each piece before moving to the next.
