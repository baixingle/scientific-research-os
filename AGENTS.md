# AGENTS.md

## Purpose

This repository defines a general framework for human-AI collaborative scientific research.

AI agents modifying or using this repository should preserve scientific rigor while keeping the researcher-facing experience lightweight.

## User Experience Contract

Scientific Research OS is **zero-config by default**.

A researcher should be able to begin with an ordinary scientific question. Do not require them to learn the architecture, choose agent roles, copy templates, select workflow modes, or configure model routing before useful work can begin.

Use internal structure only when it improves the quality or reliability of the scientific work. Prefer the least amount of visible process that preserves rigor.

Do not ask the user for a choice that can be inferred safely. Ask when the missing choice materially affects scientific interpretation, resource cost, access, confidentiality, or an irreversible action.

Templates, checklists, workflows, roles, and research-memory artifacts are implementation resources. Generate or surface them automatically when useful; do not turn them into mandatory forms for the researcher.

## Modification Principles

### Preserve evidence boundaries

Do not introduce language that upgrades observation into mechanism, correlation into causation, or a single example into a general principle.

### Keep the framework tool-independent

Do not hard-code specific AI products into the core framework. Use generic role abstractions such as Strategic Agent, Planning Agent, Task Executor Agent, and Reviewer Agent. Specific tools may be documented as optional examples only.

### Protect scientific reasoning

New workflows or rules should answer a real need: what uncertainty is reduced, what error is prevented, what evidence becomes clearer, or what recurring burden is removed?

If a new rule adds user friction without a clear scientific or operational benefit, do not add it.

### Avoid project-specific contamination

Do not add unpublished research data, private datasets, confidential project information, or identifiable research details to the reusable core. Examples must remain generic unless explicitly approved.

## File Organization

- `agents/`: role definitions and interaction protocols
- `workflows/`: optional procedures for recurring scientific situations
- `templates/`: internal reusable artifacts
- `references/`: conceptual principles
- `checklists/`: quality-control aids
- `docs/`: user and implementation guidance

The existence of a file does not mean it must be used in every project.

## Review Requirement

Before adding a new concept, ask:

1. Does it materially improve scientific judgment, reproducibility, or reliability?
2. Does it prevent a recurring failure mode or remove recurring effort?
3. Can the same value be achieved with less visible process?
4. Does it preserve user autonomy and scientific creativity?

If not, do not add it.

## Meta-principle

> Structure should reduce avoidable error without constraining scientific creativity.
