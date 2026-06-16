# Result Narrative

The experiments evaluate overload-risk classification and probabilistic line-flow forecasting on a unified synthetic European transmission-grid dataset. Critical lines are selected using training-only flow variability, high-percentile stress, and topology centrality. The external test uses a held-out suffix group that is not used for thresholding, calibration, or ablation decisions.

B-TGPRF integrates deterministic temporal-graph forecasting with Bayesian posterior risk fusion, graph-residual correction, and conformalized interval estimation. On the internal test split, the final snapshot is: test: MAE=0.4208, Macro-F1=0.9596, Brier=0.0091, ECE=0.0052, interval coverage=0.9941. On the held-out external suffix group, the final snapshot is: external_test: MAE=0.3835, Macro-F1=0.9442, Brier=0.0084, ECE=0.0010, interval coverage=0.9945.

The result should be reported with nuance. The proposed model is not assumed to dominate every metric; the strongest claims should focus on the metrics where the comparison tables show empirical gains, especially calibration, interval quality, false-negative behavior, or external stability.
