# Dataset Unification Report

## Protocol
- Year used: 2020
- Matched suffix groups: 1, 2, 3, 4
- Internal groups: 1, 2, 3
- External-test group: 4
- Selected critical lines: 100
- Rows in reusable time-series dataset: 3,494,400
- Rows in modelling dataset after future-target filtering: 3,484,800

## Critical Line Selection
Critical lines were selected using training rows only. The selection score combines training absolute-flow magnitude, variability, 95th percentile stress, and topology centrality.

## Risk Labels
Normal, Warning, and Critical labels are based on line-specific training quantiles: q90 and q95. A q99 column is saved for sensitivity analysis.

## Leakage Controls
- Future targets are produced by suffix-line group shifts.
- Lag and rolling features are shifted before rolling.
- External group 4 is excluded from fitting, thresholding, line selection, calibration, and ablations.
- Operating-regime thresholds are estimated from train rows only.
- Raw bus coordinates are stored as metadata only and are excluded from trainable feature matrices.

## Saved Artifacts
- `Data/Unified/unified_powergrid_timeseries.parquet`
- `Data/Unified/unified_powergrid_modeling_dataset.parquet`
- `Data/Unified/selected_lines_metadata.csv`
- `Data/Unified/selected_buses_metadata.csv`
- `Data/Unified/graph_edges.csv`
- `Data/Unified/graph_adjacency_matrix.csv`
- `Data/Unified/risk_label_definition.csv`
- `Data/Unified/feature_dictionary.csv`
