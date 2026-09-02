# v1.0 Release Smoke Test

## Scope

This is a lightweight pre-release smoke test of the v1.0 specification and repository content.

It is intentionally **not** a full behavioral benchmark across multiple models or tools. The goal is to catch obvious release-blocking problems without turning release preparation into another large framework project.

## Test 1 — New user can start without configuration

**Scenario:**

A new researcher begins with an ordinary scientific message such as:

> I observe X, I suspect Y, and I want to know what to test next.

**Expected behavior:**

- no requirement to select Strategist / Planner / Reviewer roles;
- no requirement to copy or fill templates before useful reasoning begins;
- system infers the minimum useful scientific structure;
- only scientifically material missing information is requested.

**Repository check:**

`SKILL.md`, `README.md`, and `QUICK_START.md` specify a zero-config, natural-language-first entry model.

**Result:** PASS

## Test 2 — Zero-config does not become black-box operation

**Scenario:**

A conversation becomes a persistent research project.

**Expected behavior:**

- the researcher can inspect the current scientific question, evidence, interpretation, alternatives, uncertainty, claim boundary, active work, and next decision;
- the system tells the researcher when persistent research artifacts are created or materially updated;
- the researcher does not have to maintain those artifacts manually.

**Repository check:**

`templates/research_state.md` defines an AI-maintained `RESEARCH_STATE.md` view and the core docs require persistent scientific structure to remain discoverable.

**Result:** PASS

## Test 3 — Important research history remains traceable

**Scenario:**

An important analysis, computation, experiment, derivation, or dataset contributes to a scientific decision.

**Expected behavior:**

- important inputs or materials, method/version information, critical conditions, outputs, and linked scientific artifacts can be traced later;
- provenance is proportional to scientific value and reproducibility risk rather than recorded for every trivial edit.

**Repository check:**

`templates/provenance_manifest.md` provides append-oriented provenance entries with stable IDs, inputs/materials, execution metadata, outputs, linked missions/reviews/decisions, status, and reproduction notes.

**Result:** PASS

## Test 4 — New evidence can overturn old interpretation without erasing history

**Scenario:**

An earlier result was validly obtained, but later evidence changes its interpretation.

**Expected behavior:**

- the old result remains in the historical record;
- a later record explicitly corrects or supersedes it;
- `RESEARCH_STATE.md` reflects the new current interpretation;
- provenance preserves the earlier path.

**Repository check:**

The provenance template explicitly requires append-oriented history and `supersedes / superseded by` links. The five-minute walkthrough demonstrates this behavior using synthetic records P-0001 and P-0002.

**Result:** PASS

## Test 5 — Wet-lab / experimental research does not inherit computational assumptions

**Scenario:**

A wet-lab researcher begins with:

> A treatment group shows a reproducible increase in phenotype X. I suspect pathway Y is involved. What should I test next?

**Expected behavior:**

- system frames the uncertainty and plausible competing explanations before recommending a large experiment series;
- proposed experiments include scientifically relevant controls and, when appropriate, replication, randomization, blinding, batch effects, or alternative explanations;
- a bounded experimental mission can refer naturally to samples/specimens, reagents/materials, protocol version, critical timing or environmental conditions, instrument settings, and protocol deviations;
- provenance can preserve sample-to-measurement mapping, reagent lot/batch, protocol/instrument metadata, and raw-data location when those details matter;
- the system does **not** require irrelevant computational metadata such as code commits, random seeds, or software environments unless computation is actually part of the work;
- the Task Executor may be a researcher, technician, collaborator, instrument, laboratory automation system, or human-AI combination rather than an AI model.

**Repository check:**

- `SKILL.md` explicitly defines domain-adaptive reproducibility and experimental/wet-lab support;
- `templates/mission.md` uses `Inputs and Materials` and provides wet-lab-specific reproducibility examples only when relevant;
- `references/reproducibility.md` separates experimental, computational/ML, and theoretical metadata;
- `agents/task_executor.md` defines the executor as a general bounded execution entity rather than an AI-only model;
- `references/model_selection.md` now applies only when a role or subtask is actually assigned to an AI model.

**Result:** PASS

## Test 6 — Release hygiene and portability

**Checks performed:**

- searched the repository for obvious unfinished-release markers such as `TODO`, `FIXME`, `TBA`, and `placeholder`;
- searched for common credential terms such as `password`, `secret`, `api_key`, `token`, and `sk-`;
- searched for hard-coded product/model names used in prior development discussions.

No matching repository results were returned by these sweeps at the time of the release review.

The reusable example remains synthetic and domain-neutral.

**Result:** PASS

## Installation Entry Check

A new user should be able to determine how to make the skill available without learning the internal architecture first.

**Repository check:**

`docs/installation_and_usage.md` now documents three lightweight entry paths:

1. native skill/repository import when supported;
2. repository-aware agents that can read `SKILL.md` and referenced files;
3. environments without skill installation, where `SKILL.md` can be supplied as persistent project instructions/context.

The installation guidance deliberately avoids hard-coding one product-specific procedure that may become stale.

**Result:** PASS

## End-to-End Usability Check

The updated `examples/generic_research_project.md` demonstrates the intended first-use flow:

```text
ordinary scientific question
        -> scientific framing
        -> optional RESEARCH_STATE / PROVENANCE creation
        -> bounded mission when execution is justified
        -> result review
        -> state update
        -> later superseding evidence without rewriting history
```

The example requires no framework-specific setup from the researcher.

**Result:** PASS

## Known Limitation of This Smoke Test

This review does not prove that every model or agent implementation will follow the skill perfectly at runtime. A future behavioral evaluation suite could compare different models, research domains, tool environments, or prompting contexts if real usage shows that such testing is valuable.

That limitation is not considered a v1.0 release blocker because the current release is a tool-independent operating specification rather than a packaged orchestration runtime.

## Overall Decision

**PASS — no specification-level release blocker identified.**

Recommended action: freeze the v1.0 architecture and release. Future changes should be driven by observed use, not pre-emptive feature accumulation.
