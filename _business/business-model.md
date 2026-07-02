# Business Model

## Overview

Revenue model, pricing strategy, funnel design, and go-to-market thinking for the personalized Monkeys in Shoes product.

> **Status: hypotheses, refined by real engagement data.** The strategy is to finish the book, build a first-cut personalization layer, instrument it, then distribute a *complete* product and measure (see [README.md](README.md) and [tasks.md](tasks.md)). Pricing and tier specifics below remain informed guesses until distribution produces real willingness-to-pay and engagement signal. The book itself is a committed deliverable regardless; only the personalization layer and its monetization are the bet.

## The Funnel

```
Free website (monkeyinshoes.com)
  → Reader discovers framework, recognizes themselves in it
    → CTA: "Get your personalized version"
      → Intake questionnaire (3-5 questions for MVP; see personalization-framework.md)
        → Payment (fixed fee)
          → Personalized content delivered
```

The free site does the heavy lifting of proving the ideas are worth engaging with. The paid product answers: "What does this mean for *me specifically*?"

## Pricing

### Model: One-Time Fixed Fee

Not a subscription. You're buying a product — your personalized version of the book/content.

**Rationale:**
- Subscriptions create pressure to produce ongoing content, which dilutes quality
- A one-time fee aligns with the philosophy: here's something valuable, take it or leave it
- Lower barrier than subscription for an unfamiliar brand
- Feels more like buying a book (familiar mental model)

**Pricing considerations:**
- A physical book costs $15-30
- A premium ebook/course costs $30-100
- A personalized product has perceived higher value
- **Starting range to explore:** $20-50 for text, $40-80 with audio

### Potential Upsell / Tiers

| Tier | What You Get | Price Range |
|------|-------------|-------------|
| Core | Personalized text (web reader + PDF) | $20-30 |
| Audio | Core + narrated audio version | $40-50 |
| Premium | Core + Audio + short-form video series | $60-80 |

These are starting hypotheses. Need to validate with actual willingness-to-pay research.

### Rough Unit Economics (Sanity Check)

Per the [technical stack](technical-stack.md), generating a full personalized book (~30k words) is roughly 40-50k output tokens via the Claude API. At current pricing (as of early 2026, subject to change):

| Cost Component | Estimate per User |
|---|---|
| AI text generation (Claude API) | ~$3-6 |
| TTS (audio tier, e.g. ElevenLabs) | ~$5-15 depending on length |
| Hosting/storage (negligible at low volume) | <$0.10 |
| Payment processing (Stripe ~3%) | $0.60-2.40 |

**Core tier ($20-30):** ~$4-7 cost → **~75% margin.** Healthy.
**Audio tier ($40-50):** ~$10-22 cost → **~50-75% margin.** Workable, but TTS costs are the swing factor. Need to get actual quotes.

These numbers assume no human review step. If we add manual QA (see [technical-stack.md](technical-stack.md) quality control section), the cost structure changes significantly — even 10 minutes of human review at $30/hr adds $5/unit, which is fine for Core but starts squeezing Audio margins.

**Bottom line:** Pricing is viable at these ranges *if* the generation pipeline is reliable enough to not require heavy human intervention. This reinforces that quality control strategy is a business-critical decision, not just a technical one.

## Target Audience

### Primary: "Curious Questioners"

People who are already asking "why" questions about life, meaning, motivation. They've probably consumed some combination of:
- Pop psychology (Thinking Fast and Slow, Sapiens, Atomic Habits)
- Philosophy-lite (School of Life, existentialist TikTok, Alan Watts clips)
- Self-improvement content but are getting disillusioned with the prescriptive nature of it

They're looking for a framework that explains without prescribing. The mantra "not good, not bad, just is" is the antidote to the self-help industrial complex.

### Secondary: "Life Transition" Moments

People going through something that forces mortality/meaning questions to the surface:
- New parents
- Career changes or crises
- Loss/grief
- Milestone birthdays
- Post-religion (deconstructing faith)

These people have high motivation to engage and a specific context that personalization can speak to directly.

## Go-to-Market

The full sequenced plan lives in [tasks.md](tasks.md). The strategy is **complete, then distribute**: finish the book, layer on first-cut personalization, instrument it, gut-check internally, then put a substantial product in front of cold audiences. The short version:

1. **Finish the book** (Stage 1) — worthwhile regardless of the bet.
2. **Build first-cut personalization + control** (Stage 2).
3. **Instrument everything** (Stage 3) — before any traffic.
4. **Internal gut-check** (Stage 4) — before spending money.
5. **Distribute & measure** (Stage 5) — Reddit first, then small paid social.

### Distribution: Reddit first, then paid social

We distribute a *complete* product, not a one-chapter experiment, because cold traffic is a one-shot first impression. Sequence:

- **Reddit (free, first).** A high-signal dry run in relevant communities (philosophy, existentialism, optimistic nihilism, adjacent self-improvement spaces). Read the comments, watch engagement, learn the messaging — all before spending a dollar. Caveat: Reddit referral traffic and tracker-blocking strip a lot of analytics, so instrumentation must degrade gracefully and not depend on any single tracker.
- **Small paid social test (second).** Modest budget, informed by what Reddit taught us. Paid lets us control the audience and test willingness-to-pay deliberately.

### Measuring both signals at once

The instrumentation (Stage 3) is designed so the same traffic answers two questions simultaneously:

- **Does personalization land?** (the product bet) — compare the *personalized cohort* against the *control cohort* on read depth, chapter completion, and conversion. This is the richer successor to the early blind-comparison test: real behavior at scale instead of self-reported survey answers.
- **Does the funnel work?** (the distribution bet) — standard funnel analytics: arrival → intake completion → reading depth → retention → willingness to pay.

If personalization doesn't move the cohort comparison, the fallback is clean: the completed book remains a valuable free product, and no content effort was wasted because the book was worth finishing anyway.

---

## Competitive Landscape

There isn't a direct competitor doing "personalized philosophy books via AI." Adjacent spaces:

- **Self-help books:** One-size-fits-all. No personalization. Prescriptive.
- **AI chatbots (Character.ai, etc.):** Interactive but no structured framework. Conversational, not educational.
- **Online courses (Masterclass, etc.):** Video-based, not personalized. Passive consumption.
- **Therapy/coaching:** Personalized but expensive, ongoing, and positioned as treatment not exploration.
- **Personality tests (MBTI, Enneagram):** Personalized output but shallow. The framework here is deeper and less reductive.

The positioning is somewhere between a book and a coaching session: structured depth + personal relevance.

---

## Open Questions

- [ ] What's the right price point? Need to talk to potential users.
- [ ] Is the free site enough top-of-funnel, or do we need additional content marketing (social, podcast)?
- [ ] How do we communicate "personalized" without it sounding gimmicky?
- [ ] Legal considerations: do we need terms of service, privacy policy for user data collection?
- [ ] Should we consider a "gift" model? (Buy a personalized version for someone else — fill out the profile for them)
- [ ] International/language considerations: is the content culturally portable? Could we localize?
