# ZUGO Bike — Support System Design

> The best support experience is one the customer never has to ask for.
> If someone contacts support, the system already failed once. The goal is to answer the question before it becomes a ticket.

---

## How support fits into the business

```
Customer has a question
        ↓
  Can they find the answer themselves?
     ↓ YES                ↓ NO
  Self-service           Contact us
  (help center)          (email / form)
     ↓                      ↓
  Confidence ↑           Ticket created
  Trust ↑                Response needed
  Ticket avoided         Cost incurred
```

Support is not a cost center. It is a trust engine. A customer who finds a clear, helpful answer on their own thinks: "These people have their act together. I trust this brand." A customer who can't find an answer and has to email thinks: "I hope they respond."

For a premium brand, the self-service experience must feel premium. Clean, fast, specific, and never condescending.

---

## Two audiences, one system

The support center serves two very different people at the same time. The design must work for both without forcing either to wade through content meant for the other.

### Pre-purchase visitors
**What they need:** Confidence that ZUGO is worth the investment.
**Questions they ask:**
- How long does the battery really last?
- Is this bike good for my size/weight/terrain?
- What's included in the box? Do I need tools?
- How hard is assembly?
- What does the warranty cover?
- What if I don't like it?

**What answering these questions does:** Removes purchase objections. Every answered question is one less reason to hesitate. This is conversion support disguised as support content.

### Post-purchase owners
**What they need:** Quick, clear answers so they can get back to riding.
**Questions they ask:**
- How do I set up my bike?
- My display is showing an error code — what does it mean?
- How do I care for the battery in winter?
- Something feels off with the brakes — is this normal?
- How do I get warranty service?

**What answering these questions does:** Reduces tickets, increases satisfaction, builds loyalty, generates referrals.

---

## Support content categories

Six categories. Every support article belongs to one. The categories are ordered by the customer journey — from unboxing to long-term ownership.

### 1. Getting Started
**Audience:** New owners (and pre-purchase visitors previewing the experience).
**Purpose:** Get from box to first ride with zero confusion.

Articles:
- What's in the box (full parts list with photos)
- Assembly guide (step-by-step with video)
- First ride checklist (tire pressure, brake check, seat height, battery charge)
- How to download the app and connect (if applicable)
- How to register your bike for warranty

**Why this category matters:** The unboxing-to-first-ride experience defines the customer's entire perception of the brand. A confusing setup creates regret. A smooth setup creates evangelists.

---

### 2. Battery and Charging
**Audience:** All owners + pre-purchase researchers.
**Purpose:** Answer the single most asked question in e-bikes: "What about the battery?"

Articles:
- How to charge your ZUGO battery
- How far can I ride on a single charge? (real-world ranges by model)
- Battery care: how to extend its lifespan
- Cold weather battery tips
- When and how to replace the battery
- Battery safety and storage

**Why this category matters:** Battery anxiety is the #1 purchase objection and the #1 source of support tickets. Comprehensive battery content does more for both sales and support than any other single category.

---

### 3. Riding and Performance
**Audience:** All owners.
**Purpose:** Help riders get the most out of their bike.

Articles:
- Understanding pedal assist levels
- How to switch between modes
- Riding on different terrains (pavement, gravel, sand, snow, trails)
- Maximum rider weight and load capacity
- Speed settings and legal considerations by state
- Tips for riding in rain

**Why this category matters:** A rider who understands their bike's capabilities rides more often, enjoys it more, and tells more people about it.

---

### 4. Maintenance and Care
**Audience:** Owners.
**Purpose:** Keep the bike in top condition and prevent problems before they start.

Articles:
- Monthly maintenance checklist
- How to clean your e-bike (what to avoid)
- Tire pressure guide and how to inflate
- Brake adjustment basics
- Chain and drivetrain care
- Seasonal storage guide
- When to take your bike to a shop vs. DIY

**Why this category matters:** Preventable maintenance issues are the second-largest source of support tickets after battery questions. A simple checklist prevents a $200 repair and a frustrated email.

---

### 5. Troubleshooting
**Audience:** Owners with a problem right now.
**Purpose:** Fix the issue or identify the next step — fast.

Structure: Every troubleshooting article follows a symptom-first format. The customer doesn't know what's broken. They know what's happening.

Articles:
- Bike won't turn on
- Display shows error code [X]
- Battery won't charge
- Motor cuts out while riding
- Brakes are squealing or rubbing
- Tire is flat — how to fix it
- Pedal assist isn't responding
- Unusual noise from the motor

**Article format for troubleshooting:**
```
Title: [Symptom the customer would describe]

What you're seeing:
[Describe the problem in the customer's words]

Most likely cause:
[Plain language — no jargon]

Try this first:
[One simple step — solves the problem 60-80% of the time]

If that didn't work:
[Second step — slightly more involved]

Still not fixed?
[Contact support with this information: model, purchase date, what you tried]
```

**Why this category matters:** A customer with a problem and no answer is a negative review. A customer with a problem and a fast answer is a loyal customer. Speed matters here more than anywhere else.

---

### 6. Warranty and Policies
**Audience:** Pre-purchase (evaluating risk) + owners (need service).
**Purpose:** Make the rules clear so no one is surprised.

Articles:
- What the ZUGO warranty covers (and what it doesn't)
- How to submit a warranty claim
- Return and exchange policy
- Shipping and delivery FAQ
- How to contact support

**Why this category matters:** Ambiguous policies create anxiety before purchase and anger after. Clear policies do the opposite.

---

## How users navigate the system

### Entry points — how people arrive

| Entry point | What they're looking for | Where they land |
|---|---|---|
| Google search ("zugo battery not charging") | Answer to a specific problem | Troubleshooting article directly |
| Blog article link ("for detailed maintenance steps, see our help center") | Related support content | Specific article in Maintenance |
| Product page link ("what's in the box?") | Pre-purchase reassurance | Getting Started article |
| Navigation bar "Support" link | General browsing | Support center index |
| Email footer "Help Center" link | Post-purchase help | Support center index |

### Support center index (`web/support/index.html`)

The index page is the front door. It must answer the question "where do I go?" in under 5 seconds.

```
┌──────────────────────────────────────────────┐
│  How can we help?                            │
│  [Search bar — full-text search across all   │
│   support articles]                          │
├──────────────────────────────────────────────┤
│                                              │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐    │
│  │ Getting  │ │ Battery  │ │ Riding & │    │
│  │ Started  │ │ &Charging│ │ Perform. │    │
│  └──────────┘ └──────────┘ └──────────┘    │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐    │
│  │ Maintain.│ │ Trouble- │ │ Warranty │    │
│  │ & Care   │ │ shooting │ │ & Policy │    │
│  └──────────┘ └──────────┘ └──────────┘    │
│                                              │
├──────────────────────────────────────────────┤
│  Most viewed articles                        │
│  • How to charge your ZUGO battery           │
│  • Assembly guide                            │
│  • Bike won't turn on                        │
│  • What the warranty covers                  │
│  • First ride checklist                      │
├──────────────────────────────────────────────┤
│  Can't find what you need?                   │
│  [Contact us — email form]                   │
└──────────────────────────────────────────────┘
```

### Navigation rules
- Search is the first thing the user sees. Most support visits are someone looking for a specific answer — let them type it
- Six category cards below search — one tap to see all articles in a category
- "Most viewed" surfaces the content that actually gets used, not what we think is important
- Contact form is always visible at the bottom — never hide the escape hatch

---

## How video integrates into support

### Where video appears

| Content type | Video format | Why |
|---|---|---|
| Assembly guide | Full walkthrough, step-by-step | Assembly is spatial. Showing is 10x faster than telling |
| First ride checklist | Quick visual guide (2 min) | Builds excitement, not just instruction |
| Battery care | Short explainer (3 min) | Demonstrates physical actions (plugging in, checking indicators) |
| Troubleshooting | Symptom-specific clips (1-2 min each) | Customer can match what they're seeing to the video |
| Maintenance | How-to with close-up shots | "Is this what my chain should look like?" |

### Video rules for support
- Embed at the top of the article, below the title
- Keep support videos short. Under 5 minutes for how-to. Under 2 minutes for troubleshooting
- No intros, no branding bumpers, no "hey guys welcome back." Start with the answer
- Use ZUGO's documentary style but optimize for clarity: tight shots on hands and parts, medium shots showing the full bike for context
- Include text overlays for key steps (Helvetica Neue, left-aligned)
- Every video has a companion article below it with the same information in text. Never video-only

---

## How support connects to the rest of the site

### Support → Blog
- Ownership and Care blog articles link to detailed support guides: "For step-by-step maintenance instructions, visit our help center"
- Support articles link back to relevant blog content for deeper context: "Want to learn more about battery technology? Read our full guide"

### Support → Products (Shopify)
- Getting Started articles reference specific models with links to their product pages
- Pre-purchase support content (warranty, what's in the box, specs) links to the store
- This is not selling. It is: "Here's the product this article is about, if you want to see it"

### Support → Comparison Tool
- "Which bike is right for me?" questions in the FAQ link to the comparison tool
- Pre-purchase visitors who land in support often need help choosing, not help fixing

### Products → Support
- Shopify product pages should link to "What's in the box" and "Assembly guide" for each model
- This reduces pre-purchase anxiety: "I can see exactly what I'm getting and how to set it up"

### Blog → Support
- Every Ownership and Care blog post links to related support articles
- Troubleshooting blog posts (if any) redirect to the help center — don't duplicate content

---

## How the support system reduces tickets

Every article in the help center exists because someone once emailed asking that question. The goal is to intercept the next person before they email.

| Ticket type | Prevention strategy |
|---|---|
| "How do I set it up?" | Assembly guide with video — linked from order confirmation email |
| "My battery won't charge" | Troubleshooting article — ranked in Google for this exact search |
| "What does this error code mean?" | Error code lookup — one article per code with clear fixes |
| "What does the warranty cover?" | Warranty page — linked from product pages and order confirmation |
| "Is this bike right for me?" | Comparison tool + buying guides — linked from support FAQ |
| "How do I return this?" | Return policy — visible, clear, no hidden steps |

### The order confirmation email
The single highest-leverage support touchpoint. Every customer reads it. Include:
1. Link to "Getting Started" guide
2. Link to assembly video
3. Link to first ride checklist
4. Link to contact support (if needed)

This one email prevents 30-40% of post-purchase support tickets.

---

## Measuring what works

| Metric | What it tells you | What to do |
|---|---|---|
| Support page views | Which articles get used | Write more content in high-traffic categories |
| Search queries with no results | What's missing from the help center | Create articles for the most common unmatched queries |
| Time on troubleshooting pages | Are people finding the fix? | Short time = fast answer (good). Long time = confusing article (rewrite) |
| Contact form submissions | Volume and categories of remaining tickets | If a category spikes, the self-service content isn't working — improve it |
| Ticket deflection rate | Ratio of support page views to contact submissions | Higher is better. Target: 20:1 (20 self-service views per 1 ticket) |

---

## What this system does not include

- Live chat (adds complexity, requires staffing — revisit in Phase 6)
- AI chatbot (the help center IS the answer — a chatbot just adds a layer in front of it)
- Community forum (use social media for community — forums require moderation)
- Phone support (email-first, with clear response time expectations)
- Ticketing dashboard for the team (Phase 2 — for now, support runs through email)

---

## Build order

```
1. Support center index page (web/support/index.html)
2. Getting Started articles (highest immediate impact for new customers)
3. Battery and Charging articles (highest search volume, #1 ticket category)
4. Troubleshooting articles (direct ticket deflection)
5. Warranty and Policies (removes pre-purchase anxiety)
6. Maintenance and Care articles
7. Riding and Performance articles
8. Contact form with Supabase edge function
9. Search functionality across all support articles
```

Start with what prevents the most tickets and removes the most purchase friction. Finish with what enhances the experience.
