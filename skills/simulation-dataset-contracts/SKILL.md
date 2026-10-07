---
name: simulation-dataset-contracts
description: "Design or review solver-independent simulation datasets and schema evolution, including units, recipe provenance, lineage-based splits, rejection records, and reproducible releases."
---

# Simulation Dataset Contracts

Identify consumers and the authoritative external contract before editing schemas or models. Separate native solver archives, canonical samples, and regenerable training tensors. A canonical sample should remain interpretable without the training code or solver-specific defaults.

Define field meanings, dimensions, units/non-dimensionalization, reference frames, sign conventions, sampling locations, missing-value semantics, and domain applicability. Preserve solver/model/mesh/recipe and source-data provenance. Results from different turbulence, transition, wall-treatment, or fidelity recipes are not interchangeable just because their columns match.

Distinguish geometry identity, case identity, solver recipe, sample identity, dataset release, and transformation revision. State hashing/canonicalization rules; sorted JSON keys alone are not a universal cross-language numeric canonicalization standard. For numerical arrays, define dtype, byte order, shape, non-finite policy, and normalization before using a content hash as identity.

Assign train/validation/test at the leakage-relevant lineage unit before fitting transforms. Near-duplicate geometries, remeshes, perturbed copies, and repeated cases should not cross splits merely because filenames differ. Fit normalization on training data only. Retain rejection records and reasons so the accepted population's selection bias is inspectable.

Check schema/model agreement at compatibility-relevant boundaries: requiredness, nullable values, enums, numeric bounds, additional fields, arrays, and references. Generated-schema textual equality alone does not prove equivalent runtime acceptance or default behavior. Exercise representative accepted and rejected examples against each implementation.

Keep released datasets immutable. Changes to conventions or recipes need an explicit compatibility decision and migration/release note. Deliver the contract, example records, split/release manifest, and actual validation evidence. Read [the worked example](references/worked-example.md) for version and split cases.
