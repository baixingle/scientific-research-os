# Agent Orchestration Protocol

## Purpose

Define how human researchers and AI agents collaborate without mixing scientific judgment, task design, routine execution, and evidence review.

## Architecture

```text
Human Scientist
      |
      v
Strategic Agent <---- Skeptic challenge
      |
      v
Planning Agent
      |
      v
Task Executor Agent
      |
      v
Reviewer Agent <----- Skeptic challenge when useful
      |
      v
Decision Log + Scientific Memory
      |
      +----> next decision
```

The roles are functional abstractions. They may be implemented by different models, tools, people, or automation systems.

## Human Scientist

Retains responsibility for:

- selecting important scientific questions;
- providing domain judgment and constraints;
- deciding how much uncertainty is acceptable;
- approving claim escalation and major resource commitments;
- making final scientific decisions.

## Strategic Agent

Responsible for:

- framing the scientific question;
- distinguishing evidence, interpretation, and assumptions;
- constructing competing hypotheses;
- identifying knowledge, method, or data gaps;
- defining evidence requirements and interpretation boundaries;
- maintaining connection to broader scientific theory.

Not responsible for routine execution.

## Skeptic

Responsible for adversarial scientific challenge:

- identify hidden assumptions;
- generate plausible alternative explanations;
- detect circular reasoning;
- challenge premature causal or general claims;
- ask what evidence would falsify the preferred interpretation.

The Skeptic is not the same as the Reviewer. It may be invoked before a mission exists, while the Reviewer evaluates concrete evidence after execution.

## Planning Agent

Responsible for:

- converting strategy into bounded missions;
- identifying the decision each task informs;
- freezing inputs, definitions, and acceptance criteria;
- setting stop conditions and failure interpretation;
- separating discovery from validation;
- defining outputs and reproducibility requirements.

The Planning Agent must not encode a desired scientific answer into the mission.

## Task Executor Agent

May be implemented by:

- coding agents;
- local models;
- cloud/API models;
- automation systems;
- scripts or conventional computational workflows.

Responsible for:

- executing the frozen mission;
- producing requested artifacts;
- recording operations, failures, and environment details;
- stopping when predefined conditions are reached.

Not responsible for changing scientific objectives, acceptance criteria, or claim boundaries.

## Reviewer Agent

Responsible for independent evaluation of:

- mission compliance;
- data/provenance integrity;
- reproducibility;
- robustness and relevant sensitivity tests;
- alternative explanations;
- evidence level;
- supported and unsupported claims.

A completed task is not automatically an accepted scientific conclusion.

## Information Flow Rule

### Pass downward only what execution requires

Normally pass:

- objective;
- frozen definitions;
- inputs and environment;
- allowed/forbidden operations;
- outputs;
- acceptance criteria;
- stop conditions;
- reproducibility requirements.

### Do not pass unnecessary strategic bias

Avoid giving a Task Executor unnecessary information such as:

- preferred mechanisms;
- expected direction of the result;
- publication target;
- desired narrative;
- unpublished strategic speculation not needed for execution.

This is not secrecy between collaborators. It is bias control and role separation.

## Model Allocation Rule

Use stronger reasoning capacity where uncertainty and scientific judgment are high.

Use the least expensive capable executor when a task is well specified and operational.

Model choice may change without changing the scientific workflow.

## Handoff Artifacts

Recommended handoffs:

```text
Strategic Agent -> Scientific Framework / Roadmap
Planning Agent  -> Mission
Task Executor   -> Outputs + Logs + Reproducibility Metadata
Reviewer        -> Acceptance + Interpretation Boundary
Human/Strategy  -> Decision Log
Memory          -> Current Scientific State for the next cycle
```

## Final Principle

Separate **what should be believed**, **what should be tested**, and **how a task is executed**.

The purpose of orchestration is not to create more agent activity. It is to make scientific decisions more reliable while using AI capability efficiently.
