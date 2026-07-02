# Monkeys in Shoes — Product Vision

## What This Is

Monkeys in Shoes is a free Jekyll-based website/book exploring human motivation through the lens of Immortality Projects (grounded in the work of Ernest Becker and Robert Jay Lifton). The longer-term vision is to evolve it into a **personalized content product** where the core framework adapts to each individual reader.

## Two things, deliberately separated

This project is really two efforts stacked on top of each other, and keeping them distinct is what keeps the plan sane:

1. **The book.** Finishing Monkeys in Shoes is worth doing *for its own sake.* The author wants this book to exist regardless of whether it ever becomes a personalized product. That means time spent completing and polishing chapters is **never wasted effort** — it is the baseline deliverable, and it stands on its own as a free book and website.
2. **The personalization layer.** Turning the finished book into a per-reader personalized experience is the *only* part of this that is a genuine bet. It may land or it may not. If it doesn't, the book still exists and still has value.

This reframing matters because it dissolves the usual "don't build before you validate" tension. The thing that would normally be risky to build first — the content — is something the author is committed to either way. So the sequence below leads with completing the book, and treats personalization as a layer added on top of a thing that's already worthwhile.

## The Core Idea (the personalization layer)

People don't all arrive at the same ideas through the same door. The Immortality Projects framework is universal — everyone has projects — but the examples, entry points, tone, and format that make the ideas click vary from person to person. AI makes it feasible to generate those different versions at scale.

**Think of it as:** a book written specifically for you. Same underlying theory, tailored stories, analogies, and framing.

> **The one real bet:** A reader who gets a version tailored to their dominant immortality project and how they think engages *meaningfully more* — reads deeper, finishes more, and would pay — than a reader given the generic version. The book's value is not a bet; this is.

## The Plan in One Paragraph

Finish the book (worthwhile regardless) → build a first-cut personalization layer across all chapters, keeping a generic version as a control → instrument everything so real traffic tells us both whether personalization lands *and* whether the funnel works → a cheap internal gut-check before spending money → then distribute properly (Reddit first, then a small paid social test) and watch engagement page-by-page, personalized cohort vs. control. Full sequence in [tasks.md](tasks.md).

This is a "complete, then distribute" approach: we put a substantial, polished product in front of cold audiences rather than a thin one-chapter experiment, because cold traffic (Reddit, paid ads) is a one-shot first impression that a single chapter would waste.

## Two Safeguards (so a big build stays survivable)

Because this plan front-loads more effort than a validate-first approach, two cheap safeguards keep it from becoming "find out it failed after months":

1. **Internal gut-check before any paid distribution.** Once personalized chapters exist, the author (and a couple of friends) read their own profile's full arc against the generic version. If even the author can't feel the difference across a whole book, fix the methodology *before* spending ad budget. Costs an evening, not a sprint.
2. **Instrument from day one.** Page analytics and personalized-vs-control cohort tagging must be built *before* traffic arrives — otherwise the first and most valuable wave of real visitors goes unmeasured. Instrumentation is part of building the payload, not a follow-up.

## Business Model (High Level)

- **Free tier:** The completed website/book. Top-of-funnel and a standalone deliverable in its own right.
- **Paid product:** Fixed one-time fee for a personalized version. Not a subscription — you buy *your version*, like commissioning a portrait vs. buying a print.
- **Format flexibility:** Personalized output could later be book, podcast, video, or short-form feed. Format expansion stays post-distribution. Text first.

See [business-model.md](business-model.md) for detail. Pricing specifics remain hypotheses until there's real engagement data.

## Current Status

- Website live at monkeyinshoes.com (domain singular, product name plural — intentional), 13 chapters in varying states of completion.
- Writing voice/style guide established (`.claude/writing-guide.md`).
- Core theory covers: Gradient Analysis, Theory of Relativity (experience), The Immortal Replicator, five Immortality Projects, Experiential Transcendence.
- Several chapters still thin (5, 8, 9, 10). **Finishing these is the current priority** — and is worthwhile regardless of the personalization bet.

## Folder Map

Two tiers. **Strategy docs** (top level) are durable reference. **Working artifacts** (`working/`) are stage-specific execution files. If a doc is lasting reference → top level; if it's the output of a specific step → `working/`.

### Strategy docs (durable reference)

| Document | Purpose |
|----------|---------|
| [tasks.md](tasks.md) | **Start here.** The sequenced plan. |
| [personalization-framework.md](personalization-framework.md) | What dimensions of a person change the output, and how |
| [content-architecture.md](content-architecture.md) | Fixed vs. variable content, modular structure |
| [analogy-tags.md](analogy-tags.md) | The in-source tag convention that marks swappable analogies inside the chapter files (implements content-architecture Layers 3–4) |
| [technical-stack.md](technical-stack.md) | Generation pipeline, instrumentation, delivery infrastructure |
| [business-model.md](business-model.md) | Pricing, funnel, distribution, go-to-market |

### Working artifacts ([`working/`](working/))

Stage-specific execution files. See [`working/README.md`](working/README.md).

| Document | Purpose |
|----------|---------|
| [working/stage0-intake.md](working/stage0-intake.md) | The 5-question reader intake (also reusable as the live intake gate) |
| [working/stage0-gradient-variations.md](working/stage0-gradient-variations.md) | Five hand-written matched variations + control — voice anchors for the AI layer and material for the internal gut-check |
| [working/stage0-test.html](working/stage0-test.html) | Self-contained blind-comparison test — repurposable as a quick internal gut-check tool |
| [working/stage0-test-README.md](working/stage0-test-README.md) | How to deploy and read the test |

## Key Risks & Contingencies

1. **Personalization doesn't land.** The one real bet. Mitigated by the internal gut-check (Safeguard 1) *before* paid distribution, and by cohort instrumentation that measures it on real traffic. Fallback if it fails: the completed book still stands as a free product — no effort wasted, because the content was worth completing anyway.
2. **AI can't hold the voice.** The style is distinctive; generic AI output defeats the purpose. The five hand-written variations in `working/` are the voice anchors. Test on a few generations early. Fallback: lean toward assembly (more hand-written, less generation — Option B in [technical-stack.md](technical-stack.md)).
3. **Distribution doesn't convert.** Cold traffic may not arrive, stay, or pay. This is why we distribute a *complete* product (stronger first impression) and start with free Reddit distribution as a dry run before spending on ads. Reddit and tracker-blocking will strip some analytics — instrumentation must degrade gracefully.
4. **Intake friction.** If readers bounce at the questionnaire, the funnel breaks. Keep it to 3-5 engaging questions.

## Guiding Principles

1. **The book is worth finishing regardless.** Completing chapters is never wasted effort; it's the baseline deliverable. Only the personalization layer is a bet.
2. **Distribute something substantial.** Cold audiences are a one-shot first impression — don't spend them on a thin payload.
3. **Instrument before you distribute.** Unmeasured launch traffic is lost signal.
4. **Personalization should deepen understanding, not just comfort.** Meet people where they are so they see further — not confirm what they believe.
5. **Quality over novelty.** The writing voice matters. Generic AI output defeats the purpose.
6. **The theory is the product.** Format is delivery. If the framework isn't compelling on its own, personalization can't fix that.
