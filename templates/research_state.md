# Research State View

> This is an AI-maintained, researcher-readable snapshot of the **current** scientific state. It is not a form the researcher must fill out and it is not the canonical historical record.

The state view must remain linked to the historical provenance needed to understand and reproduce how the project reached the current state.

```text
RESEARCH_STATE.md  -> current scientific state
PROVENANCE.md      -> traceable history of important work and artifacts
Decision records   -> why important choices were made
Missions / reviews -> what was requested and how it was accepted
Data / code / runs -> reproducible scientific evidence
```

## Project

Project name or short identifier.

## Last Updated

Date/time or project milestone.

## Current Scientific Question

What is the most important question the project is trying to resolve now?

## Current Understanding

### Established Evidence

What is directly supported by data, calculations, experiments, or trusted external evidence? Link the relevant historical artifacts or provenance entries when available.

### Current Interpretation

What is the best current interpretation of that evidence, and with what confidence?

## Competing Explanations

List only the alternatives that are still scientifically plausible and decision-relevant.

- H1:
- H2:
- H0 / other:

## Open Uncertainties

What remains unresolved? Prioritize the uncertainty that most affects the next scientific decision.

## Current Claim Boundary

What can be said now, and what should not yet be claimed?

## Active Work

What analysis, experiment, simulation, literature task, or delegated mission is currently active? Link the mission, run, or provenance entry if one exists.

## Next Decision

What is the next decision the researcher is trying to make?

What observation or result would change that decision?

## Important Decisions So Far

Summarize only decisions that still matter to the current project state. Link detailed decision records rather than rewriting their history.

## Deprioritized or Rejected Paths

Record only paths whose rejection matters for avoiding repeated work. Include the reason, the historical record, and what new evidence would justify revisiting them.

## Historical Trace

Provide concise links or IDs for the historical chain supporting the current state, for example:

- provenance manifest / relevant provenance IDs;
- key prior missions and execution runs;
- important reviews;
- important decision records;
- superseded results that are necessary to understand why the project changed direction.

Do not duplicate the full history here. Make the path to that history obvious.

## Project Artifacts

Keep a short navigational index to the most relevant current artifacts, for example:

- active mission(s)
- latest review(s)
- important decision log(s)
- key evidence/results
- provenance manifest

## Researcher Input Needed

List only decisions or missing information that genuinely require researcher judgment. If none, write `None`.

---

## Maintenance Rules for AI Agents

- Keep this file concise and current; prefer a one- to two-page snapshot over an exhaustive chronology.
- Update it after a major new result, accepted/rejected mission, important scientific decision, or meaningful change in the hypothesis space.
- Distinguish evidence from interpretation.
- Do not silently upgrade claims when updating the state.
- Never use this mutable state file as a substitute for historical provenance.
- When a current conclusion changes, preserve the older result/decision in the historical record and update this file to point to the relevant chain.
- Do not copy raw conversations, large logs, or full reports into this file; link them instead.
- Tell the researcher when this file or other persistent research artifacts are created or materially updated.
- The researcher should be able to understand both the current project state and where to inspect its history without learning the internal workflow architecture.
