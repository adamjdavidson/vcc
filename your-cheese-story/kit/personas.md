# Personas

**Purpose:** Help a maker see the specific people who buy, sell, or serve their cheese, and which part of their story reaches each one.

## Who reads it and how

The maker and Adam, as planning material. Personas are not published. They help decide which story to lead with for which audience, and they feed other outputs (pitches, posts, emails).

## Inputs

- What the maker sells, and who they think buys it, and where it's sold (from the maker).
- How many personas they want, and the mix: consumers, trade, or both. Decided in the moment. One is fine. Thirty is fine.
- The Creamery Card and the chosen story.
- Optional web research: who shops at the outlets they named, what similar cheeses are sold alongside theirs, what buyers in that channel look for.
- The kit's audience files for any trade audiences involved (mongers, retail buyers, co-ops, chefs, wholesalers, writers, farmers-market customers, general consumers).

## Rules

- Personas are informed guesses, and the output should read that way. They can include ideas and invented illustrative details about the persona (a name, a typical shopping trip). They must not invent anything about the creamery.
- Ground each persona in something real: what the maker said about their customers, the channels they sell through, or research you actually did. Say which.
- Make them specific enough to act on. "Foodies" is not a persona. "A Burlington parent who brings a cheese to every dinner party and wants something she can say a sentence about" is.
- Avoid stereotypes about age, gender, class, or region. Describe what people do and want, not what they look like.
- Include at least one trade persona when the maker sells wholesale or through mongers, unless they ask otherwise.

## For each persona

- `name`: a short descriptive handle ("The dinner-party bringer").
- `who`: one or two sentences.
- `where_they_buy`: the specific channel.
- `what_they_care_about`: two or three things.
- `story_that_reaches_them`: which part of the creamery's story, and why.
- `line_that_lands`: one sentence they'd respond to, using only confirmed facts or a gap.
- `line_that_falls_flat`: one sentence that would lose them, and why.
- `grounded_in`: what this persona is based on (maker said, research, or kit audience file).

## JSON shape

```json
{
  "personas": [
    {
      "name": "string",
      "type": "consumer | trade",
      "who": "string",
      "where_they_buy": "string",
      "what_they_care_about": ["string"],
      "story_that_reaches_them": "string",
      "line_that_lands": "string",
      "line_that_falls_flat": { "line": "string", "why": "string" },
      "grounded_in": "string"
    }
  ],
  "notes": "string (optional: patterns across personas, or what the maker might ask their customers to check these guesses)"
}
```

## Weak and strong

Weak:
> *Health-conscious millennial.* Likes organic food. Shops at Whole Foods. Values sustainability.

Strong (fictional Birch Hollow Creamery):
> *The co-op cheese buyer.* Buys for a 3-store co-op in the Champlain Valley; tastes everything before stocking it and needs a reason to give a new cheese shelf space over one that already sells. Cares about steady supply, a story her staff can repeat, and a price that clears her margin. Reached by the half-year-only story, because it explains both the taste and why supply is limited. *Lands:* "We only make it while the cows are on pasture, so we'll tell you in April how many wheels you can have." *Falls flat:* "A labor of love from our family to yours," because it tells her nothing she can use at a staff tasting. *Grounded in:* the maker said they sell to two co-ops; kit file on co-ops and independent grocers.

## Self-check

- Does each persona connect to something real?
- Does every line that lands use only confirmed facts?
- Are the personas different enough from each other to change what you'd say?
