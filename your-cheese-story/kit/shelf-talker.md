# Shelf Talker

**Purpose:** The small card beside the cheese in a shop case. It tells a shopper who hasn't tasted the cheese what it tastes like and gives one reason to believe it, in the few seconds they spend looking at the case.

## Who reads it and how

A shopper at a cheese case or grab-and-go cooler, often when no one is free behind the counter. They scan, for one to three seconds at arm's length, so design guides agree: one message, not three. Heavy specialty-cheese buyers do look for information at the case (92% in one survey).

This card is where the project's strongest number comes from. In a choice experiment with 488 US specialty-cheese buyers, a sensory shelf talker raised willingness to pay by about $1.90 on an $11.10 wedge. A generic gold award sticker raised it by about $1.55. Shown together, the two raised it further than either one did alone. The buyers split roughly in half:
- **About 47% are averse to sensory uncertainty.** For them the sensory talker mattered most. It is how a stranger's cheese becomes safe to buy.
- **About 44% are novelty seekers.** For them the award mattered more.

The authors suggest that awards help most with familiar styles, and that sensory and pairing notes help most with unfamiliar ones.

The card has a second reader: **the monger**. Many shops write their own talkers. One Los Angeles buyer called producer-printed ones "too clean, too polished" and asks distributors to hand-write them, while noting that any talker outsells none. Other retail advice wants neat, consistent lettering. No study has compared the two. So the maker supplies both: a finished printed card, and raw material the monger can rewrite in their own voice.

**Size.** Cheese-case sign holders take cards around 3½ × 2, 3 × 4, or 2 × 3¾ inches. The wine-shelf standard is 3 × 5 with a 1-inch fold tab (3 × 4 visible). Vermont's Center for an Agricultural Economy advises 2 × 3½ to 3 × 5 inches, with printed copies plus a digital file for the store. Write for the smallest: about 40 words, legible at arm's length.

## What it needs from what the maker has gathered

- The cheese name, milk, and treatment (raw or pasteurized). Shops expect these on the card.
- Taste notes the maker has confirmed, ideally including what customers say.
- One demonstrated fact from the chosen story, usually **What We Won't Do**, **This Wheel, This Season**, or **The Hands**.
- Any award, with the competition, year, and class (**The Upstart**).
- One or two pairings, if the maker has them.

## Structure

1. **Name** (the cheese, then the creamery). Below it, a small identity line: milk, raw or pasteurized, and town. "Vermont" belongs here, as identification. On its own it isn't the pitch, because "Made in Vermont" earns little in city markets.
2. **Sensory line** (one line, 6–12 words). This is the most important line on the card. Pair one broad term a novice already uses with one specific term that teaches: "Nutty, like toasted hazelnut." Use at most three notes.
3. **Story line** (one line, 8–15 words). One demonstrated, checkable fact that gives a reason for the taste or the price. It is not a value claim.
4. **Award line** (optional, under 10 words). Only a named award: competition, year, medal or class. "Award-winning" is never acceptable on its own. For a familiar style, give the award more visual weight. For an unfamiliar one, give the sensory line more.
5. **Try it with** (optional, 2–6 words). One or two pairings. This helps the uncertainty-averse buyer picture the occasion.

Total: about 40 words printed, never more than 50. The name line and sensory line go in the largest type. Everything else is smaller.

**Monger's raw material** (sent alongside the card, not printed on it):
- Two or three alternate sensory phrasings.
- One quotable "why" from the maker, in their own words.
- One character detail about the maker or the farm.

The monger picks, rewrites, or hand-letters any of it.

## Rules

- **Accuracy is the color.** The strongest pleasure comes when the cheese matches its description or slightly beats it. Describe the wedge a shopper will actually get, not the cheese at its peak. If the cheese varies by season, choose notes that hold across the year, or name the season.
- **Taste notes come from the maker** (or from published reviews, credited as such). If there are none, write `[ask: what do you and your customers taste in it?]`. Never fill the gap with "rich and complex."
- **Awards must be named and sourced.** If the maker hasn't confirmed one, use `[ask: any awards? competition, year, class?]` or leave the line off. Never write a generic "award-winning."
- **No badges standing in for story.** Printing an eco-label once erased the premium its certification had earned. If the farm's practice matters, state it as a fact in the story line.
- **No unbacked weak words** (artisan, handcrafted, small-batch, local, premium) and **none of the banned ones.**
- **Pairings may be suggestions** from general knowledge of the style. Mark them as suggestions in the draft until the maker confirms them.
- **No paragraph about the maker.** Producer text lowered perceived quality in one study; a producer photo raised it. If there's room for more, use a small photo of the maker at work.

## Weak and strong

Weak (fictional Birch Hollow Creamery):
> **Hollow Tomme** — Award-winning artisan farmstead cheese, handcrafted with love in the rolling hills of Vermont. Rich, complex, and unique. Certified humane. A true taste of Vermont!

It fails: an unnamed award, weak and banned words, no teaching sensory term, a badge instead of a fact.

Strong:
> **Hollow Tomme** · Birch Hollow Creamery
> *Raw Jersey cow's milk · Vermont*
> **Buttery and grassy: brown butter, cut grass, a little mushroom by the rind.**
> Made only May to October, while Ana's 22 Jerseys are on pasture.
> `[ask: any awards? competition, year, class]`
> Try it with: dry cider; rye bread and honey.

That's about 44 words with the award line left off.

Monger's raw material for the same cheese:
> *Other ways to say the taste:* "Like brown butter on toast, with a little meadow in it." / "Savory near the rind, sweet in the middle." `[ask: confirm which you'd stand behind]`
> *Quotable why:* `[ask: in your words, why stop making cheese in winter?]`
> *Character detail:* The first year she went seasonal she lost two wholesale accounts. Last year both came back.

## Self-check

- Does the sensory line pair a broad term with a specific one that teaches?
- Would someone tasting a typical wedge say "yes, that's it"?
- Is the story line a fact a shopper could check, not a claim?
- If there's an award, is it named, with the competition and year?
- Is it under 50 words, readable at arm's length on a 2 × 3½ card?

## JSON shape

```json
{
  "name": "", "creamery": "", "identity": "milk · raw/pasteurized · town",
  "sensory": "", "story": "",
  "award": {"competition": "", "year": "", "result": ""},
  "try_with": [],
  "monger_raw": {"alt_sensory": [], "quotable_why": "", "character_detail": ""}
}
```

## Sources

- Streletskaya et al., "How information leads consumers to select specialty foods when tasting is not an option," *Food Quality and Preference* (2023): https://www.sciencedirect.com/science/article/pii/S0950329322002440. Willingness-to-pay figures, consumer classes, and the familiar/unfamiliar recommendation. An online, hypothetical choice experiment with a generic gold-medal sticker.
- SevenFifty Daily, "The Pros and Cons of Shelf Talkers" (2018): https://daily.sevenfifty.com/the-pros-and-cons-of-shelf-talkers/. Handwritten preference; "too clean, too polished"; any talker outsells none.
- Center for an Agricultural Economy (Hardwick, VT), "Shelf Talker 101": https://hardwickagriculture.org/sites/default/files/documents/ShelfTalker101_Final.pdf. Sizes from 2 × 3½ to 3 × 5 inches; send print copies and a digital file.
- Shelf Talker, "What Is a Shelf Talker?" and "5 Tips": https://shelftalkerapp.com/what-is-a-shelf-talker ; https://shelftalkerapp.com/blog/shelf-talker-tips. The 3 × 5 standard with a fold tab; roughly three seconds of attention.
- Kapa99, "Shelf Talker & POP Display Sizes" (2026): https://kapa99.com/blog/shelf-talker-and-pop-display-sizes. Read in about a second; one claim per card; 3 × 4 to 4 × 6 typical.
- WebstaurantStore, deli case tags and sign holders: https://www.webstaurantstore.com/2753/deli-tags-accessories.html. Case holder sizes.
- Speciality Food Magazine, "How to display cheese" (2024): https://www.specialityfoodmagazine.com/food-and-drink/how-to-display-cheese. Cheese labels carry name, milk, raw or pasteurized, origin, and price; avoid messy, inconsistent handwriting.
- Other findings (the 92% figure, broad plus specific terms, liking when the product meets its description, eco-label, producer photo vs. text) come from the project's research files.
