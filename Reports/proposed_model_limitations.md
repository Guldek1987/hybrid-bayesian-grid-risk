# Proposed Model Limitations

1. The executable protocol uses the available matched 2020 suffix groups in the current project state.
2. The modelling dataset uses a selected critical-line protocol for computational feasibility.
3. The Bayesian risk layer is a feasible posterior-style approximation over graph-temporal risk features, not a full physical Bayesian power-flow simulator.
4. Validation data are used for architecture selection, calibration, and decision thresholds; test and strict external-test metrics are preserved for final evaluation only.
5. Any baseline or SOTA model that outperforms B-TGPRF on a specific metric must be reported transparently.
