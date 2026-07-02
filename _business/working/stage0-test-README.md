# Stage 0 Test — How to Run It

`stage0-test.html` is a single, self-contained blind-comparison page: intake → reader's matched variation vs. the generic control → structured reactions. No backend, no accounts, no dependencies. ~6 minutes per person.

> **Where this fits the current plan.** The plan changed from "validate one chapter first" to "finish the book, then distribute a complete instrumented product" (see [`../README.md`](../README.md) and [`../tasks.md`](../tasks.md)). This tool is no longer the make-or-break gate. It now serves two ongoing purposes: (1) the **Stage 4 internal gut-check** — a quick structured way for the author and a few friends to confirm personalization is felt before paid spend; and (2) the five matched variations it contains are **voice anchors** for the Stage 2 generation pipeline. Still useful, just not the gate.

## What it does

1. **Intake** — 3 delivery questions (borrowed from Need for Cognition + Transportability) and 2 project questions, exactly the instrument in [`stage0-intake.md`](stage0-intake.md).
2. **Scores two axes** — Analytical↔Narrative (delivery) and dominant Immortality Project.
3. **Serves two passages, blind** — the reader's *matched* variation and the *generic control* (the real Chapter 3 text), in randomized order, never labeled. The reader only ever sees "Passage 1 / Passage 2."
4. **Captures reactions** — which landed better, how strongly, could-they-tell, would-they-pay, plus optional free text.
5. **Exports CSV** — all responses stored in the browser; the Download button produces a spreadsheet.

## Matching logic (important caveat)

Only two matched variations exist so far: **Status→analytical (A)** and **Creative→narrative (B)**. So:
- A **Status** or **Creative** reader gets a *true* project match (`matchedIsTrueMatch = true`).
- Everyone else is routed to whichever variation fits their *delivery* lean, and flagged `matchedIsTrueMatch = false`.

When you read results, **filter on `matchedIsTrueMatch = true` for the cleanest read of the core bet.** The `false` rows are still useful — they tell you whether delivery-fit alone (without project-fit) moves people — but they're a weaker test. To strengthen the whole thing, write matched variations for the other three projects (a good next task).

## How to deploy (pick one)

- **GitHub Pages (free, you already use it):** this file is pure static HTML, so it'll serve as-is. Note it currently lives under `_business/working/`, which Jekyll may not publish. Easiest path: copy `stage0-test.html` to a published location (e.g. the site root or an `/experiment/` folder) and link to it. Don't leave it only in `_business/` if you want a public URL.
- **Anywhere else:** Netlify drop, any static host, or even open the file locally and screen-share. It's one file.

## How to read the results

Each CSV row is one tester. The columns map straight onto the decision criteria in [`../README.md`](../README.md):

| What you're checking | Columns to look at | Proceed signal |
|---|---|---|
| Did the matched version win? | `pref` (`matched`/`control`/`equal`), filtered to `matchedIsTrueMatch=true` | Matched beats control in a clear majority |
| Could they feel the fit? | `tell` (`yes`/`somewhat`/`no`) | Mostly `yes`/`somewhat` |
| Willingness to pay | `pay` (`yes`/`maybe`/`no`) | A couple of `yes` |
| Strength of reaction | `intensity` (1–5) | Preferred passage scoring 4–5 |

**Decision (commit before you read):**
- **Proceed** → matched reliably beats control among true-match readers, and a couple would pay.
- **Pivot** → difference is real but weak / control often wins → maybe the product is one great book, not a personalization engine.
- **Stop** → readers can't tell the versions apart, or control wins outright.

## Watch for confounds

- If one passage wins for *everyone* regardless of match, it's probably just better-written, not better-matched. That's a test-design signal, not a premise result — tighten the variations and rerun.
- Tiny sample (5–8) won't give statistical significance and isn't meant to. You're looking for an obvious signal, not a p-value. If it's ambiguous at n=8, that itself leans toward "pivot."
