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

`SKILL.md`, `README.md`, and `QUICK_START.md` all specify a zero-config, natural-language-first entry model.

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

An important analysis, computation, experiment, or dataset contributes to a scientific decision.

**Expected behavior:**

- important inputs, method/version information, parameters, outputs, and linked scientific artifacts can be traced later;
- provenance is proportional to scientific value and reproducibility risk rather than recorded for every trivial edit.

**Repository check:**

`templates/provenance_manifest.md` provides append-oriented provenance entries with stable IDs, inputs, execution metadata, outputs, linked missions/reviews/decisions, status, and reproduction notes.

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

## Test 5 — Release hygiene and portability

**Checks performed:**

- searched the repository for obvious unfinished-release markers such as `TODO`, `FIXME`, `TBA`, and `placeholder`;
- searched for common credential terms such as `password`, `secret`, `api_key`, `token`, and `sk-`;
- searched for hard-coded product/model names used in prior development discussions.

No matching repository results were returned by these sweeps.

The reusable example remains synthetic and domain-neutral.

**Result:** PASS

## End-to-End Usability Check

The updated `examples/generic_research_project.md` now demonstrates the intended first-use flow:

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

This review does not prove that every model or agent implementation will follow the skill perfectly at runtime. A future behavioral evaluation suite could compare different models, tool environments, or prompting contexts if real usage shows that such testing is valuable.

That limitation is not considered a v1.0 release blocker because the current release is a tool-independent operating specification rather than a packaged orchestration runtime.

## Overall Decision

**PASS — no specification-level release blocker identified.**

Recommended action: freeze the v1.0 architecture and release. Future changes should be driven by observed use, not pre-emptive feature accumulation.
