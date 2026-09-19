# Vital Few

Vital few: name an object, compress the field, compete, commit, stop.

An agent skill. Point it at a name, a URL, or “things like X”. It returns a frame and a top-k you would work. Then it stops.

Not a Deep Research writer. Not a scanner. Not a product. The spec is [LOOP.md](LOOP.md). The runbook is [SKILL.md](SKILL.md).

## Install

Two files. No runtime.

```bash
git clone https://github.com/Mr-Ashish/vital-few.git
```

Copy `SKILL.md` and `LOOP.md` into your agent’s skills directory as `vital-few`, or point the agent at the clone.

## Usage

Fire it when the user wants a field compressed, not toured: a terse pointer, 80/20 ontology, competing hypotheses, a top-k.

Example pointer: `anthropic autonomous vulnerability patcher`. Worked pass: [examples/worked-example.md](examples/worked-example.md).

Do not fire it for a single-file bugfix, a known-API look-up, or implementing the top-k.

The agent runs [LOOP.md](LOOP.md). What it must emit, and when to stop, is in [SKILL.md](SKILL.md).

```
name → instance → siblings → rank
    → ontology → frame → explode → cca
    → hypothesis-rank → top-k → extract loop
```

## Files

| File | Role |
|---|---|
| [SKILL.md](SKILL.md) | Runbook. Frontmatter `name: vital-few`. |
| [LOOP.md](LOOP.md) | Spec. Every step, rank geometry, anti-patterns. |
| [examples/worked-example.md](examples/worked-example.md) | One pass on vuln find-and-fix harnesses. |
| [LICENSE](LICENSE) | MIT. |

## Contributing

Issues and pull requests are welcome. Open an issue before a large change. Change the procedure in [LOOP.md](LOOP.md), not here.

## License

[MIT](LICENSE) © 2026 [Mr-Ashish](https://github.com/Mr-Ashish)
