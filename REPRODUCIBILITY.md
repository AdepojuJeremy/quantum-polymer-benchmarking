# Reproducibility policy

## Leakage control

- The raw representation stage does not fit predictive scalers or PCA models.
- Imputation, scaling, PCA, and quantum input transforms are fitted within
  training data only.
- Canonical polymer graph identities are prevented from crossing matched
  train/test partitions.
- Structural OOD clusters are constructed without target values.
- The 400-sample test partitions are not used for hyperparameter selection.

## Randomness

The global seed and every experiment configuration are stored in
`configs/experiment_configuration.json`. Step 12 separately evaluates
seed and structural-fold robustness.

## Heavy artifacts

Kernel matrices and fitted models are regenerable and are not required in
version control. The notebook records their runtime inventory but the release
archive focuses on source, configurations, split identities, reports, and
paper assets.

## Statistical claims

The Step 12 confirmatory analysis uses paired structural-cluster resampling
and multiplicity correction. Step 13 converts only those outputs into
manuscript-safe claims.
