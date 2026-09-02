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

## Adaptive use

Use only as much structure as the problem needs.

For a simple scientific question, reason directly. For an ambiguous result, make evidence and alternatives explicit. For a costly or multi-step execution task, generate a mission and acceptance criteria. For important conclusions, use independent review. For long-lived projects, maintain decision memory.

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

Teams may choose to persist missions, reviews, decision logs, provenance, or shared project memory in version-controlled storage. This is an optional scaling layer, not a prerequisite for individual use.

## Design philosophy

> Complexity belongs inside the framework. The researcher-facing interaction should remain natural and lightweight.

Scientific Research OS should evolve through demonstrated research value and practical usage, not through feature or configuration accumulation.
