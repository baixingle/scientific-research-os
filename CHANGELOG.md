# Changelog

All notable changes to this project are documented here.

## v1.0.0

First stable core specification of Scientific Research OS.

### Architecture

- Finalized functional agent roles: Strategic Agent, Skeptic, Planning Agent, Task Executor Agent, and Reviewer Agent.
- Standardized the tool-independent orchestration protocol.
- Removed duplicate and product-specific agent definitions from the core architecture.
- Added explicit separation between strategy, planning, execution, review, and scientific memory when that separation improves reliability, cost, or bias control.
- Generalized the Task Executor from an AI execution model to any appropriate bounded executor, including researchers, technicians, collaborators, instruments, laboratory automation, robotic platforms, scripts, workflows, and human-AI combinations.
- Added a researcher-facing **Research State View** for the current scientific state.
- Added a separate **Provenance / History Layer** so the mutable current-state view never replaces the historical chain required for audit and reproduction.

### Scientific rigor

- Established the evidence hierarchy from observation/association to localization, mechanism, and generalization.
- Added claim-boundary, mechanism-validation, scientific-review, and analysis-quality controls.
- Formalized discovery-versus-validation separation and pre-frozen acceptance criteria for experiments and analyses where flexibility could create confirmation bias.
- Added protection against post-hoc criterion changes, circular reasoning, cherry-picking, and unnecessary claim escalation.
- Added historical-integrity rules: old results, reviews, decisions, and provenance records are preserved when later work corrects or supersedes them.

### Research operations

- Added Research Brief, Scientific Framework, Project Roadmap, Mission, Acceptance, Interpretation, Decision Log, Paper Story, Research State, and Provenance Manifest artifacts as optional internal/system resources.
- Added an AI-maintained `RESEARCH_STATE.md` pattern for keeping the current question, evidence, interpretation, alternatives, uncertainties, active work, and next decision readable and inspectable.
- Added an AI-maintained `PROVENANCE.md` pattern for tracing important inputs/materials, method/protocol/code versions, critical conditions, executions/runs/experiments, outputs, reviews, decisions, and supersession relationships.
- Made mission and reproducibility guidance explicitly domain-adaptive across wet-lab/experimental, computational/simulation, ML/data science, theoretical/analytical, and hybrid research without requiring every domain's metadata in every project.
- Clarified the distinction between current state, provenance, decision records, and long-term scientific memory.
- Added decision-oriented project lifecycle and research-memory workflows for projects that benefit from persistent structure.
- Added cost-aware model-selection and resource-allocation principles.
- Added literature-to-strategy, unexpected-result, and mechanism-claim workflows.

### Usability and governance

- Adopted a **zero-config, natural-language-first** default: researchers can begin with an ordinary scientific question without selecting roles, workflow modes, templates, or model routing.
- Changed `SKILL.md` from a mandatory staged workflow into an adaptive framework that uses the minimum structure required by the problem.
- Reframed templates, checklists, workflows, and agent-role files as internal/optional implementation resources rather than forms every researcher must complete.
- Added an agent UX contract: do not ask for choices that can be inferred safely; surface structure only when it materially improves scientific value or reliability.
- Added a transparency contract: zero-config must not become black-box operation; researchers should be told when persistent state, provenance, mission, review, or decision artifacts are created or materially updated.
- Added the principle: **current state may change; important scientific history should remain traceable**.
- Simplified researcher-facing guidance around the principle: **automate the complexity, preserve the scientific transparency and history**.
- Preserved privacy rules preventing unpublished project data from entering generic/public framework examples.

## v0.8

Added usability layer:

- Quick start guide
- Installation and usage documentation
- Generic research workflow example

## v0.7

Added scientific project entry and review systems:

- Research brief template
- Scientific review checklist
- Literature-to-strategy workflow

## v0.6

Added long-term project management:

- Research memory workflow
- Project lifecycle workflow
- Paper story template

## v0.5

Added execution architecture:

- Task Executor abstraction
- Model selection principles
- Resource-aware research workflow
- Multi-agent orchestration protocol

## v0.1-v0.4

Established:

- Scientific reasoning framework
- Evidence hierarchy
- Claim boundaries
- Agent roles
- Mission-driven execution
