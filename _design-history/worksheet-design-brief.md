# Standalone Design Brief: Vermont Cheese Council Story Worksheets

**Purpose:** Historical design rationale for the printed worksheet packet. **LLM should skip.**

> **Historical document — not LLM input.** This brief was the prompt used to design the printed worksheet packet. The packet now exists as `cheese_worksheets.pdf` and is titled **"Tell Your Story"** (not "Make the Value Travel" as proposed below). The printed PDF is the canonical artifact for what cheesemakers will actually upload. This brief is preserved as design rationale for future maintainers; the LLM should not treat it as instructions for its own behavior — for that, see `START_HERE_FOR_LLM.md` and `ai-master-instructions.md`.

## What this document is

Use this Markdown file as a standalone prompt for an LLM-based design app or document-generation tool. It contains all the context, goals, language, page structure, and worksheet copy needed to create a simple printed handout packet for a Vermont Cheese Council conference session led by Adam Davidson.

The design app should generate a clean, printable worksheet packet, not a polished marketing brochure. The packet should be usable by cheesemakers during a live 9am session. It should also be useful afterward: participants can hand-fill the pages, photograph or scan them, and upload them to an AI tool that will help them uncover and develop the story of their cheese, themselves, or their farm/creamery.

---

# 1. Context for the design app

## Who Adam Davidson is

Adam Davidson is the co-founder of NPR’s *Planet Money*, a former journalist for *The New York Times* and *The New Yorker*, and the author of *The Passion Economy: The New Rules for Thriving in the Twenty-First Century*. In this conference session, he is applying ideas from *The Passion Economy* to artisan cheesemakers in Vermont.

Adam’s core argument is that artisan cheesemakers are not selling a commodity. They are selling a value-rich product shaped by land, animals, milk, season, craft, history, taste, judgment, and human choices. Their challenge is not that they lack value. Their challenge is that this value often does not travel clearly to buyers, cheesemongers, co-op staff, wholesalers, chefs, and customers.

## The conference setting

This is for a Vermont Cheese Council conference. The day is focused on the “last mile” of artisan cheese: helping cheesemakers communicate the value already present in their cheese.

Adam’s 9am opening hour will begin with a Passion Economy frame:

- Older local economies had **intimacy without scale**.
- The twentieth-century commodity economy created **scale without intimacy**.
- The current moment makes possible **intimacy at scale**.
- Artisan cheese is a perfect example of a product that can carry intimacy across distance, but only if the story travels with it.

Adam will briefly use the Braun Brush story from *The Passion Economy* as a five-minute business parable. Braun Brush survived by getting out of commodity brushes and focusing on specialized, high-value problems where its judgment mattered. The direct lesson for cheesemakers: do not let the market treat your cheese as an interchangeable category. Help people understand the judgment embedded in the cheese.

AI will be introduced as an optional tool. It is not the subject of the day. The subject is story, value, and craft. AI is useful because it can interview the cheesemaker, organize raw material, research the background of cheese styles and places, suggest story directions, and expose weak or generic language. AI should not invent facts or write fake authenticity.

## The audience

The audience is made up of Vermont cheesemakers and related cheese businesses. Many are small operations. Some may have only a few people doing everything: farming, cheesemaking, packaging, sales, marketing, and customer communication.

Assume many participants are not professional marketers. Some may be skeptical of AI. Some may be intimidated by story exercises. Some may have never thought of their cheese story in a structured way.

The worksheet must not ask questions like “What makes your cheese special?” or “What is your brand story?” Those questions are too abstract and put the burden on the cheesemaker to already know the answer.

Instead, the worksheet should ask concrete, answerable questions that gather raw material. The AI tool can then help identify the story hiding in the facts.

---

# 2. Core design principle

The packet should communicate this idea:

> Do not try to write a finished story yet. Just give facts, fragments, examples, and details. The story will come from the material.

The worksheets are not meant to produce polished copy during the 9am hour. They are meant to create raw material that can later become:

- a clearer story direction
- a 15-second spoken pitch
- a product sheet or info sheet
- website copy
- a buyer email
- table or tasting language
- packaging or label language
- follow-up questions for a deeper AI interview

The tone should be warm, practical, plainspoken, and non-intimidating. The design should feel like a field notebook or working farm/creamery tool, not a branding-agency intake form.

---

# 3. Design requirements

Create a printable packet with four pages:

1. **How to Use This Packet**
2. **Worksheet 1: The Cheese Story**
3. **Worksheet 2: The Maker Story**
4. **Worksheet 3: The Farm / Creamery / Place Story**

Recommended format:

- US Letter size, 8.5 x 11 inches
- Black-and-white friendly
- Enough blank space for handwriting
- Clear section headers
- Checkboxes where useful
- No dense paragraphs on participant-facing pages
- Avoid glossy corporate styling
- Avoid cheesy clip art
- Use simple, legible typography
- Make it easy to photograph each page with a phone

Each worksheet page should include a small box titled **“AI instruction for this page”** so that a participant can photograph only that page and still get useful help from an AI tool.

Use the phrase **“AI tool”** on participant-facing pages rather than “LLM,” unless the text is explicitly written for the design app.

---

# 4. Packet title

Use this title:

# Make the Value Travel

Subtitle:

## Quick story worksheets for cheesemakers

Short explanatory line:

> These pages are not here to make you sound polished. They are here to help you gather the facts, fragments, and details that make your cheese worth understanding.

---

# 5. Page 1 copy: How to Use This Packet

## Make the Value Travel

### Quick story worksheets for cheesemakers

Do not try to write polished copy. Do not try to figure out what makes you special. Just give facts, fragments, examples, and details. The story will come from the material.

Use these pages in whatever way works for you.

### How are you using this packet?

Check any that apply:

□ I will fill this out by hand.  
□ I will talk through the answers with someone else.  
□ I will take a photo of a worksheet and upload it to an AI tool.  
□ I am not filling this out. I want an AI tool to interview me from scratch.  
□ I want the AI tool to research the cheese style, place, or context.  
□ I do **not** want outside research. I only want the AI tool to use what I provide.

### Who is this story for?

Choose one or two.

#### General public

□ Farmers market customers  
□ Cheese shop customers  
□ Co-op / independent grocery customers  
□ Online customers  
□ Visitors to our farm or creamery  
□ People who are curious but not cheese experts  
□ Other: _______________________________

#### Cheese professionals

□ Cheesemongers  
□ Retail buyers  
□ Co-op staff  
□ Wholesalers / distributors  
□ Chefs / restaurants  
□ Food writers / press  
□ Tourism or event partners  
□ Other: _______________________________

### What do you want help making?

□ A clearer story direction  
□ A 15-second spoken pitch  
□ Product sheet / info sheet language  
□ Website copy  
□ Buyer email  
□ Table / tasting script  
□ Packaging or label language  
□ I’m not sure yet

---

## General AI prompt

After filling out one or more worksheets, take a photo and upload it to ChatGPT, Claude, Gemini, or another AI tool. Use this prompt:

> I am an artisan cheesemaker working on the story of my cheese, my own journey, or my farm/creamery. This is part of a workshop about helping the value in artisan cheese travel to customers, cheesemongers, buyers, wholesalers, and other people who are not in the room with me.
>
> Read the worksheet I upload. Do not invent facts about me, my cheese, my animals, my creamery, or my business.
>
> Use what I provide as raw material. Your job is to help me find possible storylines, identify what is missing, and ask better questions.
>
> If I checked “I am not filling this out,” interview me from scratch. Ask one short, concrete question at a time. Do not ask me “what makes this special?” or “what is my story?” Start with facts: what I make, where I make it, where the milk comes from, what cheese family it belongs to, who buys it, and what I currently say about it.
>
> If I name a cheese style or family, and you have browsing or search available, research the history, characteristics, and common reference points for that cheese style. Keep researched background separate from facts about my specific cheese. Cite sources when possible.
>
> Do not write generic marketing copy. Avoid empty words like “artisan,” “authentic,” “premium,” “unique,” “local,” and “handcrafted” unless they are backed by specific facts.
>
> First give me:
>
> 1. The strongest raw material I gave you
> 2. Three possible story directions
> 3. What is missing
> 4. Five follow-up questions
>
> Do not write final copy until I ask.

---

# 6. Page 2 copy: Worksheet 1 — The Cheese Story

## Worksheet 1: The Cheese Story

Use this page if you want help telling the story of one cheese. Do not try to make it sound impressive. Just write what is true.

### What kind of cheese is this?

**Cheese name:**  
____________________________________________________________

**In the plainest possible terms, what is it?**  
Milk type, style, age, format, rind, category, etc.

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

### Animal and milk

**What animal milk is involved?**

□ Cow  
□ Goat  
□ Sheep  
□ Mixed milk  
□ Other: _______________________________

**Anything specific about the animals or milk?**  
Breed, raw/pasteurized, grass, hay, seasonal milk, single herd, bought-in milk, etc.

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

### Cheese family / tradition

**What cheese family or tradition does this belong to?**  
Circle or write in.

Alpine / cheddar / washed rind / bloomy rind / fresh / blue / tomme / Gouda-style / lactic / pasta filata / mixed milk / other:

____________________________________________________________

**What other cheeses would a cheesemonger compare it to?**  
These do not have to be exact. They are just reference points.

1. ________________________________________________________
2. ________________________________________________________
3. ________________________________________________________

### Taste, texture, and use

**What words do you currently use to describe the taste or texture?**  
Use your normal words. Don’t make them fancy.

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

**What does the cheese do over time?**  
Aging, ripening, rind development, texture change, flavor change, seasonal variation.

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

**How do you usually suggest people eat or serve it?**

____________________________________________________________  
____________________________________________________________

**What do customers often say when they taste it?**  
Actual remembered phrases are best.

____________________________________________________________  
____________________________________________________________

**Copy one phrase you currently use on a label, website, product sheet, social post, or table pitch:**

____________________________________________________________  
____________________________________________________________

---

### AI instruction for this page

Take a photo of this page and upload it to an AI tool with this instruction:

> Use this worksheet to help me build the cheese-centered story. If I named a cheese family or similar cheeses, research the history, purpose, and characteristics of that cheese style. Explain what that tradition usually solves or expresses. Then compare that background to the specific facts I gave you.
>
> Keep two sections separate:
>
> 1. General cheese background
> 2. Facts about my cheese
>
> Do not invent facts about my cheese. Suggest three possible cheese-centered story angles and ask me five follow-up questions.

---

# 7. Page 3 copy: Worksheet 2 — The Maker Story

## Worksheet 2: The Maker Story

Use this page if you want help telling the story of the person or people behind the cheese. This is not a biography assignment. The goal is to find the parts of your journey that help someone understand the cheese.

### Who is behind the cheese?

**Your name / company name:**  
____________________________________________________________

**What were you doing before cheese, or before this cheese?**  
Job, farm work, family business, school, food work, dairy work, something else.

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

### How did cheese pull you in?

Circle any that fit, then add a detail.

Person / place / accident / job / animal / taste / crisis / opportunity / obsession / practical need / family history / other

Detail:

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

### What was hard about getting here?

Circle any that fit, then add a detail.

Money / land / animals / regulation / learning the craft / finding customers / family / weather / mistakes / burnout / equipment / time / other

Detail:

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

### Who shaped the work?

**Who taught you, influenced you, helped you, or challenged you?**

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

### What do you already say?

**When you hand this cheese to someone, what do you usually say?**  
Write the normal spoken version.

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

**What do you find yourself explaining again and again?**

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

**When people eat your cheese, what do you hope they understand, notice, or feel?**  
This can be practical, emotional, sensory, or economic.

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

---

### AI instruction for this page

Take a photo of this page and upload it to an AI tool with this instruction:

> Use this worksheet to help me build the maker-centered story. Do not turn this into a heroic biography unless the facts support it. Look for the parts of my journey that help someone understand the cheese: choices, constraints, influences, risks, values, mistakes, or turning points.
>
> Give me three possible maker-centered story angles:
>
> 1. A practical craft story
> 2. A personal journey story
> 3. A values or mission story
>
> For each one, tell me what facts support it and what questions I still need to answer. Do not write final copy yet.

---

# 8. Page 4 copy: Worksheet 3 — The Farm / Creamery / Place Story

## Worksheet 3: The Farm / Creamery / Place Story

Use this page if you want help telling the story of where the cheese comes from. Start with concrete facts. The poetry can come later.

### Where does this cheese come from?

**Where is the cheese made?**  
Town, county, region, public address if appropriate.

____________________________________________________________  
____________________________________________________________

**Where is it aged?**  
Same place? Different cave, cellar, facility, affineur, co-op, partner?

____________________________________________________________  
____________________________________________________________

**Where does the milk come from?**  
Same farm? Neighboring farm? Specific herd/flock? Multiple farms? Town/county?

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

### Animals and land

**What animals provide the milk?**  
Species, breed if relevant, herd/flock size if useful, anything about how they are raised.

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

**What is the land like?**  
Pasture, hills, valley, forest, hay fields, soil, weather, climate, nearby water, elevation, anything concrete.

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

### Season and physical details

**What changes during the year?**  
Milk, pasture, feed, weather, humidity, rind, flavor, production schedule, customer demand.

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

**What is one physical detail someone would see, smell, hear, or notice if they visited?**

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

**What is one thing about this place that people would not know unless you told them?**

____________________________________________________________  
____________________________________________________________  
____________________________________________________________

---

### AI instruction for this page

Take a photo of this page and upload it to an AI tool with this instruction:

> Use this worksheet to help me build the place-centered story. Look for concrete place details: land, animals, milk source, weather, season, aging environment, community, and local constraints.
>
> Do not make the place sound poetic unless the facts support it. Start with the concrete facts. Then suggest three possible place-centered story angles.
>
> If I gave a precise location and you have browsing or search available, research the town, county, geography, climate, agricultural context, and local history only as background. Do not claim that this background directly shaped my cheese unless I said so.
>
> Separate:
>
> 1. What I told you
> 2. What you researched
> 3. What still needs to be confirmed
>
> Do not write final copy yet. Ask five follow-up questions.

---

# 9. Optional short prompt for people who do not fill anything out

This can appear in a small box on Page 1 or as a tear-off / sidebar.

## If you do not want to fill this out

Use this AI prompt:

> I am an artisan cheesemaker and I do not want to fill out a worksheet. Interview me from scratch. Ask one short, concrete question at a time. Do not ask me “what makes this special?” or “what is my story?” Start with facts: what I make, where I make it, where the milk comes from, what cheese family it belongs to, who buys it, and what I currently say about it. After ten questions, summarize the strongest possible story directions.

---

# 10. Optional second-step AI prompt

This can appear at the end of the packet or in a small “What to do next” box.

## After the AI asks follow-up questions

Use this prompt after you have answered the first round of follow-up questions:

> Now create three rough story options from this material:
>
> 1. A cheese-centered story
> 2. A maker-centered story
> 3. A place-centered story
>
> For each one, give me:
>
> - a one-sentence version
> - a 75-word version
> - who this story is best for: buyer, cheesemonger, chef, distributor, farmers market customer, online customer
> - what facts from my worksheet support it
> - what still needs to be checked or clarified
>
> Keep the language plain and specific. Avoid words like authentic, artisan, premium, unique, handcrafted, and traditional unless they are backed by specific facts.

---

# 11. How Adam will use the packet during the 9am hour

This is background for the design app, not necessarily text for the participant packet.

Adam will not ask participants to complete the whole packet during the morning hour. He will explain the three story types and then invite participants to choose one worksheet:

1. The cheese story
2. The maker story
3. The farm / creamery / place story

Participants should spend roughly five to seven minutes filling out whichever worksheet feels easiest or most urgent.

Adam may then ask them to star the most concrete thing they wrote. Not the most impressive thing. The most concrete thing.

The point of the exercise is not to finish. The point is to create raw material that can be developed later in the day or after the conference.

---

# 12. Design tone and language reminders

Use plain English. Avoid jargon. Avoid asking participants to define their “brand,” “differentiator,” “positioning,” “value proposition,” or “unique selling point.” Those concepts may be useful later, but they are too intimidating for this handout.

Ask for observable facts and remembered language:

- What is it?
- Where does the milk come from?
- What cheese family does it belong to?
- What do people say when they taste it?
- What do you say when you hand it to someone?
- Where is it made or aged?
- What changes by season?
- Who taught or influenced you?
- What are you already writing on labels, websites, or product sheets?

The worksheet should make participants feel:

- “I can answer this.”
- “I do not need to be a marketer.”
- “The story can be found in the facts.”
- “AI can help, but it should not invent anything.”

---

# 13. Key language to preserve

Please preserve these phrases somewhere in the packet or supporting material:

- **Make the value travel**
- **Do not try to write the story yet**
- **Give facts, fragments, examples, and details**
- **The story will come from the material**
- **Do not invent facts**
- **Keep researched background separate from facts about my cheese**
- **Do not write final copy yet**
- **Ask five follow-up questions**

---

# 14. Final output requested from the design app

Generate a clean, printable, four-page worksheet packet titled **Make the Value Travel**.

The final packet should include:

1. A short “How to Use This Packet” page with checkboxes, audience choices, output choices, and the general AI prompt.
2. A Cheese Story worksheet with concrete questions and an AI instruction box.
3. A Maker Story worksheet with concrete questions and an AI instruction box.
4. A Farm / Creamery / Place Story worksheet with concrete questions and an AI instruction box.

Make the pages easy to scan or photograph. Leave enough space for handwriting. Keep the design humble, practical, and clear.
