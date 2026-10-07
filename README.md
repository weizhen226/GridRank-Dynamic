# GridRank-Dynamic

Research materials for **GridRank-Dynamic: Safe Distribution Network
Reconfiguration with Large Language Models under Dynamic Operating Instructions**.

The package contains simulation-derived datasets, evaluation results, source
code, experimental protocols, and task-specific LoRA adapters. Experiments
use IEEE 33-bus, IEEE 69-bus, and SimBench networks.

## Downloads

- [Data and code](GridRank_Dynamic_Data_Code.zip)
- [Complete download bundle](https://github.com/weizhen226/GridRank-Dynamic/releases),
  including the data/code archive and both model archives
- [Archive checksums](SHA256SUMS.txt)

Download files named `GridRank_Dynamic_Data_Code.zip`,
`GridRank_Dynamic_Core_LoRA.tar.gz`, and
`GridRank_Dynamic_Supplementary_LoRA.tar.gz`.
Extract all three into the same directory. They share a `gridrank_dynamic/`
root containing `datasets/`, `src/`, `results/`, `protocols/`, `models/`,
`environment/`, `manifests/`, `docs/`, and `tools/`.

The adapter family is **Llama-GridRank-Dynamic**. Built with Llama.
The external Meta-Llama-3.1-8B-Instruct base model is not included.

## Quick start

From the extracted directory, use Python 3.10 or later:

```bash
cd gridrank_dynamic
python -B tools/verify_package.py
python -B tools/recompute_point_estimates.py
```

These standard-library checks validate stored data and recompute principal
point estimates. They do not perform model training, GPU inference, or
AC power-flow simulation.

Experiment scripts can be run through `tools/run_experiment.py`, which prepares
a separate workspace without changing the supplied files. Read
`docs/REPRODUCTION_WORKFLOW.md` inside the package for model-dependent steps,
runtime requirements, and the scope of the supplied checks.

## File integrity

Place the three downloaded archives and the archive-level `SHA256SUMS.txt`
in one directory. On macOS or Linux:

```bash
shasum -a 256 -c SHA256SUMS.txt
```

## Rights and dependencies

Consult `docs/RIGHTS_AND_THIRD_PARTY.md` inside the data/code package for reuse
conditions. Each adapter archive includes the Llama 3.1 Community License
and attribution notice. Third-party materials retain their respective licenses.
