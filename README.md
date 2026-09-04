# A Controlled Benchmark of Quantum and Classical Kernels Under Out-of-Distribution Polymer Generalization

This release accompanies the research notebook implementing a controlled
comparison of quantum and classical kernels for out-of-distribution polymer
glass-transition-temperature prediction.

## Primary supervised benchmark

- Dataset: PolyMetriX Curated Tg
- Target: Tg (K)
- Matched comparison: 700 training polymers / 400 untouched test polymers
- Benchmark regimes: random_iid, structural_cluster_ood, high_tg_extrapolation, low_tg_extrapolation, class_holdout_polyimides
- Primary quantum setting: 8 qubits, depth 2, analytic statevector kernels
- Quantum kernels: fidelity quantum kernel (FQK) and projected quantum kernel (PQK)
- Strong classical comparators include RBF, Laplacian, Matérn, and Tanimoto kernels

## Notebook structure

1. Environment and project initialization
2. Real PolyMetriX dataset acquisition and curation
3. Polymer-specific raw representation engineering
4. IID and OOD benchmark construction
5. Leakage-free classical baselines
6. Quantum feature maps and kernel construction
7. Main quantum-versus-classical benchmark
8. Quantum circuit and representation ablations
9. Kernel geometry and mechanistic diagnostics
10. OOD uncertainty and conformal stress testing
11. Finite-shot and noise robustness
12. Statistical inference and robustness reruns
13. Publication figures and tables
14. Reproducibility and release packaging

## Reproduction

Run the notebook from top to bottom in a fresh Google Colab runtime.
The notebook downloads the upstream dataset rather than redistributing it.
Predictive imputation, scaling, PCA, and quantum-angle preparation are fitted
using training data only inside the corresponding benchmark split.

The release records the exact matched split indices and SHA-256 hashes in
`metadata/matched_split_manifest.*`.

## Scientific interpretation

The code is designed to test, rather than assume, a quantum advantage.
Directional quantum-versus-classical claims should only be taken from the
multiplicity-controlled confirmatory analysis produced in Step 12 and the
manuscript-safe claim inventory exported by Step 13.

A non-significant result is not interpreted as evidence of equivalence.

## Release layout

- `configs/` — frozen experiment configuration
- `metadata/` — environment, dataset provenance, split hashes, manifests
- `splits/` — exact 700/400 matched index arrays
- `paper_assets/` — final manuscript and supplementary figures/tables
- `research_reports/` — machine-readable reports from preceding steps
- `requirements_frozen.txt` — exact Python environment from the executed runtime
- `environment.yml` — compact environment specification

Large kernels, fitted estimators, and caches are intentionally not bundled
into the lightweight GitHub release because they are regenerable from the
notebook. Their runtime presence is indexed in
`metadata/heavy_artifact_inventory.csv`.

## Data

See `DATA_PROVENANCE.md`. The release does not assign or modify the upstream
dataset license.
