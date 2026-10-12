# Your Cheese Story — Spec, version 2

*Oct 11, 2026. For the Vermont Cheese Council workshop, Wed Oct 14. Replaces `claude/cheese-story-app-spec.md` (v1), which was built around a step-by-step flow. Platform pieces from v1 that still hold are copied into section 8 on purpose. Nothing else is inherited.*

*Companions: the stage model in `claude/kit/flow.md`, the story framework in `claude/kit/story-arcs.md`, and the wireframes on the canvas "Your Cheese Story wireframes."*

**How to read this.** ✅ = Adam decided. ◻ = proposed default, stands unless Adam changes it.

---

## 1. What it is, and what it believes

*Your Cheese Story* is a web app that helps an artisanal cheesemaker find and tell the story of their creamery and cheeses through a conversation with AI.

- ✅ **AI doesn't write the story or invent it.** The story already lives in the farm, the animals, the milk, the choices and the history. The app researches, listens, proposes and drafts. The maker reacts, corrects and pushes back, and every exchange makes the story more theirs.
- ✅ **Big stages, not steps.** Five stages, each with its own job. Inside each, the app does real work of its own and offers many ways to interact.
- ✅ **A default always, and it can always be overruled.** The maker never has to make a decision, because there's always a good next move on the table. They can ignore it and do anything else.
- ✅ **The app says when it's ready to move on** ("I think I have enough to start shaping a story"). That's a suggestion, not a gate.
- ✅ **Doors go both ways.** At any stage, the AI or the maker can say "this makes me think we should add or explore X in an earlier stage." Nothing is locked, and nothing is ever finished. It's a loop.
- ✅ **Story first, fact-checking last.** Until something is about to go out into the world, the work is about arcs, elements, audience and shape. Small facts (45 vs. 48 cows, store hours, dates) get settled in the fact check, just before anything is used publicly.
- ✅ **Never invent.** Not at any stage. Things the AI knows in general, or infers, are offered as ideas and never stated as facts about this maker.
- ✅ **Hold their hands without grabbing them.** These are people who have never used a Claude project. Everything is plain words, one clear thing at a time, with a big obvious button for the default.

## 2. Who uses it, and what Wednesday needs

**Users**
- ✅ Adam, driving a live demo on Zoom, screen-shared.
- ✅ Cheesemakers afterward, on their own Claude accounts.
- ✅ Working example: von Trapp Farmstead.

**Wednesday works if:**
1. Adam types "von Trapp Farmstead" and the room watches the app find them online and say what it found.
2. The von Trapp person talks, the material lands, and the suggested prompts visibly change because of what they said.
3. The app says it has enough, and Story shape offers three ideas with its pick marked. The maker reacts ("that's right" or "no, actually…").
4. The chosen idea becomes an outline. Some beats say "needs you," the maker fills or changes them, and approves it.
5. At least one door opens each way: the AI suggests going back for something, and the maker adds something that lands in another stage.
6. The approved outline is tested on pretend buyers, and the room sees what grabbed each one and what fell flat.
7. One finished piece, such as a monger card, comes out recognizably theirs, with gaps shown as questions rather than inventions.
8. Afterward, a maker opens the link on their own account and can do all of this themselves.

---

## 3. The frame (the same on every screen)

See the wireframes. From top to bottom:

- **Header.** "Your Cheese Story," the creamery's name, "All saved," Export and Help. Nothing else.
- **Stage rail.** Five stages across the top: Gathering · Story shape · Audience · The essential story · Telling it.
  - Each shows a one-line status ("14 found online · 3 from you," "First idea on the table," "1 thing to go back for").
  - The current stage is lit, and every stage is always clickable.
  - Underneath: "Move between stages anytime. Nothing is locked, and nothing is ever finished."
- **The main column.** A conversation: the app speaks, the maker answers. One thing at a time.
- **The answer box.** Type, or "Talk instead" (dictation, section 8.4). Plus "Add files or photos" and "Add a link." Anything they add is material.
- **Suggested next.** One orange bar with the default move in plain words and one big button. It's always there and always optional.
- **The side column.** What it shows depends on the stage:
  - **Gathering:** "What we have so far," a count plus rough topic meters (land, animals, family and history, how it's made, the cheeses, stories, things you invented). The meters are labeled in words, not color alone.
  - **Story shape onward:** "Your story shapes," the eight arcs filling in as material arrives. Also "Doesn't fit any shape (yet)" for leftovers, since those are often the most distinctive things.
  - **Always:** "Come back to" (below) and the button "This makes me think of something…"
- **Come back to.** Everything set aside by the maker or the app, from any stage, each with where it belongs and "Go there now." The app brings each item back up when it fits.

### 3.1 Doors

- **The AI opens a door.** After every maker turn, the app checks whether anything new bears on another stage (see the door check job, section 6). If it does, an inline card says, for example: "This makes me think we should go back to Gathering. You mentioned aging the cheese, but I don't know where or how…" It offers three choices:
  - **Go back and talk about it:** jump there with the question ready.
  - **Later:** it goes into Come back to.
  - **Not important:** dismissed and never raised again.
  - At most one AI door per turn. ◻ Never more than one open, unanswered AI door at a time.
- **The maker opens a door.** "This makes me think of something…" opens a small box: "What's on your mind?" and "Where should it go?" The default is "You decide." The other choices are the five stages. Then "Add it, stay here" or "Add it and go there." If they chose "You decide," the app files it and says where in one line.
- **Gaps are doors too.** Every missing piece, in an idea, an outline beat, a buyer test or a finished piece, carries "Answer it in Gathering."

---

## 4. The stages

Each stage below covers: its job, what the app does on its own, the default rhythm, other ways in, when it says it's ready, and its doors.

### Stage 1 — Gathering

**Job:** get as much as possible about the maker, the farm and the cheese into the pile. Deliberately promiscuous.

**What the app does itself** (the lookup job, then the bigger-picture job):
- Searches for and reads the creamery's website, articles, write-ups, podcast interviews and directory listings. Anything where they talk about themselves.
- Pulls the bigger picture: the history of their cheese styles, their town's region (soil, season, breeds), and where they sit in Vermont's cheese story.
- Shows what it found as a short list of sources with counts and a link to "See all, and what each one says." Then: "That gives me the basics. What I can't find online is what only you know. Where would you like to start?"
- ◻ An opt-out: "Skip the online search." Some makers won't want it. Bigger-picture research still runs from the kit.

**The default rhythm:**
- The app offers 5–7 **suggested prompts** as tappable chips.
- The maker answers one, or talks about anything at all.
- The app reviews what came in and acknowledges it specifically: "Three things jumped out…"
- Then it offers new prompts that follow from what they said.
- Repeat.

**Where the prompts come from**, in this order:
1. Follow-ups on something specific the maker just said.
2. Bold elements missing from the arcs the material is starting to point toward. This is how the arcs quietly steer Gathering.
3. The questions in the maker's cheese-style note.
4. The general prompt pool (section 5.4).

The interviewing rules in the core brief always apply: one concrete thing at a time, no numbers or dates, never "what makes your cheese special?"

**Ways in:** type, talk, paste, drop files or photos, add links. Long and messy is welcome. Every input is attributed ("you told us," "from your website," "from [publication]," "a guess, please check").

**Ready:** the readiness check runs after each turn. When it says yes, the "ready" card appears: "I think I have enough to start shaping a story. You can keep adding anytime. Nothing you've told me gets lost." Two buttons: **Go to Stage 2** and **Keep gathering**.
- ◻ Ready means: material from the maker (not just the web), and at least two arcs with half or more of their bold elements.

**Doors out:** a mention that opens a story question ("you said the cows go up the hill in June…") can surface as a door into Story shape later, but Gathering mostly receives doors.

**Lineup branch:** if the maker makes several cheeses, the app offers once, early: "Do you want to work on one cheese, or the whole creamery?" It defaults to the creamery, with each cheese as a thread. Source: `workflow/multi-cheese-makers.md`.

### Stage 2 — Story shape

Two moves: **three ideas**, then **the outline**.

**2a. Three ideas** (the ideas job):
- ✅ At least three story ideas, side by side. Each one:
  - is built on one of the eight arcs, or two braided together;
  - has a title and a short telling, written in serif type to read as story;
  - shows how many of its pieces are there and what's missing, in one line.
- ✅ The app marks **its pick**, with one line on why: "it's the one only you can tell."
- ✅ At least one idea builds directly on what the maker said they want people to understand. If the material points elsewhere, that idea sits alongside theirs, never instead of it.
- Ideas are written from the material. Missing pieces are shown in brackets, never invented.
- **Look closer** on any idea opens its detail:
  - "What this kind of story needs": each element marked have it / thin / missing, with where it came from.
  - "What would make it stronger."
  - "What's missing," each item with "Answer it in Gathering."
  - Reactions: **Yes, build this one out** · **Close, but…** · **Not us**.
- Below the ideas: **Show me three more** and **Combine parts of these**.
- "Not us" ideas are remembered and never come back. Starred or "close" ideas shape everything later.

**2b. The outline** (the outline job):
- ✅ The chosen idea becomes a short outline of beats, in order. Usually 5–7 beats, drawn from that arc's elements (section 5.2).
- Each beat carries its status:
  - **from you**
  - **from research**
  - **half from you**
  - **needs you**, shown dashed with "Tell me about it in Gathering"
  - **thin**
- The maker can change, move, drop or add beats, or ask to "Read it as a paragraph."
- Side column: "Pieces from the other ideas," to pull in a beat from a non-chosen idea.
- ✅ **Approve.** "Does this outline feel like your story?" with **Approve it, then try it on buyers** and **Fill the open beats first**. Approving locks nothing. It marks the outline as the version Audience tests.

**Ready:** the outline is approved.

**Doors out:** every missing element and "needs you" beat goes to Gathering. Thin arcs show "ask me about that."

### Stage 3 — Audience

✅ **Job:** see how the approved outline lands. Building comes first, so this stage tests what the maker has already approved.

- **Header chip:** "Testing: [outline title] · see the outline."
- **First, where does it sell?** Chips: farm store, Vermont shops and co-ops, cheese shops in other cities, online, restaurants, farmers' markets, somewhere else. One line explains: "This decides which buyers we try the story on."
- **Then, three buyers hear the story** (the buyer panel and buyer test jobs). ◻ The default three:
  - **The adventurous one:** loves trying something new and notices awards.
  - **The careful one:** wants to know what it tastes like before paying more.
  - **The cheesemonger:** "What do I say while they taste?"
  - Where the cheese sells adds or swaps buyers, from `audiences/*`: a co-op buyer, a chef, a farmers' market regular, a Vermont visitor, a city shopper.
  - **+ Add a buyer** lets the maker describe one.
- **For each buyer:** what grabbed them, what fell flat, and the one thing they'd repeat to a friend.
- Buyers are labeled as pretend, grounded in research, and never quoted as real people.
- **Doors out:**
  - "Fell flat" points back to a beat in the outline.
  - "What they'd need that the story doesn't have" goes to Gathering.
  - A buyer's reaction can open "Try the other idea on this buyer," which goes to Story shape.

**Ready:** the tests have run, plus one round of changes if the maker wants it.

### Stage 4 — The essential story

**Job:** boil the story down until it's small enough to carry.
- **One sentence.** It states the story's organizing idea, not a selling point. For example: "ancient history and modern inventiveness that tastes like Vermont."
- **What it rests on:** chips linking to the beats and buyer findings it comes from.
- **Other ways to say it:** three alternatives, each leaning a different way (the land, the family, the taste).
- **Reactions:** That's it · Close, but… · Let me write it myself.
- **Tests, run silently before showing** (section 5.3):
  - **Center:** can you say what it's about?
  - **Substitution:** could another creamery's name go in it?
  - **Repeatability:** could a monger say it from memory?

**Ready:** chosen. Default next: "Start telling it. The monger card is a good first piece."

### Stage 5 — Telling it

**Job:** make things with it. Everything is built from the essential story and the approved outline.

- **Things to make** (gallery; any can be made at any time, ✅ no priority among them):
  - monger card (◻ suggested first)
  - for the table
  - shelf talker
  - the longer website story
  - photo essay
  - Instagram and other social posts
  - press release
  - a short video
  - packaging and label
  - ◻ also, from the old kit: buyer email, "why it costs what it does," product sheet (trade), monger answer site (demo)
- **Each piece:**
  - shows where it came from;
  - shows gaps as `[ask: …]` with **Answer it** (a door to Gathering);
  - has a "That's not right / push it further" box.
- **Who else might tell it:** food writers, bloggers, cheesemongers, people into Alpine history, Vermont travel writers, someone else. The app researches real people (PR guide rules: every cited piece opened and read) and drafts a version for each.
- ✅ **Check the facts.** Each piece has a **Check the facts** action, and anything exported or copied runs it automatically first. It:
  - traces every claim to its source;
  - flags anything from general knowledge, inference, or disagreeing sources;
  - gives the maker a short "confirm before you print" list.

  This is the only place small facts, numbers, dates, raw vs. pasteurized and so on, are asked about.

---

## 5. The intelligence

This is the map of everything the project knows, and where it goes. Documents are either **carried** (sent to the AI in the calls that need them), **distilled** (rewritten into a shorter file before the build, then carried), **mined** (specific lines moved into another file), **source** (used only to write other files) or **retired**.

Paths: project docs are in the Cheese Narrative project; kit paths are in the original Vermont Cheese Story Kit (github `adamjdavidson/vcc`).

### 5.1 Knowledge map

**Sent with every call**

| Document | Use |
|---|---|
| `claude/kit/core-brief.md` | **Distill → Core brief v2.** Rewrite for stages. Replace "warm run" and "final check the facts step" with the stage language. Fold in the gems (5.3). |
| `claude/kit/flow.md` | **Carried** in condensed form inside Core brief v2: the stages, defaults, doors, loop. |
| kit `story-principles/story-first-fact-check-last.md`, `what-story-is.md`, `avoid-checklist-stories.md`, `story-vs-brand-positioning-copy.md`, `passion-economy-for-cheesemakers.md` | **Mined** into Core brief v2. The core already carries most of it. Add: "a story is what happens when the right facts start to explain one another"; every detail answers a why-question or is cut; find the story, then positioning, then copy; the commodity trap. |
| kit `story-principles/truth-and-source-rules.md`, `research/using-sources.md` | **Mined** into Core brief v2: source buckets, offering a connection without asserting it ("this could become part of the story if it's true of your cheese"), never assume a style's traditional method. Drop the worksheet assumption. |

**Gathering**

| Document | Use |
|---|---|
| kit `research/location-research.md`, `vermont-context/vermont-geography-seasonality.md` | **Carried** in lookup: what to research about a place, banned place words, place as active force. |
| kit `deep-research/vermont/place-and-season.md` | **Carried**, but only the maker's region section (town → region lookup), in lookup and bigger picture. Feeds Taste of Place. |
| kit `cheese-styles/*` (10 style notes + README's five questions), `research/cheese-style-research.md` | **Carried** by the maker's styles. Their questions feed suggested prompts. "Compare, do not force": treat origin stories with care. |
| kit `vermont-context/README.md`, `vermont-artisan-cheese-context.md`, `vermont-dairy-history.md` | **Mined** into Core brief v2 as guardrails: "Vermont is not a story by itself"; don't assume farmstead, own milk or family farm. |
| kit `index.html` question bank, `output-templates/follow-up-questions.md`, `workflow/interview-from-scratch.md`, `ai-master-instructions.md`, `_design-history/worksheet-design-brief.md` | **Distill → Prompt pool** (5.4). The fixed sequences and worksheet structure are dropped; the questions survive. |
| kit `workflow/multi-cheese-makers.md` | **Carried** when a maker has several cheeses (the lineup branch). |
| kit `sources-and-further-reading.md` | **Carried** in bigger picture as research seeds. |

**Story shape**

| Document | Use |
|---|---|
| `claude/kit/story-arcs.md` | **Carried, the center of the app.** Ideas, outline, readiness, missing-element prompts, side-column meters. |
| `claude/kit/lenses.md` | **Retired**, replaced by story-arcs. Two ideas move into the arcs guide: the strong/some/thin scale, and the "unlock question" for a thin arc. |
| kit `examples/good-story-patterns.md` | **Mined** into the arcs guide: each pattern's key question attaches to its arc (e.g., "what problem did the original style solve, and what does this version answer now?" → Chosen Ancestors). |
| kit `START_HERE_FOR_LLM.md`, `workflow/first-output-process.md`, `output-templates/story-options.md` | **Mined** into the ideas job: what I heard, three through-lines, what's missing as big pieces not facts. Their "draft nothing until answered" gates are dropped. |
| `claude/kit/history/alpine-cheese-history.md`, `cheddar-history.md`, `goat-cheese-history.md` | **Carried** by the maker's styles, in bigger picture, ideas and outline. Their "Careful" sections are guardrails and always travel with them. |
| `claude/kit/history/vermont-cheese-1985-2026.md` | **Carried** in ideas and outline. It feeds Working Landscape, Nobody Does It Alone, Second Life and The Upstart. |
| kit `deep-research/cheese-styles/alpine-storytelling-toolkit.md` | **Distill** its unique parts (sensory word lists, story tensions) into an Alpine add-on. The history overlaps the project's Alpine file. |
| kit `deep-research/cheese-styles/alpine-goat-cheese-vermont.md`, `goat-history-toolkit.md` | **Distill** the unique parts (goat-milk science, legend lines labeled as legends, rind trends) into a goat add-on. Producer profiles go to the peer layer (5.5). |
| kit `deep-research/vermont/dairy-and-cheese-history-1600-1980.md` | **Distill** the pre-1985 detail the project files lack (sheep built the stone walls, farmhouse cheese as women's work, the milk trains, Cabot 1919) into a short Vermont-before-1985 add-on. |
| kit `deep-research/vermont/artisan-renaissance.md`, `deep-research/cheese-styles/alpine-deep-history.md`, `claude/kit/alpine-deep-history.md` | **Retired**, superseded by the project history files. Producer data goes to the peer layer. |
| `claude/kit/research/cheese-story-elements.md` (same as root `cheese-story-elements.md`) | **Carried** in ideas and outline: why a face, care, visible labor, the underdog, lineage and a living thing work. |
| Kindstedt, *Cheese and Culture* (book text, ~89,000 words) | **Source only.** Too big to send. Used to write the missing style histories (5.6). |

**Audience**

| Document | Use |
|---|---|
| `claude/kit/research/cheese-buyer-research.md` | **Carried** in buyer panel and buyer test. Quality seekers vs. price-sensitive; maker over place; "Made in Vermont" weak in cities, strong at home; intimidation; tasting first. |
| `claude/research/selling-artisanal-food-through-story.md` (a copy is also at the project root) | **Distill → Selling-through-story digest** (~1,000 words), carried in Audience and Telling it. Keep: specific beats generic; demonstrated beats claimed; the audience-involvement table; the 44% novelty seeker / 47% uncertainty-averse split; sensory shelf talker vs. award; one causal link the taster can confirm; "ancient method, new place"; the intermediary is the real audience; self vs. gift purchase. |
| kit `audiences/*` (8 files) | **Carried** by channel: each becomes a pretend buyer's brief. Use the three mindsets from its README (mongers as translators, consumers as premium-curious, trade as sell-through thinkers). |
| kit `research/audience-research.md`, `review-checklists/audience-fit-checklist.md`, `examples/fictional-sample-stories.md` | **Carried** in buyer test: adapt the emphasis, not the story; one draft, one audience. |
| `claude/kit/personas.md` | **Distill → Buyer panel guide.** Its rules hold: grounded in something real, specific, no stereotypes, invents nothing about the creamery. Its role changes from an output to the test panel. |
| kit `workflow/intake-page-interpretation.md` | **Mined:** its channel-to-audience map goes into the buyer panel guide. The checkbox gating is dropped. |

**The essential story**

| Document | Use |
|---|---|
| kit `review-checklists/anti-slop-checklist.md`, `final-story-checklist.md` | **Carried:** the center, substitution and repeatability tests, and the eight gates (truthful, specific, unified, memorable, useful, plainspoken, worth repeating, connected to the premium). Run silently. |

**Telling it**

| Document | Use |
|---|---|
| `claude/kit/monger-card.md`, `social-posts.md`, `video-concept.md`, `pr-research-and-pitches.md`, `monger-answer-site.md` | **Carried** as each output's guide. |
| kit `output-templates/buyer-email.md`, `explaining-premium-price.md`, `visit-and-access.md` | **Carried** as guides. "Explaining premium price" also feeds the monger card's price line and the careful-buyer test. |
| kit `output-templates/15-second-pitch.md`, `tasting-table-script.md`, `audiences/farmers-market-customers.md` (five-line structure), `audiences/chefs-restaurants.md` (server line) | **Distill → new "For the table" guide.** |
| kit `output-templates/label-language.md` | **Distill → new guides for shelf talker and packaging/label.** It's only one line deep today. |
| kit `output-templates/website-copy.md`, `multi-cheese-makers.md` producer story | **Distill → new "Longer website story" guide.** |
| kit `output-templates/product-sheet.md` | **Carried** as the trade variant of the monger card. |
| kit `examples/before-after-examples.md`, `examples/bad-ai-slop.md` | **Carried** in every make and self-check: what good and bad look like. |
| kit `review-checklists/truth-checklist.md` + `final-story-checklist.md` confirm list | **Distill → Fact-check guide.** Runs only in Check the facts. Hand-back under three headings: what you told me / what research says / what to confirm. |
| kit `audiences/press-food-writers.md` | **Carried** with the PR guide, for "who else might tell it." |

**Retired** (repo plumbing or superseded): kit `MASTER-PROMPT.md`, `README.md` (keep its one line, above), `repo-guide.md`, `REPO-MAP.md`, `FILE_MANIFEST.md`, `_design-history/*` (lines mined: "propose several centers of gravity, then ask which feels true"; "the story must travel through people and materials when the maker isn't there"; "don't make AI the hero"), `examples/README.md`, `output-templates/README.md` (its rule "every piece tells the same story" goes into Core brief v2), `deep-research/README.md` (its source-discipline rules go into Core brief v2; its file index is stale), `review-checklists/README.md` (checks run silently, never reported to the maker as pass/fail), `workflow/how-to-use-worksheet.md` (keep its list of useful raw material), `cheese_worksheets.pdf`, the `index.html` UI, `claude/cheese-story-app-spec.md` (v1).

### 5.2 How the arcs drive everything

- **Gathering:** the arcs' bold elements decide what's worth asking about next.
- **Readiness:** decided by arc coverage.
- **Story shape:** each idea is an arc, or two braided. The outline's beats are that arc's bold elements in story order, plus any shared elements that fit (A face, What We Won't Do, This Wheel This Season, The Hockey Puck, The Hands, The Living Thing, The Name, The Upstart, For the Table).
- **Strength per arc:**
  - **strong:** several connecting pieces, at least one in the maker's words;
  - **some:** a couple of pieces, or good pieces needing confirmation;
  - **thin:** one piece or only background.
  - A thin arc carries one **unlock question**.
- **The Hockey Puck is never invented.** Neither is anything else the arcs list as "from the maker."

### 5.3 Rules every call carries (the gems)

Mined from the kit and the research, to live in Core brief v2:
1. Maker answers are raw evidence. The AI finds the story; it never asks the maker to name it ("what makes your cheese special?").
2. A story is what happens when the right facts start to explain one another. Every detail answers a why: why it exists, why it tastes this way, why this choice, why this place, why this audience cares. Otherwise it's cut or saved.
3. Specific and demonstrated beats claimed: a named place, a constraint that costs something, one causal link from a choice to a taste the buyer can confirm. Not "passion," "tradition," "authentic."
4. Place is active, not scenery. What does this place do to the cheese?
5. No silent fusion. A style's history isn't proof of this maker's practice, and disputed origins stay disputed. Legends are told as legends.
6. Offer connections, don't assert them: "this could become part of the story if it's true of your cheese."
7. Keep the maker's own phrases. A plain true sentence beats a slick invented one.
8. The story has to travel through people when the maker isn't there. Write for the monger's mouth and the host's table.
9. The tests, run silently and never reported as a checklist:
   - **substitution:** another creamery's name doesn't fit;
   - **center:** you can say in one sentence what it's about;
   - **repeatability:** a monger can say it from memory;
   - **checklist:** not one line per topic with nothing connecting them.
10. Don't make the AI the hero.

### 5.4 The prompt pool (Gathering)

◻ Distilled from the kit's worksheet bank and interview files. Suggested prompts are drawn from here when nothing more specific is ready, rewritten to fit what's already known.

- **The cheese:** In plain words, what is it? · How do you make it differently from other people? · What physically happens to make or age it? · What do you say when you hand someone a sample? · What do people say when they taste it, even the unflattering things? · What cheese do people wrongly compare it to? · Which part of the process takes the most judgment? · What does winter milk change?
- **The maker:** What were you doing before cheese? · How did cheese pull you in? · What was hard about getting here? · Who taught you, or challenged you? · What are you proudest of? · Something that went wrong, and what you did next.
- **The place:** What's your land like? · One thing about this place people wouldn't know unless you told them. · What would a visitor notice first: a sight, a smell, a sound? · Who else is part of this place?
- **Openers:** How did the farm begin? · Tell me about the animals. · A story you always tell visitors. · Something you figured out or invented. · What do you find yourself explaining again and again?

### 5.5 The peer layer

The kit has many claims about other real Vermont creameries: herd sizes, awards, founding years, which sometimes disagree between files. They're useful as context ("other makers in this tradition"), but never as fact in anything public.
- Keep them in a separate peer file, marked unverified.
- Never state them as fact about anyone.
- Never put them in public-facing copy without the fact check.
- Note that two operations listed as Vermont in the kit (Crown Finish Caves, Nettle Meadow) are in New York.

### 5.6 Knowledge to write before or during the build

1. **Core brief v2** (5.1, 5.3): about 3,000 words.
2. **Arcs guide additions:** a key question per arc, the strength scale, unlock questions, the rules for three ideas plus a pick, and outline beats per arc.
3. **Prompt pool** (5.4).
4. **Buyer panel guide:** default three, channel extras, three mindsets, cues each buyer responds to, test format (grabbed / fell flat / would repeat / needs).
5. **Selling-through-story digest.**
6. **Essential-story guide:** organizing idea, not selling point; the silent tests.
7. **New output guides:** for the table, shelf talker, packaging and label, longer website story, photo essay, press release. ✅ Written Oct 11: `claude/kit/for-the-table.md`, `shelf-talker.md`, `packaging-and-label.md`, `website-story.md`, `photo-essay.md`, `press-release.md`.
8. **Fact-check guide.**
9. **Style backfill from Kindstedt**, short history-and-"what it solved" notes for the styles that have only a style note today: bloomy rind, blue, washed rind, tomme, Gouda-style, pasta filata, and sheep's milk (which had no file at all). ✅ Written Oct 11 in `claude/kit/history/`.
10. **Add-ons:** Alpine (sensory words, tensions), goat (science, legends), Vermont before 1985.
11. **Peer file** (5.5).

◻ For Wednesday, items 1–4 and 8 matter most. von Trapp is Alpine-leaning, and its history is already deep.

---

## 6. What the app remembers, and the AI jobs

### 6.1 State, per creamery

- **Material:** every piece of information, with its source:
  - who it came from: maker / website / web / research kit / Claude's knowledge / inferred;
  - the link and supporting excerpt for web sources;
  - status: active / changed / removed.
  - Removed material is gone and never used again.
- **Maker's words:** what they wish people understood, who they want to reach, and their vivid phrases, kept verbatim.
- **Direction:** editorial preferences ("not about the family," "warmer"). Followed everywhere.
- **Arc coverage:** for each arc, which elements have material, and how strong.
- **Ideas:** each with arc(s), title, telling, has/missing, pick flag, and the maker's reaction (yes / close / not us).
- **Outline:** beats (text, element, status, source pieces), order, and approved flag plus the time approved.
- **Channels:** where it sells.
- **Buyer tests:** buyer, outline version, grabbed, fell flat, would repeat, needs.
- **Essential story:** chosen sentence, alternatives, what it rests on.
- **Pieces made:** kind, version history, gaps, last fact check.
- **Come back to:** text, target stage, from (maker / app), status.
- **Stage status lines** for the rail.

### 6.2 Every call receives

- Core brief v2.
- The active material, with sources.
- The maker's words.
- All direction that applies.
- The ideas they liked and rejected.
- The approved outline, once there is one.
- The last 8 conversation turns, verbatim; earlier turns are represented by what was extracted from them.
- The kit files for that job (table below), the task, and the exact reply format.

### 6.3 The jobs

| Job | Stage | Runs when | Kit loaded | Returns |
|---|---|---|---|---|
| Lookup | 1 | Start | location research, place-and-season (region), using sources | Material with sources |
| Bigger picture | 1 | After lookup | style notes + style histories, Vermont history, research seeds | Background material (marked research) |
| Extract | any | After each maker turn | — | New material, direction, arc elements touched |
| Next prompts | 1 | After extract | arcs, style questions, prompt pool | 5–7 prompts, most specific first |
| Ready check | 1 | After extract | arcs | yes/no + one line |
| Door check | any | After extract or a reaction | flow, arcs | 0–1 door: target stage, line, question |
| Ideas | 2 | On entering Story shape; "three more"; "combine" | arcs guide, story elements, style histories, Vermont history | 3 ideas + pick + why |
| Look closer | 2 | On demand | arcs guide | Elements have/thin/missing, stronger, missing |
| Outline | 2 | "Build this one out" | arcs guide, histories | Beats with status |
| Beat edit | 2 | Change / combine / add | arcs guide | One beat |
| Buyer panel | 3 | Channels chosen | buyer panel guide, audiences by channel | 3+ buyers |
| Buyer test | 3 | "Test it" | buyer research, selling digest, audience files | Per buyer: grabbed, flat, would repeat, needs |
| Essential | 4 | On entering | essential guide, checklists | Sentence + rests on + 3 alternatives |
| Make | 5 | "Make it" | that output's guide, examples, selling digest | The piece, with gaps |
| Self-check | 5 | Silently, after every make | anti-slop, audience fit | Revised piece |
| Check the facts | 5 | On demand; before every export or copy | fact-check guide | Claims traced + confirm list |
| Who else | 5 | On demand | PR guide, press audience | Verified people + a version for each |

◻ The size target is ≤120 KB per call; the platform cap is 256 KB. Each job loads only its files. History files are trimmed before the core brief or the arcs are.

---

## 7. Look and feel

From the wireframes:
- **Ground and text:** a warm paper background, near-black text, one burnt-orange accent reserved for "you are here" and the default move.
- **Type:** IBM Plex Sans for the interface, Plex Serif for anything that is story (ideas, outline beats, the essential sentence), Plex Mono for small labels.
- **Layout:**
  - one main column plus a side column that stacks on a phone;
  - large text and touch targets for screen sharing;
  - status in words, never color alone.
- **How the app shows its thinking:** in plain sentences as it works ("Reading your About page…"). No logs, prompts, file names or raw URLs anywhere.

---

## 8. Platform (carried over from v1, verified Oct 11)

These held up in v1's probes and are copied in deliberately.

### 8.1 Where it runs
- ✅ A published Claude artifact. Its AI calls run on the viewer's own Claude plan: Adam's on Wednesday, each maker's afterward. No API keys, servers or hosting.
- One self-contained page with the kit built in as named text blocks, so nothing is fetched at run time.
- Capabilities:
  - `sample` for every AI call;
  - `mcp` for web search and page reading through the viewer's search connector;
  - `downloads` for export.
- Each call is memoryless, so everything is sent fresh (6.2). JSON mode for anything that feeds state; prose streams.
- Model tiers:
  - quick: extract, ready check, door check;
  - default: prompts, beats, buyer tests, pieces;
  - complex: lookup, ideas, outline, essential.

### 8.2 Web access
- ✅ Primary: the **Parallel Search** connector (free, one click). Backup for Adam: Exa.
- Connectors inside apps need Pro, Max, Team or Enterprise. On Team and Enterprise, an owner adds the connector first.
- **The bridge,** for the free plan or no connector: the app writes a research request, the maker pastes it into an ordinary Claude chat, and pastes the answer back. Same research, one extra paste.

### 8.3 Demo mode
- ✅ von Trapp Farmstead (and Grafton Village Cheese as a second) are pre-baked:
  - the lookup;
  - the bigger picture;
  - the first prompts;
  - ◻ the first three ideas.
- Typing either name plays the lookup back in about 10 seconds. Everything after the first prompts runs live.

### 8.4 Talking instead of typing
- ✅ **Live Listen** for Adam: a companion Listener in a separate Chrome window transcribes the Zoom tab live, with speaker labels. Only the maker's words become "you told us."
  - Apps can't capture audio themselves (probe confirmed), so it runs beside the app.
  - Zoom must run in Chrome.
- Makers on their own use their computer's built-in dictation.

### 8.5 Saving and export
- Autosave to the browser after every change, one record per creamery.
- Export:
  - a readable story pack (`.md`) that drops into a Claude project;
  - a `.json` file that re-imports on another computer.

### 8.6 Getting set up
A checklist on the start screen that tests each item live:
- signed in;
- allow the app to use Claude;
- live lookup path (Pro/Max: connect Parallel Search; Team/Enterprise: owner adds it; Free: the bridge);
- allow the connector;
- optional dictation.

Each failed check shows its fix. There's also a one-page "Before you start" guide VCC can email, and a "Something's not working" panel.

### 8.7 Errors
- Only complete results change state.
- A result built on stale material can't overwrite newer material.
- Stop means stop.
- A failed refresh keeps the previous version.
- One automatic retry on a malformed result, then "Try again."
- Rate limits: "Claude needs a moment, try again in a minute."

### 8.8 Other v1 decisions that still hold
- ✅ The skin switcher (VCC, Jasper Hill, von Trapp, Grafton). It borrows colors and type feel, uses no logos, and labels the app "Your Cheese Story · for [name]."
- ✅ The number and mix of buyers is chosen in the moment.
- ✅ The monger answer site is a demo, per creamery and per cheese.

---

## 9. Build order

Each step ends when its check passes.

1. **Knowledge first:** Core brief v2, arcs guide additions, prompt pool, buyer panel guide, fact-check guide. *Check:* each read against the gems and the arcs.
2. **The shell:** frame, stage rail, side column, Come back to, doors (both kinds), autosave, setup checklist, demo playback. *Check:* click through all five stages with sample state; a door opened from Story shape lands an item in Gathering.
3. **Gathering, live:** lookup, bigger picture, extract, next prompts, ready check, door check. *Check:* von Trapp gives a sourced list of what was found; three typed answers change the prompts; the ready card appears.
4. **Story shape:** three ideas with pick, look closer, outline, beat edits, approve. *Check:* the ideas cite material; missing pieces are bracketed, never invented; one "needs you" beat answered in Gathering changes the outline.
5. **Audience:** channels, panel, buyer test, doors back. *Check:* three buyers react differently, and a "fell flat" points to a real beat.
6. **Essential story and Telling it:** essential sentence; monger card, for the table and social posts first; then the rest; check the facts. *Check:* every factual sentence in a public piece traces to material; gaps are visible.
7. **Live Listen, skins, export/import.**
8. **Full dry run on von Trapp**, and a maker-path run from a separate account.

---

## 10. Open questions for Adam

- ◻ The default three buyers (section 4, Stage 3): keep, or change the cast?
- ◻ Should Check the facts also be reachable as its own item on the rail's last stage, or stay inside each piece as above?
