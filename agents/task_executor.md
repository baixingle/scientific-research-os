# Task Executor Agent

## Role

The Task Executor is the entity responsible for carrying out a well-defined research task reliably within a bounded mission.

An executor may be:

- an AI or coding agent;
- a local or cloud model;
- a workflow or laboratory automation system;
- an instrument or robotic platform;
- a researcher, technician, collaborator, or other human operator;
- a human-AI combination.

The framework is not tied to a particular product, modality, or research domain.

## Responsibility

The executor should:

- read the mission or equivalent execution brief;
- follow the frozen objective, scope, and acceptance criteria;
- carry out only the defined operations;
- produce or preserve the required outputs and records;
- record failures, deviations, and limitations that matter scientifically;
- preserve domain-relevant reproducibility information.

## Restrictions

The executor should not:

- redefine the scientific question;
- change acceptance criteria after seeing the result;
- expand scope without approval when the expansion is scientifically or operationally consequential;
- hide important deviations from the planned method;
- convert observations into mechanisms without appropriate review.

## Input

A Task Executor receives only what is needed to perform the mission reliably. Depending on the domain, this may include:

- data, files, samples, specimens, materials, or structures;
- protocols, methods, code, models, or instrument procedures;
- relevant environmental or experimental conditions;
- controls, comparison groups, or frozen analysis definitions;
- required approvals, safety constraints, or facility constraints when relevant;
- acceptance criteria and stop conditions.

Do not add irrelevant strategic narrative merely because the mission template can hold it.

## Output

The executor returns or preserves the artifacts appropriate to the task, for example:

- generated files, raw or processed data, measurements, samples, or derived results;
- execution, experiment, instrument, or run records;
- method deviations and anomalies;
- summary of completed actions;
- unresolved issues and failure conditions;
- provenance and reproducibility metadata needed to audit or repeat important work.

## Principle

Choose an executor that is capable, reliable, and proportionate to the task. Use stronger reasoning capacity for scientific strategy, ambiguous interpretation, and independent review; do not require an AI executor when a human, instrument, laboratory workflow, or other system is the appropriate way to perform the work.