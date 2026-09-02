# Computational Showcase — Test the Explanation, Not Just More Parameters

> Synthetic example. It illustrates the Scientific Research OS working mode rather than a specific simulation package.

## Researcher starts normally

> A simulation shows an unexpected transition in observable X. I think structural variable Y may be responsible. What should I calculate next?

## Scientific Research OS separates observation from explanation

**Established**

- the transition in X appeared in the current computational setup.

**Not established**

- that Y causes the transition;
- that the result is converged or robust to sampling;
- that another structural, dynamical, or numerical factor is not responsible.

**Competing explanations**

- H1 — Y is physically linked to the transition;
- H2 — another correlated variable drives X while Y is only a marker;
- H3 — insufficient sampling creates the apparent relationship;
- H4 — a numerical or methodological choice creates the effect.

## The next calculation is chosen for discrimination

Instead of launching a broad parameter sweep, the system asks:

> What is the lowest-cost reliable calculation that would change our belief about H1 versus H2–H4?

A useful next step might therefore be a frozen comparison that deliberately separates Y from its strongest confounder, plus a convergence or independent-sampling check if that is the dominant alternative.

The exact simulation method is domain-specific. The framework decides what uncertainty should be reduced before deciding how much compute to spend.

## Bounded execution

If the calculation is expensive or delegated to another agent, Scientific Research OS can create a mission containing only execution-relevant information:

```text
Scientific objective
Frozen comparison
Input structures/data
Code/method version
Required parameters
Required outputs
Acceptance criteria
Stop conditions
Reproducibility metadata
```

The executor does not receive a preferred conclusion and cannot redefine the scientific objective after seeing the result.

## Provenance

For a consequential result, `PROVENANCE.md` can preserve:

- input structure or dataset identifiers;
- code repository and commit/version;
- software and dependency environment;
- important model or simulation parameters;
- random seeds or sampling identifiers when relevant;
- hardware/runtime details only when they can affect reproducibility;
- raw outputs, logs, and analysis scripts;
- linked mission, review, and decision records.

## Results come back

Suppose the frozen comparison weakens the original Y–X relationship while the alternative variable remains predictive under independent sampling.

The system should not search for a new post-hoc definition of Y that restores the original story.

Instead it updates the scientific state:

**Weakened**

- Y as the primary explanation.

**Strengthened**

- the alternative variable or a shared underlying process.

**Next uncertainty**

- whether the alternative variable is mechanistically relevant or still only predictive.

**Claim boundary**

> The current evidence does not support Y as the primary driver of X. The alternative variable is a better candidate, but causal interpretation requires an additional physical bridge or perturbation.

## What this showcase demonstrates

```text
unexpected simulation result
        -> competing explanations
        -> information-gain calculation
        -> frozen mission
        -> reproducible execution
        -> independent review
        -> update the hypothesis instead of moving the goalposts
```

Scientific Research OS treats compute as a scientific resource: every expensive calculation should reduce a defined uncertainty or distinguish plausible explanations.
