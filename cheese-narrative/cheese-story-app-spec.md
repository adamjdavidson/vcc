# Your Cheese Story — Product & Technical Spec

*Version 8 · Oct 11, 2026 · For the Vermont Cheese Council workshop, Wed Oct 14, 2:00–5:00pm ET*

**How to read this.** ✅ = Adam decided. ◻ = proposed default, stands unless Adam changes it.

**Name** ✅: *Your Cheese Story.* **Working example** ✅: von Trapp Farmstead, throughout the build, dry runs, and Wednesday.

## 0. How the work is ordered ✅ (Adam's core process)
Story first, fact-checking last.
- **Every step until the last** works on big-picture structure: the big emotional arcs; the big elements and pieces of the story; who the audience is; which parts of the story they'll find most appealing and engaging; how to shape and tell it; how history, family, and the land come together.
- **Fact-checking, accuracy, and compliance happen only at the very last step** ("Check the facts"). That's where 45 vs. 48 cows, store hours, raw vs. pasteurized, and dates get settled.
- Before the last step, the app never asks about small facts, numbers, dates, hours, prices, addresses, or where to buy; never pauses to resolve discrepancies between sources; and leaves logistics out entirely. It still never invents.
- Questions are written by the AI, held to three rules: one concrete thing the maker can answer in a minute (a surprise about the land, a particular challenge, a moment, a person who taught them, a choice); never vague or abstract, and never asking them to narrate feelings; never the same question twice in any wording, and no circling back to the same cheese, person, or event. The AI writes 3 candidates per turn; the app checks each against these rules and against everything already asked, and uses the first that passes. Planned questions from step 4 are asked first.
- No "what we know so far" panel on screen. Gathered material works in the background.

---

## 1. Purpose and success

**What it is.** A web app that helps an artisanal cheesemaker find and tell the story of their creamery and cheeses through an ongoing conversation with AI. The app never invents the story. It researches, asks the maker what they want people to understand, proposes, listens, and drafts. Every correction shapes everything generated from then on, and anything made earlier is flagged for a one-click refresh. The more the maker talks and pushes back, the more the output becomes theirs.

**Users.**
- ✅ Adam, driving a live demo on Zoom (screen-shared) for the VCC workshop.
- ✅ Cheesemakers afterward, on their own (von Trapp Farmstead, Grafton Village Cheese, others).
- ✅ Cheesemongers are not users yet, but several outputs are built for them.

**Wednesday is a success if:**
1. Adam types "von Trapp Farmstead" and within ~3 minutes the room sees a populated Creamery Card with sources.
2. The maker says, in their own words, what they want people to understand — and the hypothesis and evaluation screens say something specific enough that the von Trapp person reacts ("that's right" or "no, actually…").
3. The interview runs live on what they say in Zoom, and the room watches new facts land on the card.
4. The warm run and the outputs come out recognizably *theirs*, with no unsupported claims in anything public-facing.
5. One correction visibly changes downstream outputs.
6. After the session, a maker can open the link on their own Claude account and run the same flow.

---

## 2. Platform and architecture

### 2.1 Where it runs
- ✅ **A published Claude artifact** (a web page hosted on claude.ai). Its AI calls run on the *viewer's* Claude plan: Adam's on Wednesday, each maker's afterward. No API keys, no servers, no hosting to maintain.
- ◻ One self-contained page (HTML + JavaScript) with the kit built into it (6.3).
- Makers need a Claude account and must be signed in. Adam shares the link. The first time the app calls Claude, the viewer is asked to allow it to use their Claude usage.

### 2.2 Capabilities the page declares
| Capability | What it's for | Notes |
|---|---|---|
| `sample` | Every AI step | Runs on the viewer's plan. First call asks consent. |
| `mcp` | Web search and page reading during lookup, persona research, PR research | Uses the viewer's connected search tool. ✅ Primary: **Parallel Search** (`web_search`, `web_fetch`) — free, no sign-in, one click to add from Claude's connector directory, so every maker can have it. Backup for Adam: **Exa**. |
| `downloads` | Exporting the story pack and the monger answer site | Viewer confirms each save. |

◻ No shared database. Each viewer's work saves in their own browser (section 9). This keeps every maker's material private by default and avoids sharing-permission complications for people outside Adam's account.

### 2.3 How an AI call works (constraints that shape the design)
Verified from the platform's documentation:
- **Each call is memoryless.** Claude sees only what the page sends, so every call is assembled fresh from the context contract (section 5.1).
- **No hidden system prompt.** Standing instructions go in as a leading message.
- **Size cap: 256 KB of text per call.** The full kit is too big to send whole, so each step loads only the files it needs (section 6). ◻ Target ≤120 KB per call.
- **Tools are page functions.** The page gives Claude two tools — `search_web(query)` and `read_page(url)` — which the page fulfills by calling the viewer's search connector. Claude decides when to use them.
- **Timing.** Thoughtful steps take 30–90 seconds; tool-using steps (lookup, PR) can take 1–3 minutes. Every long step streams progress, shows what it's doing, and has a Stop button.
- **Model tiers.** `quick` for small extraction jobs (seconds); `default` for interview turns and most outputs; `complex` for lookup synthesis, hypothesis, evaluation, warm run.
- **Structured results.** Steps that feed the card ask for JSON and use the platform's JSON mode; prose outputs stream as text.

### 2.4 Web access for makers
The AI calls an artifact makes can't browse on their own; the platform's only door to the web is a search connector on the viewer's Claude account. So:
- ✅ **Setup step for makers:** the start screen checks for Parallel Search. If it's missing, it shows a short "Connect Parallel Search (free, one click)" panel with plain steps, then rechecks. After that, lookup, persona research, and PR research work for makers exactly as in Adam's demo.
- **The bridge** (Free plan, or no connector): the app writes a research request the maker copies into an ordinary Claude chat; the chat searches the web and returns the results in a format the app reads; the maker pastes it back. Same research, one extra paste. Used for lookup, persona research, and PR research.
- Confirmed Oct 11: connectors inside apps require Pro, Max, Team, or Enterprise; on Team/Enterprise an Owner must add the connector for the team first.

### 2.5 Live Listen ✅
Adam presses **Listen**; what the maker says on Zoom is transcribed live into the interview.
- ✅ Build: a companion **Listener** in a separate Chrome window. Adam clicks Listen and picks the Zoom tab; the Listener transcribes the audio live with a speech-to-text service on Adam's account (roughly 25¢ per hour of audio) and passes each finished answer into the interview. It keeps the raw transcript with speaker labels alongside the cleaned text; only the maker's words can become "Maker said" facts — Adam's questions and remarks are labeled as his, and a misheard cheese name gets corrected, not filed.
- Requires Zoom to run in Chrome (the Zoom web client), since the Listener captures a browser tab.
- Confirmed Oct 11: apps on this platform can't capture audio or use the microphone, so the Listener runs beside the app.
- Makers on their own type, or use their computer's built-in dictation in the answer box.

---

## 3. Information model

Everything the app knows lives in one object per creamery: the **Creamery Card** and its attachments. Every AI step reads it; every step that learns something writes to it.

### 3.1 Fact
Every factual claim is a Fact — including the basics like location, milk, rind, and aging, so everything carries a source and can be corrected.
```
Fact {
  id
  text            // "Milk comes from the farm's own herd of ~40 Jerseys"
  source          // maker | website | web | claude_knowledge | kit | inferred
  sourceUrl?      // for website / web
  excerpt?        // the supporting passage, quoted, for website / web
  retrievedAt?    // when the page was read
  confirmed       // true once the maker states or confirms it
  status          // active | superseded | deleted — only active facts are ever used in generation
  supersededBy?   // the fact that replaced it (history kept, shown struck through)
  addedAt, addedInStep
}
```
In the app, the source shows as a gentle note in plain words: "you told us" · "from your website" · "from [publication or site name]" · "a guess — please check."

### 3.2 Creamery Card
```
Creamery {
  revision                         // increments on every change to the Card or Preferences
  name, website
  location: Fact
  overview: Fact[]                 // one-paragraph who-they-are
  people: { name, role, facts: Fact[] }[]
  land: Fact[]                     // farm, terrain, buildings, history of the land
  animals: Fact[]                  // species, breeds, herd size, grazing, care
  milk: Fact[]                     // own herd vs. purchased, raw vs. pasteurized, seasonality
  history: Fact[]                  // founding, turning points, family story
  practices: Fact[]                // make room, caves, aging, distinctive methods
  cheeses: Cheese[]
  where_sold: Fact[]               // farmstand, mongers, retail, wholesale, restaurants, online
  press_and_awards: Fact[]
  current_telling: { text, sourceUrl, retrievedAt }[]   // how they describe themselves now, quoted exactly
  open_questions: string[]
}

Cheese {
  name, style (one of kit's 10 styles or "other")
  milk: Fact, rind: Fact, aging: Fact, format: Fact, availability: Fact   // any may be empty
  facts: Fact[], first_angle?, story?
}
```

### 3.3 Session attachments
```
MakerIntent { wish: string, audiences: string[], raw: string }          // Step 2, in the maker's words
Preference { id, text, scope: all | <output kind> | <cheese>, createdAt } // editorial direction: "not about our family," "warmer," "less folksy"
Hypothesis { throughlines: Throughline[3], cheese_angles: {cheese, angle}[], cardRevision, stale }
Throughline { title, one_sentence, supporting_fact_ids[], works_for[], needs_confirming[], status: open|starred|dismissed }
Evaluation { strong[], generic[] (quoted current_telling + why), missing[], underserved_audiences[], interview_agenda[], cardRevision, stale }
Interview { agenda: {topic, status: open|covered|skipped}[],
            turns: {speaker: interviewer|maker|adam, raw, clean, mode: typed|mic|listen, extracted_fact_ids[]}[] }
WarmRun { lenses: LensResult[], creamery_story { one_line, paragraph }, cheese_stories: {cheese, one_line, paragraph}[], chosen, cardRevision, stale }
LensResult { lens, strength: strong|some|thin, material_fact_ids[], one_line }
Output { id, kind, target (creamery | cheese name), audience?,
         versions: {text, gaps[], createdAt, cardRevision, fromCorrectionId?}[], stale }
Correction { id, onWhat?, text, kind: fact | preference | both, factChanges: {added[], superseded[]}, preferenceAdded?, createdAt }
DemoLog { entries: {time, type: ai_call|kit_load|search|page_read|tool|error, detail}[] }
```

---

## 4. Screens

### Layout (all steps)
- **Header:** "Your Cheese Story," the creamery's name, and one small menu (Export, Large text, Look, Demo stories, Start over). Nothing else.
- **Progress:** a simple line of eight steps with the current one named ("Step 2 of 8 · In your words"); reached steps are clickable.
- **Center:** one column where the app speaks and the maker answers. One thing at a time.
- **What we know so far:** a quiet notebook at the side (a pull-up sheet on small screens), in plain sentences with gentle source notes. New lines fade in as they're found.
- **Large text** for screen sharing.

### Start screen
- One field: *"Creamery name or website."* Button: **Look it up.**
- Below: saved creameries (from this browser) · **Import** a story pack file.
- First visit only: a three-sentence explanation — this is a conversation; AI won't invent your story; the more you tell it, the better it gets — and a note that the app uses your Claude account.

### 4.1 Step 1 — Creamery lookup
- Shows a live activity list while running: "Searching: von Trapp Farmstead Waitsfield cheese" → "Reading: vontrappfarmstead.com/about" → "Found 6 cheeses" …
- The Creamery Card fills in two passes, each a complete result: a fast pass (basic facts, cheese list) lands first, then the deeper synthesis. While each pass runs, the activity list shows every search and page read as it happens.
- When done: a summary line ("12 facts from their website, 9 from press, 4 from Claude's knowledge to confirm"), the **cheese range** as a list (name · style · milk · aging), and two buttons: **Fix something** (opens card editing) and **Next: in your words**.
- If the connector is missing: the one-click connect panel (2.4); paste only if the maker skips it.

### 4.2 Step 2 — In your words ✅
Before the AI interprets anything, the maker speaks.
- Two open questions, answered by voice (Listen or mic) or typing:
  1. *"What do you wish people understood about you and your cheese?"*
  2. *"Who do you most want to reach?"*
- Answers saved as MakerIntent, raw and cleaned; any facts in them land on the Card as "Maker said."
- Everything after this starts from it: at least one hypothesis builds directly on the maker's own framing, and the evaluation measures their current telling against what they said they want understood.
- Button: **Next: first hypothesis.**

### 4.3 Step 3 — Pieces of your story ✅ (replaces "three stories")
Not finished stories. Ingredients, then a few ideas for how they could fit, built with the maker.
- **Pieces** (about 8, under 30 words each), grouped by kind: the history of your cheeses (the tradition behind the style), the craft and the choices, the land, the family, the people, how it started and what changed, Vermont's story, surprises. The AI covers as many kinds as the material honestly supports, always including tradition, craft, and land, and never forces a piece into a kind it doesn't fit. Tradition is written as tradition, not as a claim about this maker.
- Per piece: **This matters** · **More** (2–3 sentences on what's behind it, plus one big open question) · **Not really**. The maker can add their own piece and ask for **other pieces**.
- **How it could come together**: 4 ways shown with the pieces, each with a title (its shape, e.g. "Carrying it on, and remaking it"), the 3–4 pieces it brings together, a 70–110 word rough telling, and who it would land with. Per way: **This is close** · **Push on this** ("closer, but…" reworks just that one) · **Not us**. Plus **Show other ways** and **Build from the pieces I kept**.
- Kept pieces, set-aside pieces, and liked/not-liked ideas go into every later call.
- Button: **Let's talk it through.**
- Material behind it: after the creamery's own sources, the lookup runs a third "bigger picture" pass: the tradition of their cheese styles, their land and town, and Vermont's dairy story, from web searches plus the kit's deep research (style toolkits, Vermont dairy history 1600–1980, the artisan renaissance, place and season).
- Demo: von Trapp and Grafton have prepared pieces (tested against the live prompt); "other pieces" and the "what if" ideas run live.

### 4.4 Step 4 — Storytelling challenges and opportunities
Four panels:
- **Already strong** — what in their current telling works, and why.
- **Generic** — specific lines quoted from their own website or materials that could describe any creamery, each with a one-line why. (Checked against the kit's anti-slop guidance.)
- **Missing** — what a buyer, monger, or writer would want that isn't out there.
- **Underserved audiences** — who isn't being spoken to (e.g. mongers need a counter line; writers need a person and a problem).
- Bottom: **What the interview needs to learn** — 6–10 agenda items, editable, reorderable. This becomes the interview agenda.

### 4.5 Step 5 — Guided interview
- Chat layout. The interviewer asks **one short, concrete question at a time**, working through the agenda (shown as a checklist at the side, ticking off as topics get covered).
- **Answer input**: type (or the computer's built-in dictation) · **Listen** (the companion Listener, 2.5).
- After each answer: a quick extraction step pulls new facts onto the Creamery Card (the new line fades in, marked "you told us"), and any editorial direction ("we don't want to be the cute-cows place") into Preferences, and the interviewer picks the next question — a follow-up if the answer opened something rich, otherwise the next agenda item.
- **Driver controls** (Adam): *Skip* · *Ask something else* · *Go deeper on that* · a "note to interviewer" box ("ask about the 2011 flood") · **I'm done →**.
- The interview borrows the kit's rules: questions invite facts, not performance ("Who taught you that method?" not "How does that method express your values?"); never "what makes your cheese special?"
- ◻ Soft cap: after ~12 answers, the interviewer offers to wrap up; Adam can continue. Skipping agenda items is normal and expected — following a rich answer matters more than covering the list.

### 4.6 Step 6 — Warm run (the story)
- **Narrative library** grid — one tile per lens (◻ list in 4.6.1). Each tile: strength (strong / some / thin), the one-line story that lens would tell, the facts behind it. Thin lenses show the question that would unlock them ("Ask about the cows' names?" → sends back to interview).
- **The story:** the strongest unifying story for the creamery — a one-liner and a paragraph — and the same for each cheese.
- Per story: ★ / **Push on this** / **Try another lens as the spine**.
- Button: **Make things with it →**

#### 4.6.1 Narrative lenses ◻
1. The maker's personal story
2. The farm or creamery (the actual place and how it came to be)
3. The animals — breed, herd, how they're kept
4. The milk and the season
5. The development of a particular cheese
6. The deep history of the cheese's style or family
7. The tradition reinvented — how they use that history in new ways for new audiences
8. The accident or failure that taught them something
9. Survival — Vermont dairy's decline and value-added cheese as the way to stay
10. The land — what this ground was, what it is
11. The name — why it's called what it's called
12. The people around it — neighbors, partners, mentors

### 4.7 Step 7 — Outputs
✅ Every output is built; none is prioritized over another. A gallery grouped in five sections. Each output tile: what it is · **Make it** · a selector for which cheese (or the whole creamery) and, where relevant, which audience. Results appear in place, with Copy, Download, and a **That's not right / push it further** box. Any **gaps** (5.2) are listed under the output, each with an **Answer it** button.

| Group | Output | Spec ◻ |
|---|---|---|
| Selling | **Label language** | Front: ≤25 words. Back: ≤90 words. Plain, concrete, no slop words. |
| | **15-second pitch** | ~40 spoken words, what the maker says when handing over a sample. |
| | **Monger card** ✅ | One printable card per cheese: the one-sentence story a monger can retell while slicing; tasting notes (from the maker or a source, else a gap); pairings (labeled as suggestions); the honest answer to "why does it cost this much?" (from maker facts, else a gap); how to say the name, if it needs it; one "ask the customer" line. |
| | **Buyer email** | ≤180 words, to a retail or wholesale buyer; leads with what sells. |
| | **Why it costs more** | 3–4 sentences a maker or monger can say out loud, built only on facts about their own costs and practices; anything missing is a gap. |
| Audiences | **Personas** ✅ | Input: what you sell · who you think buys it · where it's sold · ✅ **how many you want, decided in the moment** (one, five, thirty) and any mix of consumers and trade. Research step checks the market. Each persona: who they are, where they buy, what they care about, the story that reaches them, one line that would land, one that would fall flat. |
| Press | **PR research and pitches** ✅ | Finds 5–8 food writers who have covered Vermont cheese, farmstead food, or the creamery's themes; for each: name, outlet, 1–2 recent relevant pieces, why they'd care. Every cited piece is opened and read before it's shown; a link that can't be opened or doesn't say what's claimed is dropped, and a writer with no verified piece is dropped. Then a custom pitch per writer, ≤200 words, referencing their actual work, leading with a person, a moment, or a problem, and offering only access the maker has confirmed (a visit, a milking). No connector → angles and writer profiles only, no names. |
| Social & video | **Social posts** ✅ | A set of 3: Instagram caption, Facebook post, newsletter blurb. Each built on a single concrete moment. |
| | **Video concept** ✅ | 60–90 seconds: the hook (first 3 seconds), 6–10 shot list that can be filmed on an ordinary day with a phone, voiceover script, and what to capture next time something happens (calving, the first spring milk). |
| Showcase | **Monger answer site** ✅ demo only | Something to show what's possible, not a finished product. Generated per creamery and per cheese: counter story, tasting notes, pairings, price answer, the questions customers actually ask, answered. Previewed in-app; downloadable as an HTML file. |

### 4.8 Step 8 — Corrections
- Every output and story has the **That's not right / push it further** box. Editing a fact directly on the Card counts as a correction too — it creates the same Correction record, appears in the Corrections view, and triggers the same refresh marking.
- **Two kinds of feedback, handled differently:**
  - **Facts** ("forty cows, not sixty") → the Card. New facts added as "Maker said"; the old one superseded, kept in history struck through, never used again.
  - **Direction** ("stop making this about our family," "make it warmer") → Preferences, not facts. Every later call honors them.
  - The app shows what it did with each correction ("Added a fact" / "Saved as direction") and Adam can flip it with one click.
- **What updates when:** a correction shapes all generation from that moment. That output regenerates at once. Everything else made earlier (hypotheses, stories, other outputs) is marked **"Refresh"**; a **Refresh all** button regenerates them. A refresh that fails keeps the previous version.
- A **Corrections** view lists every correction in order with what it changed — the visible record of "the more you push, the more it's yours."

---

## 5. AI steps

### 5.1 What every call receives (the context contract)
Every call, every step:
- The **core brief** (6.1).
- The **Creamery Card**, active facts only (superseded and deleted facts left out), with sources.
- **MakerIntent** — what they want understood, who they want to reach.
- **Preferences** — every piece of editorial direction so far that applies to this step: all-scope ones always, output-kind or cheese-scoped ones only when they match. Each output shows the directions it followed ("Following your direction: not about the family").
- **Choices made:** starred through-lines (lean in), dismissed ones (stay away), the evaluation agenda, and — from the warm run on — the chosen story.
- **The interview** — the last 8 turns verbatim (cleaned, speaker-labeled); earlier turns represented by the facts and preferences already extracted from them, plus any lines the maker said that are marked as quotable. Nothing is paraphrased by a summarizing step.
- Step-specific kit files (table below), the task, and the exact output format.

Rules in every call: never invent facts about the maker, their animals, milk, people, or business; keep provenance; Claude's own knowledge and inferences are always marked "confirm"; no slop vocabulary (the kit's list); concrete over abstract.

### 5.2 Evidence for public-facing copy
Applies to everything a customer, buyer, monger, or writer might read: label, 15-second pitch, monger card, buyer email, why-it-costs-more, social posts, PR pitches, the monger answer site.
- May state as fact: things the maker said or confirmed, and things sourced from their own website or published coverage.
- Never states as fact: Claude's general knowledge or inferences. Those become questions.
- Tasting notes, the price explanation, awards, and any offer of access (visits, milkings) must come from the maker or a source.
- Pairings and serving ideas are labeled as suggestions.
- **Anything missing appears as a visible gap** in the draft — *[ask: what do people say when they taste it?]* — never an invention. Gaps are listed under the output; **Answer it** sends the question to the maker (Listen, mic, or typing), the answer lands on the Card, and the output refreshes.
- The self-check (7r) traces every factual sentence to an allowed fact; anything it can't trace is cut or turned into a gap before the draft is shown.

Planning outputs (personas, video concept, hypotheses, stories) may include clearly labeled ideas and suggestions.

### 5.3 Steps

| # | Step | Tier | Tools | Extra kit loaded | Returns |
|---|---|---|---|---|---|
| 1a | Lookup — gather | complex | search_web, read_page | research/location-research, research/cheese-style-research, research/using-sources | JSON: Creamery Card with Facts + sourceUrls |
| 1b | Lookup — fallback | default | — | same | JSON from pasted text + Claude's knowledge |
| 2 | In your words — extract | quick | — | — | JSON: MakerIntent + any Facts |
| 1c | Lookup — bigger picture | quick plan + default | search_web | cheese-styles/<styles>, style toolkits, vermont-dairy-history, dairy-and-cheese-history-1600-1980, artisan-renaissance, place-and-season | JSON: tradition / land / history / vermont facts (source web, kit, or claude_knowledge) |
| 3a | Pieces | complex | — | examples/good-story-patterns, lenses, story-principles/what-story-is, + the bigger-picture files | JSON: {pieces: [{kind, text}]} |
| 3b | More on a piece | default | — | bigger-picture files | JSON: {more, question} |
| 3c | Ways it could come together | complex | — | examples/good-story-patterns, lenses, what-story-is, + bigger-picture files | JSON: {ways: [{title, brings, telling, for}]} |
| 3d | Push on a way | default | — | lenses + bigger-picture files | JSON: one way |
| 4 | Evaluation | complex | — | examples/bad-ai-slop, story-principles/avoid-checklist-stories, story-principles/story-vs-brand-positioning-copy, audiences/README | JSON: Evaluation |
| 5a | Next question | default | — | workflow/interview-from-scratch, worksheet question bank (from index.html) | JSON: {question, agendaItem, why} |
| 5b | Extract from answer | quick | — | — | JSON: new/changed Facts, new Preferences, agenda items covered |
| 5c | Clean the transcribed answer | quick | — | — | clean text per speaker; raw transcript kept |
| 6 | Warm run | complex | — | lens definitions; deep-research/* selectively by style (rule: load only for the styles and lenses with material); story-principles/passion-economy-for-cheesemakers | JSON: WarmRun |
| 7 | Each output | default | search/read for Personas and PR | the matching audience file(s) + output guidance file + review-checklists/* | text (or JSON for personas, PR list, monger site data) |
| 7r | Self-check | quick | — | review-checklists/anti-slop, truth | traces each factual sentence to an allowed fact (5.2); cuts or gaps what it can't; revises once before display |
| 8 | Apply correction | default | — | — | JSON: kind (fact / direction / both), fact changes, preference, regenerated output |

Timing targets ◻: 1a ≤3 min · 3, 4, 6 ≤90 s each · 5a/5b ≤10 s combined · each output ≤60 s · PR ≤3 min.

---

## 6. The kit inside the app

### 6.1 Core brief (new) ◻
A new ~3,000-word file distilled from `START_HERE_FOR_LLM.md`, `ai-master-instructions.md`, `story-principles/what-story-is.md`, `story-principles/truth-and-source-rules.md`, and `review-checklists/anti-slop-checklist.md`. Sent with every call.

### 6.2 New guidance files ◻
Written before the build, in the kit's existing voice:
- `lenses.md` — the 12 narrative lenses: what each is, what material it needs, a good and a weak example.
- Output guidance (in-app these are "outputs," not templates): `monger-card.md`, `personas.md`, `pr-research-and-pitches.md`, `social-posts.md`, `video-concept.md`, `monger-answer-site.md`.
- Existing output guides reused as-is: label language, 15-second pitch, buyer email, explaining premium price.

### 6.3 Loading
◻ The kit is built into the page as named text blocks — about 370 KB, well inside the page size limit — so nothing is fetched at run time. Each step selects only the blocks it needs (table in section 5). A per-call size check trims deep-research blocks first if a call would exceed the target.

---

## 7. Demo mode ✅ (redefined Oct 11)
Demo mode means Adam can show it smoothly: von Trapp Farmstead and Grafton Village Cheese are pre-baked, including the website research, the bigger-picture research, the first set of pieces, and the first four ways it could come together. Typing either name or website in any form ("von Trapp", "graftonvillagecheese.com") uses the prepared material with no live search; the lookup plays back in about 10 seconds. The menu has "Look up prepared creameries live" to run them live instead. It is NOT a developer view. There are no logs, timestamps, file names, prompts, or raw URLs anywhere in the app.

How the app shows its thinking, for everyone: in plain sentences, one at a time, as it works ("Looking for von Trapp Farmstead online…", "Reading your About page…", "There's a story here: Werner and Erika von Trapp started the farm in 1959."). That is the whole "how it works" view.

## 7a. Design principles ✅
- Friendly and calm for people who have never used AI. One clear thing on screen at a time. Plain words.
- A conversation, not a dashboard: one centered column where the app speaks and the maker answers.
- "What we know so far" is a quiet notebook to the side, in plain sentences, with gentle source notes ("from your website," "from a news story," "a guess — please check"). Tap a line to say "That's right," change it, or remove it.
- Settings (export, large text, look, demo stories) live in one small menu.
- Questions the app asks are big story questions (what they wish people understood, how it started, what changed, what's hard, who's part of it, what they'd show a visitor). Never logistics (hours, prices, addresses, herd counts). Where sources disagree on a fact, it becomes a quiet "please check" note in the notebook, not a question.

---

## 8. Error handling and state safety
- **Consent declined:** the app explains it needs permission to use Claude and shows how to allow it.
- **Rate limited:** "Claude needs a moment — try again in a minute." No automatic retries.
- **Only complete results change anything.** A streaming draft can be shown as it arrives, but the Card, Preferences, and saved outputs update only from a finished, valid result. An interrupted draft stays on screen marked "interrupted," with **Try again**.
- **Stale results can't overwrite newer ones.** Each call is stamped with the Card revision it started from. If the Card changed while it ran, its new facts are merged in without overwriting anything newer, and any output it produced is saved marked "Refresh."
- **Stop means stop:** a stopped call never updates anything afterward.
- **A failed refresh keeps the previous version.**
- **Bad structured result:** one automatic re-ask with a tighter format instruction, then a manual Try again.
- **Search connector missing:** show the connect panel (2.4). **Failing:** retry once with the backup connector if present, else say so in one line and offer paste.
- **Every long step** has Stop.

---

## 9. Saving, export, import
- ◻ **Autosave** to the viewer's browser after every change, one record per creamery. Survives closing the tab and the Wednesday break.
- **Export** (two files):
  - `<creamery>-story-pack.md` — everything in readable form: the Card with sources, chosen stories, all outputs. Made to drop into a Claude Project so the maker can keep going in ordinary Claude chats.
  - `<creamery>-story-pack.json` — reimportable into the app on another computer.
- **Import** the .json on the start screen.
- Browser storage belongs to one browser; the export is how work moves between computers or people.

---

## 10. Sharing and access
- Adam publishes the artifact from this project. ✅ Demo runs on his account.
- Afterward Adam shares the link (◻ "anyone with the link who's signed in"). Each maker runs it on their own plan; nothing they enter is visible to Adam or other makers.
- Setup for makers on their own: see 10a.

---

## 10a. Getting set up ✅
Principle (Adam): the goal is that it works. Where a maker has to do something for it to work, the app tells them exactly how, in plain language, and checks that it worked.

**Setup check on the start screen.** A short checklist that tests each item live and turns green when it passes:
1. **Signed in to Claude** — if not, how to create a free account or sign in, then reopen the link. If their plan can't run something the app needs, the checklist says so plainly and what's required.
2. **Allow the app to use Claude** — what the permission prompt will look like and why to click Allow; a "Test it" button that makes a tiny call.
3. **Live lookup: which path applies.** Connectors inside apps need a paid plan (Pro, Max, Team, or Enterprise). The checklist detects what it can and shows the right path:
   - **Pro or Max:** connect Parallel Search (free, no sign-in) in Settings → Connectors, then press "Check again."
   - **Team or Enterprise:** a team Owner first adds Parallel Search for the team (Settings → Connectors → Browse connectors → Add to your team); then the member connects it.
   - **Free plan:** lookup uses the **bridge** — the app shows a ready-made research request with a Copy button; the maker pastes it into an ordinary Claude chat (which searches the web on its own) and pastes the answer back. The cheapest way to get live lookup instead is Pro ($20 a month, cancel anytime).
4. **Allow the connector for this app** — what that prompt looks like; "Test it" runs one search.
5. **Talking instead of typing (optional)** — how to turn on the computer's built-in dictation (Mac and Windows) to answer out loud.

Each failed check shows the fix right there, never a dead end. Everything passes → **Look up your creamery.**

**Also produced:**
- A one-page **"Before you start"** guide (same steps, with screenshots) VCC can email to attendees with the recording.
- A **"Something's not working"** help panel reachable from every screen, covering the common failures (usage limits, connector turned off, lost work → import your export file).

## 11. Visual design ✅
- **Neutral by default:** warm, editorial, plain — cream background, deep green and rind-brown accents, a serif for stories and headings, a clean sans for controls.
- ✅ **Skin switcher:** one menu that restyles the whole app as **VCC**, **Jasper Hill**, **von Trapp**, or **Grafton** — each skin borrows that organization's colors and typographic feel and labels the app "Your Cheese Story · for [name]." No logos.
- Source notes are plain words in a quieter style, never colored badges.
- Works on a laptop screen-shared at 1280px; usable on a phone afterward.

---

## 12. Wednesday run of show (app's part) ◻
| Time | Segment | App |
|---|---|---|
| 2:00–2:20 | Where are you with AI? How do you feel about it? | — |
| 2:20–2:40 | Why story — Adam's talk | — |
| 2:40–3:30 | von Trapp, live | Lookup → in their words → hypothesis → evaluation → interview (Live Listen) |
| 3:30–4:00 | Break | autosaved |
| 4:00–4:40 | von Trapp, continued | Warm run → outputs → corrections and refresh |
| 4:40–5:00 | Q&A; how to keep using it (setup checklist, export) | Start screen, skin switch |

---

## 13. Build plan and acceptance tests

**Sunday Oct 11**
- Capability checks, each a tiny test page: (a) AI call from the artifact on Adam's plan; (b) tool use calling Parallel Search and page read; (c) JSON results, including a two-pass lookup where each pass returns complete JSON; (d) can the page capture tab audio (decides whether the Listener lives inside the app or beside it); (e) browser autosave; (f) download; (g) **maker-path smoke test** from a separate free Claude account: open the link, connect Parallel Search, allow the app, run one AI call and one search.
- Write the core brief, `lenses.md`, and the six new output guides.
- App skeleton: layout, step navigation, Creamery Card panel, demo drawer, autosave.
- ✔ Done when: a test call returns streamed text and a search result appears in the drawer.

**Monday Oct 12**
- Steps 1–5 complete, including fallback lookup, the extraction loop, and the context contract (5.1).
- ✔ Done when: "von Trapp Farmstead" produces a card with ≥15 sourced facts and ≥4 cheeses in ≤3 min, every website fact carrying its excerpt; a spot check of 10 facts against their sources finds none wrong; the hypothesis visibly builds on the maker's own words; a 6-answer typed interview adds facts and at least one preference to the card.

**Tuesday Oct 13**
- Steps 6–8; all outputs with the evidence rules (5.2); corrections, preferences, and refresh; export/import; skins; the Listener.
- Full dry run on von Trapp from public information.
- A real Zoom test of Live Listen.
- ✔ Done when: the von Trapp dry run completes end to end under 70 minutes of app time; every factual sentence in the public-facing outputs traces to an allowed fact, with missing information shown as gaps; a fact correction and a direction ("not about the family") each visibly change refreshed outputs; the Listener carries a Zoom answer into the interview with speakers labeled correctly.

**Wednesday Oct 14, morning**
- Fixes from dry runs.
- **Maker path from a separate free Claude account**, end to end: setup checklist (including connecting Parallel Search), lookup, in your words, interview, one output, reload the page and find the work saved, export and import.
- Write the "Before you start" guide.
- Adam rehearses once; final publish; Zoom joined in Chrome; open the app in the demo browser profile and allow consent in advance.

---

## 13a. Probe results (Oct 11, Adam's main account) ✅
- AI calls on Adam's plan: work; quick tier answered in ~4 s; tool use available.
- Two-pass JSON: works; each pass ~3 s.
- Parallel Search from inside the app: works, both directly and as Claude's tool; found 6 von Trapp cheeses in ~5 s.
- Claude's own knowledge alone found only 1 cheese, so live lookup is essential, not a nicety.
- Browser save and download: work.
- Tab audio / microphone: not available in apps on this platform (Listener runs beside the app).
- Second account (Team plan): AI calls, JSON, save, download work. Parallel Search blocked until the team's Owner adds it for the team.

## 14. Decisions (Oct 11) ✅
1. No output priority — all outputs are built.
2. Number and mix of personas chosen in the moment, not fixed in advance.
3. Monger answer site is a demo, per creamery and per cheese.
4. Live Listen via the companion Listener.
5. Neutral branding, with a skin switcher: VCC, Jasper Hill, von Trapp, Grafton.
6. Name: *Your Cheese Story.*
7. von Trapp is the working example.

## 15. Out of scope (✅)
- Accounts, payments, shared databases, a Zoom marketplace app.
