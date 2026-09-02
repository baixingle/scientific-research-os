# Installation and Usage

## Installation

Scientific Research OS is repository-based and tool-independent. The goal of installation is simply to make `SKILL.md` and its referenced repository resources available to the AI environment you use.

Use the lightest installation path your environment supports:

### 1. Native skill / repository import

If your AI environment supports reusable skills, repository instructions, or project-level knowledge, add or import this repository using that environment's normal mechanism.

`SKILL.md` is the canonical entry point. The AI should load other files only when they are relevant to the current task.

### 2. Repository-aware agent

If the AI can read a local or remote project repository, clone or attach `scientific-research-os` and instruct the agent to use `SKILL.md` as the operating specification for the research project.

There is no requirement to copy every template into the user's research directory. Persistent project artifacts such as `RESEARCH_STATE.md`, `PROVENANCE.md`, missions, reviews, and decisions should be generated only when useful.

### 3. Environment without skill installation

If the environment cannot install reusable skills, provide `SKILL.md` as persistent project instructions or context and make the referenced repository files accessible when possible.

The framework still works as a scientific operating specification; the user should not have to manually reproduce the internal agent architecture.

Product-specific installation steps can change over time. Prefer the host environment's current supported method for adding repository instructions or skills rather than hard-coding one platform-specific procedure into the scientific core.

## First use

Once the skill is available, there should be no additional framework-specific setup required for ordinary use.

Start with the scientific problem in natural language, for example:

> I observed X, I suspect Y may be involved, but I am not sure what would distinguish Y from the alternatives. What should I do next?

The researcher should not have to choose roles, select a workflow, copy templates, or configure a model-routing table before the first useful result.

## Zero-config default

Do not require the user to:

- choose agent roles before starting;
- copy templates into a project directory;
- select a workflow mode;
- configure a model-routing table;
- understand the repository structure;
- manually maintain every internal artifact.

Those mechanisms exist to help the system reason and operate reliably, not to create setup work for the researcher.

## Transparent and traceable project state

Zero-config does not mean invisible operation.

When a persistent project workspace is available and the work has enough continuity to justify tracking, the AI should maintain a concise `RESEARCH_STATE.md` automatically using `templates/research_state.md`.

Important historical work that would be difficult to reproduce or audit if lost should also be linked through `PROVENANCE.md` or an equivalent project-native provenance record.

The researcher should be able to see:

- the current scientific question and uncertainty;
- established evidence versus interpretation;
- competing explanations and claim boundary;
- active work and the next decision;
- where important missions, reviews, decisions, data, methods, and provenance records are stored.

The AI should tell the researcher when it creates or materially updates these persistent artifacts.

The researcher should not be required to edit them manually. They exist so the work is inspectable, resumable, auditable, reproducible, and easier to hand off.

A persistent project may look like:

```text
project/
├── RESEARCH_STATE.md
├── PROVENANCE.md
├── missions/
├── reviews/
├── decisions/
└── ...existing data, code, experiments, notes, and results...
```

This is a suggested pattern, not a required directory schema. Preserve existing project organization when possible.

## Adaptive use

Use only as much structure as the problem needs.

For a simple scientific question, reason directly. For an ambiguous result, make evidence and alternatives explicit. For a costly or multi-step experimental, computational, analytical, or theoretical task, generate a mission and acceptance criteria when useful. For important conclusions, use independent review. For long-lived projects, maintain current state, history, decisions, and provenance in proportion to their scientific value.

The user does not need to select these modes in advance.

## Tool and executor independence

The execution layer may use researchers, technicians, collaborators, laboratory instruments, robotic or automation systems, coding agents, local models, API models, scripts, workflows, or combinations of them.

Specific products are implementation choices rather than part of the scientific method.

If automatic model or tool routing is unavailable, the current agent should still apply the framework without asking the user to reproduce the architecture manually.

## Optional configuration

Configuration is appropriate only when the researcher wants to override a sensible default, for example:

- cost or compute limits;
- privacy or local-only requirements;
- preferred tools, facilities, or models;
- required human approval before expensive, irreversible, safety-sensitive, or regulated actions;
- project-specific storage or collaboration conventions.

Defaults should make the system useful before any of these options are specified.

## Team adoption

Teams may choose to persist missions, reviews, decision logs, provenance, or shared project memory in version-controlled or otherwise controlled storage. `RESEARCH_STATE.md` can serve as the shared entry point that tells collaborators where the project currently stands before they inspect deeper artifacts.

## Design philosophy

> **Automate the complexity, preserve the scientific transparency and history.**

Scientific Research OS should evolve through demonstrated research value and practical usage, not through feature or configuration accumulation.
