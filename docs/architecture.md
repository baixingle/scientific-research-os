# Scientific Research OS Architecture

## Overview

Scientific Research OS is a human-guided scientific reasoning and execution framework.

Its internal architecture can separate scientific judgment from task execution, while researcher-facing state and provenance layers keep the project understandable, traceable, and reproducible without requiring the researcher to operate the internal workflow manually.

```text
                  Human Scientist
                        ^
                        |
                Research State View
                        ^
                        |
                Scientific Strategy
                        |
                        v
                 Planning as needed
                        |
                        v
               Bounded Task Execution
                        |
                        v
                Independent Review
                        |
                        v
          Decision Log + Research Memory
                        |
                        v
             Provenance / History Layer
                        |
                        +------> Research State View
```

Named agent roles are optional implementation abstractions. A project does not need a separate software agent for every box.

## Two Views of a Persistent Project

A durable research workspace needs both a **current view** and a **historical view**.

### Current view

`RESEARCH_STATE.md` is the preferred human-readable projection of the current project state. It answers what the project currently believes, what remains uncertain, what work is active, and what the next decision is.

### Historical view

`PROVENANCE.md` plus missions, reviews, decision records, code/data versions, run identifiers, and immutable artifacts preserve how the project reached the current state and what is needed to reproduce or audit important results.

The current state may be updated. The historical record should be append-oriented by default.

```text
Current state          Historical chain
-------------          ----------------
RESEARCH_STATE.md ---> provenance entry
                    -> mission / protocol
                    -> inputs / versions / hashes
                    -> execution run / environment
                    -> outputs
                    -> review
                    -> decision
```

A scientifically transparent project must be able to move in both directions: from the current conclusion back to the supporting historical chain, and from an old result forward to the later review or decision that accepted, rejected, or superseded it.

## Research State View

`RESEARCH_STATE.md` is generated and maintained by the AI using `templates/research_state.md`. It is not a form the researcher must complete.

The state view should answer, at a glance:

- What question are we trying to resolve now?
- What is directly established?
- What is our current interpretation?
- Which alternatives remain plausible?
- What is still uncertain?
- What can and cannot currently be claimed?
- What work is active?
- What is the next scientific decision?
- Where is the historical evidence, provenance, mission, review, and decision chain supporting this state?

The state view stays concise and current. It must not become a substitute for provenance.

## Provenance and Historical Integrity

For persistent research, preserve enough history to reproduce or audit important work. Use `templates/provenance_manifest.md` when a central provenance index is useful.

High-value provenance may include:

- timestamp or milestone;
- scientific purpose;
- input data/sample/structure/document identifiers;
- code commit or method version;
- software/environment versions;
- important parameters and random seeds;
- experimental conditions, sample IDs, instrument/run IDs when relevant;
- outputs and stable paths;
- hashes, checksums, version IDs, or persistent identifiers when useful;
- linked mission, review, decision, and interpretation records;
- supersession/correction relationships.

Do not overwrite historical records merely to make them agree with the latest interpretation. Record corrections and superseding results explicitly.

This is a reproducibility layer, not a requirement to generate heavy metadata for every trivial edit. Preserve provenance in proportion to scientific value and the cost of losing traceability.

## Core Design Rules

### Zero-config does not mean opaque

The researcher should not have to configure roles, workflows, or templates before useful work begins.

However, when the system creates persistent scientific structure, it should make that structure discoverable and briefly tell the researcher what was created or updated.

### Strategy is separated from execution when useful

The strategic layer defines scientific questions, hypotheses, priorities, and evidence requirements.

The execution layer receives only the information needed to complete a bounded task reliably. This separation is used when it reduces bias, cost, or ambiguity; it is not a mandatory ceremony for every interaction.

### Evidence before claims

Every conclusion should be traceable through:

Observation -> Interpretation -> Mechanism -> Generalization

The project state should preserve the boundary between those levels rather than presenting inference as established evidence.

### Memory is not the same as provenance

Research memory preserves scientific meaning: decisions, evidence, rejected alternatives, confidence, and future triggers.

Provenance preserves reproducibility and traceability: which inputs, versions, methods, runs, outputs, reviews, and decisions formed the historical chain.

```text
RESEARCH_STATE.md  = current readable scientific state
PROVENANCE.md      = traceable reproducibility/history index
Decision logs      = important decision records
Research memory    = scientific continuity and rationale
Raw conversation   = not the canonical scientific record
```

## Agent and Tool Independence

The framework does not depend on any specific AI product.

Any capable model, coding agent, workflow system, script, or human collaborator can serve an execution role if it follows the task requirements and preserves reproducibility.

## Architecture Principle

> **Automate the complexity, preserve the scientific transparency and history.**

The researcher should experience a simple interaction while retaining a clear, inspectable current state and a durable historical chain behind important results and decisions.
