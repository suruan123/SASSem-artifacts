# Data dictionary

## Primary files

| File | Unit / interpretation |
|---|---|
| `tables/scalability_medians.csv` | Per-configuration medians from the five-process unified cohort. |
| `records/experiments/sync_reconvergence_20261012/out/uniform/rows.json` | One record per process run, including configuration, outcome, timing, memory, expression hashes, and proof metadata. |
| `tables/ablation.csv` | One configuration/mode combination per row; modes are full, without_binding, without_provenance, without_reconstruction. |
| `tables/functional_paths.csv` | Attempted paths and feasibility; infeasible paths are not successful verification cases. |
| `tables/reconstruction_metrics.csv` | Unique mathematical nodes and finite reductions for representative configurations. |
| `tables/gpu_batches.csv` | Original hardware-batch totals, tolerances/scope descriptions, and archive source identifiers. |
| `tables/final_binary_mutations.csv` | Twenty final-binary mutations with outcome, witness kind, and analysis cost. |

## Common fields

- `id`, `case_id`: experiment/configuration identifier; not a count of independent source kernels.
- `repeat`: unified process repetition, 1 to 5.
- `recovery_seconds`: front end, binding/provenance, raw-expression construction and related recovery work, as recorded by the pipeline.
- `organization_seconds`: checked expression reconstruction stage.
- `verification_seconds`: independent-reference comparison stage.
- `pipeline_seconds`: recorded full analysis time, in seconds; aggregated separately from each stage.
- `process_wall_seconds`, `worker_seconds`, `analysis_seconds`: original measurements retained for provenance; do not substitute these for pipeline medians without checking the originating cohort.
- `peak_memory_mb`: peak CPU working set in MiB despite the historical field name.
- `outputs`: declared analyzed scalar outputs for that record; auxiliary and main outputs may have batch-specific definitions.
- `barrier_epochs`: executed synchronization-phase count; not a duration.
- `raw_expression_nodes`, `raw_unique_math_nodes`, `reconstructed_unique_math_nodes`: mathematical-expression node counts; exclude index/range attributes.
- `expression_sha256`, `reconstruction_sha256`, `canonical_sha256`: fingerprints of expressions/forms under the registered conventions.
- `Verified`: equivalence under the registered model, assumptions, path, and output domain; not unconditional bitwise floating-point equivalence.
- `Mismatch`: retained inequivalence evidence; `Unresolved`: no accepted proof or witness under the supported interpretation.
- `path_feasibility`: feasibility result. `unsat` paths are excluded from feasible-configuration success counts.

JSON field availability follows the original experiment version. Missing fields are not reconstructed or silently imputed. For per-case details, follow the record paths named in the CSV files relative to `records/` where a corresponding archived JSON record is included.
