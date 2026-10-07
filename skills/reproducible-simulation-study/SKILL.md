---
name: reproducible-simulation-study
description: "Define, execute, or review a simulation experiment with explicit variable dependencies, run provenance, verification evidence, and bounded scientific claims."
---

# Reproducible Simulation Study

Start with the question, target quantities, intended domain, and what evidence would answer it. Distinguish experimental design, solver implementation, numerical verification, comparison with physical data, and optimization. Do not introduce an expensive solver or training pipeline when the current task is to define an experiment.

Identify independent, controlled, derived, and response variables. Write dependency equations before choosing a sweep. A derived variable cannot also be fixed independently unless the model permits it. Record units, coordinate frames, reference quantities, and constraints; mark unresolved choices as decisions needed rather than using convenient defaults.

Select model fidelity against the question and available evidence. Set acceptance criteria before inspecting outcomes. Include numerical convergence and reference-case checks where relevant; separate these from physical validation and surrogate agreement. Use [NASA's V&V tutorial](https://www.grc.nasa.gov/www/wind/valid/tutorial/tutorial.html) when that terminology needs grounding. Do not claim certification from a software test.

For each executed run, capture a unique ID, experiment revision, code revision plus dirty state, resolved settings, environment/model/data versions, inputs, random seed when applicable, start/end time, status, warnings, outputs, and reproduction command. Record defaults as used, not merely an incomplete input file. Preserve failed, interrupted, and excluded runs with reasons.

Tie plots and summary tables to run IDs and processing revisions. Declare whether reproduction means byte equality or numerical agreement within a justified tolerance. Compare only commensurate cases and report missing evidence, sensitivity, and validity limits.

Deliver the requested experiment definition, run manifest, or evidence-backed report. Label planned computations as planned. Read [the worked example](references/worked-example.md) before defining an aerodynamic geometry sweep.
