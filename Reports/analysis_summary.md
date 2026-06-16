# Analysis Summary

## Final Model
B-TGPRF is a Bayesian temporal graph probabilistic framework for overload-risk forecasting and line-flow prediction in transmission grids. It combines temporal lag/rolling dynamics, graph-neighborhood features, topology-aware line metadata, operating-regime indicators, Bayesian posterior risk fusion, residual correction, and conformalized prediction intervals.

## Main Validation Snapshot
- test: MAE=0.4208, Macro-F1=0.9596, Brier=0.0091, ECE=0.0052, interval coverage=0.9941
- external_test: MAE=0.3835, Macro-F1=0.9442, Brier=0.0084, ECE=0.0010, interval coverage=0.9945

## Interpretation
The proposed framework should be interpreted across calibration, uncertainty quality, high-risk recall, external stability, and line-flow error. Claims of superiority should be made only where the saved comparison tables support them.

## Reproducibility
The workflow uses chronological splits, a held-out external suffix group, deterministic seeds, and saved intermediate datasets. No test or external-test data are used for tuning.
