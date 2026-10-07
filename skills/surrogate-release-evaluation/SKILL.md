---
name: surrogate-release-evaluation
description: "Evaluate whether a scientific ML surrogate is ready for a declared domain using grouped holdouts, baselines, calibrated uncertainty, OOD behavior, and a traceable model card."
---

# Surrogate Release Evaluation

Fix the intended use, prediction targets, reference data, applicability domain, and acceptance criteria before measuring performance. Preserve the user's model choice unless evidence motivates a comparison. A complex architecture must justify its added cost against an appropriate baseline; no single model family is presumed best.

Audit the split for correlated geometry/case lineage, near duplicates, recipe mixing, and preprocessing leakage. Reserve test data from model selection and uncertainty calibration. If thresholds or architecture were repeatedly tuned on the test set, label that contamination and use new independent evidence before a release claim.

Evaluate target-specific absolute and relative errors with declared units, denominator behavior near zero, sample counts, and important domain slices. Inspect tails and worst cases rather than only average loss. Separate error against simulation labels from numerical/modeling error and physical-data agreement. Good fit to biased labels is not proof of physical validity.

Assess uncertainty on held-out calibration and evaluation data. Report interval coverage alongside width and slice behavior. Ensemble spread or a nominal sigma band is not calibrated merely because it looks plausible. Calibrated in-domain coverage does not establish coverage outside the supported distribution.

Exercise explicit out-of-domain and malformed-input behavior. Define whether the API refuses, warns, or routes to another method, and make that state visible to downstream consumers. Do not show an unsupported prediction with a reassuring uncertainty band. Choose domain tests from actual failure modes; thresholds require evidence or a stated product decision.

Produce a release decision of supported, blocked, or evidence incomplete against the declared criteria. Include dataset/model/code revisions, baseline comparison, slice metrics, calibration, latency/resources, refusal cases, and limitations in a model card. No training, GPU spend, deployment, or promotion is authorized solely by writing the evaluation plan.

Read [the worked example](references/worked-example.md) when designing the release comparison.
