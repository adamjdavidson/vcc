# Vermont Cheese Story Kit

**Purpose:** Public-facing overview of the kit. Read this if you're a human exploring the repo. The LLM should start at `START_HERE_FOR_LLM.md`.

This repository is an LLM-facing source library for Adam Davidson’s Vermont Cheese Council conference workshop.

Adam Davidson is the author of *The Passion Economy* and co-founder of NPR’s *Planet Money*. In the 9am session, Adam frames artisan cheese as a Passion Economy product: not a commodity, but a product shaped by specificity, judgment, craft, place, people, animals, milk, weather, biology, history, and taste.

The human-facing worksheet is intentionally simple. Cheesemakers answer concrete questions about their cheese, themselves, and their farm or creamery. They may also record answers as a voice memo. The worksheet is not expected to contain a polished story.

This repository carries the deeper instructions for the LLM.

## What this repository should do

The Vermont Cheese Story Kit has one major purpose: to help small, artisanal cheesemakers communicate powerfully what makes their cheese special, distinct, memorable, and worth paying more for than commodity cheese.

The kit is designed for use by an LLM working with simple input from a cheesemaker: a worksheet, a voice memo, or an interview. The cheesemaker may not know their own story yet. The LLM’s job is to help find the strongest story hiding in the facts.

The audience may be consumers, cheesemongers, retail buyers, wholesalers, chefs, co-op staff, food writers, or other people who help a cheese reach the people who will eat it.

The ultimate output should be a compelling, engaging, truthful narrative that makes the target audience more eager to buy, sell, serve, recommend, eat, or share this cheese.

That story should also enrich the experience of eating the cheese. It should help people understand that this cheese is not just a product in a category, but the result of particular choices, places, histories, techniques, animals, milk, weather, biology, people, and craft.

Do not try to include every possible detail. The story may center on the cheese style, the maker’s journey, the farm or creamery, the milk, the animals, the aging process, the geography, the weather, the history, the sensory experience, the market context, or something else entirely.

The LLM’s job is not to reduce the cheese to one selling point. It is to find the strongest unifying narrative: the thread that makes several true facts belong together.

## Core principle

A story is not a list of attributes.

A story is what happens when the right facts start to explain one another.

## How to use this repository

When a cheesemaker uploads a worksheet or voice memo, the LLM should:

1. Read `START_HERE_FOR_LLM.md`.
2. Use the cheesemaker’s worksheet, voice memo, or interview as the primary source for claims about that specific cheese.
3. Use this repository for story principles, examples, audience guidance, output templates, and research direction.
4. Conduct outside research into the location and cheese style when helpful.
5. Keep all source types separate: what the cheesemaker said, what this repository says, what outside research suggests, and what still needs confirmation.
6. Ask follow-up questions before writing finished copy.

## Repository structure

- `START_HERE_FOR_LLM.md` — the operational entrypoint for the LLM. Always read first.
- `ai-master-instructions.md` — full behavioral instructions for the LLM.
- `MASTER-PROMPT.md` — the short paste-in prompt cheesemakers can give their AI tool.
- `REPO-MAP.md` — quick navigation table for finding the right kind of help.
- `cheese_worksheets.pdf` — the printed *Tell Your Story* worksheet packet.
- `story-principles/` — what story means, how it differs from brand, and how to avoid generic copy.
- `workflow/` — how to work from worksheets, voice memos, or interviews; how to interpret the *About Your Business* intake page.
- `research/` — how to research place, cheese style, audience, and sources.
- `cheese-styles/` — style-specific context and story possibilities.
- `vermont-context/` — Vermont dairy, geography, seasonality, and artisan-cheese context.
- `audiences/` — how to adapt the same story for different people.
- `examples/` — good patterns, bad AI slop, before/after examples, and fictional samples.
- `output-templates/` — practical outputs: spoken pitch, product sheet, website copy, buyer email, tasting script, and label language.
- `review-checklists/` — pass/fail checks the LLM runs on its own draft before handing it back.
- `deep-research/` — long-form source material on Vermont, Alpine, and goat-cheese history. **Selective-load only** — see `deep-research/README.md`.
- `_design-history/` — historical design briefs. The LLM should skip this folder.
- `sources-and-further-reading.md` — source list for background research.
