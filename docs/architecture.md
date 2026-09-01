# Scientific Research OS Architecture

## Overview

Scientific Research OS is designed around a human-guided multi-agent research workflow.

The architecture separates scientific judgment from task execution.

```
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

## Core Design Rules

### Strategy is separated from execution

The strategic layer defines:

- scientific questions;
- hypotheses;
- priorities;
- evidence requirements.

The execution layer receives only the information needed to complete a mission.

### Evidence before claims

Every conclusion should be traceable through:

Observation -> Interpretation -> Mechanism -> Generalization

### Memory stores decisions, not conversations

Research memory preserves:

- decisions;
- evidence;
- rejected alternatives;
- confidence;
- future triggers.

## Agent Independence

The framework does not depend on any specific AI product.

Any capable model can serve as an executor if it follows mission specifications and acceptance criteria.
