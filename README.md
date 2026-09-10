# Product Thinking Quiz

Eight multiple-choice questions that test whether an engineer can *apply* product thinking —
not whether they can recite it. Every answer is followed immediately by an explanation, and
the correct option is marked either way, so a wrong answer still teaches.

**Take it:** https://shionhigashi.github.io/product-thinking-quiz/

## What it covers

| # | Framework | The question tests |
|---|-----------|--------------------|
| 1 | Problems before solutions | Treating a ticket as evidence of a problem, not a spec |
| 2 | Outputs vs outcomes | Telling what you delivered from what became different |
| 3 | Five Whys | Not stopping the chain at "the user was careless" |
| 4 | The 4Cs | Spotting the missing C — Confirmation, the evidence |
| 5 | Leading vs lagging | Picking an indicator you can still act on |
| 6 | SMART targets | Stating a goal two people can't disagree about |
| 7 | Riskiest assumption | Buying the cheapest answer to the biggest unknown |
| 8 | Staged delivery | Not doing stage-three work at stage one |

The wrong answers are the tempting engineer defaults — gold-plating the export, building the
scheduler before anyone wants it — rather than filler.

## Running it

Open `index.html`. That's all — no build step, no dependencies, no server.

```
open index.html
```

Fonts load from Google Fonts when online and fall back to system stacks when not.

## Interaction

- Click an option, or press `1`–`4`
- `Enter` or `→` to advance
- Options lock on answer; the correct one is always marked
- Score summary at the end with a per-question review, then **Try again**

Options are shuffled on each attempt (correctness rides on the option object, so the answer
key can't desync). Question order stays fixed — it's a learning arc.

## Editing the questions

Everything lives in the `QUESTIONS` array in the `<script>` block:

```js
{
  tag: "Leading & lagging",        // framework label above the question
  stem: "You ship the fix...",     // scenario (HTML allowed; .quote for a blockquote)
  ask: "Which is a leading indicator?",
  options: [
    { t: "Quarterly support volume" },
    { t: "Share of uploads auto-detected", ok: true }   // exactly one ok: true
  ],
  why:  "Explanation shown after answering.",
  diff: { m: "the wrong framing", p: "the right one" }, // optional −/+ block
  also: "Secondary note.",                              // optional
  take: "One line for the end-of-quiz review."
}
```

Add or remove questions freely — the progress bar and counter size themselves from the array.

## Source

The frameworks are adapted from Singapore's Innovation & Digital Governance product-thinking
pathway — <https://www.idg.gov.sg/product-thinking/> — which covers the three shifts, 5 Whys,
the 4Cs, SMART, leading/lagging indicators, Value-Cost Ratio, staged de-risking and the
11-star exercise. The scenarios, distractors and explanations are written for this quiz.

## Deployment

GitHub Pages serves `main` from the repo root. Pushing a change to `index.html` redeploys it.
