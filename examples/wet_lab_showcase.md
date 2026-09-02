# Wet-Lab Showcase — From an Observation to a Discriminating Experiment

> Synthetic example. It illustrates the Scientific Research OS working mode, not a domain protocol.

## Researcher starts normally

> A treatment group shows a reproducible increase in phenotype X. I suspect pathway Y is involved. What should I test next?

No framework setup is required.

## Scientific Research OS first reframes the decision

**Current observation**

- phenotype X is higher in the treated group under the conditions observed so far.

**What is not established**

- that pathway Y caused the phenotype;
- that the effect is independent of batch, toxicity/stress, measurement artifacts, or another pathway.

**Competing explanations**

- H1 — pathway Y contributes causally to phenotype X;
- H2 — treatment changes phenotype X through another biological process correlated with Y;
- H3 — a batch, handling, or measurement effect produces the apparent difference;
- H4 — a nonspecific treatment effect changes both Y-related readouts and phenotype X.

**Highest-value next question**

What observation would most efficiently distinguish a Y-dependent effect from these alternatives?

## The next experiment is chosen for information gain

Rather than proposing a long experiment list, the system recommends a small decision-oriented test set, for example:

- reproduce the phenotype in an independent experimental batch with appropriate controls;
- measure an orthogonal Y-related readout rather than relying on the same signal used to define the hypothesis;
- perturb Y in a way appropriate to the domain and compare the phenotype under pre-defined conditions;
- preserve controls needed to distinguish nonspecific treatment effects or measurement artifacts.

The exact biological method is domain-specific. Scientific Research OS structures the scientific decision without pretending that one universal wet-lab protocol fits every system.

Before execution, the key comparison and acceptance criteria are frozen so that the interpretation is not silently changed after seeing the data.

## If this becomes a persistent project

The system may automatically maintain:

```text
RESEARCH_STATE.md
PROVENANCE.md
missions/mission_001.md
```

A concise state might read:

```text
Current question:
Does pathway Y contribute to the treatment-associated increase in phenotype X?

Established evidence:
Phenotype X increased in the original treatment comparison.

Open uncertainty:
Y dependence has not yet been separated from batch, nonspecific effects, or correlated pathways.

Next decision:
Run the pre-defined discriminating experiment before expanding the mechanism claim.
```

The researcher did not have to fill out these files manually.

## What provenance preserves

For an important wet-lab result, the project record may retain only the metadata that materially affects audit or repeatability, such as:

- sample/specimen identifiers and preparation history;
- reagent/material identity and relevant batch or lot;
- protocol version and important deviations;
- controls and replicate structure;
- experimental batch and critical environmental/timing conditions;
- instrument/settings when they affect the result;
- raw-data location and sample-to-measurement mapping.

It does **not** require irrelevant fields such as code commits or random seeds unless computation is actually part of the work.

## Results come back

Suppose the independent batch reproduces phenotype X, the orthogonal Y readout changes consistently, and perturbing Y weakens the phenotype.

Scientific Research OS updates the interpretation conservatively:

**Supported more strongly**

- the treatment-associated phenotype is reproducible under the tested conditions;
- Y is functionally linked to the phenotype under the tested perturbation.

**Still not proven**

- a complete molecular mechanism;
- that Y is the only causal route;
- generalization beyond the tested system and conditions.

**Claim boundary**

> The evidence supports a functional contribution of Y to phenotype X under the tested conditions; it does not yet establish a complete or universal mechanism.

## Months later, a hidden batch dependence appears

The old result is not deleted.

Instead:

```text
P-0001  Original experiment — accepted at the time
P-0017  Batch-dependence analysis — changes interpretation
        supersedes the relevant interpretation of P-0001
```

`RESEARCH_STATE.md` shows the new current conclusion, while `PROVENANCE.md` preserves how the project got there.

## What this showcase demonstrates

```text
ordinary wet-lab question
        -> competing explanations
        -> smallest discriminating experiment
        -> bounded execution
        -> experimental provenance
        -> evidence-controlled interpretation
        -> updated state without rewriting history
```

The framework structures scientific reasoning; it does not replace the researcher's experimental expertise or judgment.
