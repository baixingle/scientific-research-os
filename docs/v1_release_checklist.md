# v1.0 Release Checklist

## Architecture

- [x] Strategic reasoning layer
- [x] Skeptic/challenge role
- [x] Planning layer
- [x] Tool-independent Task Executor abstraction
- [x] Independent Reviewer layer
- [x] Decision Log and Scientific Memory concept
- [x] Research State View for researcher-facing transparency
- [x] Provenance layer for important historical and reproducibility records
- [x] Duplicate agent-role definitions removed
- [x] Tool-specific role names removed from the core architecture

## Scientific rigor

- [x] Evidence hierarchy
- [x] Claim-boundary control
- [x] Mechanism-validation workflow
- [x] Alternative-explanation review
- [x] Discovery/validation separation
- [x] Acceptance criteria defined before flexible or expensive execution
- [x] Stop conditions and failure interpretation
- [x] Information-gain/resource-allocation rule
- [x] Historical scientific records are append-oriented by default
- [x] Superseding results correct history without silently rewriting it

## Reproducibility and traceability

- [x] `RESEARCH_STATE.md` pattern distinguishes current state from history
- [x] `PROVENANCE.md` pattern records important inputs, methods, versions, parameters, outputs, and linked scientific artifacts
- [x] Code/data/environment identifiers can be preserved when scientifically useful
- [x] Important missions, reviews, and decisions can be linked into the provenance chain
- [x] Provenance burden is proportional to scientific value and reproducibility risk
- [x] Raw conversation is not treated as the canonical scientific record

## Usability

- [x] Stable `SKILL.md` entry point
- [x] Zero-config, natural-language-first default
- [x] No requirement to select agent roles or workflow modes before starting
- [x] Templates and checklists are system resources rather than mandatory user forms
- [x] System should not ask for choices that can be inferred safely
- [x] Persistent project artifacts are surfaced to the researcher when created or materially updated
- [x] Quick start guide
- [x] Five-minute synthetic end-to-end example
- [x] Installation and architecture documentation

## Privacy and portability

- [x] Generic framework contains no unpublished project-specific example
- [x] Public/reusable examples are required to remain generic or synthetic
- [x] Core roles are independent of specific AI products
- [x] Efficient execution models can be substituted without changing scientific strategy
- [x] No credentials, API keys, passwords, or product-specific dependencies are required by the core

## Release smoke test

- [x] New user can begin from an ordinary scientific question without framework configuration
- [x] Persistent project state can be made visible through `RESEARCH_STATE.md`
- [x] Important historical work can be preserved through append-oriented provenance
- [x] Later corrections can supersede earlier records without erasing them
- [x] Repository sweep found no obvious release placeholders, credential terms, or hard-coded model/product names in the core
- [x] Static/manual release smoke test recorded in `reviews/v1_release_smoke_test.md`

## v1.0 Freeze Decision

**PASS — the v1.0 core is release-ready at the specification level.**

The architecture should now remain stable. Additional work should be driven by observed usage problems rather than feature accumulation.

## Post-v1 possibilities

Possible extensions, only if real use demonstrates their value:

- automated provenance capture from execution environments;
- machine-readable mission or provenance schemas;
- domain-specific research modules;
- experiment/computation scheduling;
- structured handoff formats between agents;
- behavioral evaluation suites across different models;
- team collaboration protocols;
- connectors or orchestration integrations.
