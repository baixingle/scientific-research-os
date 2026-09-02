# Scientific Research OS Architecture

## Overview

Scientific Research OS is a human-guided scientific reasoning and execution framework.

Its internal architecture can separate scientific judgment from task execution, while a researcher-facing state layer keeps the project understandable without requiring the researcher to operate the internal workflow manually.

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
                        +------> Research State View
```

Named agent roles are optional implementation abstractions. A project does not need a separate software agent for every box.

## Research State View

`RESEARCH_STATE.md` is the preferred human-readable projection of the current project state when persistent project storage is available.

It is generated and maintained by the AI using `templates/research_state.md`. It is not a form the researcher must complete.

The state view should answer, at a glance:

- What question are we trying to resolve now?
- What is directly established?
- What is our current interpretation?
- Which alternatives remain plausible?
- What is still uncertain?
- What can and cannot currently be claimed?
- What work is active?
- What is the next scientific decision?
- Which artifacts contain the relevant evidence, missions, reviews, and decisions?

The state view stays concise and current. Historical reasoning belongs in decision logs and research memory rather than accumulating indefinitely in the state file.

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

### Memory stores decisions, not conversations

Research memory preserves:

- decisions;
- evidence;
- rejected alternatives;
- confidence;
- future triggers.

The state view and memory serve different purposes:

```text
RESEARCH_STATE.md  = current readable scientific state
Decision logs      = important decision records
Research memory    = longer-term continuity and history
Raw conversation   = not the canonical scientific record
```

## Agent and Tool Independence

The framework does not depend on any specific AI product.

Any capable model, coding agent, workflow system, script, or human collaborator can serve an execution role if it follows the task requirements and preserves reproducibility.

## Architecture Principle

> **Automate the complexity, preserve the scientific transparency.**

The researcher should experience a simple interaction while retaining a clear, inspectable view of the scientific state and the evidence behind project decisions.
