# Repository Guide for Maintainers

**Purpose:** Maintainer's guide. For Adam and future contributors. The LLM does not need to read this file.

This repository is meant to be read by an LLM, not by conference participants.

The participant-facing worksheet should remain simple. It should ask concrete questions about the cheesemaker’s cheese, maker journey, and farm / creamery / place. It should not include this whole repository’s logic.

## Maintain the distinction

- Worksheet = human intake.
- Repository = LLM instructions, examples, research guidance, and story principles.
- LLM = interpreter, researcher, interviewer, and drafter.

## Add new files only if they help the LLM

Before adding a document, ask:

> Will this help the LLM find, test, deepen, or express a stronger truthful story for a particular cheese?

If not, do not add it.

## Preferred file style

Each file should be:

- plain English,
- practical,
- LLM-facing,
- rich enough to guide judgment,
- not overly long,
- filled with examples where useful.

## Do not make the repository an encyclopedia

The repository is not meant to contain every fact about Vermont, cheese, or storytelling.

It is meant to teach the LLM how to use facts in service of story.

## Two tiers of files

The repository now has two tiers, and maintainers should know which is which.

**Always-load (the kit's core).** Short, instructional, LLM-facing. The LLM reads these as default context. Includes everything in `story-principles/`, `workflow/`, `research/`, `cheese-styles/`, `vermont-context/`, `audiences/`, `examples/`, `output-templates/`, and `review-checklists/`.

**Selective-load (deep research).** Long, narrative, source-rich. The LLM loads these only when a specific cheesemaker query requires depth. Lives in `deep-research/`. The folder's README explains when to load.

When adding new material, decide which tier it belongs to. If a new file is more than ~300 lines, it almost certainly belongs in `deep-research/` — and the relevant always-load meta-file should add a pointer to it. Do not load up the always-load tier with bulk material.

## Folders to leave alone in regular maintenance

- `_design-history/` — historical reference, not part of the live kit.
- `cheese_worksheets.pdf` — the printed artifact. If the printed worksheet changes, regenerate the PDF and update the workflow files (especially `workflow/how-to-use-worksheet.md` and `workflow/intake-page-interpretation.md`) to match.
