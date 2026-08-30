# Monetization Strategy — Cash First, Code Second

**Audience:** Solo founder shipping global micro-SaaS / developer tools  
**Rule #0:** No unpaid feature marathon. Validate payment intent before productizing.  
**Last updated:** 2026-08-28

> 先卖，再造。先人工交付，再自动化。  
> Sell → deliver manually → automate. Never invert.

---

## 1. Revenue Objectives (90 days)

| Milestone | Definition | Why it matters |
|-----------|------------|----------------|
| **M0** | Payment rails live (Stripe or MoR) | Can accept USD |
| **M1** | First **$1+** USD revenue | Breaks “hobby” psychology |
| **M2** | **$100** MRR **or** **$500** cumulative one-time | Proves repeatability path |
| **M3** | Documented unit economics (gross margin ≥ 70% target) | Survives as one-person co. |

If M1 is not hit by Day 90, the failure is almost always **distribution + offer**, not “missing features.”

---

## 2. Mainstream Indie Monetization Paths

### 2.1 Comparison matrix

| Path | Cash speed | Support load | Best for | Avoid when |
|------|------------|--------------|----------|------------|
| **Stripe Checkout / Payment Link** | Fast | Low–med | Single SKU SaaS or digital tool | Need complex tax/VAT handling alone |
| **Merchant of Record** (Lemon Squeezy, Paddle) | Fast | Low | Global tax + VAT without headache | Ultra-thin margins / heavy custom billing |
| **Subscription (MRR)** | Medium | Medium | Ongoing value, updates, cloud/API | Tool is “set and forget” once |
| **One-time / buyout** | Fast | Low if stable | Finite utilities, CLI, templates | Expect continuous infra cost |
| **API metered** | Medium–slow | Medium | Clear usage unit (tokens, seats, jobs) | No observability / cost control |
| **Credits pack** | Medium | Low–med | AI wrappers with COGS | Users hate opaque credit math |
| **Freemium** | Slow cash | High | Strong viral loop already exists | Early stage with zero audience |
| **Open-core** | Slow | High | Dev-tool with clear paid gate | You need revenue this quarter |
| **Services → product** | Fastest cash | High initially | Domain expertise (your Java/AI edge) | You never productize (stay stuck in hours) |

**Default stack for this company (Phase 1):**

1. **Stripe Payment Link** or Lemon Squeezy for first SKU  
2. **One paid plan only** (monthly **or** lifetime — pick one)  
3. Optional: tiny free “preview” that does **not** replace the paid outcome  
4. Manual license / access grant until ≥ 10 customers

---

### 2.2 Stripe integration — minimum viable money

**Week-1 checklist (no custom billing portal yet):**

1. Stripe account + USD settlement path cleared (personal/company as applicable)  
2. Product + Price created in Dashboard  
3. **Payment Link** or Checkout Session with success/cancel URLs  
4. Success page: “Access within 24h” + email collection  
5. Webhook **or** manual Stripe dashboard check → grant access (Airtable/Notion OK)  
6. Refund policy published (7–14 days)

**Ship later (after M2):** Customer Portal, trials, prorations, tax automation, usage meters.

**Do not build first:** Full billing microservice, seat management UI, invoice PDF engine.

---

### 2.3 Buyout vs Subscription — decision tree

```text
Does the product create ongoing cloud/API COGS or frequent updates users expect?
  ├─ YES → Subscription (or credits)
  └─ NO  → Prefer one-time / lifetime with clear “updates for 12 months” clause

Is churn psychology high (tool used weekly)?
  ├─ YES → Monthly/annual SaaS
  └─ NO  → Buyout may convert better

Do you need predictable MRR for runway planning?
  ├─ YES → Push annual subscription hard (2 months free)
  └─ NO  → Buyout OK for first cash
```

| Model | Example price | Positioning line |
|-------|---------------|------------------|
| Monthly | $49/mo | “Cancel anytime. ROI in week one.” |
| Annual | $490/yr | “Two months free. Founder plan.” |
| Lifetime | $199–$499 | “Pay once. Updates for 12 months.” |
| Hybrid | $29/mo or $249 lifetime | Only after you see which cohort converts |

**Recommendation for first offer:**  
- If AI/API COGS: **$29–$99/mo** or credit packs  
- If offline/CLI/template: **$79–$249 one-time**

---

### 2.4 API / usage-based billing

Use when the buyer already thinks in units: requests, seats, repos, jobs, tokens.

| Design rule | Practice |
|-------------|----------|
| Unit must be understandable | “per 1,000 jobs” beats “per compute second” early on |
| Soft cap + hard cap | Soft: email warning; Hard: stop at 120% with upgrade CTA |
| Include a base plan | e.g. $39/mo includes 10k units, then overage |
| Show COGS | Track provider cost per unit; target ≥ **70%** gross margin |
| Abuse controls | API keys, rate limits, per-account quotas from day one of API |

**MVP metering (acceptable hacks):**  
Daily cron counting rows in DB → Stripe metered items later. Spreadsheet is fine for first 20 customers.

---

## 3. Lean Strategy: Validate Before You Build

### 3.1 Forbidden until paid intent

- Multi-tenant auth polish  
- Design system / dark mode  
- Mobile apps  
- Public API v1  
- “Platform” plugins marketplace  
- Rewriting for scale

### 3.2 Allowed before code (preferred)

| Artifact | Purpose | Pass signal |
|----------|---------|-------------|
| Problem posts (X/Reddit/HN Show-adjacent) | Demand sniff | Problem-rich comments |
| Interview script (10 questions) | Language of pain | Budget quotes |
| Landing page (1 screen) | Offer clarity | Waitlist + price reaction |
| Figma / Loom demo | Fake product | “When can I buy?” |
| Concierge service | Real delivery | Paid invoice |
| Pre-sale checkout | Hard validation | Stripe success |

### 3.3 Pre-sale playbook (7 days)

| Day | Action |
|-----|--------|
| 1 | Write offer: who / pain / outcome / price / guarantee |
| 2 | Landing: headline, 3 bullets, price, CTA, FAQ (refund) |
| 3 | Payment Link live (even if fulfillment is manual) |
| 4–5 | 20 warm outreaches + 3 public posts |
| 6 | Follow-ups; book calls for confused buyers |
| 7 | Decide: **ship MVP** / **pivot offer** / **kill** |

**Pre-sale copy skeleton (English):**

> **Headline:** Get [outcome] for [buyer] without [pain].  
> **Sub:** [Specific workflow] in [time]. Built by a senior engineer going indie.  
> **Price:** $X/mo or $Y one-time.  
> **CTA:** Buy early access — fulfillment within 7 days (manual onboarding OK).  
> **Guarantee:** 14-day refund if we fail to deliver the stated outcome.

### 3.4 MVP Landing Page — content spec (one viewport + FAQ)

Must include:

1. **Buyer** in the headline  
2. **Outcome** (time/money/risk)  
3. **Price** (visible without scrolling forever)  
4. **CTA** (Buy / Pre-order / Join paid waitlist)  
5. **Proof** (screenshots, Loom, GitHub activity, founder story — even thin)  
6. **Scope boundary** (“v1 does X, not Y”) to reduce refunds

Optional: email capture **only if** price is still shown (otherwise you train free-tire-kickers).

### 3.5 Concierge → Product bridge

```text
Paid concierge (Week 1–4)
  → Checklist of repeated steps
  → Scripts / AI prompts / templates
  → Thin web UI around the painful step
  → Self-serve checkout
```

Every feature in the product backlog must map to a step you already got paid to do manually.

---

## 4. Packaging & Offer Design

### 4.1 Single SKU rule

Until **10** paying customers: **one** paid offer.  
Add tiers only when customers ask for a higher ceiling (seats, limits, SSO later).

### 4.2 Guarantee that sells (and you can honor)

| Guarantee | Use when |
|-----------|----------|
| 14-day refund | Digital goods / SaaS |
| “Setup call included” | First 20 customers |
| “Outcome or refund” | Concierge / service-led | Keep definition of outcome written |

### 4.3 Free tier policy (strict)

Allow free **only if** one is true:

- Free is a **demo with watermark / export locked**, or  
- Free drives distribution you can measure (templates that link back), or  
- Free is time-limited trial (7–14 days) with card optional

Otherwise: **no free plan**.

---

## 5. Unit Economics Sketch

Track weekly after first sale:

| Line | Formula / note |
|------|----------------|
| ARPU | Revenue / paying accounts |
| COGS | Hosting + AI API + MoR fees |
| Gross margin | (Revenue − COGS) / Revenue → target **≥ 70%** |
| Support minutes / customer | Cap early; automate FAQ |
| CAC | Mostly time: hours × opportunity cost; keep **$0 ad** until M2 |
| Payback | For sub: months to recover CAC; aim **< 2 months** of founder time equivalent |

**Kill / reprice if:** Gross margin < 50% with no path to cut COGS within 30 days.

---

## 6. Compliance & Trust (lightweight, Day 1)

- Public Terms + Privacy (simple templates OK)  
- Clear “who we are” (Build in Public founder page)  
- Support email that you actually answer within 48h  
- No dark patterns on cancel (for subscriptions)

Trust converts better than another feature.

---

## 7. Decision Log Template

```text
Date:
Offer:
Price:
Channel that produced interest:
Paid? Y/N amount:
Fulfillment method:
Lesson:
Next experiment:
```

Store copies under `docs/04-indie-log/` weekly reviews.

---

## 8. Linkage

| Doc | Role |
|-----|------|
| [`../01-market-research/business-framework.md`](../01-market-research/business-framework.md) | Funnel gates before monetization |
| [`services-offer-graalvm.md`](services-offer-graalvm.md) | **Cash track**: fixed-price GraalVM consulting (parallel to SaaS) |
| [`services-offer-trading-discipline.md`](services-offer-trading-discipline.md) | **Interest track**: trading discipline cohort (non-advisory, ≤4h/wk) |
| [`../03-growth-and-automation/tea-promotion-one-pager.md`](../03-growth-and-automation/tea-promotion-one-pager.md) | TEA open-source promotion (engineering angle) |
| [`../03-growth-and-automation/distribution-channels.md`](../03-growth-and-automation/distribution-channels.md) | Where buyers come from at $0 ads |
| [`../04-indie-log/roadmap-and-milestones.md`](../04-indie-log/roadmap-and-milestones.md) | Week-by-week revenue KPIs |

---

*If you are coding more than selling, you are volunteering — not founding.*
