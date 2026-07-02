# Analogy Tags

> The in-source mechanism behind [content-architecture.md](content-architecture.md)'s
> **Layer 3 (Variable Examples)** and **Layer 4 (Variable Tone & Depth)**. Where
> `content-architecture.md` says *which* content is swappable in the abstract,
> these tags mark the swappable spots *inside the chapter files themselves*, so
> the generation pipeline ([technical-stack.md](technical-stack.md)) can act on
> them. Governs the analogies; the book's *voice* is governed separately by
> `../.claude/writing-guide.md`.

## Why this exists

The **analogies** in the book — the movies, quotes, sports, foods, and metaphors
used to make abstract ideas land — are the highest-leverage personalization
surface (see [personalization-framework.md](personalization-framework.md),
dimension 1). The trap is to sand these references off to make the book
"universal." That also sands off the voice.

The better move is to keep every analogy vivid in the seed text but mark it as
**swappable**, so the pipeline can trade the *skin* of an analogy (the specific
reference) while keeping its *skeleton* (the concept it teaches) and the book's
tone. These tags are how we mark them.

## The tag

Each analogy is marked with an HTML comment placed on its own line directly
**above** the paragraph, sentence, or blockquote it refers to. HTML comments do
not render in the published site — they're invisible to readers and exist only
as metadata for the personalization pass.

```
<!-- analogy | concept: <the invariant idea> | assumes: <what the reader must know or have lived> | type: swappable | fallback: <what plays when we know nothing about the reader> -->
```

Not every field is required on every tag (an epigraph rarely needs a `fallback`,
for example), but `concept`, `assumes`, and `type` should always be present.

## Fields

- **concept** — The idea the analogy exists to teach. This is *invariant*: any
  swap the pipeline makes must still deliver this. The most important field; it's
  the contract a replacement has to honor.
- **assumes** — The knowledge, experience, or cultural context the reader needs
  for the *current* reference to land. This is what the reader profile is checked
  against to decide whether a swap is needed.
- **type** — How freely the reference may be replaced (see taxonomy below).
- **fallback** — The universal-default version to use when there's no profile,
  or when the reader's profile doesn't match any prepared variant. The seed text
  itself should already be written as, or close to, the fallback.
- **slot** *(optional)* — A category label when many analogies share a role,
  e.g. `slot: epigraph-authority`. Lets the pipeline treat a whole class
  uniformly.

## Type taxonomy (maps to the content-architecture layers)

- **swappable** — Freely substitute the domain to match the reader's affinities.
  A gamer gets a game, a musician gets a band's legacy, a churchgoer gets a
  scripture reference. Same concept, same beat, different world. This is the
  default, and is exactly **Layer 3 (Variable Examples)**.
- **load-bearing** — The analogy carries a structural moment (a chapter's
  framing device, the book's opening hook, the empirical backbone of an
  argument). It sits close to the **Fixed Core (Layer 1)** / **Variable Structure
  (Layer 2)**. Do **not** let the pipeline auto-generate a replacement; swap only
  with a hand-curated alternate, or leave it and *add* a reader-relevant example
  alongside it.
- **decorative** — Flavor. Can be swapped freely or dropped entirely without
  harming the argument.

## How the pipeline should use them

1. **Match, then swap.** Read `assumes`, check it against the reader's profile
   (dominant project + intellectual entry point — see
   [personalization-framework.md](personalization-framework.md)). If the reader
   plausibly shares that context, keep the original. If not, and `type` allows,
   generate a replacement that (a) honors `concept`, (b) draws on a domain in the
   reader's affinity set, and (c) preserves the book's voice
   (`../.claude/writing-guide.md`).
2. **Fall back gracefully.** No profile, or no confident match → use `fallback`
   (or the seed text as written, which is the control version).
3. **Epigraphs are an authority layer.** Every chapter-opening quote is a
   `slot: epigraph-authority`. A quote's job is *borrowed credibility*, so match
   the source of authority to who the reader trusts — a lyric, a scientist, a
   philosopher, a scripture verse — all pointing at the same `concept`.
4. **Technical level is a global dial (Layer 4), not a per-tag rewrite.** Graphs,
   equations, and jargon (relativity, nucleotides, action potentials) can render
   as formal-and-precise for an analytical reader or as plain metaphor with no
   math for another. Set this once from the profile; it interacts with `type:
   swappable` references but is decided globally.

## What NOT to tag

- The central mantra ("Not good, not bad. Not better, not worse. Just is.").
- Framework terms and their definitions: Gradient Analysis, Immortality
  Projects, the five project names, Experiential Transcendence, the Why Game,
  Feeling Fade, upper/lower bounds. (These are the Fixed Core in
  [content-architecture.md](content-architecture.md).)
- Core factual content that is not a stand-in for something else (e.g. "your DNA
  is ~99% the same as a chimpanzee's"). It's an argument, not an analogy.

If it's the *spine* of the book, it stays fixed. If it's a *handle* we grabbed to
make the spine graspable, it's a candidate for a tag.

## Status

Initial tags cover the analogies flagged in the first review pass — 24 tags
across chapters 1–13: the Wikipedia→Philosophy opener, every chapter epigraph,
the relativity/graph/hangover examples in ch. 4, the food list in ch. 5, the
Terror Management study plus "Grade 1" and sport in ch. 6, the legacy passage in
ch. 8 (which replaced an Oppenheimer example), Pascal's wager and sports fandom
in ch. 10, the nature imagery in ch. 11, and Yoda plus the transistor/neural-net
aside in ch. 13.

This is a living convention — add a tag whenever a new analogy is written, and
revisit `type` classifications as the pipeline takes shape.
