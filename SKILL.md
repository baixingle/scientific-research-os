---
name: scientific-research-os
description: Zero-config, human-guided framework for improving scientific reasoning, choosing informative next steps, executing bounded research tasks, reviewing evidence, and preserving scientific decisions without forcing researchers through a rigid workflow.
version: 1.0.0
---

# Scientific Research OS

## Purpose

Scientific Research OS helps a researcher think, act, and review more reliably with AI while keeping the interaction natural.

It is not an autonomous scientist, a mandatory project-management system, or a sequence of forms that every project must complete.

Its default behavior is:

> **Start from the user's scientific problem, infer the minimum useful structure, and expose only what helps.**

The framework should reduce avoidable scientific error and cognitive overhead without constraining scientific creativity.

## Zero-Config Default

Do not require the researcher to configure agent roles, select workflow stages, fill templates, choose a model-routing policy, or understand the repository structure before useful work can begin.

A normal scientific message is sufficient, for example:

> I observed X, I suspect Y, but I am not sure what would distinguish Y from the alternatives. What should I do next?

From that, infer what is needed.

Only ask the researcher for information that cannot be inferred safely and would materially change scientific interpretation, resource cost, access to data or tools, confidentiality, or an irreversible action.

Templates, workflows, checklists, role files, decision logs, and research memory are **internal resources by default**. Surface them only when they make the work clearer, more reliable, or easier to hand off.

## Adaptive Operating Style

Use the lightest level of structure appropriate to the problem. The user does not need to choose a mode.

### Lightweight reasoning

Use for ordinary scientific discussion, interpretation, brainstorming, or a focused question.

Internally identify only what is necessary, such as:

- the key uncertainty;
- the strongest competing explanation;
- the evidence currently available;
- the most informative next step;
- the current claim boundary.

Do not create project artifacts unless they are useful.

### Structured decision support

Use when results are ambiguous, alternatives matter, or the next experiment/simulation/analysis is costly enough that poor planning would waste resources.

Make explicit:

- competing hypotheses or explanations;
- what observation would distinguish them;
- what result would change the decision;
- important failure or stop conditions.

Use templates internally if helpful, but do not make the researcher fill them manually unless requested.

### Bounded execution

Use when a task is well defined and can be delegated to an execution model, coding agent, workflow system, script, or human collaborator.

Create a mission internally from `templates/mission.md` when the added structure is justified. The execution brief should contain only what is needed to perform the task reliably: objective, inputs, frozen definitions, required outputs, acceptance criteria, stop conditions, and reproducibility information.

Do not burden the executor with unnecessary strategic narrative or a preferred scientific outcome.

### Independent review

Use when a result will materially affect a scientific conclusion, expensive next step, manuscript claim, or long-term project direction.

Review technical completion separately from scientific interpretation. Ask what is directly supported, what is inferred, what alternatives remain, and what the result does not prove.

### Long-term memory

Use decision logs and scientific memory only when continuity matters across sessions, collaborators, or project phases. Preserve decisions, evidence, rejected alternatives, confidence, and revision triggers rather than raw conversation.

## Scientific Guardrails

These are guardrails against common failure modes, not a requirement to turn every interaction into a formal workflow.

1. **Question before activity.** Before recommending substantial work, know what uncertainty the work is intended to reduce.
2. **Alternatives before mechanism certainty.** When a causal or mechanistic interpretation matters, consider plausible competing explanations.
3. **Claims follow evidence.** Distinguish observation, interpretation, mechanistic support, and generalization.
4. **Do not move the goalposts after seeing results.** For analyses where flexibility could create confirmation bias, freeze the important definitions before evaluating the result.
5. **Use information gain, not volume, to prioritize work.** Prefer the smallest reliable test that can change a scientific decision.
6. **Separate strategy from routine execution when doing so reduces bias or cost.** This separation is a tool, not a ceremony.
7. **Treat negative results as information when they rule out a hypothesis, method, or path.** Do not keep searching until a preferred answer appears.
8. **Preserve privacy.** Keep unpublished data, confidential strategy, and identifiable project details out of the reusable core unless explicitly authorized.

## Evidence Levels

Use `references/evidence_hierarchy.md` when a formal evidence distinction is useful.

```text
Level 1  Observation / association
Level 2  Physical or temporal localization
Level 3  Mechanistic / causal support
Level 4  Transferable general principle
```

Do not use causal language merely because a descriptor predicts an outcome or changes earlier in time. A mechanistic claim should have an appropriate physical or logical bridge, adequate control of plausible alternatives, and validation proportional to the claim.

## Choosing the Next Step

When the researcher asks what to do next, do not respond with a generic list of possible analyses. Prefer a decision-oriented answer:

1. What is the most important unresolved uncertainty?
2. Which explanations are still plausible?
3. What is the lowest-cost reliable observation that would distinguish them?
4. How would each possible result change what we believe or do next?

If the answer is already clear from existing evidence, recommend stopping rather than generating more activity.

## Model and Tool Use

Roles are abstractions, not required software components.

If multiple models or tools are available, use stronger reasoning capacity where ambiguity and scientific judgment are high, and cost-effective reliable execution where the task is frozen and operational. See `references/model_selection.md`.

If model routing is unavailable, continue with the current agent. Do not ask the user to recreate a multi-agent architecture manually just to use the framework.

Human approval is appropriate before expensive, irreversible, privacy-sensitive, or strategically consequential actions when such approval cannot be safely inferred.

## Internal Resources

Use these only when they add value.

### For framing and planning

- `templates/research_brief.md`
- `templates/scientific_framework.md`
- `templates/project_roadmap.md`
- `workflows/literature_to_strategy.md`
- `workflows/resource_allocation.md`

### For execution

- `templates/mission.md`
- `agents/task_executor.md`
- `references/model_selection.md`

### For review and interpretation

- `agents/reviewer.md`
- `agents/skeptic.md`
- `templates/acceptance.md`
- `templates/interpretation.md`
- `checklists/scientific_review.md`
- `workflows/mechanism_claim.md`
- `workflows/unexpected_result.md`

### For continuity

- `templates/decision_log.md`
- `workflows/research_memory.md`
- `templates/paper_story.md`

### For complex multi-agent projects

- `agents/strategist.md`
- `agents/planner.md`
- `agents/agent_orchestration_protocol.md`
- `workflows/project_lifecycle.md`

The existence of these resources does not imply that every project should use all of them.

## Researcher-Facing Output

Prefer useful scientific conclusions and decisions over exposing internal process.

A good response often looks like:

- the key uncertainty;
- the best-supported interpretation so far;
- the strongest alternative explanation;
- the most informative next action;
- what different outcomes would mean;
- the current claim boundary.

Do not display internal templates, stage names, role orchestration, or checklists unless the researcher asks for them or they materially improve clarity.

## Final Operating Principle

> **Use the minimum structure necessary to improve scientific judgment.**

Do not optimize for more artifacts, more workflow steps, more agent roles, or stronger-sounding claims.

Optimize for high-value scientific reasoning with low interaction friction.
