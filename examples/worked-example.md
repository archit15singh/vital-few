# Worked example: autonomous vuln find-and-fix

One pass of Vital Few. Object came in as `anthropic autonomous vulnerability patcher`.

## 1. Name

**Object.** Defending Code Reference Harness (and the class it sits in: closed-loop CRS).

**Job.** Autonomous recon → find → verify → patch, with a witness that is not a paragraph.

## 2. Instance

[anthropics/defending-code-reference-harness](https://github.com/anthropics/defending-code-reference-harness). Unmaintained Apache-2.0 reference. C/C++ memory bugs, Docker + ASAN, gVisor. Find agent emits a crashing input (3/3). Grader in a fresh container sees only PoC bytes. Patch ladder: build, PoC gone, tests, re-attack. Human still merges.

Not Claude Security (hosted). Not a general SAST wrapper.

## 3–4. Siblings, ranked

Criterion: runnable OSS that closes find → prove → patch, not GitHub stars.

1. FuzzingBrain + [OSS-CRS](https://oss-crs.openssf.org/) — merged-patch scoreboard, OSS-Fuzz-shaped
2. Defending-code-reference-harness — clearest loop, C/C++ only, unmaintained
3. [google/mantis](https://github.com/google/mantis) — maintained skills, repro-gated patch
4. [Visa VVAH](https://github.com/visa/visa-vulnerability-agentic-harness) — S0–S11 Glasswing descendant
5. [Capital One VulnHunter](https://github.com/capitalone/VulnHunter) — hunt → fix → verify on Claude Code
6. [Hadrian OpenHack](https://github.com/hadriansecurity/OpenHack) — whitebox web/API (different genus)

Closed, not ranked as clones: Claude Security, Microsoft MDASH, Big Sleep.

## 5. Ontology

**Entities.** Target · Threat model · Witness · Trust split · Fix gate

**Relation.** Threat model scopes the find agent, which emits a witness; an independent grader may see only that witness; a unique bug goes to a patch agent; a fix gate; then a human.

**First cut.** Does a finding require an executable witness, and does a patch have to survive an independent check?

**Genera.** Closed-loop CRS · Skill pipeline on a coding agent · Whitebox AppSec hunter. Everything else is the tail.

## 6. Frame

Stanford Symbolic Systems. Axes: Philosophical Analysis, Formal Methods, Computational Methods, Empirical Cognitive Science. Concepts: computation, representation, communication, intelligence.

[Core requirements](https://symsys.stanford.edu/undergraduates/major-policies-requirements/core-requirements). [SYMSYS 1](https://bulletin.stanford.edu/courses/1408381).

**Framing sentence (draft, before top-k).** A CRS is a hybrid symbolic system: neural finder, symbolic oracle, public language, second agent forbidden from the first agent’s inner story.

## 7–8. Explode, collate

Fifteen ideas after collapsing the 5×4 matrix. Load-bearing ones: witness as proof object; threat model as compiled common ground; bytes-only as a principle; finding-as-communication (1,596 disclosed / 97 patched); patch as uninhabiting `Vuln(T')`.

## 9. Competing hypotheses

| | Claim | Promotes |
|---|---|---|
| H1 Formalization | Next leap is proof-like witnesses and fix-gates | proof object, uninhabited Vuln |
| H2 Communication | Bottleneck is symbols humans merge | compiled threat model, merge artifact |
| H3 Architecture | Load-bearing invention is the trust split | bytes-only, nested re-attack |
| H4 CogSci of the researcher | Model the human process | traces, de-biasing |
| H5 Hybrid is the object | Neural finder + symbolic grader *is* the system | interface ideas |
| H6 Philosophy-first is vocabulary | Chinese room / Gettier do not ship | demote to names |

**Resolution.** H5 is the frame. Rank projects by H1∧H2∧H3. H6 is vocabulary. H4 is measurement, not the product.

## 10. Top-k

1. Witness as a checkable proof object
2. Threat model as compiled common ground
3. Public-language / bytes-only as the computational-level claim
4. Finding-as-communication (the merge bottleneck)
5. Patch as making the vulnerability uninhabited

**Framing sentence.** Autonomous vulnerability research is a symbolic system: a neural finder and a symbolic grader that may communicate only in public proof-like objects, under a compiled account of what the target considers a vuln, until a patch makes that object uninhabited — and then the remaining problem is saying that to a human who can merge.

## 11. Extract

The procedure of this pass, with topic nouns stripped, is Vital Few in `LOOP.md`.
