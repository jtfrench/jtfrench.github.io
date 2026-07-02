# Tasks

## How This Works

Running task list for Monkeys in Shoes. The sequencing reflects a deliberate **"complete the book, then distribute a substantial product"** strategy (see [README.md](README.md) for the reasoning). Two facts shape the order:

1. **The book is worth finishing regardless of the personalization bet** — so content completion leads, and is never at-risk effort.
2. **Cold distribution (Reddit, paid ads) is a one-shot first impression** — so we don't spend it on a thin payload; we finish and instrument first.

Work top-down. Two safeguards (internal gut-check before paid spend; instrument before traffic) are baked into the relevant stages, not left to chance.

See [README.md](README.md) for the one real bet and the guiding principles.

---

## 🟢 STAGE 1: Finish the Book (worthwhile regardless)

*This is the baseline deliverable. Even if personalization never ships, this stage produces a complete free book and website. No part of it is wasted.*

### Content completion
- [ ] **Finish Chapter 5 (The Immortal Replicator):** placeholder sections ("How do we do it?", "The Emergence of Symbols") are empty. Load-bearing — the framework depends on it. **Start here.**
- [ ] **Flesh out Chapter 8 (Status Project):** more rough essay than structured chapter. Needs concrete examples and clearer framework connection.
- [ ] **Flesh out Chapter 9 (Creative Project):** very short. The "art as novelty" idea is strong but underdeveloped.
- [ ] **Flesh out Chapter 10 (Community Project):** sports/nationalism are decent starts; religion section could expand.
- [ ] **Consistency pass:** voice, cross-references, formatting, permalink patterns across all 13 chapters.

### 🚩 MILESTONE: Complete book
*A polished, finished free book/website. Shippable and shareable on its own. This alone justifies the project to date.*

---

## 🟠 STAGE 2: Build First-Cut Personalization (the bet)

*Now layer personalization on top of the finished book. Keep a generic version intact as the control cohort — we need both to measure whether personalization lands.*

- [ ] **Finalize the intake.** The 3-5 question instrument already drafted in [working/stage0-intake.md](working/stage0-intake.md) becomes the live entry gate (dominant project + analytical↔narrative axis).
- [ ] **Develop the generation/assembly approach** across all chapters. Use the five hand-written variations in [working/stage0-gradient-variations.md](working/stage0-gradient-variations.md) as voice anchors / few-shot examples. Per the hybrid approach in [technical-stack.md](technical-stack.md): fixed core ships as-is, variable examples/tone are generated or assembled.
- [ ] **Define content modules** across the book — fixed vs. variable blocks per [content-architecture.md](content-architecture.md).
- [ ] **Preserve a generic version** as the control. Every reader is tagged personalized or control so engagement can be compared later.

### 🚩 MILESTONE: Personalized book + control both exist

---

## 🔵 STAGE 3: Instrument Everything (before any traffic)

*Safeguard 2. This must be in place BEFORE distribution — the first wave of real visitors is the most valuable signal and must not go unmeasured.*

- [ ] **Page-level analytics:** pageviews, scroll/read depth, chapter completion, drop-off points.
- [ ] **Cohort tagging:** personalized vs. control, so engagement can be compared like-for-like.
- [ ] **Funnel events:** intake start/finish, entry into the reader, depth reached, any paid-conversion intent.
- [ ] **Graceful degradation:** Reddit traffic and tracker-blockers strip analytics — ensure core metrics still work for a meaningful fraction, and don't rely on any single tracker.

### 🚩 MILESTONE: Instrumented and ready to measure both signals (does personalization land? does the funnel work?)

---

## 🟣 STAGE 4: Internal Gut-Check (before spending money)

*Safeguard 1. Cheap, fast, and the last off-ramp before paid distribution.*

- [ ] **Read your own arc.** The author reads their profile's full personalized arc against the generic version. Can you feel the difference across a whole book, not just one chapter?
- [ ] **A couple of friends do the same.** The [working/stage0-test.html](working/stage0-test.html) blind-comparison tool can be repurposed here for a quick structured read.
- [ ] **Decide:** if even the author/friends can't feel it, fix the personalization methodology before Stage 5. If it lands, proceed.

---

## 🔴 STAGE 5: Distribute & Measure

*Only now spend distribution energy — on a complete, polished, instrumented product.*

- [ ] **Reddit first (free, high-signal dry run).** Post to relevant communities (philosophy, existentialism, optimistic nihilism, self-improvement-adjacent). Watch engagement, read comments, treat it as a rehearsal before paid spend.
- [ ] **Small paid social test.** Modest budget. Compare against Reddit learnings.
- [ ] **Measure both signals together:**
  - *Does personalization land?* → personalized cohort vs. control: read depth, completion, conversion.
  - *Does the funnel work?* → arrival, intake completion, retention, willingness to pay.
- [ ] **Pricing validation** once there's real willingness-to-pay signal.
- [ ] **Legal basics:** privacy policy for data collection, terms of service.

---

## ⚪ STAGE 6: Future (track, don't plan in detail yet)

- [ ] Audio pipeline (TTS)
- [ ] Video / short-form exploration
- [ ] Payment integration (Stripe)
- [ ] User accounts vs. unique links
- [ ] Gift/share model
- [ ] Partnerships (therapy, education, corporate)

---

## Completed

*(Stage 0 validation tooling — intake, five matched variations, blind-test page — was built and now feeds Stages 2 and 4 as voice anchors and the gut-check tool.)*

---

## Notes

- Reference the relevant `_business/` doc for context on any task.
- `.claude/writing-guide.md` is the voice bible — always check it.
- Chapters in `_chapters/` are the source of truth for the theory.
- The book stands on its own. If the personalization bet fails at Stage 4 or 5, Stage 1's output remains a complete, valuable free book — by design.
