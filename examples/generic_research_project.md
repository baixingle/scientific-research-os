# Five-Minute Generic Research Walkthrough

This example is intentionally synthetic and domain-neutral. It demonstrates how Scientific Research OS should feel to a new researcher without requiring framework configuration.

## 1. Start with an ordinary scientific question

**Researcher:**

> We repeatedly observe phenomenon X after changing condition C. I suspect mechanism Y is involved, but I am not sure whether Y is causal or only correlated. I want to start a project around this. What should I do first?

**Scientific Research OS should respond approximately like this:**

```text
Current scientific question:
Does Y causally contribute to X, or do Y and X respond to another change caused by C?

What is established:
- X changes reproducibly after C.
- Y is associated with the same condition.

What is not established:
- Y has not yet been shown to cause X.

Decision-relevant explanations:
H1: Y contributes causally to X.
H2: Y is a correlated response while another variable drives X.
H0: the current framework already explains X without invoking Y.

Most informative next step:
Choose the lowest-cost observation or perturbation that produces different predictions under H1 and H2.

Current claim boundary:
The present evidence supports an association between Y and X, not a mechanism.
```

If a persistent workspace is available and the project is now worth tracking, the system may create:

```text
RESEARCH_STATE.md
PROVENANCE.md
```

The researcher should be told that these files were created and what they are for. The researcher does not fill them out manually.

## 2. The researcher accepts a proposed test

**Researcher:**

> Good. Run the discriminating analysis you proposed using the existing dataset. Keep it lightweight.

The system should create only the structure needed for reliable execution.

For example, it may internally prepare a bounded mission:

```text
Objective:
Test whether the early response of Y distinguishes samples that later show X from those that do not.

Inputs:
Existing dataset D and frozen preprocessing definition.

Required outputs:
- comparison statistic;
- uncertainty estimate;
- diagnostic plot;
- reproducibility metadata.

Acceptance criteria:
Use the pre-defined comparison and report the result whether positive or negative.

Stop condition:
Do not scan alternative windows, features, or thresholds after seeing the result unless a new exploratory mission is explicitly created.
```

The user should not have to write this mission manually.

A provenance entry may then record the important execution details:

```text
P-0001
Purpose: distinguish H1 from H2 using existing data
Input: dataset D, version 1
Method: analysis definition A
Code/environment: recorded version identifiers
Outputs: linked result files
Mission: linked mission record
Status: active -> accepted / rejected / failed
```

## 3. The result comes back

Assume the result shows a strong early difference in Y.

**Researcher:**

> The analysis is finished. What does it actually tell us?

A useful review should say something like:

```text
Observed:
Y differs before the later appearance of X under the frozen analysis.

Supported interpretation:
This strengthens H1 relative to a purely simultaneous association.

Still unresolved:
Temporal precedence alone does not establish causality. H2 remains possible if another upstream variable changes Y first and X later.

Claim boundary:
The result supports temporal localization of Y before X. It does not yet establish Y as the causal mechanism.

Next decision:
Decide whether a targeted perturbation or independent validation is worth the cost.
```

The system can now update:

```text
RESEARCH_STATE.md   # current understanding and next decision
PROVENANCE.md       # P-0001 result and links
reviews/...         # if a formal review was justified
decisions/...       # if the result changed project direction
```

The researcher is briefly told what changed.

## 4. Later evidence overturns part of the interpretation

Months later, an independent experiment shows that manipulating Y does not change X.

Scientific history should **not** be rewritten as if P-0001 never existed.

Instead, add a new record:

```text
P-0002
Purpose: independent causal validation of Y -> X
Result: perturbing Y did not change X
Status: accepted
Supersedes interpretation linked to P-0001
```

Then update the current state:

```text
Current interpretation:
Y is an early marker associated with the pathway to X, but current evidence does not support Y as the causal driver.

Historical record:
P-0001 remains preserved as a valid earlier observation.
P-0002 explains why the causal interpretation was revised.
```

This distinction is essential:

> **State shows what the project currently believes. Provenance preserves what actually happened. Decision memory preserves why the interpretation changed.**

## 5. What the new user had to configure

Nothing framework-specific.

The researcher only:

1. described the scientific problem;
2. approved or redirected meaningful scientific choices;
3. provided data or access when needed;
4. inspected the resulting state, evidence, and decisions.

The framework handled the rest proportionally to the problem.

## Takeaway

Scientific Research OS should feel like a rigorous scientific collaborator, not a form-filling system.

It should make the project easier to reason about **now** while preserving enough evidence, decisions, and provenance to understand and reproduce the research **later**.
