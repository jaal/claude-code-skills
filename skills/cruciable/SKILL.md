---
name: cruciable
description: |
  Stress-test an idea, decision, or claim through a structured 3-round debate between two personas — an Advocate (argues for) and a Devil's Advocate (argues against). The Advocate opens each round; the Devil's Advocate responds. Across three rounds each side must engage the other's points, add something new, and never repeat an argument. Ends with a synthesis.
  Trigger whenever the user:
  - Asks to "debate this", "argue both sides", "steelman and criticize", "play devil's advocate", or "run a cruciable"
  - Wants a claim or plan pressure-tested from both directions before committing
  - Says something like "convince me / talk me out of it" or "what's the case for and against"
  Do NOT use this for a simple factual question, or when the user just wants a single recommendation.
---

# The Cruciable — Two-Persona Structured Debate

Drop an idea in; three rounds of heat come out. Two personas argue a single question in good faith — one **for**, one **against** — and what survives the pressure becomes the summary.

Your job is to run *both* personas honestly. This is not a performance where one side is secretly right; it's a real stress test. Steelman every point. The user should come out with a sharper view than they walked in with.

---

## Step 0 — Frame the motion

Before the debate, restate what's actually being argued as a single clear **motion** — one sentence, phrased so that "for" and "against" are unambiguous.

> "Here's the motion we'll debate: **[clear one-sentence claim]**. Three rounds — Advocate opens, Devil's Advocate answers. Ready?"

If the user's input is vague ("should I do this?"), sharpen it into a concrete motion first. If it's genuinely two options rather than a yes/no, frame the motion as "We should choose X over Y."

The two personas:

- 🟢 **The Advocate** — argues *for* the motion.
- 🔴 **The Devil's Advocate** — argues *against* it.

---

## The rules (enforce these strictly)

1. **The Advocate always opens each round. The Devil's Advocate always responds.**
2. **Three rounds total.** No more, no fewer.
3. **Engage before you extend.** From Round 2 onward, each persona must *first* directly address the opponent's most recent points — concede what's fair, rebut what isn't — and *then* add something new. No ignoring the other side and monologuing.
4. **No repeating an argument.** Once a point has been made by either side, it's spent. Every turn must advance the discussion with fresh reasoning, a new angle, or a sharper version of a concession — never restate what's already on the table.
5. **Examples are welcome and encouraged.** Concrete cases, analogies, numbers, historical precedents, or "imagine X happens" scenarios beat abstract assertions. Reward specificity.
6. **Good faith only.** Steelman the opposing view; never strawman. If a persona can't find a genuinely strong new point, it may concede ground — that's a legitimate and useful move.
7. **Keep turns tight.** 2–4 punchy points per turn, not a wall of text. Momentum matters.

---

## Format

Label every turn clearly and keep the structure visible:

```
## Round 1

🟢 Advocate
- [opening argument 1]
- [opening argument 2 — with a concrete example]

🔴 Devil's Advocate
- [directly answers/undercuts the above, then adds new counter-arguments]

## Round 2

🟢 Advocate
- [addresses the Devil's Advocate's points, then extends with something new]

🔴 Devil's Advocate
- [addresses the Advocate, then extends]

## Round 3

🟢 Advocate
- [final push — best remaining argument, engages what's still standing]

🔴 Devil's Advocate
- [final push]
```

Run all three rounds in a single response unless the user asks to go turn-by-turn (in which case, pause after each persona and wait).

---

## The summary (always close with this)

After Round 3, step out of both personas and deliver a clear-eyed synthesis:

---
**The motion:** [restated in one line]

**Strongest surviving argument for:** [the single best point the Advocate made that the other side never fully answered]

**Strongest surviving argument against:** [same, for the Devil's Advocate]

**The real crux:** [the one question the whole disagreement actually hinges on — the thing that, if settled, would settle the debate]

**What would change the answer:** [the piece of information or evidence that would tip it decisively one way]

---

Then hand the decision back to the user:

> "That's the crux. Where do you actually land — and what does that tell you?"

Don't declare a winner unless the user explicitly asks for your verdict. The point is a sharper view, not a ruling.

---

## Tone & boundaries

- Both personas are sharp, fair, and a little bit rival — this should be *fun* to read, not dry.
- Never let one side get lazy. If the Advocate is winning easily, make the Devil's Advocate find its strongest possible objection.
- If the motion is a genuine life decision, keep the personas arguing the *substance*, and let the closing synthesis (not the personas) hold the warmth.
- If the user jumps in mid-debate with a new point, fold it into the next round rather than restarting.

---

## Example (opening exchange)

**Motion:** *We should ship the feature now and polish it in the next release, rather than delay launch to polish first.*

## Round 1

🟢 **Advocate**
- Shipping now starts the feedback clock immediately — a week of real usage teaches us more than a month of internal polish guessing at what matters.
- Every day unshipped is a day competitors close the gap. Example: the last feature we delayed "one more sprint" slipped six weeks and launched into a market that had moved on.

🔴 **Devil's Advocate**
- The feedback-clock argument assumes early users forgive rough edges — they don't; they form a first impression and churn. A broken first release *poisons* the feedback, because people rage-quit instead of teaching you anything.
- And "competitors closing the gap" cuts both ways: a rushed launch that flops hands them the exact story they want to tell about us. Better late and sharp than early and forgettable.

[...continues through Round 3, then the synthesis...]
