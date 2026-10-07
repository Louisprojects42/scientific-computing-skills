---
name: airfoil-geometry-validation
description: "Validate and canonicalize ordered airfoil coordinate data before meshing, similarity grouping, or ML preprocessing. Use for DAT ingestion, contour normalization, and shape-quality checks."
---

# Airfoil Geometry Validation

Identify the coordinate format and physical conventions before transforming the data. Distinguish a single ordered contour from separate upper/lower surface blocks and from an unordered cloud. Inspect declared counts and actual records; numeric header lines can be counts rather than coordinates. See [the UIUC airfoil data site](https://m-selig.ae.illinois.edu/ads.html) for source datasets and their provenance.

Retain the raw source and record each transformation. Validate finite numeric coordinates, sufficient distinct points, nonzero extent, duplicate/near-duplicate handling, ordering, self-intersection, and endpoint semantics. Preserve a finite trailing-edge gap when that is the intended shape; do not auto-close every contour or sort all points by x. An unordered cloud needs an explicit reconstruction method, not guessed ordering.

Define leading/trailing-edge landmarks, chord reference, origin, orientation, scale, surface direction, and tolerance units. Use project conventions when present. Canonicalize consistently across translated/rotated/scaled equivalents and document cases with ambiguous landmarks. Sharp and blunt trailing edges need distinct handling.

Resample along the contour with explicit surface allocation and landmark retention. Do not let interpolation erase a leading-edge region or create a crossing. Quantify resampling/reconstruction error in declared chord units; do not import one project's point count or tolerance as a universal requirement.

For shape similarity, compare commensurate representations and report both aggregate and worst-case deviations where needed. A diagnostic descriptor filter may miss close pairs unless its no-false-negative property is established. Keep similarity grouping thresholds and family lineage separate from the input validity decision.

Verify invariance, reversed ordering, repeated endpoints, coarse contours, blunt trailing edges, malformed files, and self-intersection using synthetic or licensed fixtures. Return accepted/rejected status, reasons, transformation metadata, and measured error. Geometry validity alone does not prove mesh quality or aerodynamic accuracy.

Read [the worked example](references/worked-example.md) for format and identity traps.
