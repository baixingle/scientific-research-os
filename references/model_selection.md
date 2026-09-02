# Model Selection Policy

## Purpose

This reference applies **only when a Scientific Research OS role or subtask is being performed by an AI model**.

Scientific Research OS does not assume that every research task should be executed by AI. A bounded Task Executor may instead be a researcher, technician, collaborator, instrument, robotic platform, laboratory automation system, script, workflow, or human-AI combination.

When AI is appropriate, allocate model capability according to the cognitive difficulty, uncertainty, and consequences of the AI-assigned task.

The strongest model is not always required. The appropriate model is the one that provides sufficient reliability at acceptable cost for the role it is actually performing.

---

# Principle

Use stronger reasoning for scientific judgment and ambiguity.

Use efficient capable models for well-defined AI operations.

```text
Scientific judgment or ambiguity
        ↓
Stronger reasoning model when AI is used
        ↓
Bounded task specification
        ↓
Appropriate executor
   ├── human / instrument / workflow / automation
   └── efficient AI model when AI execution is appropriate
        ↓
Independent validation when needed
```

Model routing is therefore a **subproblem of executor selection**, not the architecture of the entire research workflow.

---

# AI Model Roles

## Strategic Reasoning Model

Use when AI is assisting with:

- defining or reframing scientific questions;
- evaluating competing hypotheses;
- deciding research direction;
- interpreting ambiguous or conflicting results;
- manuscript-level scientific synthesis.

Useful requirements:

- strong reasoning ability;
- broad or relevant scientific understanding;
- ability to challenge assumptions;
- calibrated handling of uncertainty and evidence boundaries.

---

## Planning Model

Use when AI is helping to:

- convert strategy into bounded missions;
- design decision-oriented workflows;
- freeze relevant controls, definitions, or acceptance criteria before results are visible;
- prepare experimental, analytical, computational, or mixed research plans.

---

## AI Execution Model

Use only when the bounded task is suitable for AI execution, for example:

- coding or scripting;
- data processing and file operations;
- routine analysis;
- batch calculations or simulation setup;
- structured literature or document processing;
- preparation of reproducible machine-readable artifacts.

Useful requirements:

- reliable instruction following;
- reproducible behavior and artifact generation;
- appropriate tool access;
- cost proportional to the task.

Do not choose an AI model merely because an execution step exists. If the work is properly performed by a human operator, laboratory instrument, experimental workflow, or other non-AI executor, use that executor instead.

---

## Reviewer Model

Use when AI is assisting with:

- checking scientific logic;
- evaluating whether evidence supports the stated claim;
- identifying alternative explanations;
- detecting overclaiming, circular reasoning, leakage, or post-hoc changes;
- independently reviewing important outputs before they alter project direction.

For high-stakes conclusions, independence of the review may matter more than using the same strongest model again.

---

# Selection Rule

Match AI capability to uncertainty and consequence:

- **High ambiguity / high scientific consequence** → stronger reasoning model.
- **Clear, bounded, low-ambiguity AI task** → efficient capable model.
- **Task not naturally suited to AI execution** → use the appropriate non-AI executor.

If only one adequate model is available, continue with that model rather than forcing the researcher to configure an artificial multi-model architecture.

---

# Anti-patterns

Avoid:

- assuming every Task Executor must be an AI model;
- using expensive models for repetitive or deterministic AI execution without a reliability benefit;
- using weak models for consequential scientific judgment;
- letting an execution model redefine research goals or acceptance criteria;
- creating model-routing configuration that adds more user friction than scientific value.
