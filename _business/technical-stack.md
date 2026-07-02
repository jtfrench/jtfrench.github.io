# Technical Stack

## Overview

Notes on the AI generation pipeline, delivery infrastructure, and technical decisions for the personalized content product.

> **What's needed, in plan order.** Per [tasks.md](tasks.md), the build sequence is: finish the book (no new tech), then (Stage 2) the **generation/assembly pipeline** that produces personalized chapters + a preserved generic control, then (Stage 3) **instrumentation** — page analytics, scroll/completion depth, and personalized-vs-control cohort tagging — which must be live *before* distribution. Payment, audio, and video infrastructure stay deferred until after distribution proves the funnel. Two design constraints to honor early: keep a clean generic/control version alongside every personalized one, and make analytics **degrade gracefully** (Reddit traffic and tracker-blockers will strip a lot of it). Read the format "Phases" below as a map of where things go, not the build order.

## Current Stack

- **Website:** Jekyll static site, hosted on GitHub Pages
- **Domain:** monkeyinshoes.com
- **Content:** Markdown files in `_chapters/` collection
- **Styling:** Custom CSS, no framework
- **Deployment:** GitHub Actions → GitHub Pages

## Proposed Product Architecture

*Note on terminology: the "Phases" below are **format tiers** (text → audio → video), a different axis from the **Stages** in [tasks.md](tasks.md). Phase 2 (audio) and Phase 3 (video) sit downstream of distributing and measuring the text product.*

### Phase 1: Text-Based Prototype

**Intake → Profile → Generation → Delivery**

```
User answers questions (web form)
       ↓
Profile built (dominant project, life stage, entry point, tone)
       ↓
Content generation pipeline (AI)
  - Selects chapter order
  - Swaps examples/analogies per profile
  - Adjusts tone and depth
       ↓
Output: Personalized text (web reader, PDF, or ePub)
```

**Key Technical Decisions:**

1. **AI Model:** Claude API (Anthropic) — strong at maintaining voice/tone with detailed system prompts; the writing guide already exists as a style reference
2. **Generation approach:** 
   - Option A: Generate each chapter from scratch using the theory + profile as context
   - Option B: Use modular content blocks (pre-written variations) and assemble/adapt them
   - Option C: Hybrid — fixed core passages + AI-generated variable sections
   - **Recommendation:** Start with Option C. Pure generation (A) risks voice drift. Pure assembly (B) limits true personalization. Hybrid gives control where it matters and flexibility where it helps.
   - **How this connects to content architecture:** The variable examples in [content-architecture.md](content-architecture.md) Layer 3 are *directional*, not a library of pre-written blocks to slot in. We write 2-3 hand-crafted reference variations per concept (to anchor voice quality), then use those as few-shot examples for AI generation targeting other profiles. Fixed core content (Layer 1) ships as-is. Variable structure (Layer 2, chapter ordering) is rule-based. Variable examples and tone (Layers 3-4) are where AI generation does the heavy lifting.
3. **Intake form:** Simple web form on the existing site. 3-5 questions for Phase 1, targeting the two MVP dimensions (dominant project + intellectual entry point — see [personalization-framework.md](personalization-framework.md)). Can expand to more dimensions later. Results stored as a profile JSON.
4. **Delivery format (Phase 1):** Web-based reader on monkeyinshoes.com, with option to export as PDF/ePub.

### Phase 2: Audio

**Additional pipeline after text generation:**

```
Personalized text
       ↓
Text-to-speech (AI voice)
       ↓
Output: Podcast-style audio files (MP3)
```

**Considerations:**
- TTS quality is good enough now for narration (ElevenLabs, OpenAI TTS, etc.)
- Conversational/podcast format (two voices discussing the ideas) is more engaging but significantly harder to generate well
- Could offer both: narrated version (easier) and conversational version (harder, premium?)

### Phase 3: Video / Short-Form

**Most speculative. Depends on where AI video tooling is when we get here.**

```
Personalized text + visual direction
       ↓
Video generation or templated animation
       ↓
Output: Short-form clips (TikTok/Reels style) or longer essay videos
```

**Considerations:**
- Short-form is more feasible than long-form video
- Could use existing stock/nature footage + text overlay + voiceover as a simpler approach
- Full AI video generation is evolving fast but not production-ready for this use case yet

---

## Infrastructure Needs

| Component | Phase 1 | Phase 2 | Phase 3 |
|-----------|---------|---------|---------|
| Intake form | Simple web form | Same | Same |
| User profiles | JSON/database | Same | Same |
| AI generation | Claude API | Claude API + TTS API | Claude API + TTS + Video |
| Content storage | File system / S3 | + Audio files | + Video files |
| Delivery | Web reader + PDF/ePub export | + Audio player / podcast feed | + Video player |
| Payment | Stripe (one-time) | Same | Same |
| Hosting | GitHub Pages (free site) + separate app for product | Same | Same |

## Cost Considerations

- **AI generation cost per user:** Depends on token count. A full personalized book (~30k words) would be roughly 40-50k tokens of output. At current Claude API pricing this is manageable per-unit but needs to be factored into pricing.
- **TTS cost per user:** Variable by provider. ElevenLabs charges per character. A full audiobook would be significant — may need to price the audio version higher or optimize generation.
- **Hosting:** Minimal for text. Audio/video storage costs scale with users.

---

## Open Questions

- [ ] Build the product app separately from the Jekyll site, or integrate?
- [ ] How much pre-generation vs. on-demand? Pre-generate common profiles to reduce latency and cost?
- [ ] What's the acceptable wait time for generation? Instant (pre-built) vs. "your book will be ready in X minutes"?
- [ ] Do we need user accounts, or is it a one-time purchase with a unique link?
- [ ] How do we handle quality control? Every generated output should meet the voice standard — do we need a review step? **Proposed approach:** During Phase 2 (soft launch), manually review every output to calibrate the system prompt and catch failure patterns. Build a rubric (voice consistency, factual accuracy of the theory, personalization relevance). Once we can characterize the failure modes, build automated checks for the common ones (e.g., LLM-as-judge pass for voice consistency, keyword checks for theory accuracy). Goal for Phase 3 (public launch): automated QA catches 90%+ of issues, human review only for edge cases or flagged outputs. This keeps margins healthy (see [business-model.md](business-model.md) unit economics) while ensuring quality during the learning phase.
- [ ] Should the writing guide (`.claude/writing-guide.md`) be adapted into a system prompt for the generation pipeline?
