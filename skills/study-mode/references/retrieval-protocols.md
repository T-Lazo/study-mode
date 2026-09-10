# Retrieval protocols

How to run a recall check, prompt self-explanation, and detect the illusion of knowing.

## The recall check

The core move. Use it to close every NEW topic and to open every SEEN one.

1. **Close the material.** Explicitly. "Notes away" is part of the instruction, not a formality — retrieval only counts if nothing is being read.
2. **Ask for production, not recognition.** "What does X do?" beats "Does X do A or B?". Multiple choice tests recognition, which is nearly free and nearly worthless.
3. **Wait.** Do not fill the silence with a hint. The effortful pause is where the strengthening happens.
4. **Grade against the material, not against plausibility.** A confident wrong answer is the most valuable thing in the session — it is a misconception surfacing. Name it precisely.
5. **Update the log.** `tested +1`, set `conf`, set `due`.

## Confidence, honestly

Ask the reader to rate 1–3 **before** you grade them, then compare.

- Rated 3, got it wrong → the important case. They have a fluency illusion on this topic. Log `conf 1` regardless of how well they know it tomorrow, and re-test within a day.
- Rated 1, got it right → they know it better than they think. Log 2, not 3.
- Rating matches outcome → log it and move on.

The gap between predicted and actual performance is a better signal than either number alone.

## Self-explanation prompts

Use during a worked example, not after. The reader explains each step as it happens.

- "Why does this step follow from the last one?"
- "What would break if this line were removed?"
- "Where have you seen this pattern before?"
- "What is this step trying to achieve?" (the subgoal — name it)

Self-explanation is rated moderate-utility on its own and much higher when paired with worked examples. It is the mechanism that turns a worked example from reading into learning.

## Metacognitive checks by content type

Adapt the check to what is being learned. These are not interchangeable.

| Content | Check |
|---|---|
| Concept | "What is the big idea here?" Then: explain it to someone who has not taken the course. |
| Vocabulary | Define it in your own words, then use it correctly in a new sentence. |
| Formula or theorem | Not "can you state it" — "why does it matter, and when would you reach for it?" |
| Competing positions | What do these two authors or approaches disagree about, precisely? |
| Procedure | Name each step's subgoal, then run it on an input you have not seen. |

## Teaching aloud

The strongest single check available. Have the reader explain the concept out loud with nothing in front of them.

Listen for the failure signature: fluent for two sentences, then vague. The vagueness marks the exact boundary of understanding. Stop there and work on that, not on the part they got through.

Ask them to do it verbally rather than in writing when possible — writing permits editing and rereading, which lets them repair gaps without noticing they had one.

## What not to offer

Rated low-utility in Dunlosky et al. (2013), *Improving Students' Learning With Effective Learning Techniques*:

- Highlighting and underlining
- Rereading
- Summarisation
- Keyword mnemonics
- Imagery for text

All produce fluency without retrieval. Only **practice testing** and **distributed practice** were rated high utility. Elaborative interrogation, self-explanation, and interleaved practice were rated moderate.

Mnemonics are the defensible exception: genuinely useful for arbitrary ordered lists (PEMDAS, resistor colours) where there is no underlying logic to understand. Useless for anything with structure — and reaching for one on structured material is a sign the structure has not been understood.

## Spacing

Set `due` from confidence: `1 → +1 day`, `2 → +3 days`, `3 → +10 days`.

Failed retrieval drops confidence by one and reschedules from the lower value. A topic that keeps falling back to 1 is not a memory problem — it is a missing prerequisite. Stop drilling it and go find what it rests on.
