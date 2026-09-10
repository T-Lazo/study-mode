# study-mode

A Claude Code skill that turns a session into deliberate study instead of an answer service.

Claude's default instinct is to be maximally helpful by answering well. When you are trying to *learn* something, that instinct is the failure case — you read an excellent explanation, feel like you learned, and retain almost none of it. This skill inverts that: it makes you produce the answer.

Built for university coursework, with a bias toward software engineering material and toward readers who lose the thread easily.

## Install

```bash
/plugin marketplace add T-Lazo/study-mode
```

```bash
/plugin install study-mode
```

Then, in a directory for your current block:

```bash
/study-mode
```

It stays on until you say `stop study mode`.

## What it actually does

**One outcome per session, restated every turn.** The first thing it does is establish a single testable learning outcome — derived from your material, or sharpened from your question. It appears at the top of every response. Sessions drift; this is the cheapest defence.

**Tangents get parked, not followed.** Anything interesting that does not serve the outcome goes to a visible list. Named, not explored. At session end you decide which deserve a session of their own.

**Answers are gated once you have seen a topic.** First encounter with a topic gets a clean worked example — making a novice struggle is load without learning. Every encounter after that, it asks what you think first and does not answer until you have attempted. `just tell me` overrides it, once, and gets logged.

**It knows what you have covered.** A markdown log per subject tracks each topic's confidence and when it is next due. Nothing else to install, no database, no app — you can read and edit the log by hand.

**It tells you what to study next.** Weight × confidence × overdue, top three. Deciding what to work on is the expensive part of starting.

## Block structure

The skill works inside a *block* — a directory holding one teaching period's subjects.

```
block-3/
  BLOCK.md
  functional-programming/
    material/          # drop slides, PDFs, notes here
    LOG.md
  databases/
    material/
    LOG.md
```

`BLOCK.md` declares what exists and what it is worth:

```markdown
# Block 3 — Semester 1

| subject                | tier  | weight |
|------------------------|-------|--------|
| functional-programming | major | 40     |
| software-design        | major | 40     |
| databases              | minor | 10     |
| professional-practice  | minor | 10     |
```

Run `/study-mode` in an empty directory and it builds this for you. Run it in an existing block and it validates the structure first — missing logs, subjects listed but absent, weights that do not sum to 100 — because a missing `LOG.md` silently downgrades every topic to "new" and the gate stops working.

Any number of majors and minors. The tiers are just labels; the weights do the work.

## Writing code

Most code in a study session is not what you are learning — scaffolding, config, a test harness. The skill writes that normally.

When the code *is* the outcome, it runs [PRIMM](https://primmportal.com/) instead: predict what it does, run it, investigate it, modify it, then make something new. Say `build mode` to drop the gate entirely.

## What it will refuse

Highlighting, rereading, passive summarising, and recopying notes. All four are rated low-utility in the standard review of learning techniques, and they share one failure — they make text feel familiar, and familiarity gets mistaken for knowledge.

It will offer you the replacement and move on. It will not lecture you about it.

## Evidence base

The design leans on cognitive load theory: working memory holds about four items, and every rule in the skill exists to stop extraneous load from eating that budget.

- Dunlosky et al. (2013), [*Improving Students' Learning With Effective Learning Techniques*](https://journals.sagepub.com/doi/10.1177/1529100612453266) — the utility ratings behind what the skill recommends and refuses
- Greg Wilson, [*Teaching Tech Together*](https://teachtogether.tech/) — cognitive load, Parsons problems, faded examples, subgoal labelling
- [PRIMM](https://primmportal.com/) — the code-learning ladder
- Harvard Academic Resource Center — [effective learning](https://academicresourcecenter.harvard.edu/2023/09/27/effective-learning/), [assessing understanding](https://academicresourcecenter.harvard.edu/2023/09/27/assessing-understanding/), [memory and attention](https://academicresourcecenter.harvard.edu/2023/09/27/memory-and-attention/), [reading](https://academicresourcecenter.harvard.edu/2023/10/02/reading/)
- [UCD Library revision guide](https://libguides.ucd.ie/StudySkills/revision) — past papers and revision scheduling

Output shaping is adapted from [i-have-adhd](https://github.com/ayghri/i-have-adhd) by Ayoub G., re-tuned for studying rather than shipping.

## A warning

The two best parts of this skill — the stated outcome and the answer gate — are the two you will want to turn off. They add friction on purpose, and friction is least welcome exactly when you are tired, which is when you would otherwise study badly.

`stop study mode` is always there. Using it is fine. Knowing that you reached for it is the useful part.

## License

MIT
