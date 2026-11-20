# IFCF household coordination reproducibility artifact — v2.0.0-rc3

These instructions apply to the four archives distributed with the GitHub prerelease. The archived README inside the core archive records the prepublication state at packaging time.

## Scientific scope

This mechanism-oriented discrete-event testbed compares selected household coordination policies with component co-deployment. It is not an empirically calibrated household population model. The exact published scientific baseline is commit `29ebc435c55c6b7576bf4b0c9e520337629cc06c`, tree `efa4601d3a36ac973cdc28440240304ac3b06388`. No Git checkout or private repository is needed to read this package or use the supported commands.

Education prompts are synchronous; there is no persistent queue or waiting-time congestion. Shared offer budgets, topic cooldowns, fatigue and cross-member efficacy are the tested displacement/learning mechanisms. Nonnegative enforcement reinforcement constrains privacy direction, whereas stochastic magnitudes and security outcomes remain conditional. The propagation flag does not implement contagion or lateral movement.

Three evidence groups remain separate:

- Historical primary analysis: 500 paired seeds, 42–541, with 9 component configurations and 8 mechanism configurations in separate files. Available historical sensitivity and attenuation records are also included. The pre-education-gate archive is superseded history and must not be pooled with submitted results.
- Controlled structural experiments: 1,924 independent paired final seeds, 2000000–2001923; 15 distinct simulator arms per seed. Seven predeclared comparisons use two-sided paired Student-t inference and a seven-comparison Bonferroni family. Both security and privacy NRL are co-primary; combined NRL is secondary.
- Exploratory parameter/interaction experiments: 2,130 final paired blocks, 2000000–2002129; 34 new arms per seed and 9 reference anchors. The first 1,924 seed blocks reuse structural-study anchors. Nine anchors were extended for the remaining 206 seeds. The studies overlap, are not independent replications and must not be pooled. All 120 primary and 60 secondary columns are retained, with 34 structural identities, 66 supported-variance and 20 rare-event-limited primary columns.

The additional experiments followed historical findings and reviewer feedback, with their comparisons and analysis definitions specified before the final runs. Variance-planning seeds 1000000–1000999 are excluded from final estimation. The 0.001 half-width objective concerns Monte Carlo precision, not practical importance or equivalence.

## Layout

- `source/baseline/`: baseline source and native supporting layout. Critical simulator transition modules are byte-identical to the recorded published source. File-level baseline membership is identified in the source map; convenience historical records are not all part of the tagged tree.
- `source/structural/`, `source/parameter/`: verified variant engines and original construction/analysis definitions. Original `revision_s3`/`revision_s6` filenames are preserved for module resolution and provenance.
- `configurations/`: complete parameters, settings, seeds, study protocols and release layout index.
- `historical_results/available_archive/`: original primary CSVs, available sensitivity records, archived single/double attenuation outputs and nested original integrity records.
- `structural_experiments/final/`: every final raw per-seed/member/trace file, detailed verification subset, seven-comparison analysis and saved bootstrap outputs.
- `parameter_robustness/final/`: all new raw runs, extended anchors, anchor-reuse map, traces, diagnostics, the 54-logical-arm feature cube, 180 contrast vectors and saved bootstrap outputs.
- `companion_data/companion/`: all 40 original companion files plus the reader index. Numerical data remain unchanged; provenance locators/branch-status metadata have public export derivatives where necessary.
- `analysis/`: **supported portable entry points** below. They do not call historical private-checkout integrity guards.
- `tests/`: portable verification plus archived original deterministic-verification records.
- `documentation/manuscript/`: accepted scientific paper/supplement sources, PDFs, figures and tables for locating claims. These have not been edited as part of this assembly.
- `checksums/`: file-level download integrity and source-to-release identity map.

## Environment

The supported commands were tested with CPython **3.10.12**, NumPy **1.21.5**, SciPy **1.8.0**, Matplotlib **3.5.1** on Linux. Use Python 3.10; do not assume old pinned dependencies support newer Python versions. Standard-library modules handle CSV/JSON, archive and hash operations. TeX compilation additionally needs TeX Live/pdfLaTeX, latexmk, and the upstream Elsevier CAS bundle (install separately; the archived sources may need a local TeX search path); it is not required for statistical reproduction.

Create an environment and install `requirements.txt`, for example:

```sh
python3.10 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt
.venv/bin/python -s -B tests/verify_package.py
```

The independent offline audit used a fresh venv with system-site packages supplying the exact versions above, disabled user-site packages, cleared PYTHONPATH/PYTHONHOME, and no private-checkout imports. This is process isolation, not a container or a fully hermetic dependency installation. Legacy requirements/environment files are preserved as historical records; the top-level pins describe the tested portable analysis path.

All commands below run from the extracted package root and write only to new `generated/` subdirectories. Never replace archived files or reuse an existing output directory.

## Reproducibility level 1 — recompute statistics from saved outputs

```sh
.venv/bin/python -s -B analysis/reproduce.py --output generated/reanalysis-001
.venv/bin/python -s -B analysis/export_tables.py --input generated/reanalysis-001 --output generated/tables-001
.venv/bin/python -s -B analysis/rebuild_features.py
.venv/bin/python -s -B analysis/reproduce_morris.py
.venv/bin/python -s -B analysis/reproduce_attenuation.py
.venv/bin/python -s -B analysis/replot_historical_figures.py
```

The first command reconstructs all seven structural contrasts from raw paired outcomes, merges the exploratory raw/anchor panel, verifies every logical endpoint against the saved cube, and rebuilds all 180 vectors. It independently recomputes estimates, paired SD/SE, marginal and Bonferroni intervals, and covariance. Bootstrap sensitivity intervals are reproduced from the **saved 100,000 whole-seed bootstrap mean draws**, not newly regenerated random weights in the tested path. The exact weight-generation code/seeds are also archived (`bootstrap_means` in structural production_analysis.py and the exploratory code/analysis.py); that original private-control orchestration is not the supported CLI.

`rebuild_features.py` independently reconstructs all 57 feature columns from raw outcomes and member records using the original pure analysis function. It checks origin/stage counts, gross-learning/decay/final-state accounting and zero queue-full suppression. `export_tables.py` emits machine-readable main Tables 7–8 and Supplementary Tables S29–S32, operational means and historical tables from unrounded sources. No estimates are reconstructed from printed rounded manuscript values.

The Morris command reconstructs elementary effects from the 40 archived trajectories and repeats the conditional 20-trajectory comparisons/subsets. It does not create new simulation trajectories or establish global convergence. The attenuation command compares the archived records; it does not resolve the extended harness's incomplete provenance. The figure command re-plots the saved numerical inputs without new simulation or bootstrap estimation; binary PDF identity is not claimed across plotting environments.

## Reproducibility level 2 — rerun available simulator configurations

```sh
.venv/bin/python -s -B tests/portable_checks.py
.venv/bin/python -s -B analysis/replay_one.py parameter BC I3 2000000 --full-record --output generated/example-BC-I3.json
.venv/bin/python -s -B tests/check_full_record.py --input generated/example-BC-I3.json
```

The test runs three predetermined 120-event reference replays (baseline, structural and parameter engines), compares all 41 legacy fields to the archived record, and checks all 20 setting constructors across three logical arms without events. The full-record replay uses the original production observer and loop, producing unrounded outcomes, diagnostics, member summaries and the trace. A predetermined BC/I3 full record and all four member records matched the archive exactly. The replay command runs **one configuration/seed**, profile P1, combined 120-event workload and H=168. It is suitable for bounded verification and understanding the supplied configurations. Original trace generation and purpose-keyed draws are preserved. For extensive independent reruns, the same functional entry point can be called over the archived seed/arm lists with the recorded aliases/deduplication; that full campaign was not executed in this audit.

The retained original production/analysis source is supplied for provenance, but its old integrity/orchestration routines refer to private-checkout layouts, archived planning records and Git state. They are **not portable supported entry points** and must not be mistaken for the commands above. The local audit did not rerun a full campaign or regenerate the 100,000 bootstrap weights; do not claim those levels were independently re-executed.

## Reproducibility level 3 — exact historical reconstruction

This is **partially supported**, not universally verified. Historical numerical CSVs, available raw component/mechanism outputs, original statistical scripts, archived intervals, forms/tipping/factorial summaries, Morris points and attenuation records are included. However:

- Historical factorial per-cell raw replication records were not recovered. The 32-cell summaries and 40-pair design do not permit reconstructing all standardized paired effects/covariances.
- The extended attenuation audit's complete harness/source revision was not recovered. Its 20,000 stored records can be compared, but that is not a complete independent recreation or mathematical-equivalence proof.
- Some historical bootstrap offsets depend on Python `hash()` without a preserved process hash seed. Their published intervals can be read, but exact bitwise regeneration is not established.
- Some historical CSV outputs were stored at rounded precision; do not infer missing underlying precision or manufacture raw data from summary tables.
- Original Morris archive precision bounds elementary-effect reconstruction; subset stability is conditional on those 40 trajectories.

Scientific limitations are separate: no measured household calibration or external validation, no externally established practical-importance threshold, nonadaptive/stylized workloads, and rare-event-limited exploratory inference remain. No artifact-access mechanism resolves these.

## Provenance, privacy and integrity

`checksums/source_map.json` maps each copied file to a symbolic source root, original relative path, original SHA-256 and delivered SHA-256. Model transition modules and raw numerical payloads are unchanged. Selected public metadata derivatives retain source hashes and omit private locators. Portable analysis adapters are identified separately. Retained scientific source files are byte-identical to their originals. Those transformations do not change scientific numeric fields. Original nested checksum records identify pre-export source versions; **use checksums/SHA256SUMS for this delivered package**, not an archival manifest as if it described the export derivatives.

Archived source locators in provenance are identities, not operational file dependencies. Supported commands and all active release links use relative paths. No .git history, credentials, personal account configuration, reviewer correspondence or unrelated project tree is included. Publication-build/QA transcripts and pre-version manuscript drafts were intentionally excluded; their source digests/reasons are recorded in the source map. No CSV/JSON/NPZ simulation dataset was excluded by that filter. Search-pattern literals in the security audit are not credentials or machine locators.

Download the four planned assets, verify their separately provided ASSET_SHA256SUMS, then extract all four into the same parent directory before verifying the complete file manifest. No Git command is necessary. See documentation/DISTRIBUTION.md and documentation/REPRODUCIBILITY_COVERAGE.md inside the extracted package.

This GitHub prerelease has no assigned DOI.

Historical manuscript and archive filenames are mapped in `checksums/historical_filename_lookup.json`. Named public extracts preserve the fields listed in their provenance, and their checksums identify the delivered bytes. A null public path denotes an excluded record.
