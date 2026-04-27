# Deep Research

**Purpose:** Long-form source material on Vermont, cheese styles, and the cheese trade. **Selective-load** — do not read these files by default. See selective-loading rules below before opening any file in this folder.

Long-form source material on Vermont, cheese styles, and the cheese trade. **Selective-load**: do not read these files by default.

## Why this folder exists

The kit's main folders (`story-principles/`, `workflow/`, `cheese-styles/`, `vermont-context/`, `audiences/`, etc.) are short and instructional. They tell the LLM how to think about a problem.

This folder is different. It holds **rich narrative source material** — long histories, named producers, specific dates and places, sensory lexicons, citation-laden surveys. The material is too dense to load on every cheesemaker query.

## Folder structure

```
deep-research/
├── README.md                  ← this file
├── vermont/                   ← deep research on Vermont
├── cheese-styles/             ← deep history of specific cheese styles
└── audiences/                 ← how the cheese trade actually works
```

## Selective-loading rules

Load a file from this folder only when at least one of the following is true:

1. **The cheesemaker's worksheet, voice memo, or interview asks for depth that the meta-files cannot supply** — for example, they want their cheese situated in a specific period of Vermont dairy history, or compared to a specific Alpine tradition, or framed alongside named pioneer producers.

2. **The LLM has already narrowed to a clear story angle** that requires concrete historical or technical detail to enrich — and the meta-file pointers (in `vermont-context/`, `cheese-styles/`, or `audiences/`) explicitly direct here.

3. **The cheesemaker has asked a direct question** that requires depth — for example: *what is the relationship between Vermont's bulk-tank crisis and today's artisan movement?*, *how do specialty distributors actually work?*, *what did the 1980 Farm Bill do to Vermont dairy?*

Do not load deep research as default reading. Do not load multiple files when one will do. Do not summarize everything in the file — pull only what serves the specific story you are working on.

## Source discipline still applies

Everything in this folder is **general history or general industry knowledge**, not proof about any specific cheesemaker. The truth-checklist (`review-checklists/truth-checklist.md`) applies fully:

- General Vermont dairy history is not proof that *this* cheesemaker preserves a working farm.
- Named producer profiles are not proof that *this* cheesemaker uses similar methods or shares similar values.
- Cheese-style origin lore is not proof that *this* cheese descends from any specific tradition.
- Industry observations about cheesemongers, buyers, or distributors are general patterns, not facts about *this* specific contact.

Cite outside research as outside research. Confirm with the cheesemaker before claiming a connection.

## File index

### `vermont/` — Vermont depth

| File | Roughly covers |
|---|---|
| `vermont/place-and-season.md` | The five Vermont dairy landscapes (Champlain Valley, Connecticut River Valley, Vermont Piedmont, Green Mountains, Northeast Kingdom) broken out by region — soil, climate, what animals thrive there, forage, seasonality patterns, anchor producers. Plus a cross-cutting Vermont-wide seasonality section. **Load only the section matching the cheesemaker's region.** |
| `vermont/dairy-and-cheese-history-1600-1980.md` | Pared story-facts: glaciers and the five regions, the sheep boom that built the pastures, the cow shift, women's farmhouse cheese, Crowley/Cabot/Grafton/Shelburne origin moments, the bulk-tank collapse, the counterculture seeds of the 1980 revival. |
| `vermont/artisan-renaissance.md` | Pared story-facts on the modern era (1980–today): the Farm Bill commodity-collapse setup; pioneers (Hooper/Reese, Major, Kehlers, Dixon, Fondiller); infrastructure plays (Cabot Clothbound, Cellars at Jasper Hill, VCC, VIAC); terroir science (Iberville Shale, autochthonous starters); awards record; producer reference table. |

### `cheese-styles/` — cheese-style deep histories

| File | Roughly covers |
|---|---|
| `cheese-styles/alpine-storytelling-toolkit.md` | Alpine cheese history + sensory lexicon + copy formulas + Vermont alpine examples (Spring Brook Tarentaise, Jasper Hill Whitney, Parish Hill Idyll). The most "ready to use" file. |
| `cheese-styles/alpine-goat-cheese-vermont.md` | 9000 BCE to 2026 goat-and-alpine history with detailed Vermont alpine-goat producer profiles (Twig Farm, Barn First, Blue Ledge, etc.). |
| `cheese-styles/goat-history-toolkit.md` | Long-arc goat-cheese history (Neolithic origins, Mediterranean, Loire AOPs, modern American renaissance). |
| `cheese-styles/cheddar-history.md` | *Phase 2A — to be added.* English origins, the 1851 Jesse Williams factory, the cheddaring process, the commoditization trap, Vermont's clothbound revival. |
| *(Phase 2B):* washed-rind, blue, bloomy-rind, tomme, pasta-filata, gouda | Deferred. |

### `audiences/` — cheese-trade depth

| File | Roughly covers |
|---|---|
| `audiences/cheesemonger-world.md` | *Phase 2A — to be added.* How cheesemongers operate, the ACS, Cheesemonger Invitational, the producer-monger relationship. |
| *(Phase 2B):* retail-buyer-mindset, chef-sourcing, specialty-distributors, food-writers | Deferred. |

## How to cite from this folder

When you draw on a deep-research file, name it explicitly when reporting back:

> Outside research from `deep-research/vermont/dairy-and-cheese-history-1600-1980.md` notes that Vermont's peak farmhouse cheese year was 1869, when the state produced 4,830,700 pounds. I do not know whether that history is part of your specific cheese's story — please confirm or set aside.

Keep the source separation discipline intact.
