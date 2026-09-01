---
name: scientific-research-os
description: Human-guided, evidence-controlled workflow for planning, executing, reviewing, and recording scientific research with AI agents. Use for new projects, mechanism studies, unexpected results, expensive computational decisions, literature-to-strategy work, and manuscript-level scientific synthesis.
version: 1.0.0
---

# Scientific Research OS

## Purpose

Scientific Research OS is a reusable operating framework for rigorous human-AI collaborative research. It is not an autonomous scientist and does not replace researcher judgment.

Its central rule is:

> Claim strength must not exceed evidence strength.

The system separates scientific strategy, task planning, execution, independent review, and long-term scientific memory.

## When to Activate

Use this skill when:

- starting or reframing a scientific project;
- deciding which experiment, simulation, or analysis should be run next;
- interpreting unexpected or ambiguous results;
- evaluating a proposed mechanism or causal claim;
- deciding whether expensive computation is justified;
- converting literature into a research strategy;
- reviewing evidence before changing a project claim;
- constructing a manuscript-level scientific story.

Do not invoke the full workflow for routine deterministic operations that already have a frozen mission and acceptance criteria. Those belong directly to the Task Executor layer.

## Core Architecture

```text
Human Scientist
      |
      v
Strategic Agent
      |
      v
Planning Agent
      |
      v
Task Executor Agent
      |
      v
Reviewer Agent
      |
      v
Decision Log + Scientific Memory
      |
      +----> next scientific decision
```

A Skeptic role may be inserted before execution or interpretation to challenge assumptions and competing explanations.

## Non-Negotiable Rules

1. **Question before method.** Do not begin with a list of calculations or descriptors. First define the unresolved scientific uncertainty.
2. **Competing hypotheses before confirmation.** Include plausible alternatives and, when appropriate, an H0 in which the current explanation is sufficient.
3. **Acceptance before execution.** Define success, failure, and stop conditions before results are visible.
4. **Strategy and execution remain separate.** Task Executors receive only the context required to perform the mission reliably.
5. **Discovery and validation remain separate.** Once a candidate rule, descriptor, or mechanism is discovered, freeze its definition before independent validation.
6. **Information gain over activity.** Every costly task must identify what uncertainty it reduces and what decision its possible outcomes would change.
7. **Evidence before claims.** Observation, localization, mechanism, and generalization are different evidence levels.
8. **Failures are informative when pre-specified.** Do not keep changing windows, features, models, or criteria until a preferred result appears.
9. **Memory stores scientific state, not raw conversation.** Preserve decisions, evidence, rejected alternatives, confidence, and revision triggers.
10. **Protect unpublished work.** Do not place private data, unpublished project details, or confidential scientific strategy into generic examples or public framework files.

## Evidence Levels

Use `references/evidence_hierarchy.md` for the full rule set.

```text
Level 1  Observation / association
Level 2  Physical or temporal localization
Level 3  Mechanistic / causal support
Level 4  Transferable general principle
```

Do not use causal language merely because a descriptor predicts an outcome or changes earlier in time. Mechanistic claims require an appropriate physical bridge, alternative-explanation control, and validation suited to the claim.

## Workflow

### Stage 0 — Research Brief

Use `templates/research_brief.md`.

Capture the project background, current state, constraints, and the scientific change in understanding being sought.

**Gate 0:** Do not proceed if the project is only a topic, a preferred mechanism, or a request to “look for interesting variables.”

### Stage 1 — Scientific Framework

Use `templates/scientific_framework.md` and, when needed, `workflows/literature_to_strategy.md`.

Define:

- established evidence versus interpretation and assumptions;
- the knowledge, method, or data gap;
- competing hypotheses;
- minimum evidence that distinguishes them;
- current claim boundary;
- next decision point.

**Gate 1:** The problem must be falsifiable enough that both positive and negative outcomes can change the project state.

### Stage 2 — Project Roadmap

Use `templates/project_roadmap.md` and `workflows/resource_allocation.md`.

Plan milestones as decision points, not as a list of calculations. Prefer the smallest test that separates competing explanations.

**Gate 2:** No expensive task should start without a stated uncertainty-reduction target.

### Stage 3 — Mission Design

Use `templates/mission.md`.

A mission must contain:

- scientific objective expressed as an uncertainty to reduce;
- hypothesis or comparison being tested;
- execution-relevant context only;
- inputs and environment;
- allowed and forbidden operations;
- required outputs;
- acceptance criteria;
- stop conditions;
- failure interpretation;
- reproducibility metadata requirements.

The Planning Agent must not encode a desired scientific answer into the execution instructions.

### Stage 4 — Execution

Use `agents/task_executor.md` and `references/model_selection.md`.

Choose the least expensive capable executor for a frozen, well-defined task. Reserve high-reasoning models for uncertain strategic, interpretive, and review decisions.

The Task Executor must not silently change scope, criteria, hypotheses, or analysis definitions.

### Stage 5 — Independent Review

Use `agents/reviewer.md`, `templates/acceptance.md`, `checklists/scientific_review.md`, and relevant mechanism/analysis checklists.

Review separately:

- technical completion;
- data and provenance integrity;
- robustness and sensitivity;
- alternative explanations;
- evidence level;
- supported and unsupported claims.

**Gate 5:** A completed task is not automatically an accepted scientific conclusion.

### Stage 6 — Interpretation and Decision

Use `templates/interpretation.md` and `templates/decision_log.md`.

Record:

- what is directly known;
- what remains uncertain;
- alternative explanations;
- what the result enables;
- what it does not prove;
- the current decision and confidence;
- what future evidence would require revision.

### Stage 7 — Scientific Memory and Story

Use `workflows/research_memory.md` to preserve project state. Use `templates/paper_story.md` only after evidence boundaries are stable enough to support a coherent story.

The manuscript narrative must be derived from the evidence architecture, not used to dictate it.

## Special Workflows

- New project: `workflows/new_project.md`
- Unexpected result: `workflows/unexpected_result.md`
- Mechanism claim: `workflows/mechanism_claim.md`
- Literature to strategy: `workflows/literature_to_strategy.md`
- Resource allocation: `workflows/resource_allocation.md`
- Project lifecycle: `workflows/project_lifecycle.md`
- Research memory: `workflows/research_memory.md`

## Agent Roles

- `agents/strategist.md` — frames the scientific problem and hypothesis space.
- `agents/skeptic.md` — attacks assumptions and alternative explanations.
- `agents/planner.md` — turns strategy into frozen missions and decision rules.
- `agents/task_executor.md` — performs bounded work reproducibly and cost-effectively.
- `agents/reviewer.md` — independently evaluates evidence, acceptance, and claim boundaries.
- `agents/agent_orchestration_protocol.md` — defines information flow between roles.

## Final Operating Principle

Do not optimize for producing more analyses, stronger wording, or a preferred mechanism.

Optimize for the smallest rigorous reduction in scientific uncertainty that changes what the researcher can justifiably believe or do next.
