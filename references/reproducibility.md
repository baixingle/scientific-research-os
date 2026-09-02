# Reproducibility

## Principle

A reproducible scientific record preserves whatever another competent researcher would need to understand, audit, and reasonably repeat an important result.

The required metadata depends on the research domain. Do not force computational fields onto experimental work or experimental fields onto theoretical work.

Record detail in proportion to scientific value, ambiguity, and the cost of losing the history.

## Common Core

For important work, preserve enough information to trace:

```text
scientific purpose
    -> inputs / materials
    -> method or protocol
    -> critical conditions and versions
    -> execution / experiment / derivation
    -> outputs
    -> review and interpretation
    -> decision
```

Useful cross-domain elements may include:

- identifiers for inputs, samples, datasets, structures, or source material;
- method, protocol, code, model, or derivation version;
- critical parameters and conditions;
- raw or primary output location;
- deviations, failures, exclusions, or anomalies that affect interpretation;
- links to the mission, review, decision, and provenance record when they exist.

## Experimental and Wet-Lab Research

When relevant, preserve items such as:

- sample, specimen, or material identity and preparation history;
- reagent identity, vendor/catalog, batch, or lot information;
- protocol and protocol version;
- controls, replicates, randomization, or blinding;
- timing, temperature, atmosphere, incubation, handling, or other critical conditions;
- instrument identity, settings, calibration, and acquisition method;
- operator or experimental batch when scientifically relevant;
- protocol deviations and unexpected events;
- raw-data location and mapping between samples and measurements.

Not every experiment needs every item. Preserve what could materially affect interpretation or repeatability.

## Computational, Simulation, and ML Research

When relevant, preserve items such as:

- input structures, datasets, preprocessing, and split definitions;
- code repository and commit/version;
- software, dependency, and environment versions;
- parameters and model configuration;
- random seeds;
- hardware or execution environment when it can affect results;
- raw outputs, logs, checkpoints, and analysis scripts.

## Theoretical and Analytical Research

When relevant, preserve items such as:

- assumptions, definitions, and conventions;
- boundary or initial conditions;
- derivation, notebook, or manuscript version;
- numerical approximations and solver settings if used;
- external constants, reference values, or source equations that affect the result.

## History

Reproducibility includes historical traceability. If a later result changes the interpretation of earlier work, preserve the earlier record and explicitly link the correction or superseding result rather than rewriting the history.

Results without traceability are difficult to evaluate, reproduce, audit, or reuse.
