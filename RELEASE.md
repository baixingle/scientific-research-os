# Scientific Research OS v1.0.1

## Overview

Scientific Research OS v1.0.1 is a backward-compatible patch release that makes the path from scientific reasoning to **tool-connected AI execution** explicit, while preserving the zero-config, human-guided scientific core introduced in v1.0.0.

The central loop is now stated directly:

```text
Scientific question
        ↓
Competing explanations
        ↓
Most informative next step
        ↓
Bounded mission + acceptance criteria
        ↓
Available authorized tool / executor performs the work
        ↓
Technical acceptance / failure check
        ↓
Scientific review and claim boundary
        ↓
Research state + provenance update
```

## What Changed in v1.0.1

### Tool-connected execution is explicit

When the host AI environment provides suitable authorized tools, Scientific Research OS should not stop at producing a plan if a well-bounded mission can be executed reliably in the current environment.

Depending on the host environment, available capabilities may include files and repositories, code execution, shell or notebooks, analysis packages, literature/search systems, databases, local or remote compute, workflows, laboratory automation, instruments, robotic platforms, project APIs, or other domain-specific interfaces.

Scientific Research OS itself remains tool-independent: it does not bundle or promise a universal execution engine or connector layer. It governs how available capabilities are turned into bounded, reviewable scientific work.

If execution capability, authorization, safety, or budget is missing, the correct fallback is a precise mission or handoff — never a claim that the work was executed.

### Execution remains human-guided

Tool availability is not permission. Appropriate human approval remains required before expensive, irreversible, privacy-sensitive, safety-sensitive, ethically regulated, or strategically consequential actions when approval cannot be safely inferred.

A proposed experiment, calculation, search, analysis, upload, instrument run, or other action must never enter the scientific record as completed unless the environment actually executed it and returned evidence of completion.

### Better onboarding and examples

v1.0.1 also improves the project entry experience:

- README now makes the reasoning -> execution -> review -> provenance loop visible near the top;
- Quick Start distinguishes direct execution from external mission handoff;
- synthetic wet-lab, computational/simulation, and ML/data-science showcases demonstrate the domain-neutral scientific-method layer;
- contributor guidance now invites real-world reports of missed alternatives, overclaiming, workflow friction, execution failures, and reproducibility gaps.

### Release and citation hygiene

- Added `CITATION.cff` with version-specific citation metadata.
- Normalized MIT license metadata for correct GitHub recognition.
- Preserved the v1.0 architecture: no new mandatory role, workflow, configuration system, or domain-specific module was introduced.

## What Remains the Same

Scientific Research OS is still:

- **zero-config by default** — start with the scientific problem, not framework setup;
- **human-guided** — the researcher remains the final scientific decision maker;
- **evidence-controlled** — claim strength must not exceed evidence strength;
- **decision-oriented** — prioritize information gain rather than activity volume;
- **transparent** — current scientific state should remain inspectable;
- **historically traceable** — important scientific history is append-oriented rather than silently rewritten;
- **domain-neutral at the scientific-method level** — applicable across wet-lab, computational/simulation, theory, ML/data science, literature-driven, and hybrid research;
- **tool-independent** — it can use capabilities supplied by the host environment without depending on one vendor or execution stack.

## Core Components

- `SKILL.md` — canonical adaptive operating specification
- `QUICK_START.md` — researcher-facing zero-config entry
- `templates/research_state.md` — current human-readable scientific state
- `templates/provenance_manifest.md` — historical provenance and reproducibility pattern
- `templates/mission.md` — bounded execution mission
- `templates/acceptance.md` — technical/result acceptance structure
- `templates/decision_log.md` — important scientific decisions
- `agents/task_executor.md` — domain-neutral executor abstraction
- `references/reproducibility.md` — cross-domain reproducibility guidance
- `examples/` — synthetic cross-domain walkthroughs

## Release Principle

> **Automate the complexity, preserve the scientific transparency and history.**

Use available execution capabilities to reduce unnecessary handoff friction, but never hide what actually happened, weaken evidence standards, or remove human control over consequential scientific actions.
