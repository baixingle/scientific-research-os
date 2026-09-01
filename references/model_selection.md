# Model Selection Policy

## Purpose

Scientific AI workflows should allocate model capability according to the cognitive difficulty of the task.

The strongest model is not always required. The correct model is the one that provides sufficient reliability at acceptable cost.

---

# Principle

Use expensive reasoning for decisions.

Use efficient execution models for well-defined operations.

```
Scientific judgment
        ↓
High reasoning model
        ↓
Task specification
        ↓
Efficient execution model
        ↓
Validation
```

---

# Model Roles

## Strategic Reasoning Model

Use for:

- defining scientific questions;
- evaluating hypotheses;
- deciding research direction;
- interpreting ambiguous results;
- manuscript-level reasoning.

Requirements:

- strong reasoning ability;
- broad scientific understanding;
- ability to challenge assumptions.

---

## Planning Model

Use for:

- converting strategy into missions;
- designing workflows;
- preparing analysis plans.

---

## Task Executor Model

Use for:

- coding;
- data processing;
- file operations;
- routine analysis;
- batch calculations.

Requirements:

- instruction following;
- reproducibility;
- low cost.

---

## Reviewer Model

Use for:

- checking logic;
- evaluating evidence;
- detecting overclaiming.

---

# Selection Rule

The model should match the uncertainty of the task.

High uncertainty → stronger reasoning model.

Low uncertainty and clear instructions → efficient execution model.

---

# Anti-patterns

Avoid:

- using expensive models for repetitive execution;
- using weak models for scientific decisions;
- letting execution models redefine research goals.
