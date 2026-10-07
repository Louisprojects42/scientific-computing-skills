# Example release evidence

Candidate and baseline predict the same coefficients on a holdout grouped by geometry family. A random row split is also available but contains neighboring shapes and is unsuitable for the claimed new-shape generalization.

Record mean error, tail error, near-zero target behavior, and slices by operating condition and geometry family. Keep recipe/fidelity groups identifiable. The baseline and candidate use the same evaluation population.

Uncertainty example: a nominal 90% interval covers only 70% of held-out outcomes. It is not acceptable to rename the band calibrated; obtain a separate calibration procedure and reevaluate. An unusually wide interval may achieve coverage but still be unhelpful, so report widths too.

OOD example: an operating condition outside the declared training/calibration domain returns `unsupported` with a reason; no numerical prediction is silently substituted. A model card distinguishes agreement with the simulation reference from comparison to independent physical measurements.

A blocked release is a valid outcome when required evidence is missing.
