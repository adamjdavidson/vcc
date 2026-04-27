# Master Prompt

**Purpose:** The short paste-in prompt cheesemakers use to invoke this kit with their AI tool.

This is the prompt a Vermont cheesemaker can paste into Claude (or another AI tool) along with a worksheet photo, voice memo, or no upload at all. The prompt's job is small: point the AI at this repository, and tell it what kind of material it's getting.

The repository carries the deeper instructions. The prompt does not need to duplicate them.

---

## The prompt

> Before helping me, read the Vermont Cheese Story Kit at https://github.com/adamjdavidson/vcc and follow the instructions in `START_HERE_FOR_LLM.md`.
>
> I am a Vermont cheesemaker. I am working on the story of one of my cheeses, my own journey into cheese, or my farm or creamery — for an audience that may include consumers, cheesemongers, retail buyers, wholesalers, distributors, chefs, or food writers.
>
> One of these is true:
>
> 1. I uploaded one or more filled-out worksheet pages. Use them as my raw material.
> 2. I uploaded a voice memo (and possibly a worksheet photo). Use the memo as my raw material.
> 3. I uploaded only the cover page (or nothing). Interview me from scratch, one short concrete question at a time.
>
> Do not invent facts about me, my cheese, my animals, my milk, my creamery, or my business. Use what I provide as raw material. Use this repository for principles, examples, audience guidance, output templates, and research direction. Do outside research where helpful and keep it clearly separate from things I told you.
>
> Do not write final copy yet.
>
> First give me:
>
> 1. The strongest raw material I gave you.
> 2. Useful context from the Vermont Cheese Story Kit and from outside research.
> 3. Three possible story through-lines.
> 4. What is missing or unclear.
> 5. Five short, concrete follow-up questions.
>
> After I answer the follow-up questions, we can shape one unifying story and turn it into the assets I need.

---

## Notes for maintainers

The prompt above is short on purpose. The repository — not the prompt — is where complexity belongs.

If you change folder names, file names, or the top-level orientation of this repo, update `START_HERE_FOR_LLM.md` and `REPO-MAP.md` first. The master prompt does not need to change.
