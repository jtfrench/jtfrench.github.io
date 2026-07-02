# Working Artifacts

Stage-specific execution files — the *outputs* of running the plan in [`../tasks.md`](../tasks.md), as opposed to the durable strategy docs one level up.

## What belongs here

- Anything tied to a single stage: drafts, intake instruments, test variations, generation prompts, prototype notes, feedback logs.
- Name files by stage prefix so they sort and group on their own: `stage0-*`, `stage1-*`, `stage2-*`, etc.

## What does NOT belong here

- Durable reference that outlives a stage (the framework, the architecture, the business model, the plan). Those live at the top level of `_business/`.
- If you're unsure: ask "will this still be the source of truth three stages from now?" Yes → top level. No → here.

## Current contents

| File | Stage |
|------|-------|
| [stage0-intake.md](stage0-intake.md) | 0 — validation (the intake instrument) |
| [stage0-gradient-variations.md](stage0-gradient-variations.md) | 0 — validation (the test passages) |
| [stage0-test.html](stage0-test.html) | 0 — validation (runnable, shareable test page) |
| [stage0-test-README.md](stage0-test-README.md) | 0 — how to deploy and read the test |
