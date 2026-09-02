# Research Provenance Manifest

> AI-maintained, researcher-readable provenance index for a persistent research project. This is not a lab notebook replacement and not a form the researcher must fill out.

## Purpose

Preserve enough historical information to answer:

- What was done?
- Why was it done?
- Which inputs, code, parameters, environment, samples, or instruments were used?
- What outputs were produced?
- Which review or decision accepted, rejected, or superseded the result?
- Can the result be reproduced or traced later?

`RESEARCH_STATE.md` shows where the project is now. `PROVENANCE.md` preserves how the project got there.

## Project

Project name or short identifier.

## Canonical Storage

Record the main locations for project data, code, results, missions, reviews, decisions, and external archives when relevant.

## Provenance Entries

Use stable IDs such as `P-0001`, `P-0002`, ... . Keep entries append-oriented: do not erase old scientific history merely because the interpretation later changes. If an entry is wrong or obsolete, create a new entry that explicitly supersedes or corrects it.

### P-XXXX — Short title

**Timestamp / milestone:**

**Purpose:**
What scientific question, uncertainty, mission, or decision motivated this work?

**Inputs:**
- data / sample / structure / document identifiers;
- source paths or persistent references;
- versions, hashes, checksums, or immutable IDs when useful.

**Method / execution:**
- method or protocol;
- code repository and commit/version;
- software/environment version;
- important parameters;
- random seed when relevant;
- instrument, experimental conditions, or operator metadata when relevant.

**Outputs:**
- result paths or persistent references;
- output hashes/checksums or version IDs when useful;
- figures, tables, datasets, logs, or derived artifacts.

**Linked scientific artifacts:**
- mission:
- review:
- decision:
- evidence / interpretation record:

**Outcome:**
What happened technically? Keep this separate from scientific interpretation.

**Status:**
`active` / `accepted` / `rejected` / `superseded` / `failed` / `archived`

**Supersedes / superseded by:**
Link related provenance IDs when the work replaces or corrects an earlier result.

**Reproduction notes:**
What would another researcher or future AI need to reproduce or audit this result?

---

## Minimum Provenance Rule

Do not create heavy metadata for every trivial edit. Preserve provenance when losing it would make an important result, decision, analysis, computation, experiment, or dataset difficult to reproduce or audit.

For large files, do not duplicate the data in this manifest. Record stable paths/references plus hashes, versions, or identifiers when appropriate.

## Maintenance Rules for AI Agents

- Treat historical scientific records as append-oriented by default.
- Never silently rewrite a past result to match a newer interpretation.
- Record corrections and superseding work explicitly.
- Link current state to historical evidence rather than copying full reports into `RESEARCH_STATE.md`.
- Prefer reproducible identifiers: commit SHA, dataset version, file hash, run ID, sample ID, environment lockfile, parameter file, or instrument/run record as appropriate.
- Keep provenance proportional to scientific value and reproducibility risk.
- Tell the researcher when a persistent provenance record is created or materially extended.
