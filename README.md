# Scientific Research OS

[![Release](https://img.shields.io/github/v/release/baixingle/scientific-research-os)](https://github.com/baixingle/scientific-research-os/releases/latest)
[![License](https://img.shields.io/github/license/baixingle/scientific-research-os)](LICENSE)
[![Agent Skill](https://img.shields.io/badge/Agent%20Skill-SKILL.md-000000)](SKILL.md)

**A zero-config, human-guided Agent Skill for rigorous, tool-connected, traceable, and reproducible scientific research.**

Scientific Research OS helps researchers decide **what is worth doing next**, turn clear next steps into **bounded execution**, use **available AI tools to carry out the work when the host environment supports it**, keep **claim strength proportional to evidence**, and preserve the **scientific history needed to understand and reproduce important results later**.

It is tool-independent and designed for experimental / wet-lab research, computational science and simulation, theory, machine learning and data science, literature-driven work, and hybrid projects.

Current stable release: **[v1.0.0](https://github.com/baixingle/scientific-research-os/releases/tag/v1.0.0)**.

## Start in one sentence

There is no framework-specific setup required before the first useful interaction.

Just describe the science:

> I observed X, I suspect Y may be involved, but I am not sure what would distinguish Y from the alternatives. What should I do next?

or:

> Here are the latest results. What do they actually support, what remains uncertain, and what is the most informative next step?

The framework infers the minimum useful structure. Researchers should not have to choose agent roles, copy templates, select workflow modes, or configure model routing just to begin.

When the host AI environment has the required tools and permissions, the workflow can continue beyond advice: the AI can turn a sufficiently clear next step into a bounded mission, use available tools to execute it, check the returned outputs, review what the evidence supports, and update research state and provenance. If execution capability is unavailable, the same mission becomes a precise handoff instead of pretending the work was done.

See [`QUICK_START.md`](QUICK_START.md) for the shortest usage guide and [`docs/installation_and_usage.md`](docs/installation_and_usage.md) for installation options.

## Why this exists

AI can already accelerate literature work, coding, data processing, simulations, analysis, and writing. In tool-enabled environments it can increasingly carry out those operations directly. The harder scientific problems remain:

1. **What is the real uncertainty?**
2. **Which next experiment, calculation, analysis, or observation would actually distinguish plausible explanations?**
3. **What should be delegated to AI and tools, with what boundaries and acceptance criteria?**
4. **What does the returned result support — and what does it not prove?**
5. **Can we still reconstruct why we made this decision months later?**

Scientific Research OS is designed around that full loop rather than around maximizing autonomous activity.

> **Reason scientifically → execute with available tools → review the evidence → preserve the research history.**

> **High scientific value with low interaction friction.**

## From reasoning to tool-connected execution

Scientific Research OS is not only a planning or prompting framework. When the host AI has authorized access to suitable tools, a clear research task can move through a controlled execution loop:

```text
Scientific question
        ↓
Competing explanations
        ↓
Most informative next step
        ↓
Bounded mission + acceptance criteria
        ↓
AI uses available tools to execute
        ↓
Technical acceptance / failure check
        ↓
Scientific review and claim boundary
        ↓
RESEARCH_STATE.md + PROVENANCE.md
```

Depending on the environment and research domain, those tools may include files, code execution, shell or workflow systems, data-analysis packages, literature/search systems, databases, remote compute, laboratory automation, instruments, robotic platforms, or other project-specific interfaces.

The framework itself does **not** bundle or promise access to those tools. It governs how available capabilities are selected and used. Expensive, irreversible, privacy-sensitive, safety-sensitive, ethically regulated, or strategically consequential actions should still require appropriate human approval.

If a tool cannot perform the needed operation, Scientific Research OS should say so and produce a reproducible mission or handoff rather than claiming execution occurred.

## See it in action

Three short synthetic walkthroughs show the same scientific-method layer adapting to different kinds of research:

- **[Wet-lab / experimental research](examples/wet_lab_showcase.md)** — competing explanations, discriminating experiments, controls, experimental provenance, and conservative mechanism claims.
- **[Computational / simulation research](examples/computational_showcase.md)** — information-gain calculations, frozen comparisons, reproducible execution, and avoiding post-hoc descriptor chasing.
- **[Machine learning / data science](examples/ml_showcase.md)** — leakage and robustness checks before model scaling, frozen validation definitions, and independent evidence.

A more abstract end-to-end example is available in [`examples/generic_research_project.md`](examples/generic_research_project.md).

## Five jobs the framework is optimized for

### 1. Think clearly

Identify the real uncertainty, plausible alternatives, and the smallest reliable observation that can change a scientific decision.

### 2. Choose the most informative next step

Prioritize work by information gain: ask which observation, experiment, calculation, analysis, or derivation is most likely to distinguish the remaining explanations and change the next decision.

### 3. Execute with AI and tools when available

When a task is sufficiently clear, turn it into a bounded mission with frozen objectives, relevant inputs or materials, required outputs, acceptance criteria, stop conditions, and reproducibility requirements.

If the host AI has the necessary authorized tools, use them to carry out the mission instead of stopping at a plan. If not, produce a precise handoff to the appropriate human, instrument, workflow, or external executor.

### 4. Review without overclaiming

Check technical completion separately from scientific meaning. Keep observation, interpretation, mechanistic support, and generalization distinct.

> **Claim strength must not exceed evidence strength.**

### 5. Preserve the research path

Keep important results and decisions traceable so future researchers — or future AI sessions — can understand how the project reached its current state.

## Zero-config, not black-box

The researcher should not have to operate the framework manually, but should be able to inspect both the **current scientific state** and the **historical chain** behind it.

For a persistent project, the preferred pattern is:

```text
RESEARCH_STATE.md  -> concise view of where the project is now
PROVENANCE.md      -> traceable history of important work and reproducibility metadata
missions/          -> what was requested
reviews/           -> how important results were checked
decisions/         -> why important choices were made
data/code/runs     -> underlying scientific evidence and execution records when relevant
```

The AI maintains these artifacts when useful. The researcher does not fill them out manually.

A project may therefore look like:

```text
project/
├── RESEARCH_STATE.md
├── PROVENANCE.md
├── missions/
├── reviews/
├── decisions/
└── ...existing data, code, experiments, notes, and results...
```

This is a transparency and reproducibility pattern, **not a mandatory directory schema**. Existing project organization should be preserved whenever possible.

The key rule is:

> **Current state may change; important scientific history should remain traceable.**

If an interpretation changes, do not silently rewrite the old result or decision. Preserve the earlier record and add the correction, review, or superseding result explicitly.

## Evidence architecture

When a formal evidence distinction is useful, the framework uses four broad levels:

```text
Level 1  Observation / association
Level 2  Physical or temporal localization
Level 3  Mechanistic / causal support
Level 4  Transferable general principle
```

Predictive association alone is not automatically a mechanism. Temporal precedence alone is not automatically causality. A mechanism supported in one system is not automatically a general principle.

See [`references/evidence_hierarchy.md`](references/evidence_hierarchy.md).

## Choosing the next step

The framework prefers decision-oriented research over activity for its own sake:

```text
What is the most important unresolved uncertainty?
        ↓
Which explanations are still plausible?
        ↓
What is the lowest-cost reliable observation that distinguishes them?
        ↓
How would each possible result change what we believe or do next?
```

If existing evidence already answers the question, the correct recommendation may be to stop rather than generate more work.

## Domain-adaptive execution and reproducibility

The scientific-method layer is shared; execution details are not forced into one universal schema.

**Experimental / wet-lab work** may need sample or specimen identity, reagent/material lot, protocol version, controls, replicates, critical conditions, instrument settings, experimental batch, deviations, and raw-data mapping.

**Computational / simulation work** may need input structures or datasets, code/version, software environment, parameters, seeds, execution details when relevant, raw outputs, and logs.

**ML / data-science work** may need dataset and split versions, preprocessing, model configuration, seeds, checkpoints, evaluation definitions, and raw predictions.

**Theory / analytical work** may need assumptions, conventions, boundary conditions, derivation versions, approximations, solver settings, and external reference values.

Only information that materially supports interpretation, audit, or reasonable reproduction should be required.

See [`references/reproducibility.md`](references/reproducibility.md).

## The Task Executor does not have to be AI

A bounded research task may be carried out by:

- a researcher, technician, or collaborator;
- a laboratory instrument or robotic platform;
- a workflow or automation system;
- a script or coding agent;
- an AI model;
- a human-AI combination.

When the current AI environment itself has suitable authorized tools, it may act as the executor and continue directly from reasoning into execution. When it does not, executor selection should route the mission to the appropriate external system or human rather than forcing an AI-only workflow.

Model selection is therefore a subproblem of executor selection, not the architecture of the entire research workflow. Stronger AI reasoning should be reserved for ambiguity and consequential scientific judgment; efficient capable models are appropriate for clear AI-executable subtasks.

See [`agents/task_executor.md`](agents/task_executor.md) and [`references/model_selection.md`](references/model_selection.md).

## Installation

Scientific Research OS is repository-based and tool-independent. The goal is simply to make `SKILL.md` and the referenced repository resources available to your AI environment.

Typical options are:

1. import the repository through a native Agent Skills / project-instructions mechanism;
2. attach or clone the repository for a repository-aware agent and point it to `SKILL.md`;
3. in environments without reusable skill installation, use `SKILL.md` as persistent project instructions and make supporting files accessible when needed.

After that, start with the scientific problem in ordinary language. Any tools already available and authorized in the host environment can then be used for bounded execution when appropriate; Scientific Research OS does not require a separate orchestration product.

See [`docs/installation_and_usage.md`](docs/installation_and_usage.md) for details.

## Internal resources

```text
scientific-research-os/
├── SKILL.md                    # canonical operating specification
├── QUICK_START.md              # zero-config researcher entry
├── AGENTS.md                   # repository / agent UX contract
├── agents/                     # optional role abstractions
├── workflows/                  # optional recurring procedures
├── templates/                  # state, provenance, mission, decision artifacts
├── references/                 # scientific reasoning principles
├── checklists/                 # optional quality controls
├── docs/                       # architecture and usage guidance
├── reviews/                    # self-audit and release checks
└── examples/                   # synthetic usage walkthroughs
```

The existence of these resources does **not** mean every project should use all of them.

## Security and privacy

The reusable core is an instruction-and-document framework. It does not require credentials or a proprietary backend, and the v1.0 core does not bundle an execution engine, tool connector, or mandatory network calls.

When a downstream AI environment already provides tools, APIs, scripts, remote compute, instruments, or automation systems, Scientific Research OS may direct their use for an approved bounded mission. Those capabilities remain governed by their own permissions, security, privacy, safety, and access requirements.

Do not place unpublished project data, confidential scientific strategy, private datasets, credentials, or identifiable research details into the reusable/public framework unless explicitly intended for public release.

## What this is not

Scientific Research OS is not:

- an autonomous scientist;
- a universal tool connector or execution engine;
- an automatic paper factory;
- a mandatory project-management system;
- a requirement to use multiple AI agents;
- a requirement to formalize every scientific conversation;
- a replacement for researcher judgment.

The human researcher remains the final scientific decision maker.

## Cite this project

A [`CITATION.cff`](CITATION.cff) file is included so GitHub and compatible scholarly tools can provide citation metadata. When research depends materially on the framework, cite the specific version used.

## Status

**v1.0.0** defines the stable scientific core: evidence discipline, adaptive strategy/execution separation, zero-config researcher entry, bounded missions when useful, independent review, an inspectable research-state layer, and durable provenance for important scientific history.

The current `main` branch also clarifies the tool-connected execution path: when the host environment provides suitable authorized tools, a bounded mission may be executed directly before review and provenance updates.

Release: **[Scientific Research OS v1.0.0](https://github.com/baixingle/scientific-research-os/releases/tag/v1.0.0)**

> **Automate the complexity, preserve the scientific transparency and history.**

Future changes should be judged by one standard:

> **Does this materially improve scientific value, traceability, or reproducibility without adding unnecessary interaction friction?**