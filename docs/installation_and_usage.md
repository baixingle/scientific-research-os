# Installation and Usage

## Zero-config default

Scientific Research OS is a workflow framework, not a specific model or application. Once the skill is available to an AI agent, there should be no additional framework-specific configuration required for ordinary use.

The researcher should be able to start by describing a scientific problem in natural language.

Do not require the user to:

- choose agent roles before starting;
- copy templates into a project directory;
- select a workflow mode;
- configure a model-routing table;
- understand the repository structure;
- manually maintain every internal artifact.

Those mechanisms exist to help the system reason and operate reliably, not to create setup work for the researcher.

## Transparent project state

Zero-config does not mean invisible operation.

When a persistent project workspace is available and the work has enough continuity to justify tracking, the AI should maintain a concise `RESEARCH_STATE.md` automatically using `templates/research_state.md`.

The file should give the researcher a readable view of the current question, evidence, interpretation, competing explanations, open uncertainties, claim boundary, active work, next decision, and links to important project artifacts.

The AI should tell the researcher when it creates or materially updates this state file, a mission, a review, or an important decision record.

The researcher should not be required to edit these files manually. They exist so the work is inspectable, resumable, auditable, and easier to hand off.

A lightweight persistent project may look like:

```text
project/
├── RESEARCH_STATE.md
├── missions/
├── reviews/
├── decisions/
└── ...existing project files...
```

This is a suggested pattern, not a required directory schema. Preserve existing project organization when possible.

## Adaptive use

Use only as much structure as the problem needs.

For a simple scientific question, reason directly. For an ambiguous result, make evidence and alternatives explicit. For a costly or multi-step execution task, generate a mission and acceptance criteria. For important conclusions, use independent review. For long-lived projects, maintain state, decisions, and research memory.

The user does not need to select these modes in advance.

## Tool independence

The execution layer may use coding agents, local models, API models, scripts, workflow systems, human collaborators, or other capable tools. Specific products are implementation choices rather than part of the scientific method.

If automatic model or tool routing is unavailable, the current agent should still apply the framework without asking the user to reproduce the architecture manually.

## Optional configuration

Configuration is appropriate only when the researcher wants to override a sensible default, for example:

- cost or compute limits;
- local-only or privacy-sensitive execution;
- a preferred model or tool;
- required human approval before expensive or irreversible actions;
- project-specific storage or collaboration conventions.

Defaults should make the system useful before any of these options are specified.

## Team adoption

Teams may choose to persist missions, reviews, decision logs, provenance, or shared project memory in version-controlled storage. `RESEARCH_STATE.md` can serve as the shared entry point that tells collaborators where the project currently stands before they inspect deeper artifacts.

## Design philosophy

> **Automate the complexity, preserve the scientific transparency.**

Scientific Research OS should evolve through demonstrated research value and practical usage, not through feature or configuration accumulation.
