# PR Research and Pitches

**Purpose:** Find food writers who would plausibly care about this creamery's story, and draft a pitch to each one that shows the maker has read their work.

## Who reads it and how

The maker sends the pitches. The writers read them in a crowded inbox, skeptically. The kit's file on press and food writers explains what they want: a story worth telling, specific people, real tension, verifiable facts, and access. Follow it.

## Phase 1: research

Use the search and page-reading tools.

1. Search for writers who have recently covered Vermont cheese, farmstead dairy, the creamery's cheese style, or the themes in its chosen story (regenerative farming, family succession, a particular tradition).
2. For each candidate, find one or two recent relevant pieces and **open and read each one** with the page-reading tool. Confirm the piece exists, is by that writer, and actually covers what you say it covers.
3. Drop any link you could not open or that doesn't say what you'd claim. Drop any writer left with no verified piece.
4. Prefer fewer writers, verified, over a long list. Five verified writers are more useful than twelve guesses.
5. Never invent a writer, an outlet, a title, or a URL.

For each writer:
- `name`, `outlet`
- `pieces`: title, URL, date if shown, and one sentence on what it covered, from your reading
- `why_they_would_care`: the specific link between their work and this creamery's story

## Phase 2: pitches

One pitch per writer, under 200 words.

- Open with a person, a moment, or a problem from the creamery's story. Not the product, and not the farm's founding date.
- Refer specifically to one of their pieces, and say why this story connects to it. One sentence is enough. No flattery.
- Give two or three verifiable facts: names, dates, places, numbers.
- Acknowledge what was hard or uncertain. A pitch with no tension reads as press release.
- Offer access only if the maker has confirmed it (a visit, a call, a day in the make room). Otherwise: `[ask: what access can you offer a writer: a visit, a call, samples?]`
- Close with a plain ask and the maker's contact line as a gap: `[maker's name and phone/email]`.
- Subject line: specific and short, under 10 words.

Never use: award-winning (unless the specific award is named and sourced), premium, world-class, passion, labor of love, "I think your readers would love."

## JSON shape (research phase)

```json
{
  "writers": [
    {
      "name": "string",
      "outlet": "string",
      "pieces": [{ "title": "string", "url": "string", "date": "string or null", "what_it_covered": "string" }],
      "why_they_would_care": "string"
    }
  ],
  "dropped": [{ "name": "string", "reason": "string" }],
  "searched_for": ["string"]
}
```

## Without web access

If the app is running without a search connector, do not name writers. Instead, describe three or four *kinds* of writer to look for (beat, outlet type, what they've covered), and draft one pitch per kind with the writer-specific sentence left as a gap: `[name a piece of theirs you read and why this connects]`.

## Weak and strong

Weak:
> Subject: Award-winning Vermont cheese!
> Hi, I think your readers would love our artisan cheese, handcrafted with passion on our family farm since 1962...

Strong (fictional Birch Hollow Creamery):
> Subject: A tomme that only exists half the year
>
> Your piece on dairies shifting to seasonal milking made the point that the cows' calendar is becoming a selling point. Birch Hollow is a version of that story with a cheese attached. Since 2019, Ana Ruiz has made Hollow Tomme only from May to October, when her 22 Jerseys are on pasture, and stops making cheese entirely in winter. The first year she did it, she lost two wholesale accounts that wanted year-round supply. Last year both came back. `[ask: what access can you offer a writer: a visit, a call, samples?]`
>
> `[maker's name and phone/email]`

## Self-check

- Was every cited piece opened and read?
- Does each pitch refer to something the writer actually wrote?
- Does every fact in the pitch trace to the maker or a source?
- Is any access offered only if confirmed?
