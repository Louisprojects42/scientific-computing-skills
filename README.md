# Scientific Computing Skills

Define reproducible simulation studies, validate airfoil geometry, design dataset contracts, and evaluate surrogate models.

Four portable Agent Skills for Claude and ChatGPT/Codex. They contain original workflow guidance and synthetic examples, with no application source, credentials, live data, or project-specific infrastructure.

## Skills

| Skill | Use it for |
| --- | --- |
| [Reproducible Simulation Study](skills/reproducible-simulation-study/SKILL.md) | Define, execute, or review a simulation experiment with explicit variable dependencies, run provenance, verification evidence, and bounded scientific claims. |
| [Airfoil Geometry Validation](skills/airfoil-geometry-validation/SKILL.md) | Validate and canonicalize ordered airfoil coordinate data before meshing, similarity grouping, or ML preprocessing. Use for DAT ingestion, contour normalization, and shape-quality checks. |
| [Simulation Dataset Contracts](skills/simulation-dataset-contracts/SKILL.md) | Design or review solver-independent simulation datasets and schema evolution, including units, recipe provenance, lineage-based splits, rejection records, and reproducible releases. |
| [Surrogate Release Evaluation](skills/surrogate-release-evaluation/SKILL.md) | Evaluate whether a scientific ML surrogate is ready for a declared domain using grouped holdouts, baselines, calibrated uncertainty, OOD behavior, and a traceable model card. |

## Try a workflow

- `reproducible-simulation-study`: Define a simulation study with clear variable roles and reproducible runs.
- `airfoil-geometry-validation`: Validate and normalize these airfoil coordinates without silently changing the shape.
- `simulation-dataset-contracts`: Define a simulation dataset contract and leakage-safe release manifest.
- `surrogate-release-evaluation`: Evaluate this surrogate against a baseline and a declared release domain.

Each skill is self-contained under skills/. Its SKILL.md is the entrypoint; references/ provides a worked example; agents/openai.yaml supplies optional OpenAI UI metadata. The two helper-bearing skills across this collection need Python 3.11+; other workflows use the tools already available in the host.

Read [installation and compatibility](INSTALL.md). Each skill works from the same source folder across hosts; there are no separate copies to drift apart. Host permissions and available tools still determine what can execute.

## Check and package

From this folder, using Python 3.11+ with the standard library:

```text
python -B scripts/validate.py
python -B -m unittest discover -s tests -v
python -B scripts/package.py
```

The last command creates one ZIP per skill under dist/. Each archive has one top-level skill folder. Validation checks structure, links, metadata, obvious private-path/credential patterns, and Python syntax. Run the unittest command only in packs containing tests/. Tests check helper behavior where present. [Behavioral evaluation prompts](evals/README.md) are provided for manual testing; no AI-model pass rate is claimed. CI is included for Windows and Linux and has not been run remotely.

## Sharing

This folder is an independent GitHub-ready repository. Review the files, publish it to a repository you own, and share its URL. plugin.json and .claude-plugin/plugin.json provide OpenAI/portable and Claude packaging metadata. No marketplace listing, remote repository, or publication is created automatically.

The newly authored content and helpers are MIT licensed; see [LICENSE](LICENSE) and [provenance](PROVENANCE.md). Linked documentation and original project materials retain their own terms.
