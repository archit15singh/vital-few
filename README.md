# Vital Few

Name an object, compress the field to a few entities, import a frame, explode, compete, commit. Then stop.

This repo is the spec. It is not a product, a scanner, a Deep Research report writer, or a 15-stage pipeline.

## Short form

```
name → instance → siblings → rank
    → ontology → frame → explode → cca
    → hypothesis-rank → top-k → extract loop
```

**Aspiration.** Stop when the framing sentence names the ontology, top-k is from the front, item 1 is something you would start tomorrow, and no further search is queued.

## Files

| File | Role |
|---|---|
| [LOOP.md](LOOP.md) | Source of truth: recursive breakdown of every step |
| [SKILL.md](SKILL.md) | Agent runbook |
| [examples/worked-example.md](examples/worked-example.md) | One pass on autonomous vuln find-and-fix harnesses |

## Recursion rule

Run each step on the cut (3–5 substeps). Recurse into a step only if its output is blocking the next step. Never recurse into `siblings`, `rank`, or `top-k` beyond one extra pass. `extract loop` is terminal.

## Whole-loop contract

| | |
|---|---|
| **In** | A terse pointer (a name, a URL, a “things like X”) |
| **Out** | Named object, ontology, framing sentence, top-k from the front, item-1 witness |
| **Invariant** | Findings are public artifacts (sources, tables, votes), not vibes. Rank geometry is in LOOP.md. Aspiration is four checks. |
| **Do not** | Expand the long tail. Star-count rank. Scalarize at step 4. Skip CCA. New eval inside the loop. Hypotheses that all promote everything. |

## Install as a skill

Copy `SKILL.md` (and `LOOP.md` next to it) into your agent’s skills directory as `vital-few`. Or clone this repo and point the agent at it.
