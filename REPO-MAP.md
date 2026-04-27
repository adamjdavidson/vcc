# Repository Map

**Purpose:** Navigation table. Tells the LLM where to find each kind of help.

A short guide for the LLM to find the right kind of help quickly.

## Read first

- `START_HERE_FOR_LLM.md` — operational entrypoint. Always read this first.
- `ai-master-instructions.md` — full behavioral instructions.

## When you need help with…

| You need… | Look in |
|---|---|
| Story principles, the Passion Economy frame, anti-slop, source rules | `story-principles/` |
| How to interpret a worksheet, voice memo, or interview | `workflow/` |
| How to research a cheese style, a place, or an audience | `research/` |
| Background on a specific cheese style or family | `cheese-styles/` |
| Vermont dairy history, geography, seasonality, artisan-cheese context | `vermont-context/` |
| How to adapt the same story for a specific audience | `audiences/` |
| Good and bad examples, before/after, fictional samples | `examples/` |
| How to shape an asset (15-second pitch, product sheet, website copy, etc.) | `output-templates/` |
| Reviewing your own draft before handing it back | `review-checklists/` |
| Pointers for further outside research | `sources-and-further-reading.md` |

## Selective-load (do NOT load by default)

- `deep-research/` — long-form source material. Open files in this folder only when the cheesemaker's specific worksheet, follow-up, or chosen story angle calls for depth. The relevant `cheese-styles/` and `vermont-context/` meta-files include explicit pointers when a deep-research file is appropriate. See `deep-research/README.md` for the selective-loading rule.

## Folders the LLM should skip

- `_design-history/` — historical design briefs that shaped the printed worksheet and this repository. Useful to maintainers, irrelevant to the LLM's work.

## How to use this map

This file is a navigation tool, not a source of authority. When in doubt, the cheesemaker's own worksheet, voice memo, or interview is the primary source for claims about their specific cheese, farm, milk, or maker journey. The repository provides principles, context, and examples — it does not provide facts about any individual cheesemaker.
