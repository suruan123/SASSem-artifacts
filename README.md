# SASSem: Experimental Data

Experimental records supporting **SASSem: Recovering Operator Semantics from GPU Binaries**.

Authors: Jiahua Liu, Jinguo Li, and Xin Yao. Jiahua Liu and Jinguo Li are affiliated with Shanghai University of Electric Power; Xin Yao is affiliated with Central South University. This snapshot was assembled on 2026-11-18 from archived experiments. It does not report new experiment executions.

## Download

Download [SASSem_Experimental_Data.zip](SASSem_Experimental_Data.zip) and extract it to access all 72 data/documentation files. CSV tables are also browsable in this repository. The `records/` paths below are inside the ZIP archive.

## Contents

- `tables/`: six CSV tables covering scalability medians, ablation, functional paths, expression sizes, GPU replay batches, and final-binary mutations.
- `records/`: archived JSON run records, registrations, summaries, and mutation witnesses. Paths below this directory retain the archive hierarchy for traceability.
- `provenance.json`: original archive hashes, shared-file hashes, and the transformation applied to each data file.
- `validation.json`: checked counts and median reconciliation.
- `DATA_DICTIONARY.md`: field meanings, units, and interpretation boundaries.
- `SHA256SUMS.txt`: hashes of this data snapshot.

## Scope and interpretation

The unified cohort contains 26 configurations, each measured in five independent serial processes (130 runs). It includes 23 scalability configurations and three additional functional configurations. The ablation cohort comprises eight configurations in four modes (32 runs). The functional baseline contains 66 attempted paths, of which 61 are verified configurations and five are infeasible paths. These cohorts overlap and must not be added as independent kernels.

The replay records cover 334 archived launches and 195,084 scalar comparisons. They include auxiliary FA/LayerNorm states where the original batch does so. Different original tolerances and scopes are retained. Original optimized TF32 replay covers only the first tile; the conditional full-matrix relation is not full-grid hardware replay or bitwise IEEE-754 equivalence.

The final-binary mutation cohort has 20 cases: 19 output-changing mismatches and one semantics-preserving control. These are controlled post-compilation edits, not reproduced compiler defects. Earlier fault and support-development records retained under `records/` are supporting historical evidence, not additional final-mutation cases.

This is a **data snapshot**, not an executable software release. It does not contain the SASSem implementation, third-party source trees, cubins, checkpoint/model weights, manuscript sources, private credentials, or internal editorial correspondence. Original archived records vary in granularity: a batch with only an aggregate record is not presented as having a new per-output trace.

## Data integrity and privacy

Numerical values and recorded outcomes are preserved. JSON is formatted for readability; absolute host paths are normalized to archive-relative paths or `<LOCAL_PATH>/basename`. Scientific configuration values and software versions are preserved. `provenance.json` records hashes before and after these changes. Original fingerprints refer to the private archive, not to files promised to exist at those original paths in this data-only repository.

Stage medians are computed separately and need not sum to the median total time. Peak memory is the analysis process's peak CPU working set, in MiB; it is not GPU memory. Expression-node counts exclude index/range attributes and are not a measure of peak storage. Formal outcomes are conditional on the declared mathematical model and supported paths; replay is evidence only for the tested inputs.

## Citation

Jiahua Liu, Jinguo Li, and Xin Yao. *SASSem: Experimental Data*. Snapshot 2026-11-18. Associated manuscript: *SASSem: Recovering Operator Semantics from GPU Binaries* (submitted manuscript; no publication DOI assigned here).

No DOI or journal acceptance is claimed for this repository.
