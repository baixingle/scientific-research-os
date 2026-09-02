# ML Showcase — Check Leakage Before Scaling the Model

> Synthetic example. It illustrates the Scientific Research OS working mode rather than a specific ML stack.

## Researcher starts normally

> A new feature set improves validation performance substantially. I think it captures a real scientific signal. What should I do next?

## Scientific Research OS first asks what could mimic the result

**Established**

- performance improved under the current validation procedure.

**Not established**

- that the gain reflects a transferable scientific signal;
- that the feature construction is independent of labels or future information;
- that the improvement survives dataset shift, resampling, or a truly independent test set.

**Competing explanations**

- H1 — the new features capture a real transferable signal;
- H2 — data leakage or split contamination inflates validation performance;
- H3 — the gain is specific to one split or batch;
- H4 — the features exploit a nuisance variable correlated with the target.

## The next step is not automatically a larger model

The highest-information next action is usually to challenge the evaluation design first.

A bounded validation mission might freeze:

- dataset and version;
- train/validation/test split definitions;
- preprocessing and feature-generation rules;
- leakage checks;
- baseline and ablation definitions;
- evaluation metrics;
- acceptance criteria before results are inspected.

Only after this check should additional model capacity or hyperparameter search become a priority.

## Reproducibility and provenance

For an important ML result, preserve the relevant subset of:

- dataset version and source;
- split definitions and sample IDs where appropriate;
- preprocessing and feature pipeline version;
- code commit/version;
- model configuration and hyperparameters;
- random seeds;
- software environment;
- checkpoints and raw predictions;
- evaluation script and metric definitions;
- linked review and decision records.

## Results come back

Suppose the performance gain largely disappears when groups are split independently and one nuisance variable is controlled.

Scientific Research OS should update the project state rather than search for another favorable split.

**Supported**

- the original validation procedure overstated generalization.

**Weakened**

- the claim that the feature set captures a transferable scientific signal.

**Open**

- whether a smaller residual gain survives on independent data.

**Claim boundary**

> The current evidence supports a split-sensitive association, not yet a robust transferable scientific signal.

## If an independent dataset later confirms the residual gain

The earlier result remains in provenance.

A later entry records the independent validation and may strengthen the claim without rewriting the earlier failure:

```text
P-0004  Original validation — inflated by grouping leakage
P-0012  Corrected grouped split — residual effect remains uncertain
P-0021  Independent dataset — confirms residual gain
```

## What this showcase demonstrates

```text
promising ML result
        -> alternative explanations
        -> leakage / robustness check before scaling
        -> frozen validation definitions
        -> reproducible provenance
        -> claim strength follows independent evidence
```

Scientific Research OS treats model performance as evidence that must survive the same scientific scrutiny as experimental or computational results.
