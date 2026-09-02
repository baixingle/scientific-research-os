# Contributing

Scientific Research OS should improve through **real research use**, not through feature accumulation for its own sake.

Contributions, issues, and usage reports are welcome when they help make the framework more scientifically rigorous, reproducible, transparent, domain-neutral, or easier to use.

## Especially useful contributions

Early feedback is particularly valuable in these forms:

- a case where the framework helped identify a better next experiment, calculation, analysis, or decision;
- a case where it missed an important competing explanation or encouraged an over-strong claim;
- a reproducibility or provenance failure: information that should have been preserved but was not;
- unnecessary workflow friction or documentation that the researcher should not have had to manage;
- behavior differences across AI agents or research environments;
- domain-compatibility problems in wet-lab, computational, theoretical, ML/data-science, literature-driven, or hybrid research;
- a synthetic or already-public example that demonstrates a recurring scientific failure mode.

You do not need to propose a new framework component to contribute. A clear failure report can be more valuable than a new workflow or template.

## Privacy first

Do **not** post unpublished research data, confidential scientific strategy, private datasets, credentials, identifiable participant information, or other sensitive project details in a public issue or pull request.

When possible, reduce a real problem to a synthetic or already-public example that preserves the scientific failure mode without exposing private research.

## Design principles for changes

- Prefer general scientific principles over domain-specific assumptions in the reusable core.
- Use domain-specific metadata only when it is relevant to interpretation, audit, or reproducibility.
- Preserve evidence boundaries: do not upgrade observation into mechanism or association into causation.
- Preserve important research history rather than silently rewriting it after conclusions change.
- Keep strategy and bounded execution separate when that reduces bias, ambiguity, or cost; do not make the separation ceremonial.
- Preserve zero-config use. New structure should not become new setup work for ordinary researchers.
- Every workflow or rule change should explain what scientific uncertainty, failure mode, reproducibility risk, or recurring burden it addresses.

## Before adding a new component

Ask:

1. What real problem does this solve?
2. Is the problem recurring rather than hypothetical?
3. Could the same value be achieved by simplifying or clarifying an existing component?
4. Does the change improve scientific value without adding unnecessary interaction friction?

If the answer is unclear, an issue describing the observed problem is usually better than immediately adding another agent, template, workflow, or configuration layer.

## Pull requests

Keep pull requests focused. Explain:

- the problem or failure mode;
- why the current framework is insufficient;
- the smallest change that addresses it;
- any effect on zero-config behavior, reproducibility, evidence boundaries, or privacy.

Public examples should remain synthetic or use material that is already public and appropriate to redistribute.

## Review standard

New concepts should pass:

1. Scientific usefulness.
2. General applicability or clearly justified scope.
3. Compatibility with evidence-based reasoning.
4. Reproducibility and historical traceability where relevant.
5. Low unnecessary user friction.

The goal is not to make Scientific Research OS larger. The goal is to make it more useful and trustworthy in real research.
