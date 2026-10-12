# Monger Answer Site

**Purpose:** The content for a small demo web page a cheesemonger could keep open at the counter: everything they need to answer a customer's questions about this creamery and each of its cheeses.

This is a demonstration of what's possible. It should still be accurate and useful.

## Who reads it and how

A monger mid-shift, on a phone or a counter tablet, looking up one thing quickly while a customer waits. Then, sometimes, a curious customer reading over their shoulder.

## What it needs from the Creamery Card

The creamery's chosen story; each cheese's name, style, milk, rind, aging, format, and story; maker-confirmed tasting notes; price-explanation facts; seasonality; where to buy; and anything the maker has said customers often ask.

## Structure

**For the creamery:**
- `one_line`: the creamery's story in one sentence a monger can say.
- `about`: three or four sentences, specific.
- `quick_facts`: location, animals, milk (raw/pasteurized), number of cheeses, how long they've made cheese. Only confirmed facts.

**For each cheese:**
- `counter_line`: one sentence, under 25 words.
- `what_it_is`: milk, style, rind, age, format.
- `taste`: two to four notes (maker or source; else a gap).
- `pairings`: two or three, marked as suggestions.
- `price_answer`: two sentences, from confirmed facts.
- `seasonality`: how it changes, if the maker has said.
- `customer_questions`: four to six questions customers actually ask at a cheese counter, each with a short answer drawn from confirmed facts. Common ones: Is it raw milk? Can I eat the rind? Is it strong? How long does it keep? What's it like? Is it vegetarian (rennet)? Why does it cost this? Where's it made? Answer only what the Card supports; for the rest, give the gap.

## Rules

- Everything except pairings is public-facing. Only maker-confirmed or sourced facts. Gaps appear as `[ask: …]`; the app will show them as visible placeholders.
- Never answer a safety or health question (raw milk and pregnancy, allergens) beyond the plain fact. "It's made with raw milk." Not advice.
- Keep each answer short enough to read in a few seconds.

## JSON shape

```json
{
  "creamery": {
    "name": "string",
    "one_line": "string",
    "about": "string",
    "quick_facts": [{ "label": "string", "value": "string" }]
  },
  "cheeses": [
    {
      "name": "string",
      "counter_line": "string",
      "what_it_is": "string",
      "taste": ["string"],
      "pairings": ["string"],
      "price_answer": "string",
      "seasonality": "string or null",
      "customer_questions": [{ "q": "string", "a": "string" }]
    }
  ]
}
```

## Strong example (fictional Birch Hollow Creamery, one cheese)

> **Hollow Tomme.** *Counter line:* Made only May to October, while 22 Jerseys are on pasture. *What it is:* Raw cow's milk, natural rind, 5–8 months, 4-lb wheels. *Taste:* Brown butter, cut grass, a little mushroom near the rind. *Pairings (suggestions):* Dry cider; rye bread with honey.
> *Can I eat the rind?* `[ask: do you recommend eating the rind?]`
> *Is it raw milk?* Yes.
> *Why does it cost this?* One small herd, a cheese made only half the year, and every wheel turned by hand for at least five months.

## Self-check

- Could a monger find any answer in a few seconds?
- Does every answer trace to the maker or a source?
- Are pairings marked as suggestions?
- Are safety questions answered with facts only?
