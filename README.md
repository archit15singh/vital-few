# Vital Few

Vital few: name an object, compress the field, compete, commit, stop.

An agent skill and a spec. Give it a terse pointer. It returns a reusable frame and a top-k you would actually work. Then it stops.

It is not a Deep Research report writer, a scanner, a product, or a 15-stage pipeline. The spec lives in [LOOP.md](LOOP.md). The runbook lives in [SKILL.md](SKILL.md).

## Install

Copy the two files into your agent's skills directory as `vital-few`:

```bash
git clone https://github.com/Mr-Ashish/vital-few.git
# then copy SKILL.md and LOOP.md next to each other into the skills dir
```

Or clone the repo and point the agent at it. No runtime, no package manager, no API key.

## Usage

Use when the user names a thing, pastes a URL, or says "things like X", and wants the field compressed, not toured. Also when they ask for 80/20 ontology, competing hypotheses, or a top-k.

The agent follows [LOOP.md](LOOP.md) steps 1–11. Stay on the cut (3–5 substeps per step). Recurse only if that step's output blocks the next. Never recurse `siblings`, `rank`, or `top-k` more than once.

A finished run emits:

1. `object` + `job`
2. Instance card (is / is not / limits) with primary URLs
3. Sibling front (non-dominated set + named tail) + sweep axes
4. Ontology entities, binding relation, first-cut question, genera
5. Frame (name, source, axes, framing sentence)
6. Deduped idea list after CCA
7. Competing hypotheses and the resolution rule
8. Top-k from the front, plus item-1 witness (`yes`/`no` + one line)
9. Short form + aspiration four-check

**Stop when** all four hold: the framing sentence names the ontology; top-k is from the front and k is not N; you would start item 1 tomorrow; no further search is queued. If the witness is `no`, recut once inside step 10, then stop anyway.

Do not use this skill for a single-file bugfix, a look-up of a known API, or implementing the top-k.

## Files

| File | Role |
|---|---|
| [SKILL.md](SKILL.md) | Agent runbook. Frontmatter `name: vital-few`. |
| [LOOP.md](LOOP.md) | Spec. Recursive breakdown of every step. Rank geometry is here. |
| [examples/worked-example.md](examples/worked-example.md) | One pass: autonomous vuln find-and-fix harnesses. |
| [LICENSE](LICENSE) | MIT. |

## Short form

```
name → instance → siblings → rank
    → ontology → frame → explode → cca
    → hypothesis-rank → top-k → extract loop
```

## Contributing

Issues and pull requests are welcome. Open an issue before a large change. The spec is [LOOP.md](LOOP.md); do not fork the procedure inside the README.

## License

[MIT](LICENSE) © 2026 [Mr-Ashish](https://github.com/Mr-Ashish)
