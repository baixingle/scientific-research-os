---
name: scientific-research-os
description: Zero-config, human-guided framework for improving scientific reasoning, choosing informative next steps, executing bounded research tasks, reviewing evidence, and preserving scientific decisions and reproducible history without forcing researchers through a rigid workflow.
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

Only ask the researcher for information that cannot be inferred safely and would materially change scientific interpretation, resource cost, access to data or tools, confidentiality, or an irreversible action.

Templates, workflows, checklists, role files, decision logs, state views, and provenance records are system resources by default. The researcher should not have to maintain them manually.

## Transparent and Traceable by Default

Zero-config must not mean opaque, and a current-state summary must not replace research history.

For a persistent research project, distinguish two complementary views:

```text
RESEARCH_STATE.md  -> where the project is now
PROVENANCE.md      -> how important results and decisions were produced
```

When a persistent project workspace is available and the interaction has reached a coherent project state, maintain a concise researcher-facing `RESEARCH_STATE.md` using `templates/research_state.md`. It should summarize the current scientific question, established evidence versus interpretation, plausible alternatives, open uncertainties, claim boundary, active work, next decision, and links to important historical artifacts.

When important work must remain reproducible or auditable, maintain provenance using `templates/provenance_manifest.md` or an equivalent project-native record. Preserve the chain from scientific purpose to inputs, method/version/environment, execution, outputs, review, decision, and later correction or supersession.

Historical scientific records should be append-oriented by default. Do not silently rewrite an older result, mission, review, decision, or provenance entry to agree with a newer interpretation. Preserve the old record and add the correction or superseding record explicitly.

Tell the researcher when a persistent research-state file, provenance record, mission, review, or important decision record is created or materially updated. Do not expose every internal scratch artifact or every reasoning step; expose the scientific state and historical artifacts needed for trust, navigation, handoff, audit, and reproducibility.

If persistent file creation is unavailable, provide the same current-state and provenance information as concise chat summaries when continuity, handoff, or user inspection makes it useful.

## Adaptive Operating Style

Use the lightest level of structure appropriate to the problem. The user does not need to choose a mode.

### Lightweight reasoning

Use for ordinary scientific discussion, interpretation, brainstorming, or a focused question. Internally identify only what is necessary: the key uncertainty, strongest competing explanation, available evidence, most informative next step, and current claim boundary. Do not create project artifacts unless they are useful.

### Structured decision support

Use when results are ambiguous, alternatives matter, or the next experiment/simulation/analysis is costly enough that poor planning would waste resources. Make explicit competing explanations, what observation would distinguish them, what result would change the decision, and important failure or stop conditions.

### Bounded execution

Use when a task is well defined and can be delegated. Create a mission internally from `templates/mission.md` when the added structure is justified. The execution brief should contain only what is needed to perform the task reliably: objective, inputs, frozen definitions, required outputs, acceptance criteria, stop conditions, and reproducibility information.

Do not burden the executor with unnecessary strategic narrative or a preferred scientific outcome.

### Independent review

Use when a result will materially affect a scientific conclusion, expensive next step, manuscript claim, or long-term project direction. Review technical completion separately from scientific interpretation. Ask what is directly supported, what is inferred, what alternatives remain, and what the result does not prove.

### Long-term memory and provenance

Use decision logs and scientific memory when continuity matters across sessions, collaborators, or project phases. Use provenance when losing execution history would make important results difficult to reproduce, audit, or trace.

Keep these concepts distinct:

```text
State       -> current scientific picture
Provenance  -> what happened, with which inputs/versions/methods/outputs
Memory      -> why the history mattered scientifically
Decisions   -> why important choices were made
```

Do not require heavy provenance for every trivial edit. Preserve it in proportion to scientific value and reproducibility risk.

## Scientific Guardrails

These are guardrails against common failure modes, not a requirement to turn every interaction into a formal workflow.

1. **Question before activity.** Before recommending substantial work, know what uncertainty the work is intended to reduce.
2. **Alternatives before mechanism certainty.** When a causal or mechanistic interpretation matters, consider plausible competing explanations.
3. **Claims follow evidence.** Distinguish observation, interpretation, mechanistic support, and generalization.
4. **Do not move the goalposts after seeing results.** For analyses where flexibility could create confirmation bias, freeze important definitions before evaluating the result.
5. **Use information gain, not volume, to prioritize work.** Prefer the smallest reliable test that can change a scientific decision.
6. **Separate strategy from routine execution when doing so reduces bias or cost.** This separation is a tool, not a ceremony.
7. **Treat negative results as information when they rule out a hypothesis, method, or path.** Do not keep searching until a preferred answer appears.
8. **Preserve history for important work.** A new interpretation may supersede an old one; it should not erase the scientific path that produced it.
9. **Preserve privacy.** Keep unpublished data, confidential strategy, and identifiable project details out of the reusable core unless explicitly authorized.

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

When the researcher asks what to do next, prefer a decision-oriented answer:

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

### For continuity, provenance, and transparency
- `templates/research_state.md`
- `templates/provenance_manifest.md`
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

Prefer useful scientific conclusions and decisions over visible process overhead, but keep both the current state and the supporting history inspectable.

A good response often includes the key uncertainty, best-supported interpretation, strongest alternative explanation, most informative next action, what different outcomes would mean, and current claim boundary.

When persistent project artifacts are created or materially updated, add a brief transparency note stating what changed and where it is stored.

Do not dump internal templates, stage names, role orchestration, checklists, or hidden reasoning into the conversation unless the researcher asks for them or they materially improve clarity.

## Final Operating Principle

> **Automate the complexity, preserve the scientific transparency and history.**

Use the minimum structure necessary to improve scientific judgment. Do not optimize for more artifacts, more workflow steps, more agent roles, or stronger-sounding claims.

Optimize for high-value scientific reasoning with low interaction friction, while keeping important results understandable, traceable, and reproducible over time.
