# Personalization Framework

## Overview

This document maps the dimensions along which content gets personalized. The goal is to identify the **minimum viable profile** that produces a genuinely different experience — not a horoscope, but a real shift in how the material lands.

## Personalization Dimensions

### 1. Dominant Immortality Project(s)

The most important dimension. Everyone has a pie chart (see Chapter 6). Knowing someone's primary and secondary projects determines:
- Which chapter/topic serves as the entry point
- Which examples and analogies resonate
- What language feels natural vs. alienating

**How to assess:** Direct questions about what they spend time on, what they care about most, what they'd want to be remembered for. Could also be inferred from profession, hobbies, life stage.

**Examples of how output changes:**
- Someone heavy on Biological → lead with health, family, evolutionary biology examples
- Someone heavy on Creative → lead with art, music, the "love for the game" angle
- Someone heavy on Community → lead with belonging, religion, nationalism, sports fandom
- Someone heavy on Status → lead with legacy, Oppenheimer-style narratives, social dynamics
- Someone heavy on Natural → lead with nature experiences, cosmic perspective, interconnection

### 2. Life Stage / Context

Where someone is in life shapes what questions feel urgent. A college student, a new parent, someone grieving, someone in a midlife crisis, and a retiree all have different relationships to mortality and meaning.

**How to assess:** Age range, major recent life events, what question or situation brought them here.

**Examples of how output changes:**
- New parent → Biological Project feels immediately relevant; Experiential Transcendence through birth is a powerful hook
- Recent loss → Careful tone; the "death is boring" framing needs different handling
- Career-focused 20-something → Status and Creative Projects as entry; biological may feel distant
- Retiree → Legacy thinking; Natural Project may resonate more strongly

### 3. Intellectual Entry Point (grounded in validated constructs, NOT "learning styles")

Some people are moved by a tight argument; others by a story; others by a concrete everyday scene. The same idea can be expressed through evolutionary biology, an extended narrative, or "here's what happened last Tuesday."

> **Important — what this dimension is and isn't.** This is *not* the popular "learning styles" idea (visual/auditory/kinesthetic). That model, and its "meshing hypothesis" (that matching delivery to a person's style improves outcomes), has been repeatedly tested and **fails** — see Pashler et al.'s 2008 review for the Association for Psychological Science. We are not claiming people *learn better* from a matched version. We're claiming they *engage with and are persuaded by* it more — a different, well-evidenced effect.

**The constructs that actually predict this** (and that the Stage 0 intake borrows items from — see [stage0-intake.md](working/stage0-intake.md)):

- **Need for Cognition (NFC)** — how much someone enjoys effortful thinking. Per the Elaboration Likelihood Model, high-NFC readers are persuaded by strong arguments processed carefully (central route); low-NFC readers lean on peripheral cues like tone, story, and vividness. *(Cacioppo & Petty, 1982; 6-item short form available.)*
- **Transportability** — the trait tendency to get absorbed in narrative. Research shows people are persuaded by stories *only to the degree they're transportable*, and the effect is unique to narratives — it doesn't transfer to argument-based writing. This is the empirical backbone of the story-vs-argument split.
- **Openness/Intellect** (Big Five facet) — high openness prefers abstract, theoretical, novel framing; lower openness prefers concrete, practical, conventional presentation. Governs construal level (how abstract vs. grounded the prose is).

These three correlate and collapse into roughly **one axis: Analytical ↔ Narrative.** That's convenient — the intake doesn't need three separate scales.

**How to assess:** A few borrowed scale items (see [stage0-intake.md](working/stage0-intake.md)), not full questionnaires.

**Examples of how output changes:**
- Analytical end → argument-first, more depth (Dawkins/Feynman-level), let the reader chew on it; abstract framing
- Narrative end → open inside a scene, let the idea emerge from story, keep argumentation light; concrete, everyday framing

### 4. Format Preference

How someone prefers to consume content. This is less about personalization of the *ideas* and more about the delivery vehicle.

**Options (in order of current feasibility):**
- Long-form text (personalized book/chapters)
- Short-form text (daily insights, feed-style)
- Audio (podcast-style, conversational or narrated)
- Video (short-form reels, longer essay-style)

### 5. Tone Calibration

The book's voice is conversational-nihilist-optimistic. But within that, there's a spectrum. Some people respond to more irreverence ("fuck enlightenment"), others need a gentler on-ramp.

**How to assess:** Harder to ask directly. Could be inferred from other dimensions or offered as a preference (casual vs. reflective).

---

## Minimum Viable Profile (Proposed)

Not all five dimensions carry equal weight. For Phase 1, the MVP profile is **two dimensions**:

1. **Dominant Immortality Project** — This is the single highest-leverage input. It determines entry point, examples, and language. It's also the easiest to assess (a few direct questions).
2. **Intellectual Entry Point** — This determines *how* ideas are expressed (science vs. stories vs. philosophy vs. personal experience). Combined with the dominant project, this gives us a meaningful 5×4 matrix of 20 profile types.

**What we're deferring:**
- **Life stage** — Valuable but adds combinatorial complexity. Can be layered in Phase 2 once we've proven the core two dimensions work.
- **Tone calibration** — Hard to assess via intake. Start with the book's natural voice (conversational-nihilist-optimistic) and only introduce tone variation if testing shows it matters.
- **Format preference** — Phase 1 is text-only, so this is moot until audio/video.

**Why this works:** If someone's dominant project is Creative and their entry point is stories/narrative, we know enough to choose their chapter order, swap in relevant analogies, and skip the deep evolutionary biology. That should produce a noticeably different experience from someone who's Status-dominant and science-oriented. If testing shows it doesn't, the framework has a bigger problem than adding more dimensions would solve.

---

## Open Questions

- [ ] How many questions is too many for the intake? Need to balance profile quality against friction.
- [ ] Can we infer dimensions from behavior rather than asking? (e.g., which free chapters they read first)
- [ ] How do we handle people whose profile changes over time? Is the product a one-time snapshot or does it evolve?
- [x] What's the minimum personalization that produces a noticeably different experience? **Proposed answer: dominant project + intellectual entry point (see Minimum Viable Profile section above).** Still needs validation through testing.
- [ ] Should the intake itself be part of the experience? (i.e., the questions themselves start teaching the framework)

## What "It Works" Actually Means (Validation Criteria)

This framework is a hypothesis. It's only worth anything if the dimensions it picks produce output that readers can feel. Before testing, commit to what counts as success — otherwise any result can be rationalized as "kind of working."

Under the current plan (see [tasks.md](tasks.md)), this gets measured two ways: an early **internal gut-check** (Stage 4 — the author and a couple of friends read a personalized arc against the generic version, using the blind-comparison material in `working/`), and then **at scale on real traffic** (Stage 5 — the personalized cohort's read depth/completion/conversion vs. the control cohort). The criteria below apply to both.

- **The framework is validated if:** readers can reliably identify which version was written "for someone like them," they *prefer* that version to the generic control, and the preference is strong enough that a couple say they'd pay. This means the two MVP dimensions are doing real work.
- **The framework is wrong (not the premise) if:** readers feel a difference but it doesn't track the *profiles* — i.e., the variations differ in quality or randomness, not in a way that maps to dominant project × entry point. → The dimensions chosen are weak; revisit which dimensions to personalize on.
- **The premise is wrong (not just the framework) if:** readers can't distinguish the versions at all, or the generic control wins (in the gut-check or the cohort data). → No choice of dimensions fixes this. The fallback is clean: the completed book still stands as a free product (see [README.md](README.md) — the book is worth finishing regardless).

Distinguishing "wrong dimensions" from "wrong premise" matters: the first says try different inputs, the second says stop.

## Next Steps

1. Write 2-3 versions of the same chapter (suggest Gradient Analysis — early, universal, clear variable potential) varying by dominant project × entry point, plus keep the generic version as a control. These hand-crafted versions serve double duty: running the validation test above *and* becoming few-shot examples for the AI pipeline if it passes.
2. Run the blind test with real people against the criteria above.
3. **Only if it passes:** design the prototype intake questionnaire — **3-5 questions** mapping to dominant project and intellectual entry point. Keep it tight; more dimensions layer in later.
