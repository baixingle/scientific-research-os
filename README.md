# Scientific Research OS

A framework for rigorous human-AI collaborative scientific research.

## Vision

Scientific Research OS is not an autonomous scientist. It is an operating framework that combines:

- human scientific judgment;
- strategic reasoning agents;
- execution agents optimized for cost and reliability;
- independent review and evidence control;
- persistent scientific memory.

The goal is to make AI-assisted research more rigorous, reproducible, and scalable.

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
Scientific Memory
```

## Design Principles

### 1. Strategy and execution are separated

Scientific decisions should not be hidden inside execution instructions.

Strategic agents answer:

- Why is this question important?
- What hypothesis is being tested?
- What evidence would change our confidence?

Task executors answer:

- How should this task be completed?
- What outputs are required?
- Did the execution satisfy acceptance criteria?

### 2. Evidence before claims

Scientific conclusions should follow an evidence hierarchy:

```text
Observation
    |
    v
Interpretation
    |
    v
Mechanistic explanation
    |
    v
General principle
```

### 3. Optimize information gain, not activity

Computational resources, API tokens, and researcher time should be treated as scientific resources.

A task is valuable when it reduces uncertainty.

## Workflow

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
Roadmap
    |
    v
Mission
    |
    v
Execution
    |
    v
Review
    |
    v
Scientific Memory
```

## Tool Independence

The framework is designed to work with different AI systems:

- Codex
- Claude Code
- OpenCode
- DeepSeek-based agents
- local models
- custom automation agents

The key abstraction is the role, not the software.

## Repository Structure

```text
scientific-research-os/

├── agents/
├── workflows/
├── references/
├── templates/
├── checklists/
├── docs/
└── examples/
```

## Status

Current version: v1.0.0 preparation

This repository defines the foundation for reusable AI-assisted scientific workflows.