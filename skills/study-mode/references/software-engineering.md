# Learning software engineering

Code is a special case: reading it feels like understanding it, and the gap between reading and writing is enormous. These protocols close that gap.

## PRIMM

Use when the code **is** the learning outcome — an algorithm, a pattern, a technique being assessed. Not for scaffolding, config, or tooling, which run in build mode.

The stages are already an escalation ladder. Do not skip to Make.

**P — Predict.** Show a short program. Ask what it outputs *before* running it. This is the highest-value stage and the one most often skipped. A wrong prediction is a misconception made visible.

**R — Run.** Run it and compare to the prediction. The reader does not type it — transcription burns working memory on syntax while the goal is behaviour.

**I — Investigate.** Go inside. Pick from: trace execution line by line, annotate what each block does, name the variables and their roles, introduce a deliberate bug and have them find it, or reorder scrambled lines.

**M — Modify.** Incremental changes to working code. Start small — change a constant, then a condition, then a data structure. Each modification has a predicted outcome before it runs.

**M — Make.** Write something new that solves a different problem, reusing what was learned. This is where "build mode" would have started. It is the last stage, not the first.

Stages can repeat and not every session needs all five.

## Parsons problems

Give the correct lines, scrambled. The reader orders them.

Use when someone understands the concept but cannot yet produce the code — the common case where "explain it" is too easy and "write it" is too hard. Isolates logic from syntax entirely.

Add difficulty by including one or two distractor lines that do not belong.

## Faded examples

The bridge from worked example to independent work. Fade across a sequence of problems, not within one.

1. Complete worked solution, fully explained.
2. Same shape of problem, one step blanked.
3. Two or three steps blanked.
4. Only the subgoal labels remain as scaffolding.
5. Nothing.

If they stall at a step, go back one level rather than explaining. Fading is the whole mechanism; explaining collapses it.

## Subgoal labelling

Name what each chunk of a procedure is *for*, not what it does mechanically.

```
# create empty accumulator      <- subgoal
result = []
# filter to matching items      <- subgoal
for x in items:
    if pred(x):
        result.append(x)
```

Measurably improves transfer to new problems. Have the reader supply the labels — writing them is the exercise; reading them is not.

## Novice, competent, expert

Adjust which technique you reach for by where they are on the current topic. Note that this is per-topic, not per-person: the same reader is expert on recursion and novice on type classes in the same session.

- **Novice** — no working mental model. Wants worked examples and concrete cases. Withholding the answer here produces frustration, not learning.
- **Competent** — a model that works for ordinary cases. Wants Parsons problems, faded examples, modification tasks. The gate belongs here.
- **Expert** — a model including the exceptions. Wants hard problems and edge cases. Worked examples actively slow them down — the expertise reversal effect.

Getting this wrong in either direction wastes the session. `LOG.md` confidence is your best available signal.

## Code tracing

Before debugging anything, have them trace it by hand — a table of variables and their values, line by line.

Most debugging failures in novices are not reasoning failures. They are a wrong mental model of what a construct does, and tracing surfaces that in about a minute. It is also the fastest way to find where a prediction went wrong in PRIMM.

## Where "understanding" differs by material

These are genuinely different targets and generic advice blurs them:

- **An algorithm** — can you predict its behaviour on an input you have not seen, and state its complexity and why?
- **A design pattern** — can you say what problem it solves and, more importantly, when *not* to reach for it?
- **A language feature** — can you say what it costs, not just what it does?
- **A proof or formal argument** — can you identify which step fails if a premise is removed?
- **A tool or framework** — mostly reference knowledge. Do not gate it. Look it up and move on.

That last one matters: gating recall on things a working engineer would look up is wasted session time.
