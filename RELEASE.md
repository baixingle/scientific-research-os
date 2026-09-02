# Scientific Research OS v1.0.0

## Overview

Scientific Research OS v1.0 is a human-guided, tool-independent framework for improving scientific reasoning and research execution without forcing researchers through a rigid workflow.

Its central design goal is simple:

> **High scientific value with low interaction friction.**

A researcher can begin with an ordinary scientific question. The framework infers the minimum useful structure, keeps important scientific state inspectable, and preserves enough history for later audit and reproduction.

The scientific-method layer is domain-neutral. v1.0 is intended to support experimental and wet-lab research, computation and simulation, theory, machine learning and data science, literature-driven work, and hybrid projects. Domain-specific execution and reproducibility details appear only when they matter.

## What Makes v1.0 Different

### Zero-config by default

Researchers do not need to configure agent roles, choose workflow modes, fill templates, or build a model-routing table before useful work begins.

Start with the science. Additional structure appears only when it materially improves rigor, reliability, traceability, or handoff.

### Transparent, not black-box

For persistent projects, the system can maintain a concise `RESEARCH_STATE.md` showing the current question, evidence, interpretation, competing explanations, open uncertainties, claim boundary, active work, and next decision.

The researcher does not fill this file manually. It is an AI-maintained, human-readable projection of the project state.

### Traceable research history

Important work should remain auditable and reproducible as the project evolves.

A project can maintain append-oriented provenance through `PROVENANCE.md`, linking important inputs or materials, methods or protocols, code/environment versions when relevant, critical conditions, outputs, missions, reviews, decisions, and superseding results.

Old scientific history should not be silently rewritten to match a newer interpretation.

### Evidence-controlled reasoning

The framework distinguishes:

```text
Level 1  Observation / association
Level 2  Physical or temporal localization
Level 3  Mechanistic / causal support
Level 4  Transferable general principle
```

The core rule is:

> **Claim strength must not exceed evidence strength.**

### Decision-oriented research

The framework prioritizes information gain rather than research activity.

Before recommending substantial work, ask what uncertainty it reduces, what alternatives it distinguishes, and how possible outcomes would change the next decision.

### Adaptive execution

When a task is sufficiently clear, it can be converted into a bounded mission with frozen objectives, relevant inputs or materials, required outputs, acceptance criteria, stop conditions, and domain-relevant reproducibility requirements.

The Task Executor is not assumed to be an AI model. It may be a researcher, technician, collaborator, laboratory instrument, robotic or automation system, script, workflow, coding agent, AI model, or human-AI combination.

When AI is used, stronger reasoning capacity can be reserved for ambiguity, scientific judgment, interpretation, and review, while efficient capable models can handle clear operational subtasks.

### Domain-adaptive reproducibility

Reproducibility uses a common scientific principle but not a universal metadata form.

For experimental work, important records may include samples/specimens, reagent lots, protocol versions, controls, replicates, critical conditions, instrument settings, experimental batches, deviations, and raw-data mapping.

For computational, simulation, ML, or data-science work, relevant records may include datasets or structures, code/version, environment, parameters, seeds, model/data-split definitions, logs, checkpoints, and raw outputs.

For theoretical work, relevant records may include assumptions, definitions, boundary conditions, derivation versions, approximations, solver settings, and external reference values.

Only information that materially supports interpretation, audit, or reasonable reproduction should be required.

## Core Components

- `SKILL.md` — adaptive operating rules
- `QUICK_START.md` — researcher-facing entry point
- `templates/research_state.md` — current human-readable scientific state
- `templates/provenance_manifest.md` — historical provenance and reproducibility pattern
- `templates/mission.md` — bounded execution handoff
- `templates/acceptance.md` — result acceptance structure
- `templates/decision_log.md` — important scientific decisions
- `workflows/research_memory.md` — durable project continuity
- `agents/` — optional role abstractions for strategy, planning, execution, skepticism, and review

The existence of these resources does not mean every project should use all of them.

## Tool and Executor Independence

Scientific Research OS is not tied to a specific AI product, coding agent, model provider, orchestration system, laboratory platform, or execution environment.

Roles are functional abstractions. A capable human, instrument, automation system, model, coding agent, script, workflow engine, or combination can fill an execution role if it satisfies the scientific and reproducibility requirements.

## Privacy

The reusable core contains generic or synthetic material only. Private data, unpublished project details, confidential scientific strategy, credentials, and identifiable research examples should not be placed in the reusable/public framework unless explicitly authorized.

## What v1.0 Is Not

Scientific Research OS is not:

- an autonomous scientist;
- an automatic paper factory;
- a mandatory project-management system;
- a requirement to use multiple agents;
- a requirement to formalize every scientific conversation;
- a replacement for researcher judgment.

The human researcher remains the final scientific decision maker.

## Release Principle

> **Automate the complexity, preserve the scientific transparency and history.**

Use the minimum structure necessary to improve scientific judgment, reproducibility, and continuity.
