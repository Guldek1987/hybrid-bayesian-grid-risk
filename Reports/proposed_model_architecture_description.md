# B-TGPRF Architecture Description

B-TGPRF is a hybrid Bayesian temporal graph probabilistic model for transmission-grid overload risk forecasting.

## Architecture Components
1. Validation-selected point-forecasting backbone: `Validation-weighted forecast fusion`.
2. Temporal lag and rolling representations from the unified modelling dataset.
3. Graph-neighborhood aggregation features for adjacent-line flow context.
4. Topology-aware line features including endpoint degree, line centrality proxy, and available capacity-derived ratios.
5. Operating-regime awareness for high-load, high-generation, high-ramp, low-margin, and stress regimes.
6. Bayesian posterior-style risk layer using Bayesian Ridge and Gaussian posterior evidence over risk-design features.
7. Validation-only probability calibration: `platt`.
8. Residual correction for near-threshold and high-risk regimes: `near_threshold_weighted`.
9. Probabilistic interval estimation: `residual_conformal`.
10. Validation-derived Normal, Warning, and Critical risk decision thresholds.

## Outputs
Prediction files contain point line-flow forecast, lower interval, median forecast, upper interval, interval width, overload risk probability, calibrated overload risk probability, risk class, uncertainty score, and external-test prediction rows.
