# Scientific Research OS Quick Start

## Start with the science

There is no framework-specific setup required before the first useful interaction.

Describe the research problem in ordinary language. For example:

> I observed X, I suspect Y may be involved, but I am not sure what would distinguish Y from the alternatives. What should I do next?

or:

> Here are the latest results. What do they actually support, what remains uncertain, and what is the most informative next step?

That is enough to start.

If the AI environment already has suitable tools and permissions, Scientific Research OS can continue beyond advice: it can define a bounded mission, use those tools to carry out the work, check whether the outputs satisfy the acceptance criteria, review what the result scientifically supports, and update the project state and provenance.

If the required execution capability is unavailable, the system should make that limitation explicit and produce a precise handoff instead of pretending the task was executed.

## The normal loop

For work that actually needs execution, the intended flow is:

```text
scientific question
-> uncertainty / competing explanations
-> most informative next step
-> bounded mission + acceptance criteria
-> AI + available tools execute, when authorized and capable
-> technical acceptance / failure check
-> scientific interpretation and claim review
-> state + provenance update
```

The researcher should not have to manually recreate this sequence or decide which internal role handles each step.

Tool-connected execution is environment-dependent. Available tools may include files, code execution, shell or workflow systems, analysis packages, search or literature systems, databases, remote compute, laboratory automation, instruments, robotic platforms, or other project-specific interfaces. Scientific Research OS does not itself provide those connectors; it governs their use when the host environment provides them.

## What the researcher should see

Zero-config does not mean the system works invisibly.

The researcher should be able to tell:

- what scientific question the system thinks is current;
- what is established evidence versus interpretation;
- which alternatives still matter;
- what the next decision is;
- whether a task is being reasoned about, executed, reviewed, or handed off;
- which tools or external executors materially produced an important result;
- what persistent project artifacts have been created or updated;
- where the historical chain behind important results can be inspected.

When a persistent workspace is available and the project becomes worth tracking, the system should normally maintain two complementary views:

```text
RESEARCH_STATE.md  -> current scientific state
PROVENANCE.md      -> important historical and reproducibility chain
```

A typical acknowledgement can be as simple as:

```text
Scientific Research OS is tracking this project.

Current question: ...
Main uncertainty: ...
Next decision: ...

Execution:
- bounded mission M-0012
- used available analysis / compute tools
- acceptance check passed

Updated:
- RESEARCH_STATE.md
- PROVENANCE.md (new reproducibility entry P-0007)
```

The researcher does not fill these files out. They are AI-maintained and researcher-readable.

## Current state versus history

`RESEARCH_STATE.md` is intentionally concise and mutable. It shows where the project is now.

Historical records should not be overwritten just because the project changes direction. Important earlier results, missions, reviews, decisions, code/data versions, tools/executors, and execution records should remain traceable through `PROVENANCE.md` or equivalent project-native records.

This means a future researcher or AI should be able to answer:

> Why do we currently believe this?

and then follow the chain back to:

```text
scientific question
-> mission / protocol
-> input data or sample
-> code / method / environment / parameters
-> tool / instrument / workflow / executor
-> execution or experiment run
-> outputs
-> review
-> decision
-> later correction or supersession, if any
```

## What the system should do automatically

The framework should infer the minimum structure needed for the current problem. It may internally identify the key uncertainty, competing explanations, useful evidence, acceptance criteria, or a bounded execution mission, but the researcher should not have to fill templates or configure agent roles just to begin.

Use the lightest workflow that preserves scientific rigor:

- simple question -> reason directly;
- ambiguous result -> separate evidence, interpretation, alternatives, and next test;
- clear tool-executable task -> create a bounded mission and use available authorized tools to execute it;
- task that cannot be executed in the current environment -> create a precise handoff to the appropriate human, instrument, workflow, or external agent;
- expensive or consequential task -> define acceptance / stop conditions and obtain human approval when needed before execution;
- returned result -> check technical completion before scientific interpretation;
- important conclusion -> perform an independent claim/evidence review;
- persistent important work -> preserve provenance sufficient for later audit/reproduction;
- long-running project -> maintain current state, historical decisions, provenance, and revision triggers.

Do not create heavy metadata for trivial work. Preserve history in proportion to scientific value and reproducibility risk.

## What project files may appear

The system should create persistent artifacts only when they have a real purpose. A project might eventually contain:

```text
RESEARCH_STATE.md
PROVENANCE.md
missions/
reviews/
decisions/
data/
code/
runs/
```

This is not a required folder structure. Existing project organization should be preserved whenever possible.

The important behavior is that the system tells the researcher what it created, what materially executed the work, keeps `RESEARCH_STATE.md` readable, and never lets the current-state summary erase the historical chain required for reproducibility.

## When to ask the researcher

Do not ask for configuration that can be inferred safely. Ask only when the missing choice would materially change scientific interpretation, cost, access to data/tools, confidentiality, safety/approval constraints, or an irreversible action.

Having a tool available is not the same as having permission to use it. Expensive, irreversible, privacy-sensitive, safety-sensitive, ethically regulated, or strategically consequential execution should receive appropriate human approval.

## Optional control

Researchers can always override the default behavior in natural language, for example:

> Keep this lightweight.

> Show me the current research state.

> Show me the provenance behind this conclusion.

> Challenge my hypothesis aggressively.

> Turn this into an execution mission.

> Use the available tools to carry this mission out.

> Prepare the mission, but do not execute it yet.

> Do not run anything expensive without asking me first.

> Review the result as a skeptical referee.

## Core principle

> **Automate the complexity, preserve the scientific transparency and history.**

Scientific Research OS should reduce avoidable error and cognitive overhead without turning research into a rigid or opaque procedure. When tool execution is available, automation should extend the scientific workflow rather than hide it: the user should still be able to see what was executed, what evidence came back, and how that changed the scientific state.
