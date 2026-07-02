# Content Architecture

## Overview

This document maps the existing Monkeys in Shoes content into fixed (universal) and variable (personalizable) components. The goal is to identify which parts of the theory are load-bearing walls and which are interchangeable furniture.

## Content Layers

### Layer 1: Fixed Core (Never Changes)

These are the foundational claims and frameworks that every version must include, regardless of personalization. They are the theory itself.

- **Gradient Analysis** (Ch 3): Everything is a gradient, language creates false binaries
- **Relativity of Experience** (Ch 4): Upper/lower bounds, feeling fade, magnitudes
- **The Immortal Replicator** (Ch 5): We are self-replicating chemistry; consciousness is a gradient
- **Immortality Projects framework** (Ch 6): Five projects, all equal, everyone has a pie chart
- **Experiential Transcendence** (Ch 12): Moments of glimpsing immortality as the pinnacle of projects
- **Central mantra:** "Not good, not bad. Not better, not worse. Just is."

### Layer 2: Variable Structure (Order Changes)

The sequence in which ideas are introduced can vary based on the person's dominant project and entry point.

**Current book order:** Why → Beauty in Understanding → Nuance → Relativity → Replicator → IP 101 → Biological → Status → Creative → Community → Natural → Transcendence → Don't Try Too Hard

**Possible alternative orders:**
- For someone deep in Community (e.g., religious background): Start with Community Project → show how it connects to biological roots → introduce Gradient Analysis through the lens of religious vs. secular (a false binary) → build out from there
- For someone deep in Creative (e.g., artist/musician): Start with Creative Project → Experiential Transcendence through art → then zoom out to the framework
- For someone in crisis/grief: Start with "Why" and the Why Game → move gently toward the mantra → introduce projects as a map, not a prescription

### Layer 3: Variable Examples (Swappable)

This is the highest-leverage personalization layer. The same concept illustrated through different stories, analogies, and references. These swappable spots are marked directly in the chapter files with **analogy tags** — see [analogy-tags.md](analogy-tags.md) for the tag schema and how the pipeline consumes them.

**How these get produced:** The examples below are *direction*, not pre-written copy. Per the hybrid approach in [technical-stack.md](technical-stack.md), we write a few hand-crafted reference variations (to nail voice and quality) and then use those as few-shot examples for AI generation of additional profiles. The goal is to have 2-3 human-written variations per concept as anchors, with AI filling the gaps for profiles that fall between them.

**Example: Introducing Gradient Analysis**
- Science person → evolution, species classification, gene expression
- Sports person → "at what point is someone good at basketball?" / skill as a gradient
- Music person → genres blending into each other, the gradient between jazz and blues
- Parent → child development milestones as arbitrary lines on a continuous spectrum
- Business person → the gradient between "startup" and "corporation"

**Example: Introducing Experiential Transcendence**
- Biological → birth of a child (already in book)
- Status → standing ovation, seeing your name on something
- Creative → losing yourself in music, flow state while painting
- Community → crowd roaring after a goal, collective prayer
- Natural → sunrise over a mountain, standing in old growth forest

### Layer 4: Variable Tone & Depth

- **Depth:** Some people want the Dawkins quotes and evolutionary biology. Others want the Tim Minchin lyrics and the bed/pee analogy. Same idea, different resolution.
- **Tone:** "Fuck enlightenment" vs. "The challenge with the concept of enlightenment is..." Same argument, different packaging.
- **Length:** Some concepts need more runway for some people than others. If someone already gets Gradient Analysis intuitively, don't belabor it.

---

## Chapter-by-Chapter Modular Breakdown

| Chapter | Fixed Core | Variable Elements |
|---------|-----------|-------------------|
| 1 - Why | The Why Game concept; feelings as terminal point of introspection | Opening hook; specific why-chain examples; tone of mortality discussion |
| 2 - Beauty in Understanding | Think vs. feel duality; understanding doesn't kill the magic | Feynman quote vs. other entry; specific emotion examples |
| 3 - Nuance | Gradient Analysis framework; everything is a gradient | Color example vs. other sensory gradients; grammar depth; evolution examples |
| 4 - Theory of Relativity | Bounds, magnitudes, feeling fade | Physical vs. emotional examples weighted differently; graph complexity |
| 5 - Immortal Replicator | Consciousness as gradient; we are replicators | Depth of evolutionary biology; Dawkins framing vs. simpler versions |
| 6 - IP 101 | Five projects; pie chart model; all equal | Entry project emphasized; sport example vs. other activity |
| 7-11 - Individual Projects | Core definition and connection to biological roots | Examples heavily personalized; depth proportional to relevance |
| 12 - Transcendence | Moments of glimpsing immortality | Examples matched to dominant project |
| 13 - Don't Try Too Hard | Mantra; action potential model; optimistic nihilism | Buddhism framing vs. other "trying too hard" traditions; closing tone |

---

## Open Questions

- [ ] How granular should the modular chunks be? Paragraph level? Section level? Chapter level?
- [ ] Do we need to write multiple versions of fixed core content or just variable elements?
- [ ] How do we maintain narrative coherence when reordering? Transitions between chapters need to still flow.
- [ ] Should there be "bonus" content that only appears for certain profiles? (e.g., deeper evolutionary biology appendix for science-oriented readers)
- [ ] How do we handle the images/diagrams? Some are tied to specific examples that might get swapped out.
