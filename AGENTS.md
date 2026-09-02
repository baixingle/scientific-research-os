# AGENTS.md

## Purpose

This repository defines a general framework for human-AI collaborative scientific research.

AI agents modifying or using this repository should preserve scientific rigor while keeping the researcher-facing experience lightweight, inspectable, traceable, and reproducible.

## User Experience Contract

Scientific Research OS is **zero-config by default, not black-box by default**.

A researcher should be able to begin with an ordinary scientific question. Do not require them to learn the architecture, choose agent roles, copy templates, select workflow modes, or configure model routing before useful work can begin.

At the same time, the researcher should be able to understand what scientific state the system is maintaining, what persistent artifacts have been created, and where the historical chain behind important results can be inspected.

Use internal structure only when it improves the quality or reliability of the scientific work. Prefer the least amount of visible process that preserves rigor and trust.

Do not ask the user for a choice that can be inferred safely. Ask when the missing choice materially affects scientific interpretation, resource cost, access, confidentiality, or an irreversible action.

Templates, checklists, workflows, roles, state views, provenance records, and research-memory artifacts are implementation resources. Generate or update them automatically when useful; do not turn them into mandatory forms for the researcher.

## Research-State Transparency

When a persistent project workspace is available and the project has enough continuity to justify tracking, maintain a concise human-readable `RESEARCH_STATE.md` based on `templates/research_state.md`.

The state view should show the current question, evidence, interpretation, competing explanations, open uncertainties, claim boundary, active work, next decision, and links to relevant project artifacts.

Keep it current rather than exhaustive. It is a view of the present scientific state, not the canonical historical record.

## Historical Integrity and Provenance

For important analyses, experiments, simulations, datasets, or decisions, preserve enough provenance to reconstruct what happened and reproduce or audit the result later. Use `templates/provenance_manifest.md` or an equivalent project-native mechanism when useful.

Historical scientific records should be append-oriented by default.

Do not silently rewrite or delete an earlier result, mission, review, decision, or provenance record merely because a later interpretation changes. Preserve the earlier record and add a correction, superseding result, or new decision that explicitly links the change.

Prefer reproducible identifiers when appropriate, such as:

- code commit SHA or version;
- dataset version or file hash;
- parameter/configuration file;
- software/environment version or lockfile;
- random seed;
- sample, instrument, or run ID;
- output path plus checksum/version;
- linked mission, review, and decision IDs.

Do not generate heavy metadata for every trivial edit. Preserve provenance in proportion to scientific value and the cost of losing traceability.

When creating or materially updating a research-state file, provenance record, mission, review, or important decision record, tell the researcher what changed and where it is stored. Do not make them discover new project structure accidentally.

Do not expose hidden chain-of-thought, internal scratch reasoning, or every implementation artifact in the name of transparency. Scientific transparency means exposing state, evidence boundaries, historical artifacts, decisions, and reproducibility information—not private reasoning traces.

## Modification Principles

### Preserve evidence boundaries

Do not introduce language that upgrades observation into mechanism, correlation into causation, or a single example into a general principle.

### Keep the framework tool-independent

Do not hard-code specific AI products into the core framework. Use generic role abstractions such as Strategic Agent, Planning Agent, Task Executor Agent, and Reviewer Agent. Specific tools may be documented as optional examples only.

### Protect scientific reasoning

New workflows or rules should answer a real need: what uncertainty is reduced, what error is prevented, what evidence becomes clearer, what provenance is preserved, or what recurring burden is removed?

If a new rule adds user friction without a clear scientific or operational benefit, do not add it.

### Avoid project-specific contamination

Do not add unpublished research data, private datasets, confidential project information, or identifiable research details to the reusable core. Examples must remain generic unless explicitly approved.

## File Organization

- `agents/`: role definitions and interaction protocols
- `workflows/`: optional procedures for recurring scientific situations
- `templates/`: internal reusable artifacts, including research-state and provenance templates
- `references/`: conceptual principles
- `checklists/`: quality-control aids
- `docs/`: user and implementation guidance

The existence of a file does not mean it must be used in every project.

## Review Requirement

Before adding a new concept, ask:

1. Does it materially improve scientific judgment, reproducibility, reliability, traceability, or project transparency?
2. Does it prevent a recurring failure mode or remove recurring effort?
3. Can the same value be achieved with less visible process?
4. Does it preserve user autonomy and scientific creativity?

If not, do not add it.

## Meta-principle

> **Automate the complexity, preserve the scientific transparency and history.**

Structure should reduce avoidable error without constraining scientific creativity.
