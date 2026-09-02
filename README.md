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

See [`QUICK_START.md`](QUICK_START.md) for the researcher-facing usage model.

## Zero-config, not black-box

The researcher should not have to operate the framework manually, but should be able to see both the **current scientific state** and the **historical chain** behind it.

For persistent projects, the preferred model is:

```text
RESEARCH_STATE.md  -> concise view of where the project is now
PROVENANCE.md      -> traceable history of important work and reproducibility metadata
missions/          -> what was requested
reviews/           -> how important results were checked
 decisions/        -> why important choices were made
 data/code/runs    -> the underlying scientific evidence and execution record
```

The AI maintains these artifacts when useful. The researcher does not fill them out manually.

A persistent project may therefore look like:

```text
project/
├── RESEARCH_STATE.md        # current human-readable scientific state
├── PROVENANCE.md            # append-oriented provenance / reproducibility index
├── missions/                # bounded delegated work, when it exists
├── reviews/                 # acceptance / scientific review, when needed
├── decisions/               # important persistent decisions
├── data/                    # project data or links to canonical storage
├── code/                    # code, scripts, notebooks, version-controlled methods
├── runs/                    # execution / simulation / experiment records when useful
└── ...existing project structure...
```

This is a recommended transparency and reproducibility pattern, not a mandatory directory schema. Existing projects should keep their own organization when it already works.

The key rule is:

> **Current state may change; important scientific history should remain traceable.**

If an interpretation changes, do not erase the old result or decision. Preserve the earlier record and explicitly add the correction, review, or superseding result.

## Why history matters

A scientific project must be able to answer two different questions:

1. **Where are we now?** — answered by the current state view.
2. **How did we get here, and can we reproduce it?** — answered by provenance, missions, runs, reviews, decisions, code/data versions, and historical records.

For important analyses, computations, experiments, or datasets, useful provenance may include input identifiers, code commit/version, environment, parameters, random seed, sample/instrument/run IDs, output paths, hashes/checksums, linked reviews, and the decision that accepted or superseded the result.

The framework should not create heavy metadata for every trivial edit. It should preserve history in proportion to scientific value and reproducibility risk.

> **Automate the complexity, preserve the scientific transparency and history.**

## What it is for

AI can accelerate literature work, coding, data processing, simulations, analysis, and writing. The harder problem is deciding **what is worth doing next**, knowing **what the evidence really supports**, preserving **why decisions were made**, and ensuring important results remain **traceable and reproducible** as the project evolves.

Scientific Research OS focuses on four high-value jobs:

1. **Think clearly** — identify the real uncertainty, plausible alternatives, and evidence that would distinguish them.
2. **Execute reliably** — turn a sufficiently clear task into a bounded, reproducible mission when delegation is useful.
3. **Do not overclaim** — separate observation, interpretation, mechanism, and generalization before changing the scientific conclusion.
4. **Preserve the research path** — keep enough history to audit, reproduce, and understand important results and decisions later.

Everything else in the repository exists to support those jobs when needed.

## Design principle

> **Use the minimum structure necessary to improve scientific judgment and reproducibility.**

The framework should absorb operational complexity rather than transfer it to the researcher.

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
- record important decisions and revision triggers;
- maintain the current research state;
- preserve provenance for important results, runs, and decisions.

These are implementation mechanisms, not mandatory user tasks.

When the system creates or materially updates persistent artifacts, it should briefly tell the researcher what changed and where it is stored. The user should be able to inspect the work without being forced to manage it.

## Internal architecture

For complex work, the framework can separate roles internally while maintaining both current-state and historical views:

```text
                  Human Scientist
                        ^
                        |
                Research State View
                        ^
                        |
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
Decision Memory
            |
            v
Provenance / History
            |
            +----------------------> Research State View
```

The named role files in `agents/` are abstractions for implementing this separation. They are not roles that the user must configure.

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

```text
scientific-research-os/
├── SKILL.md
├── QUICK_START.md
├── AGENTS.md
├── agents/
├── workflows/
├── templates/
│   ├── research_state.md       # current human-readable state
│   ├── provenance_manifest.md  # historical provenance / reproducibility
│   └── ...
├── references/
├── checklists/
├── docs/
├── reviews/
└── examples/
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

**v1.0.0** defines the stable scientific core: evidence discipline, adaptive strategy/execution separation, optional mission/review/memory artifacts, zero-config researcher entry, an inspectable research-state layer, and durable provenance for important scientific history.

Future changes should be judged by a simple standard:

> **Does this materially improve scientific value, traceability, or reproducibility without adding unnecessary interaction friction?**
