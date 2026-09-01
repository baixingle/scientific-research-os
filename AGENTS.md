# AGENTS.md

## Purpose

This repository defines a general framework for human-AI collaborative scientific research.

AI agents modifying this repository must preserve the separation between:

1. Scientific strategy
2. Task execution
3. Evidence review
4. Research memory

## Modification Principles

### 1. Preserve evidence boundaries

Do not introduce language that upgrades:

- observation into mechanism;
- correlation into causation;
- a single example into a general principle.

### 2. Keep the framework tool-independent

Do not hard-code specific AI products.

Use generic terms:

- Strategic Agent
- Planning Agent
- Task Executor Agent
- Reviewer Agent

Specific tools may be documented as examples only.

### 3. Protect scientific reasoning

New workflows should answer:

- What uncertainty is reduced?
- What hypothesis is tested?
- What evidence is required?
- What decision follows?

### 4. Avoid project-specific contamination

Do not add unpublished research data, private datasets, or confidential project information.

Examples must remain generic unless explicitly approved.

## File Organization

- `agents/`: agent roles and interaction protocols
- `workflows/`: repeatable scientific procedures
- `templates/`: reusable artifacts
- `references/`: conceptual principles
- `checklists/`: quality control

## Review Requirement

Before adding a new concept, evaluate:

1. Does it improve scientific reasoning?
2. Does it improve reproducibility?
3. Does it reduce ambiguity?
4. Does it preserve claim boundaries?

If not, do not add it.
