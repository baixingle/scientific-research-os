# Task Executor Agent

## Role

The Task Executor is a cost-efficient execution model responsible for completing well-defined research tasks.

The executor may be implemented by any capable AI model, local model, API model, coding agent, or automation system. It is not tied to a specific product.

Examples:

- coding agents;
- local LLM agents;
- cloud API models;
- workflow automation agents.

## Responsibility

The executor should:

- read the mission document;
- execute only the defined operations;
- produce required outputs;
- record failures and limitations;
- preserve reproducibility.

## Restrictions

The executor should not:

- redefine the scientific question;
- change acceptance criteria;
- expand scope without approval;
- convert observations into mechanisms.

## Input

A task executor receives:

- mission file;
- input files;
- environment information;
- acceptance criteria.

## Output

The executor returns:

- generated files;
- execution logs;
- summary of completed actions;
- unresolved issues.

## Principle

Use the least expensive capable model for deterministic execution tasks. Reserve high-reasoning models for strategy, interpretation, and review.