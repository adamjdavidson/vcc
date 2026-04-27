# Vermont Cheese Story Kit — GitHub Repository Build Brief

**Purpose:** Historical design rationale for this repository. **LLM should skip.**

> **Historical document — not LLM input.** This brief was the original prompt for building this repository. The repository now exists; this brief is preserved as design rationale and as a record of original intent. Some folder names ended up different from those proposed here (the kit uses `story-principles/`, `workflow/`, and `research/` instead of `principles/`, `intake/`, and `research-guides/`). The LLM should follow the live repository structure described in `START_HERE_FOR_LLM.md` and `REPO-MAP.md`, not this brief.

## Purpose of this document

You are an LLM being asked to create the documentation for a GitHub repository called the **Vermont Cheese Story Kit**.

This repository will be used during Adam Davidson’s session at the Vermont Cheese Council conference. Adam Davidson is the author of *The Passion Economy* and co-founder of NPR’s *Planet Money*. His session is about helping Vermont cheesemakers tell more compelling, truthful stories about their cheese so that customers, cheesemongers, retail buyers, co-op staff, wholesalers, chefs, and others understand why these cheeses are special and worth paying more for than commodity cheese.

The repository is not primarily for cheesemakers to browse. It is a source library for an AI tool to read.

The cheesemaker-facing workflow is simple:

1. A cheesemaker fills out a short worksheet by hand, or records answers as a voice memo.
2. They upload the worksheet photo or voice memo to an AI tool.
3. The worksheet tells the AI tool to read this GitHub repository.
4. The AI tool uses the repository as its guide and uses the cheesemaker’s answers as raw material.
5. The AI tool helps uncover possible story directions, asks follow-up questions, conducts research, and eventually helps draft usable story assets.

The repository carries the complexity. The worksheet stays simple.

---

# What this repository should do

The Vermont Cheese Story Kit should help an AI tool do five things well:

1. Understand the purpose of the Vermont Cheese Council workshop.
2. Understand the Passion Economy frame: these cheesemakers are not selling commodity cheese; they are selling specificity, judgment, taste, craft, place, method, and trust.
3. Use the cheesemaker’s worksheet or voice memo as raw material, not as finished copy.
4. Research the cheese style and the cheesemaker’s location in a useful, story-rich way.
5. Help shape one clear, compelling, truthful story — not a checklist of every possible detail.

The AI should help find the story’s **center of gravity**.

Some cheeses may have a strong cheese-style story. Others may have a maker story, a place story, a technique story, a sensory story, a buyer-use story, or some unexpected angle. The AI should not force every story to mention milk, animals, weather, geography, history, technique, and the maker. Those are possible sources of story, not required ingredients.

---

# Core philosophy

Use this philosophy throughout the repository:

> The goal is to help people who might buy, sell, serve, or eat a cheese understand why it is special — and why it is worth paying more for than commodity cheese.
>
> Build one compelling, engaging, truthful narrative from the strongest material available.
>
> The story may come from the cheese tradition, the maker’s choices, the milk, the animals, the farm, the creamery, the aging process, the weather, the geography, the biology, the history, customer reactions, trade context, or something else entirely.
>
> Do not try to include everything. Choose the most compelling facts and shape them into a clear, unified story that people can remember, repeat, and share.

Also include this idea:

> Do not write a checklist story.
>
> Do not give one sentence about milk, one sentence about animals, one sentence about weather, one sentence about geography, and one sentence about history. That will feel mechanical.
>
> Find the center of gravity. Pick the angle that best explains why this cheese matters and why someone should care.

---

# Important distinction

The cheesemaker-facing worksheet should stay simple. It asks concrete questions about:

- the cheese
- the maker
- the farm, creamery, milk source, animals, and place

This GitHub repository should contain the deeper AI instructions, examples, research guidance, story principles, and background material.

Do not cram long prompts or complex options into the participant worksheet.

---

# Required repository structure

Create the following folder and file structure.

```text
vermont-cheese-story-kit/
  README.md
  START-HERE-FOR-LLM.md
  MASTER-PROMPT.md
  REPO-MAP.md

  principles/
    README.md
    passion-economy-for-cheesemakers.md
    do-not-be-a-commodity.md
    story-is-value.md
    center-of-gravity.md
    avoid-ai-slop.md
    truth-and-confirmation.md

  intake/
    README.md
    worksheet-overview.md
    cheese-story-intake.md
    maker-story-intake.md
    place-story-intake.md
    voice-memo-intake.md
    interview-from-scratch.md

  research-guides/
    README.md
    cheese-style-research.md
    location-research.md
    vermont-context-research.md
    how-to-separate-research-from-claims.md

  cheese-styles/
    README.md
    alpine.md
    cheddar.md
    washed-rind.md
    bloomy-rind.md
    fresh-goat.md
    blue.md
    tomme.md
    gouda-style.md
    lactic.md
    pasta-filata.md
    mixed-milk.md

  vermont-context/
    README.md
    vermont-dairy-history.md
    vermont-cheese-history.md
    geography-and-regions.md
    weather-seasonality-pasture.md
    milk-animals-and-landscape.md
    retail-coops-and-cheese-trade.md

  audiences/
    README.md
    general-public.md
    farmers-market-customers.md
    cheese-shop-customers.md
    cheesemongers.md
    retail-buyers-and-coops.md
    wholesalers-and-distributors.md
    chefs-and-restaurants.md
    online-customers.md
    press-and-food-writers.md

  examples/
    README.md
    before-and-after-examples.md
    good-story-patterns.md
    bad-ai-slop.md
    fictional-cheese-stories.md
    product-info-sheet-examples.md
    spoken-pitches.md
    buyer-facing-examples.md

  output-templates/
    README.md
    fifteen-second-spoken-pitch.md
    seventy-five-word-description.md
    product-info-sheet.md
    website-product-page.md
    buyer-email.md
    tasting-table-script.md
    package-or-label-copy.md

  review-checklists/
    README.md
    anti-slop-checklist.md
    truth-checklist.md
    audience-fit-checklist.md
    final-story-checklist.md
```

---

# File-by-file instructions

## `README.md`

Create a concise public-facing overview of the repository.

Include:

- What the Vermont Cheese Story Kit is.
- Who it is for.
- How it is used in the conference workflow.
- The simple distinction between the worksheet and the repository.
- A clear statement that the repository is background for the AI tool, while the cheesemaker’s worksheet or voice memo is the authority on their actual cheese.

Keep it short. Do not make this a technical manual.

Recommended language:

> The Vermont Cheese Story Kit is a source library for AI tools helping cheesemakers develop truthful, specific, compelling stories about their cheese. It is designed for the Vermont Cheese Council conference session led by Adam Davidson.

## `START-HERE-FOR-LLM.md`

This is the most important file in the repository.

Write it as direct instructions to the AI tool.

It should tell the AI:

1. Read this file first.
2. Use the repository as background and guidance.
3. Use the cheesemaker’s worksheet, photo, transcript, or voice memo as the primary source for their actual cheese.
4. Do not invent facts.
5. Research where helpful.
6. Separate what the cheesemaker said from what the repository says and from what outside research says.
7. Do not write final marketing copy immediately.
8. First identify raw material, useful context, possible story directions, missing information, and follow-up questions.

Required first output:

```text
1. Strongest raw material from the cheesemaker
2. Useful context from the Vermont Cheese Story Kit
3. Useful outside research, if available
4. Three possible story directions
5. What is missing or unclear
6. Five simple follow-up questions
```

Include this rule:

> Do not ask the cheesemaker, “What makes your cheese special?” Ask concrete, answerable questions.

## `MASTER-PROMPT.md`

Create a clean master prompt that can be pasted into an AI tool along with a worksheet photo or voice memo.

This prompt should tell the AI to read the GitHub repository and then use the uploaded worksheet or voice memo.

Keep it shorter than the full repository instructions. The point of the prompt is to point the AI to the repository, not to duplicate the entire repository.

Include:

```text
Before helping me, read the Vermont Cheese Story Kit at this repository: [INSERT GITHUB URL]

Use the repository as your guide. Then use my worksheet, photo, transcript, or voice memo as raw material.
```

Then include the two possible modes:

```text
I either uploaded a completed worksheet, or I want you to interview me from scratch.
```

## `REPO-MAP.md`

Create a short guide explaining where the AI should look for different kinds of help.

Example:

- For overall behavior: `START-HERE-FOR-LLM.md`
- For story principles: `principles/`
- For worksheet interpretation: `intake/`
- For cheese-style background: `cheese-styles/`
- For Vermont background: `vermont-context/`
- For audience-specific language: `audiences/`
- For examples: `examples/`
- For output formats: `output-templates/`
- For final review: `review-checklists/`

---

# Principles folder

## `principles/README.md`

Explain that this folder gives the AI the strategic and storytelling principles behind the kit.

## `principles/passion-economy-for-cheesemakers.md`

Explain Adam Davidson’s Passion Economy frame in plain language as it applies to cheesemakers.

Cover these ideas:

- The old economy rewarded sameness, scale, and efficiency.
- The Passion Economy rewards specificity, judgment, niche value, intimacy at scale, and customers who care.
- Artisan cheese is a natural Passion Economy product.
- The cheese already contains value; the story helps people understand it.
- The story should help a buyer, cheesemonger, or customer understand why the cheese is worth paying more for than commodity cheese.

Do not write this as a book summary. Write it as practical guidance for the AI tool.

## `principles/do-not-be-a-commodity.md`

Explain the commodity trap.

Include:

- Commodity products are judged mostly by price and convenience.
- Artisan cheesemakers must avoid letting the market reduce their cheese to a category: “cheddar,” “goat cheese,” “washed rind,” “local Vermont cheese,” etc.
- Those terms may be accurate, but they are not enough.
- The story must restore specificity.

Use the Braun Brush lesson as a short analogy:

- Braun Brush survived by leaving commodity brushes and focusing on specialized problems.
- The key lesson is not “brushes”; it is “sell the judgment and expertise embedded in the product.”
- Cheesemakers are selling judgment embedded in cheese.

Keep Braun Brush concise.

## `principles/story-is-value.md`

Explain that story is not decoration.

Include:

- Story helps customers understand the value already present in the cheese.
- A good story can make a cheese easier to buy, easier to sell, easier to describe, and richer to eat and share.
- The story must be true.
- Avoid fake authenticity.
- The story should travel through labels, product sheets, websites, shelf tags, market tables, co-op staff, cheesemongers, buyers, distributors, chefs, and customers.

## `principles/center-of-gravity.md`

This should be one of the strongest files.

Explain:

- The AI should not write a checklist story.
- The AI should not try to include every possible detail.
- The AI should look for the strongest organizing idea.
- The story may be about cheese style, place, maker, technique, seasonality, animal life, customer reaction, trade usefulness, or something else.
- The AI should propose several possible centers of gravity, then ask the cheesemaker which feels true.

Include examples of possible centers of gravity:

- “A Vermont take on an old Alpine problem: preserving mountain milk.”
- “A washed-rind cheese built around daily attention and controlled risk.”
- “A goat cheese that turns a small herd’s seasonal milk into a bright, direct table cheese.”
- “A maker story about leaving another career to build a life around milk, animals, and fermentation.”

Label these as illustrative examples, not templates.

## `principles/avoid-ai-slop.md`

Explain what bad AI writing looks like.

Bad phrases to avoid unless backed by specific facts:

- artisan
- authentic
- premium
- unique
- handcrafted
- local
- traditional
- crafted with care
- made with passion
- flavor journey
- nestled in the hills
- farm-fresh goodness

Explain that the AI should replace empty adjectives with concrete evidence.

## `principles/truth-and-confirmation.md`

Explain source discipline.

The AI must always separate:

1. What the cheesemaker said
2. What the repository says
3. What outside research found
4. What is plausible but needs confirmation

The AI must not claim that general Vermont history, cheese-style history, climate, geography, or trade context is true of a specific cheese unless the cheesemaker confirms it.

---

# Intake folder

## `intake/README.md`

Explain that the worksheet is the source of raw material.

The AI should treat worksheet answers as clues, not finished prose.

## `intake/worksheet-overview.md`

Explain the three worksheet types:

1. Cheese Story
2. Maker Story
3. Farm / Creamery / Place Story

The AI should be able to work from any one of them or from all three.

## `intake/cheese-story-intake.md`

Explain how to interpret answers from the Cheese Story worksheet.

The worksheet asks about:

- cheese name
- plain description
- animal milk
- milk or animal details
- cheese family or tradition
- comparable cheeses
- how this cheese is made differently from others
- what physically happens in making or aging
- what the maker says when handing someone a sample
- what people say when tasting it

Tell the AI what to look for:

- specific process details
- style references
- technical choices
- sensory clues
- customer reactions
- maker language that sounds natural and repeatable
- missing facts that should be asked about

## `intake/maker-story-intake.md`

Explain how to interpret answers from the Maker Story worksheet.

The worksheet asks about:

- name and company
- what the person did before cheese
- how cheese pulled them in
- what was hard about getting here
- who taught, influenced, helped, or challenged them
- what they are proudest of
- what they hope happens when people eat the cheese

Tell the AI:

- Do not turn this into a heroic biography unless the facts support it.
- Look for the parts of the person’s journey that explain the cheese.
- Look for choices, constraints, influences, values, risks, and turning points.
- Avoid self-indulgence. The maker story should help someone understand the product.

## `intake/place-story-intake.md`

Explain how to interpret answers from the Farm / Creamery / Place worksheet.

The worksheet asks about:

- where the cheese is made
- where the creamery is
- where the cheese is aged
- where the milk comes from
- what animals provide the milk
- who else is part of the place
- what someone would notice if they visited

Tell the AI:

- Use the location to conduct outside research.
- Research physical address, town, county, region, or milk-source location as appropriate.
- Look for concrete context: geography, landscape, history, weather patterns, dairy history, agriculture, food traditions, and local character.
- Keep research separate from claims about the specific cheese.

## `intake/voice-memo-intake.md`

Give instructions for working from a voice memo or transcript.

Tell the AI:

- Transcribe or organize the answers.
- Preserve the maker’s natural phrases when they are vivid or useful.
- Notice spoken language that could become a table pitch.
- Ask for clarification if the transcript is unclear.

## `intake/interview-from-scratch.md`

Give the AI an interview mode for cheesemakers who do not fill out the worksheet.

Rules:

- Ask one short, concrete question at a time.
- Do not ask “What makes your cheese special?”
- Do not ask “What is your story?”
- Start with facts.
- Keep questions non-intimidating.
- After about ten questions, summarize possible story directions.

Sample first questions:

1. What cheese or company are we talking about?
2. In plain terms, what is the cheese?
3. What animal milk is involved?
4. Where is it made?
5. Where does the milk come from?
6. What cheese family or tradition does it belong to?
7. What cheeses would someone compare it to?
8. What do you say when handing someone a sample?
9. What do people say when they taste it?
10. Who are you hoping will buy, sell, serve, or talk about this cheese?

---

# Research guides folder

## `research-guides/README.md`

Explain that research should enrich the story, not replace the cheesemaker’s truth.

## `research-guides/cheese-style-research.md`

Give the AI instructions for researching a cheese style.

Use this language:

> Conduct research into the type, family, or tradition of cheese the cheesemaker names.
>
> Find its history, where it is generally believed to have developed, why it developed there, who is associated with developing it if known, and what practical problem the style was solving.
>
> Look for what makes this style distinctive in the larger world of cheese: milk type, texture, rind, aging, flavor, serving traditions, production method, seasonal logic, and common reference cheeses.
>
> If the history is disputed or uncertain, say so. Do not pretend there is one clean origin story if there is not.

Add:

- The goal is not to dump history into the final story.
- The goal is to find context that might help explain why this cheese matters.

## `research-guides/location-research.md`

Give the AI instructions for researching place.

Use this language:

> Conduct research into the location the cheesemaker provides — whether that is a farm address, creamery address, town, county, region, or milk-source location.
>
> Look for concrete details that might help tell a richer, more truthful story: local history, geography, landscape, beauty, weather patterns, seasons, soil, water, elevation, agriculture, dairy history, food traditions, and other distinctive characteristics.
>
> Do not turn this into generic tourist language. Avoid “charming,” “picturesque,” and “nestled in the hills” unless there is a specific fact behind it.

Add:

- Keep researched place context separate from facts provided by the cheesemaker.
- Ask before turning plausible connections into claims.

## `research-guides/vermont-context-research.md`

Give the AI guidance for using Vermont context.

Include:

- Vermont’s dairy history
- Vermont’s landscape and climate
- seasonality and pasture
- the role of small farms and creameries
- the relationship between local identity and national markets
- co-ops, independent grocers, cheese shops, wholesale channels, and farmers markets

The AI should use this context carefully. “Vermont” should not become a lazy substitute for specificity.

## `research-guides/how-to-separate-research-from-claims.md`

Create a practical source-separation protocol.

Require the AI to organize research findings under headings:

```text
What the cheesemaker told me
What the Vermont Cheese Story Kit says
What outside research suggests
Possible connection to confirm
```

---

# Cheese styles folder

For each cheese-style file, create a concise, useful guide for the AI.

Each file should include:

1. What this cheese style is.
2. Where it developed, if known.
3. Why it developed or what practical problem it solved.
4. Typical milk, texture, rind, aging, and flavor characteristics.
5. Common reference cheeses.
6. What a cheesemonger might want to know.
7. What a general customer might find interesting.
8. Story opportunities.
9. Follow-up questions for a cheesemaker using this style.
10. Cautions: what not to assume.

Use external research where needed. Cite sources if the final repository format allows citations.

The required files are:

- `alpine.md`
- `cheddar.md`
- `washed-rind.md`
- `bloomy-rind.md`
- `fresh-goat.md`
- `blue.md`
- `tomme.md`
- `gouda-style.md`
- `lactic.md`
- `pasta-filata.md`
- `mixed-milk.md`

Keep each style guide useful but not enormous. Aim for practical story context, not an encyclopedia entry.

---

# Vermont context folder

## `vermont-context/README.md`

Explain that Vermont context should enrich stories but never replace the specific facts of a particular farm, creamery, or cheese.

## `vermont-context/vermont-dairy-history.md`

Create a concise history of dairy in Vermont.

Focus on story-relevant context, not exhaustive history.

Include:

- dairy as part of Vermont agricultural identity
- small farms and regional agriculture
- shifts in dairy economics
- how artisan cheesemaking fits into a broader dairy landscape

Use reliable sources and cite them if possible.

## `vermont-context/vermont-cheese-history.md`

Create a concise history of artisan cheese in Vermont.

Include:

- emergence of Vermont as a recognized artisan cheese region
- role of small producers
- relationship between Vermont identity and national cheese markets
- the importance of cheesemongers, co-ops, farmers markets, specialty retailers, and wholesale channels

Avoid over-centering any one company unless necessary.

## `vermont-context/geography-and-regions.md`

Create a practical guide to Vermont geography for storytelling.

Include:

- mountains
- valleys
- rivers
- pasture
- forest
- soil and terrain at a high level
- how geography can shape farm life, without making unsupported claims about specific cheeses

## `vermont-context/weather-seasonality-pasture.md`

Create a guide to Vermont weather, seasons, pasture, forage, and milk seasonality as potential story context.

Be careful:

- Do not claim that all Vermont cheese varies in a specific way by season.
- Present seasonality as something to ask about and confirm.

## `vermont-context/milk-animals-and-landscape.md`

Create a guide to how milk, animals, feed, landscape, and management choices can matter in cheese stories.

This should help the AI ask better questions.

Do not overstate cause and effect.

## `vermont-context/retail-coops-and-cheese-trade.md`

Create a practical guide to the channels through which small cheesemakers’ stories travel.

Include:

- co-ops
- independent grocers
- cheese shops
- cut-to-order shops
- farmers markets
- wholesale buyers
- distributors
- chefs
- shelf tags
- product info sheets
- websites

The key idea:

> The story must travel through people and materials when the cheesemaker is not there.

---

# Audiences folder

For each audience file, explain what that audience needs from a cheese story.

Each file should include:

1. What this audience cares about.
2. What they do not need.
3. What level of technical detail is useful.
4. What kind of language works.
5. What a 15-second version should accomplish.
6. What follow-up questions the AI should ask.

Required files:

- `general-public.md`
- `farmers-market-customers.md`
- `cheese-shop-customers.md`
- `cheesemongers.md`
- `retail-buyers-and-coops.md`
- `wholesalers-and-distributors.md`
- `chefs-and-restaurants.md`
- `online-customers.md`
- `press-and-food-writers.md`

Audience guidance examples:

- General customers need vivid, plain language and a reason to care.
- Cheesemongers need sensory details, style context, comparison points, and repeatable language.
- Retail buyers need practical reasons the cheese belongs in their case.
- Wholesalers need clarity, differentiation, reliability, and trade usefulness.
- Chefs need use cases, flavor behavior, pairing potential, format, and consistency.

---

# Examples folder

## `examples/README.md`

Explain that examples are teaching tools, not templates to copy.

## `examples/before-and-after-examples.md`

Create several before-and-after examples.

Each example should include:

- generic version
- what is wrong with it
- better version
- why the better version works

Use fictional or clearly anonymized cheeses unless you have permission or public sources.

## `examples/good-story-patterns.md`

Create examples of strong story patterns, such as:

- style/history story
- maker journey story
- place story
- technique story
- sensory story
- buyer-use story
- customer reaction story

Each pattern should include a brief explanation and a short fictional example.

## `examples/bad-ai-slop.md`

Create a file showing bad generic AI copy.

Include examples like:

- “crafted with passion”
- “nestled in the rolling hills of Vermont”
- “a unique flavor journey”
- “premium artisan cheese made with care”

For each, explain why it is weak and how to replace it with specifics.

## `examples/fictional-cheese-stories.md`

Create several fictional cheese-story examples.

Use clearly fictional names and creameries.

Include at least:

- a washed-rind cow’s milk cheese
- a fresh goat cheese
- an Alpine-style cheese
- a cheddar-style cheese
- a blue cheese

Each example should show a unified story with a center of gravity, not a checklist.

## `examples/product-info-sheet-examples.md`

Create examples of product info sheet language.

Include:

- short product description
- sensory notes
- style context
- maker/place note
- serving or use suggestions
- trade talking points

## `examples/spoken-pitches.md`

Create examples of 15-second spoken pitches for market tables, tastings, and cheese counters.

They should sound like real people talking, not brochure copy.

## `examples/buyer-facing-examples.md`

Create examples aimed at retail buyers, co-ops, wholesalers, distributors, and chefs.

The tone should be practical and clear.

---

# Output templates folder

Each output template should tell the AI how to turn raw story material into a specific asset.

Required templates:

## `output-templates/fifteen-second-spoken-pitch.md`

A short spoken pitch someone could say at a market table, tasting, or cheese counter.

Should be memorable, plain, and repeatable.

## `output-templates/seventy-five-word-description.md`

A concise product description for websites, product sheets, or retail partners.

Should not cram in every detail.

## `output-templates/product-info-sheet.md`

A template for a product slick / info sheet.

Include sections:

- cheese name
- plain description
- milk and format
- style context
- sensory notes
- story paragraph
- serving / pairing / use ideas
- buyer talking points
- practical details, if provided

## `output-templates/website-product-page.md`

A website product page structure.

Include:

- headline
- short hook
- story paragraph
- tasting notes
- serving ideas
- where to buy or inquire

## `output-templates/buyer-email.md`

A concise buyer email template.

Include:

- what the cheese is
- why it may fit the buyer’s case, shop, menu, or customers
- the strongest story angle
- practical ask

## `output-templates/tasting-table-script.md`

A table script for farmers markets, tastings, and events.

It should sound conversational.

Include a structure like:

1. Invite tasting.
2. Name the cheese plainly.
3. Give one memorable story point.
4. Tell the person what to notice.
5. Offer a serving or pairing idea.

## `output-templates/package-or-label-copy.md`

Short label or package copy.

Warn the AI that packaging has very little room. It should choose one strong phrase or one tiny story, not a full essay.

---

# Review checklists folder

## `review-checklists/anti-slop-checklist.md`

Create a checklist the AI can use to evaluate its own output.

Questions:

- Does this sound like any cheese could have written it?
- Are there empty adjectives?
- Are there unsupported claims?
- Is this a checklist instead of a story?
- Is there a clear center of gravity?
- Would a cheesemonger or customer remember this?

## `review-checklists/truth-checklist.md`

Create a truth and evidence checklist.

Questions:

- What facts came from the cheesemaker?
- What came from the repository?
- What came from outside research?
- What is plausible but unconfirmed?
- What must be asked before final copy?

## `review-checklists/audience-fit-checklist.md`

Create a checklist for audience fit.

Questions:

- Who is this for?
- Does it use the right level of technical detail?
- Is it useful to someone who has to repeat the story?
- Does it help the audience buy, sell, serve, or enjoy the cheese?

## `review-checklists/final-story-checklist.md`

Create a final review checklist.

The final story should be:

- truthful
- specific
- unified
- memorable
- useful
- plainspoken
- worth repeating
- connected to why the cheese is special and worth paying more for than commodity cheese

---

# Writing style for the repository

Use plain English.

Avoid jargon unless necessary. If you use a technical term, explain it.

Write for an AI tool, but make the files human-readable.

Be practical. This is not an academic project. This is a working kit for cheesemakers and AI tools.

Use short sections and clear headings.

Make the AI’s job obvious.

---

# Research standards

When creating the repository content, conduct research where needed, especially for:

- cheese-style histories
- Vermont dairy history
- Vermont artisan cheese context
- geography and seasonality
- trade audiences and cheese retail context

Use reliable sources. Prefer:

- official cheese organizations
- university extension sources
- government agricultural sources
- reputable food history sources
- respected cheese books or publications
- Vermont agricultural or historical sources
- reputable trade sources

If a fact is uncertain or disputed, say so.

Do not invent clean origin stories for cheese styles when the history is messy.

Do not imply that all cheeses in a style follow the same rules.

---

# What not to create

Do not create a complicated participant guide.

Do not create multiple alternate user workflows.

Do not tell cheesemakers they need to understand GitHub.

Do not create a technical manual about GitHub.

Do not create a generic branding workbook.

Do not ask participants to identify “what makes your cheese special” as a starting point.

Do not write examples that sound like generic luxury food marketing.

Do not make AI the hero. The cheesemaker, the cheese, and the place are the heroes. AI is only a tool.

---

# Desired final output from you, the LLM

Create the full repository documentation described above.

For each file:

1. Use the exact file path as a heading.
2. Write the complete Markdown content for that file.
3. Keep files concise but useful.
4. Include citations or source notes in research-heavy files if the environment supports them.
5. Clearly label fictional examples as fictional.
6. Make sure the repository works as a source library an AI tool can read before helping a cheesemaker.

The final repository should make this workflow possible:

A cheesemaker uploads a worksheet or voice memo and tells the AI:

> Before helping me, read the Vermont Cheese Story Kit at this repository. Use that source library as your guide. Then use my worksheet or voice memo as raw material.

The AI should then be able to help the cheesemaker discover and develop a compelling, truthful, unified story about their cheese, maker journey, or farm / creamery / place.
