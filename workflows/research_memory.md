# Research Memory Workflow

## Purpose

Research memory should preserve important decisions, reasoning, evidence, and historical context rather than raw conversation history.

It complements the researcher-facing `RESEARCH_STATE.md` and the reproducibility-oriented `PROVENANCE.md` rather than replacing either one.

```text
RESEARCH_STATE.md  -> concise current scientific state
PROVENANCE.md      -> traceable history of important work, inputs, outputs, versions, and runs
Decision records   -> why important choices were made
Research memory    -> durable continuity across the project
```

The state view shows where the project is now. Provenance preserves what happened and how it can be traced or reproduced. Research memory preserves the scientific meaning of that history.

## What Belongs in Memory

Record information when losing it would cause repeated work, inconsistent interpretation, loss of scientific context, or inability to understand why the project changed direction.

For each important decision, preserve:

## Decision

What was decided?

## Evidence

What observations or analysis support it? Link the underlying provenance or evidence artifacts when available.

## Alternatives Considered

What other explanations or paths were evaluated?

## Rejected or Deprioritized Options

Why were alternatives not selected?

## Confidence Level

How strong is the current conclusion?

## Next Trigger

What future result would change this decision?

## Historical Integrity

Scientific history should be append-oriented by default.

Do not silently rewrite an earlier decision, result, mission, review, or provenance record because the interpretation later changed. Preserve the old record and create a new record that explains the correction, supersession, or changed conclusion.

This allows a future researcher or AI to reconstruct not only the latest answer, but the path by which the project arrived there.

## Relationship to the Research State View

After an important decision or accepted new result:

1. preserve the detailed decision or memory record when it has long-term value;
2. append/update the relevant provenance record when reproducibility or auditability matters;
3. update `RESEARCH_STATE.md` with only the consequences that matter to the current project state;
4. link from the state view to detailed historical records instead of copying their full contents.

Do not turn `RESEARCH_STATE.md` into an ever-growing chronology, and do not treat the mutable current-state view as the canonical history.

## Principle

> State shows where the project is. Provenance shows what happened. Memory preserves why it mattered.

A useful scientific record stores decisions, evidence, and reproducible history—not conversation transcripts.
