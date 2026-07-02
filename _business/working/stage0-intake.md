# Stage 0 Intake Questionnaire (Validation Prototype)

## What this is

A **5-question** reader intake for the Stage 0 validation test (see [tasks.md](../tasks.md)). It is deliberately *not* a full psychometric battery — it borrows a handful of items from validated instruments and adapts the language to fit the book's voice. The goal is to sort a reader onto two axes cheaply, with minimal friction, while resting on constructs that actually have evidence behind them (unlike "learning styles" — see [personalization-framework.md](../personalization-framework.md)).

The two axes it produces:

1. **Analytical ↔ Narrative** — *how* this person likes ideas delivered. Built from Need for Cognition + Transportability + Openness items, which research shows correlate and load onto roughly one engagement-preference dimension.
2. **Dominant Immortality Project** — *which* examples and analogies land. The book's own framework; categorical, not a spectrum.

> Note on honesty in marketing: these constructs predict *engagement and persuasion preference*, not learning outcomes. The intake sorts people toward the version they'll most enjoy and be moved by — not a version they'll "learn better" from. Keep product claims on that side of the line.

---

## The Questions

### Axis 1 — Analytical ↔ Narrative (Q1–Q3)

Each is answered on a 5-point scale: **Strongly disagree (1) → Strongly agree (5)**. Q2 is reverse-keyed.

**Q1 — (adapted from the Need for Cognition short form)**
> "I'd rather wrestle with a complex idea than be handed a simple takeaway."

High agreement → analytical. (Original NFC item: "I prefer complex to simple problems.")

**Q2 — (adapted from the Need for Cognition short form, reverse-keyed)**
> "I prefer to just be told the point rather than think it all the way through myself."

High agreement → narrative/peripheral. (Reverse of: "I only think as hard as I have to.")

**Q3 — (adapted from the Transportability scale)**
> "When I read a good story or watch a film, I lose track of the world around me and get pulled right in."

High agreement → narrative. (Transportability taps the trait tendency to be absorbed in narrative, which predicts who is moved by stories vs. arguments.)

**Scoring Axis 1:** Reverse Q2 (6 − score), then average Q1, Q2(reversed), Q3.
- **Avg ≥ 3.5 with Q1 high → lean Analytical.** Lead with the argument; give them depth; don't oversimplify.
- **Avg ≤ 2.5 or Q3 high → lean Narrative.** Open inside a scene; let the idea emerge from story; keep argumentation light.
- **Middle → default to the book's natural voice** (which already blends both — Minchin lyrics *and* evolutionary biology).

### Axis 2 — Dominant Immortality Project (Q4–Q5)

**Q4 — Values sort (adapted in spirit from the Portrait Values Questionnaire approach: describe a person, ask how much they're "like you")**
> "Which of these sounds most like you? Pick the closest, even if none is perfect."
> - **(Biological)** "What matters most to me is the people I love — family, raising kids, the people who'll carry on after me."
> - **(Status)** "I want to make a mark — to do something that outlasts me and that people remember."
> - **(Creative)** "I'm happiest making things — art, music, writing, building — the act itself is the point."
> - **(Community)** "I feel most myself as part of something bigger — a team, a faith, a place, a cause."
> - **(Natural)** "I feel most connected when I'm part of nature — the cosmos, the wilderness, the bigger whole."

**Q5 — Confirmation / secondary (so we capture the 'pie chart', not a single slice)**
> "And which would be your *second* closest?" (same five options)

**Scoring Axis 2:** Q4 = dominant project (drives examples). Q5 = secondary (use for a supporting analogy or two). This mirrors the "everyone has a pie chart" model in Chapter 6.

---

## Output: the reader's profile

Two values, e.g. **`{ delivery: "Narrative", project: "Creative", secondary: "Natural" }`**. That's enough to pick which hand-written variation to serve in the test (and later, enough to seed the AI generation prompt).

## How it's used in the Stage 0 test

For validation you only need a few cells of the matrix, not all 5×3. Recommended minimum:
- An **Analytical / Status** version
- A **Narrative / Creative** version
- The **existing generic chapter** as control

Serve each tester the version matching their intake — *blind*, without telling them it was matched — plus the control, and ask the Gate 0 questions (could you tell one was for someone like you? which landed best? would you pay?). See `stage0-gradient-variations.md` for the actual drafts.

## Friction check

Five questions, all single-tap, ~60 seconds. No free text. The two project questions double as a soft introduction to the book's central idea, so the intake itself starts teaching the framework — which the framework doc flagged as a desirable property.

---

## Sources for the borrowed items

- Need for Cognition: Cacioppo & Petty (1982); six-item short form, [Lins de Holanda Coelho et al., 2020 (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC7545655/)
- Transportability: Dal Cin, Zanna & Fong; ["This Story Is Not for Everyone"](https://www.researchgate.net/publication/247789676_This_Story_Is_Not_for_Everyone_Transportability_and_Narrative_Persuasion)
- Openness/Intellect: [Oleynick et al., 2017](https://scottbarrykaufman.com/wp-content/uploads/2017/03/Oleynick-et-al.-2017.pdf)
- Why NOT learning styles: [Pashler et al. review (ScienceDaily summary)](https://www.sciencedaily.com/releases/2009/12/091216162356.htm)
