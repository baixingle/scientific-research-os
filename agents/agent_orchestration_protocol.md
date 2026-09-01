# Agent Orchestration Protocol

## Purpose

Define how multiple AI agents collaborate in scientific research without mixing responsibilities.

---

# Architecture

```
Human Scientist
        |
        ↓
Strategic Agent
        |
        ↓
Planning Agent
        |
        ↓
Task Executor Agent
        |
        ↓
Reviewer Agent
        |
        ↓
Scientific Memory
```

---

# Strategic Agent

Responsible for:

- scientific questions;
- hypotheses;
- priorities;
- interpretation boundaries.

Not responsible for routine execution.

---

# Planning Agent

Responsible for:

- mission generation;
- defining inputs and outputs;
- acceptance criteria.

---

# Task Executor Agent

Can be:

- coding agents;
- local models;
- API models;
- automation agents.

Responsible for:

- executing defined missions;
- producing artifacts;
- recording operations.

Not responsible for changing scientific objectives.

---

# Reviewer Agent

Checks:

- evidence quality;
- reproducibility;
- claim boundaries;
- alternative explanations.

---

# Communication Rule

Pass downward:

- necessary context;
- explicit requirements;
- acceptance criteria.

Do not pass unnecessary strategic speculation to execution agents.

---

# Final Principle

Separate thinking from doing.

High-level reasoning determines what should be done.

Execution agents determine how efficiently it can be done.
