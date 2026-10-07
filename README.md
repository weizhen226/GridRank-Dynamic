# GridRank-Dynamic

Research materials for **GridRank-Dynamic: Safe Distribution Network
Reconfiguration with Large Language Models under Dynamic Operating Instructions**.

The package contains simulation-derived datasets, evaluation results, source
code, and experimental protocols. Task-specific LoRA adapters are distributed
separately. The experiments use IEEE 33-bus, IEEE 69-bus, and SimBench networks.

## Downloads

- [Data and code](GridRank_Dynamic_Data_Code.zip)
- [Model adapter archives](https://github.com/weizhen226/GridRank-Dynamic/releases):
  `GridRank_Dynamic_Core_LoRA.tar.gz` and
  `GridRank_Dynamic_Supplementary_LoRA.tar.gz`
- [Archive checksums](SHA256SUMS.txt)

The adapter family is named **Llama-GridRank-Dynamic**. Built with Llama.
The external Meta-Llama-3.1-8B-Instruct base model is not included.

## Data and code package

After extraction, the `GridRank_Dynamic_Research_Materials/` directory contains:

| Directory | Contents |
|---|---|
| `artifacts/` | Dataset construction, training, evaluation, analysis code, and experiment results |
| `derived/` | Dynamic training and development partitions |
| `code/variants/` | Source implementations associated with experiment hashes |
| `environment/` | Software requirements and recorded runtimes |
| `manifests/` | Dataset inventory, source bindings, model catalog, and validation scope |
| `docs/` | Data definitions, manuscript mapping, reproduction instructions, and rights |
| `tools/` | Package verification and point-estimate recomputation |

## Quick start

Extract the data and code archive, then run the following commands with
Python 3.10 or later:

```bash
cd GridRank_Dynamic_Research_Materials
python -B tools/verify_package.py
python -B tools/recompute_point_estimates.py
```

These commands use the Python standard library to check the stored files and
recompute principal point estimates. They do not perform model training,
GPU inference, or AC power-flow simulation.

For the data format and experimental workflow, read the following files inside
the extracted package:

- `docs/DATA_DICTIONARY.md`
- `docs/PAPER_ARTIFACT_MAP.md`
- `docs/REPRODUCTION_WORKFLOW.md`

## File integrity

Place the three archives and the archive-level `SHA256SUMS.txt` in the same
directory. On macOS or Linux, verify the downloads with:

```bash
shasum -a 256 -c SHA256SUMS.txt
```

## Rights and dependencies

Consult `docs/RIGHTS_AND_THIRD_PARTY.md` inside the data and code package for
reuse conditions and external dependencies. Each adapter archive includes
the Llama 3.1 Community License and attribution notice. Third-party materials
remain subject to their respective licenses.
