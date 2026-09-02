# Scientific Research OS Quick Start

## Start with the science

There is no framework-specific setup required before the first useful interaction.

Describe the research problem in ordinary language. For example:

> I observed X, I suspect Y may be involved, but I am not sure what would distinguish Y from the alternatives. What should I do next?

or:

> Here are the latest results. What do they actually support, what remains uncertain, and what is the most informative next step?

That is enough to start.

## What the researcher should see

Zero-config does not mean the system works invisibly.

The researcher should be able to tell:

- what scientific question the system thinks is current;
- what is established evidence versus interpretation;
- which alternatives still matter;
- what the next decision is;
- what persistent project artifacts have been created or updated.

When a persistent workspace is available and the project becomes worth tracking, the system should normally create or update a concise `RESEARCH_STATE.md` automatically and tell the researcher where it is.

A typical acknowledgement can be as simple as:

```text
Scientific Research OS is tracking this project.

Current question: ...
Main uncertainty: ...
Next decision: ...

Updated: RESEARCH_STATE.md
```

The researcher does not fill this file out. It is an AI-maintained view of the current scientific state.

## What the system should do automatically

The framework should infer the minimum structure needed for the current problem. It may internally identify the key uncertainty, competing explanations, useful evidence, acceptance criteria, or a bounded execution mission, but the researcher should not have to fill templates or configure agent roles just to begin.

Use the lightest workflow that preserves scientific rigor:

- simple question -> reason directly;
- ambiguous result -> separate evidence, interpretation, alternatives, and next test;
- expensive or multi-step task -> create a bounded mission and acceptance criteria;
- important conclusion -> perform an independent claim/evidence review;
- long-running project -> maintain research state, decisions, and revision triggers.

Templates, checklists, workflows, and agent-role files are implementation resources. They should appear to the user only when they make the work clearer, more reliable, or easier to inspect and hand off.

## What project files may appear

The system should create persistent artifacts only when they have a real purpose. A lightweight project might eventually contain:

```text
RESEARCH_STATE.md
missions/
reviews/
decisions/
```

This is not a required folder structure. Existing project organization should be preserved whenever possible.

The important behavior is that the system tells the researcher what it created and keeps `RESEARCH_STATE.md` readable as the project evolves.

## When to ask the researcher

Do not ask for configuration that can be inferred safely. Ask only when the missing choice would materially change scientific interpretation, cost, access to data/tools, confidentiality, or an irreversible action.

## Optional control

Researchers can always override the default behavior in natural language, for example:

> Keep this lightweight.

> Show me the current research state.

> Challenge my hypothesis aggressively.

> Turn this into an execution mission.

> Do not run anything expensive without asking me first.

> Review the result as a skeptical referee.

## Core principle

> **Automate the complexity, preserve the scientific transparency.**

Scientific Research OS should reduce avoidable error and cognitive overhead without turning research into a rigid or opaque procedure.
