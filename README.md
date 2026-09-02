# Scientific Research OS

**Scientific Research OS** is a tool-independent framework for making human-AI scientific collaboration more rigorous **without making it harder to use**.

Current stable specification: **v1.0.0**.

## Start in one sentence

There is no framework-specific setup required before the first useful interaction.

Just describe the science:

> I observed X, I suspect Y may be involved, but I am not sure what would distinguish Y from the alternatives. What should I do next?

or:

> Here are the latest results. What do they actually support, what remains uncertain, and what is the most informative next step?

The framework should infer the minimum structure needed for the problem. Researchers should not have to choose agent roles, copy templates, select workflow modes, or configure model routing just to begin.

See [`QUICK_START.md`](QUICK_START.md) for the full zero-config usage philosophy.

## What it is for

AI can accelerate literature work, coding, data processing, simulations, analysis, and writing. The harder problem is deciding **what is worth doing next**, knowing **what the evidence really supports**, and preserving scientific judgment as AI increases the amount of work that can be produced.

Scientific Research OS focuses on three high-value jobs:

1. **Think clearly** — identify the real uncertainty, plausible alternatives, and the evidence that would distinguish them.
2. **Execute reliably** — turn a sufficiently clear task into a bounded, reproducible mission when delegation is useful.
3. **Do not overclaim** — separate observation, interpretation, mechanism, and generalization before changing the scientific conclusion.

Everything else in the repository exists to support those jobs when needed.

## Design principle

> **Use the minimum structure necessary to improve scientific judgment.**

The framework should absorb complexity rather than transfer it to the researcher.

A simple question should stay simple. A costly, ambiguous, long-running, or multi-agent project may justify more structure. The user does not need to choose that level in advance.

A second principle protects scientific validity:

> **Claim strength must not exceed evidence strength.**

## What should happen automatically

Depending on the situation, the system may internally:

- identify the key scientific uncertainty;
- compare competing explanations;
- suggest the lowest-cost discriminating test;
- create acceptance criteria before flexible or expensive execution;
- prepare a bounded mission for an execution agent;
- review technical results independently from scientific interpretation;
- record important decisions and revision triggers for long projects.

These are implementation mechanisms, not mandatory user tasks.

Templates, checklists, workflows, and role definitions should be surfaced only when they make the work clearer, safer, easier to review, or easier to hand off.

## Example interaction

A useful answer to “what should I do next?” should usually be closer to this:

```text
Key uncertainty:
Does explanation A or B account for the observed difference?

Best current evidence:
The existing result supports X, but it does not yet distinguish A from B.

Most informative next step:
Run test Y because it is relatively cheap and produces opposite predictions under A and B.

If Y gives result 1:
Increase confidence in A and proceed to validation Z.

If Y gives result 2:
Deprioritize A and test B directly.

Current claim boundary:
The present data support association X; they do not yet establish mechanism A.
```

The researcher should not need to see a hypothesis-tree template, a mission form, a reviewer checklist, or an internal agent graph unless those artifacts are actually useful.

## Internal architecture

For complex work, the framework can separate roles internally:

```text
Human Scientist
      |
      v
Scientific Reasoning / Strategy
      |
      v
Planning when needed
      |
      v
Bounded Execution when needed
      |
      v
Independent Review when needed
      |
      v
Decision Memory when useful
```

The named role files in `agents/` are abstractions for implementing this separation. They are not roles that the user must configure.

A coding agent, local model, cloud model, workflow system, script, human collaborator, or other capable tool can serve an execution role if it follows the relevant task contract.

## Evidence architecture

When formal evidence distinctions matter, the framework uses four broad levels:

```text
Level 1  Observation / association
Level 2  Physical or temporal localization
Level 3  Mechanistic / causal support
Level 4  Transferable general principle
```

Predictive association alone is not automatically a mechanism. Temporal precedence alone is not automatically causality. A mechanism supported in one system is not automatically a general principle.

See [`references/evidence_hierarchy.md`](references/evidence_hierarchy.md).

## Cost-aware execution

The strongest available model does not need to perform every task.

Use stronger reasoning where scientific uncertainty is high. Use efficient capable models or tools for frozen operational work. If automatic routing is unavailable, use the current agent rather than forcing the researcher to reproduce a multi-agent architecture manually.

Configuration should be optional and used mainly to override sensible defaults, such as cost limits, privacy requirements, preferred tools, or approval before expensive/irreversible actions.

## Internal resources

The repository contains reusable resources for situations where extra structure is genuinely helpful:

```text
scientific-research-os/
├── SKILL.md                 # adaptive operating rules
├── QUICK_START.md           # zero-config researcher entry
├── AGENTS.md                # repository and agent UX contract
├── agents/                  # optional role abstractions
├── workflows/               # optional recurring procedures
├── templates/               # internal reusable artifacts
├── references/              # scientific reasoning principles
├── checklists/              # optional quality-control aids
├── docs/                    # usage and architecture notes
├── reviews/                 # self-review / audit material
└── examples/                # generic examples only
```

The existence of these files does **not** mean every project should use them.

## Privacy and unpublished research

The reusable core should not contain unpublished project data, confidential scientific strategy, private datasets, or identifiable research details unless a researcher explicitly chooses to add them to a private deployment.

Public and reusable examples should remain synthetic or generic.

## What this is not

Scientific Research OS is not:

- an autonomous scientist;
- an automatic paper factory;
- a mandatory project-management system;
- a requirement to use multiple AI agents;
- a requirement to formalize every scientific conversation;
- a replacement for researcher judgment.

The human researcher remains the final scientific decision maker.

## Status

**v1.0.0** defines the stable scientific core: evidence discipline, adaptive strategy/execution separation, optional mission/review/memory artifacts, and a zero-config researcher-facing philosophy.

Future changes should be judged by a simple standard:

> **Does this materially improve scientific value without adding unnecessary interaction friction?**
