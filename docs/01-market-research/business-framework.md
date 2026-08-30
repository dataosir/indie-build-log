# Business Framework — Global Micro-SaaS Funnel & Niche Filter

**Audience:** Solo operator / lean founder  
**North star:** First paying USD customer → repeatable cashflow  
**Last updated:** 2026-08-28

> 盈利不是“做出产品之后的结果”，而是漏斗每一层被量化验证后的必然结果。  
> Profit is the output of a measured funnel — not a reward for shipping code.

---

## 1. Operating Thesis

| Constraint | Implication |
|------------|-------------|
| One person, finite runway | Only bets that can reach **$1 of revenue** without a team or ad budget |
| Global (USD) market | English surface, Stripe-ready, timezone-agnostic support |
| Senior engineering leverage | Sell **outcomes** (time saved, risk reduced, money made) — not “cool tech” |
| AI as force multiplier | Compress research / content / support; never use AI as the product story alone |

**Kill rule:** If an idea cannot clear the Micro-Niche scorecard below **within 2 weeks of research**, drop it. Do not start a repo.

---

## 2. Commercial Funnel Model

```
Traffic → Validation → Pricing → Monetization → Automation
 获客       验证         定价        变现          自动化
```

Each stage has a **pass/fail gate**. Do not advance until the gate metric is hit.

### Stage A — Traffic（流量）

**Goal:** Put the offer in front of people who already have budget and pain.

| Channel type | Role | Example |
|--------------|------|---------|
| Owned | Compounding asset | Public GitHub log, personal site, email list |
| Earned | Trust + spike | X/Twitter BIP threads, Reddit replies, PH launch |
| Borrowed | Fast signal | Guest posts, newsletter swaps, indie maker Discords |

**Gate (Week 1–3):**  
- ≥ **500** qualified impressions / week on English channels **or**  
- ≥ **30** profile visits from niche communities **or**  
- ≥ **10** DMs / comments that mention the problem (not “cool project”)

**Anti-pattern:** Building in silence for 60 days, then “launching into the void.”

---

### Stage B — Validation（验证）

**Goal:** Prove someone will **pay or pre-commit** before you build the full product.

| Method | What counts as signal | What does NOT count |
|--------|----------------------|---------------------|
| Problem interviews (5–15) | “I pay $X for Y today” / “I’d pay if Z” | “Interesting idea” |
| Waitlist + email | Email + use-case + willingness-to-pay field | Anonymous star on GitHub |
| Fake-door / landing CTA | Click “Buy” / “Join waitlist” with price shown | Pageviews alone |
| Pre-sale / deposit | Stripe payment link / invoice paid | Verbal “sure, maybe later” |
| Concierge / manual MVP | Deliver value via Notion + Zoom + scripts | Polished UI with zero users |

**Gate:** At least **one** of:

1. **3+** written pre-commitments at a stated price, **or**
2. **1** real USD payment (any amount) for a manual/concierge delivery, **or**
3. **50+** waitlist emails with ≥40% answering “would pay $29+/mo” (or equivalent one-time)

**Kill rule:** Soft praise without money language → park the idea. No MVP sprint.

---

### Stage C — Pricing（定价）

**Goal:** Price for **high AOV / low support**, not vanity user counts.

| Principle | Practice |
|-----------|----------|
| Price from buyer ROI | If tool saves 4h/week at $50/h → $200/mo value → charge **$29–$99/mo** without guilt |
| Prefer B2B / prosumer | Companies and freelancers pay; consumers complain |
| Anchor high, offer wedge | Annual plan = 2 months free; lifetime only if support cost is near-zero |
| Show price early | Landing page without price = validation theater |

**Default price bands (USD) for this company:**

| Band | When to use | Target |
|------|-------------|--------|
| $19–$49 / mo | Broad tool, self-serve, low touch | Volume + retention |
| $79–$199 / mo | Niche workflow, clear ROI | **Preferred** |
| $299–$999 one-time | Finite tool, low update burden | Buyout / lifetime |
| $0.01–usage / API | Clear unit economics | Metered power users |

**Gate:** Published price on landing + ≥ **5** people who saw price and still converted to waitlist/buy intent.

---

### Stage D — Monetization（变现）

**Goal:** Cash in, not “activation vanity.”

Minimum viable money stack for global indie:

1. **Stripe** Checkout / Payment Links (or Lemon Squeezy / Paddle if tax/Merchant of Record needed)
2. One SKU first (monthly **or** one-time — not both at day 1)
3. Receipt email + simple license / access grant (even if manual at first)
4. Refund policy ≤ 7–14 days (reduces chargeback anxiety)

**Gate (company-level, 90-day):**  
- **First $1 USD** → celebrate + document  
- Then **$100 MRR or $500 one-time cumulative** before expanding scope

**Anti-pattern:** Free forever tier that attracts support load and zero revenue.

---

### Stage E — Automation（自动化）

**Goal:** Replace founder-as-glue with systems **after** revenue exists.

| Automate only when… | Examples |
|----------------------|----------|
| Same task ≥ 3× / week | Onboarding email, license key, invoice |
| Error cost is low | Status page, usage reset scripts |
| Revenue justifies it | Support macros, churn dunning |

**Sequence (do not invert):**

1. Manual delivery that earns money  
2. Checklist / templates  
3. Scripts / Zapier / n8n / small backend jobs  
4. Productize the automation itself (only if it’s the moat)

**Gate:** Founder hours on ops ≤ **20%** of week while revenue is non-zero — otherwise scope is wrong.

---

## 3. Funnel Dashboard (weekly review)

Copy into weekly indie log:

| Metric | Target (early) | Actual | Pass? |
|--------|----------------|--------|-------|
| Qualified conversations | ≥ 5 / week | | |
| Waitlist / email adds | ≥ 10 / week | | |
| Paid intents (click Buy / reply “I’ll pay”) | ≥ 2 / week | | |
| Revenue (USD) | > 0 by Day 90 | | |
| Hours coding without validation | **≤ 8 / week** until Gate B | | |

---

## 4. Micro-Niche Selection Scorecard

### 4.1 Definition

A **Micro-Niche** is a narrow buyer + painful workflow + existing spend, small enough that a solo founder can own distribution, large enough to clear **$5k–$20k MRR** over time without becoming a VC-scale category war.

### 4.2 Hard filters (must all be YES)

| # | Filter | Pass condition | Fail examples |
|---|--------|----------------|---------------|
| 1 | **USD / global pay** | Buyers routinely pay in USD via card; English OK | Local-only WeChat pay ecosystems as primary |
| 2 | **High willingness to pay** | Budget exists today (SaaS, agencies, freelancers, B2B tools) | “Students might use it” |
| 3 | **High AOV potential** | Path to ≥ **$49/mo** or ≥ **$99** one-time without heroics | $3/mo consumer toys |
| 4 | **Low maintenance** | No 24/7 SLA, no heavy compliance Day 1, no multiplayer realtime core | Trading exchange, medical device, kids social |
| 5 | **Not pure red ocean** | Not “another ChatGPT wrapper / Notion AI / generic CRM” with zero wedge | Me-too without distribution angle |
| 6 | **Founder unfair advantage** | Java/backend/AI/ops skills OR audience OR domain scars | Random trendy niche with zero edge |
| 7 | **Reachable buyers** | Known forums, subreddits, X lists, newsletters, GitHub topics | “Everyone who uses the internet” |

### 4.3 Soft score (0–5 each, max 40)

| Dimension | 5 looks like | 0 looks like |
|-----------|--------------|--------------|
| Pain urgency | Missed deadline / lost money this week | Mild inconvenience |
| Budget owner clarity | Buyer = user = cardholder | Needs 6-month procurement |
| Competition intensity | 1–3 weak tools or DIY spreadsheets | Dominated by well-funded giants |
| Switching cost out of status quo | Spreadsheet hell / agency invoices | Already happy with incumbent |
| Content / SEO surface | Searchable pain phrases | Only brand keywords |
| Build scope to v1 | ≤ 2 weeks to concierge or thin MVP | 6-month platform fantasy |
| Support burden | Self-serve docs + email | Custom onboarding forever |
| Expansion path | Adjacent SKUs / API later | Dead-end single feature |

**Decision:**

- **≥ 28** → enter Validation (Stage B)  
- **20–27** → research 1 more week or merge niches  
- **< 20** → kill / archive

### 4.4 Red-ocean escape tactics (if category is crowded)

1. **Verticalize** — “CI flaky-test triage for Java monorepos” not “AI testing platform”  
2. **Job-to-be-done wedge** — one workflow, one outcome, one integration  
3. **Buyer swap** — sell to agencies/consultants who resell outcomes  
4. **Distribution-first niche** — where you can already get replies in 48h  
5. **Price-up, feature-down** — fewer features, stronger guarantee / SLA lite

---

## 5. 30-Day Research Cadence (executable)

| Week | Output | Artifact |
|------|--------|----------|
| 1 | 10 raw ideas → scorecard → top 3 | Table in this folder |
| 2 | Competitor teardown + pricing screenshots | `niche-<name>-teardown.md` |
| 3 | 8–12 interviews / public threads | Notes + quotes |
| 4 | One landing + price + waitlist OR pre-sale | Live URL + metrics |

**Forbidden until Gate B:** multi-tenant auth, fancy design system, mobile app, “platform” roadmap.

---

## 6. Example Scoring Sketch (template)

```text
Niche: ____________________
Buyer: ____________________
Pain: _____________________
Current spend: $____ / mo
Score total: __ / 40
Hard filters: PASS / FAIL
Next action: Validate / Kill / Merge
```

---

## 7. Linkage to Other Docs

| Next doc | Why |
|----------|-----|
| [`../02-product-mvp/monetization-strategy.md`](../02-product-mvp/monetization-strategy.md) | How cash actually enters the company |
| [`../03-growth-and-automation/distribution-channels.md`](../03-growth-and-automation/distribution-channels.md) | How Traffic stage gets filled at $0 ads |
| [`../04-indie-log/roadmap-and-milestones.md`](../04-indie-log/roadmap-and-milestones.md) | 90-day milestones tied to this funnel |

---

*Framework owner: one-person company. Review every Sunday. Kill ideas early.*
