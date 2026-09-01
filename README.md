# Scientific Research OS

**Scientific Research OS** is a tool-independent framework for rigorous human-AI collaborative scientific research.

It organizes scientific strategy, task planning, cost-aware execution, independent review, and long-term research memory into one evidence-controlled workflow.

Current stable specification: **v1.0.0**.

## Why This Exists

AI can accelerate literature work, coding, data processing, simulation workflows, analysis, and writing. The difficult part is not generating more research activity; it is preserving scientific judgment while that activity scales.

Scientific Research OS is designed to prevent common failure modes such as:

- starting with methods or descriptors instead of a scientific gap;
- turning correlation into mechanism;
- changing analysis definitions after seeing results;
- using expensive models for routine execution;
- letting execution agents inherit unnecessary strategic bias;
- losing the reasoning behind old project decisions;
- writing a stronger story than the evidence supports.

The framework is therefore not an autonomous scientist and not an automatic paper generator. The human researcher remains the final scientific decision maker.

## Core Principle

> **Claim strength must not exceed evidence strength.**

A second operating principle follows:

> **Optimize for information gain, not research activity.**

Every meaningful task should reduce a defined uncertainty or change a defined decision.

## Architecture

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

A **Skeptic** role can challenge assumptions before execution or interpretation.

### Strategic Agent

Frames the scientific question, competing hypotheses, evidence requirements, priorities, and interpretation boundaries.

### Planning Agent

Turns strategy into bounded missions with frozen inputs, outputs, acceptance criteria, failure interpretation, and stop conditions.

### Task Executor Agent

Carries out well-defined work reproducibly. The executor should be selected for reliability and cost-effectiveness rather than prestige or maximum reasoning capacity.

### Reviewer Agent

Independently checks execution quality, reproducibility, alternative explanations, evidence level, and claim boundaries.

### Scientific Memory

Stores scientific state rather than raw conversation: decisions, evidence, alternatives, confidence, and conditions for revision.

## Standard Project Workflow

```text
Research Idea
    |
    v
Research Brief
    |
    v
Scientific Framework
    |
    v
Project Roadmap
    |
    v
Mission
    |
    v
Execution
    |
    v
Acceptance Review
    |
    v
Interpretation + Decision Log
    |
    v
Scientific Memory
    |
    v
Next Decision / Publication Story
```

Start with [`QUICK_START.md`](QUICK_START.md). The complete operating rules are in [`SKILL.md`](SKILL.md).

## Evidence Architecture

The framework separates evidence levels that are often collapsed in ordinary scientific discussion:

```text
Level 1  Observation / association
          |
          v
Level 2  Physical or temporal localization
          |
          v
Level 3  Mechanistic / causal support
          |
          v
Level 4  Transferable general principle
```

Higher-level language requires stronger evidence. Predictive association alone is not automatically a mechanism; temporal precedence alone is not automatically causality; a mechanism in one sampled system is not automatically a general principle.

## Strategy–Execution Separation

Scientific strategy and routine execution are intentionally separated.

A Task Executor should receive what it needs to do the work reliably:

- objective;
- frozen definitions;
- input files and environment;
- permitted operations;
- required outputs;
- acceptance criteria;
- stop conditions;
- reproducibility requirements.

It does **not** need the full unpublished narrative, preferred mechanism, target journal, or strategic expectation when those details could bias execution.

## Cost-Aware Model Use

The framework does not assume that the strongest available model should perform every task.

Use stronger reasoning where uncertainty is high:

- scientific framing;
- hypothesis comparison;
- ambiguous interpretation;
- reviewer-level critique;
- manuscript-level synthesis.

Use efficient capable models where the task is frozen and operational:

- coding;
- file manipulation;
- routine data processing;
- batch analysis;
- reproducible execution.

See [`references/model_selection.md`](references/model_selection.md).

## Repository Structure

```text
scientific-research-os/
├── SKILL.md
├── QUICK_START.md
├── AGENTS.md
├── VERSION
├── CHANGELOG.md
├── RELEASE.md
├── LICENSE
│
├── agents/
│   ├── strategist.md
│   ├── skeptic.md
│   ├── planner.md
│   ├── task_executor.md
│   ├── reviewer.md
│   └── agent_orchestration_protocol.md
│
├── workflows/
│   ├── new_project.md
│   ├── unexpected_result.md
│   ├── mechanism_claim.md
│   ├── literature_to_strategy.md
│   ├── resource_allocation.md
│   ├── research_memory.md
│   └── project_lifecycle.md
│
├── templates/
│   ├── research_brief.md
│   ├── scientific_framework.md
│   ├── project_roadmap.md
│   ├── mission.md
│   ├── acceptance.md
│   ├── interpretation.md
│   ├── decision_log.md
│   └── paper_story.md
│
├── references/
├── checklists/
├── docs/
├── reviews/
└── examples/
```

## Tool Independence

Roles are abstractions, not product names. A role can be implemented by a cloud model, local model, coding agent, workflow system, script, or human collaborator if it satisfies the role contract.

Specific products may be used in a real deployment, but the core framework should remain portable when products, prices, or model capabilities change.

## Privacy and Unpublished Research

The generic framework must not contain unpublished project data, confidential scientific strategy, private datasets, or identifiable research details unless a researcher explicitly chooses to add them to a private deployment.

Public examples should remain synthetic or generic.

## Using the Framework

For a new project:

1. Fill `templates/research_brief.md`.
2. Build `templates/scientific_framework.md`.
3. Define competing hypotheses and minimum distinguishing evidence.
4. Build a decision-oriented roadmap.
5. Generate a frozen mission from `templates/mission.md`.
6. Execute with an appropriate Task Executor.
7. Review with `templates/acceptance.md` and the review checklists.
8. Record interpretation and a decision log.
9. Update scientific memory before starting the next cycle.

For an existing project with confusing results, begin with `workflows/unexpected_result.md` or `workflows/mechanism_claim.md` rather than restarting the whole lifecycle.

## Status

**v1.0.0** defines the stable core architecture, evidence rules, agent roles, workflow templates, review gates, and scientific-memory protocol.

Future versions may add automation, provenance tooling, scheduling, and domain-specific modules, but those extensions should preserve the v1 core principles.
