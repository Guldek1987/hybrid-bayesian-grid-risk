# Hybrid Bayesian Grid Risk

◇ **Hybrid Bayesian Temporal Graph Model for Overload Risk Forecasting in Electric Transmission Networks**

`hybrid-bayesian-grid-risk` is a lightweight GitHub repository for the B-TGPRF workflow. It contains notebooks, compact result tables, figures, PDF diagrams, and execution reports. Large datasets, trained binary models, and prediction dumps are excluded from the repository and referenced externally.

## ▣ Overview

The project implements **B-TGPRF**: Bayesian Temporal Graph Probabilistic Risk Forecaster. It combines temporal line-flow dynamics, load and generation signals, graph-topology features, Bayesian posterior-style risk estimation, probability calibration, residual correction, and conformal prediction intervals.

```text
External dataset
      |
      v
Notebook workflow
      |
      v
Leakage-safe graph-temporal features
      |
      v
Baselines + compact temporal/graph-temporal models + B-TGPRF
      |
      v
Validated result tables, figures, diagrams, and reports
```

## ◈ Dataset

The full dataset is not stored in this repository because of its size. Download it from the original sources:

| Ref. | Dataset source | Link |
|---|---|---|
| [23] | Gillioz, M.; Dubuis, G.; Jacquod, P. *A large synthetic dataset for machine learning applications in power transmission grids*. Scientific Data, 2025. DOI: `10.1038/s41597-025-04479-x`. | https://doi.org/10.1038/s41597-025-04479-x |
| [24] | Gillioz, M.; Dubuis, G.; Jacquod, P. *A large synthetic dataset for machine learning applications in power transmission grids*. Zenodo Dataset, 2024. DOI: `10.5281/zenodo.13378476`. | https://doi.org/10.5281/zenodo.13378476 |

Expected source files for reproducing the workflow are:

- `europe_network.json`
- `loads_2020.zip`
- `gens_2020.zip`
- `lines_2020.zip`

The notebooks expect these files to be placed under a local `Data/Raw/` directory when reproducing the full pipeline.

## ▣ Repository Contents

| Path | Contents |
|---|---|
| `Notebooks/` | Six ordered notebooks covering data audit, feature engineering, baselines, compact temporal models, B-TGPRF, validation, and final outputs |
| `Tables/` | Compact metrics, summaries, ablation results, calibration summaries, robustness checks, and model-comparison tables |
| `Figures/` | Generated diagnostic and result figures |
| `Reports/` | Execution summaries, protocol notes, model evidence, limitations, and architecture notes |
| `Docs/` | Exported PDF diagrams for the pipeline and B-TGPRF architecture |
| `Bayesian_PowerGrid_Risk_Forecasting_pipeline_and_architecture.drawio` | Editable architecture diagram source |

Excluded by design:

- raw datasets and generated parquet datasets;
- trained binary model artifacts;
- large prediction CSV dumps;
- Word-processing files;
- OS metadata and temporary files.

## ◇ Notebook Workflow

| Step | Notebook | Main Output |
|---|---|---|
| 01 | `01_dataset_download_audit_and_research_design.ipynb` | Dataset audit and experiment configuration |
| 02 | `02_unified_dataset_feature_engineering_and_risk_labels.ipynb` | Unified graph-temporal dataset and risk labels |
| 03 | `03_baseline_models.ipynb` | Classical baseline models |
| 04 | `04_sota_models.ipynb` | Compact temporal and graph-temporal model comparisons |
| 05 | `05_proposed_bayesian_model_and_ablations.ipynb` | B-TGPRF training, calibration, and ablation |
| 06 | `06_validation_explainability_final_figures_and_tables.ipynb` | Final validation, explainability, figures, and tables |

## ▣ Model Design

```text
Temporal features
  + graph-neighbourhood features
  + topology/capacity features
  + operating-regime indicators
        |
        v
Validation-weighted forecast fusion
        |
        v
Bayesian posterior-style risk layer
        |
        v
Probability calibration + residual correction
        |
        v
Conformal intervals + overload-risk classes
```

B-TGPRF produces point forecasts, calibrated overload probabilities, Normal / Warning / Critical risk classes, interval forecasts, and uncertainty scores.

## ◈ Key Results

| Split | MAE | RMSE | Macro-F1 | Balanced Accuracy | Recall | Brier | ECE | Interval Coverage |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Validation | 0.3492 | 0.5483 | 0.9136 | 0.8829 | 0.7692 | 0.0094 | 0.0040 | 0.8655 |
| Test | 0.4102 | 0.6007 | 0.8278 | 0.7628 | 0.5284 | 0.0280 | 0.0293 | 0.8136 |
| External-style test | 0.3650 | 0.5478 | 0.8960 | 0.8747 | 0.7568 | 0.0147 | 0.0064 | 0.8494 |

Source: `Tables/final_result_snapshot.csv`.

## ▣ Data Protocol

- Executable year: `2020`.
- Matched scenario groups: `1`, `2`, `3`, `4`.
- Selected monitored lines: `100`.
- Forecast horizons configured: `1`, `6`, and `24` hours.
- Primary critical-risk threshold: line-specific 95th percentile of training absolute flow.
- Geographic coordinates are metadata only and are excluded from trainable feature matrices.

## ◇ Main Artifacts

| Artifact | Location |
|---|---|
| Final metrics snapshot | `Tables/final_result_snapshot.csv` |
| Full model comparison | `Tables/all_model_comparison.csv` |
| Validation forecasting metrics | `Tables/final_validation_forecasting_metrics.csv` |
| External-style classification metrics | `Tables/final_external_classification_metrics.csv` |
| Calibration summary | `Tables/calibration_summary.csv` |
| Architecture notes | `Reports/proposed_model_architecture_description.md` |
| Evidence map | `Reports/final_model_claims_and_evidence.md` |
| Pipeline PDF | `Docs/Data Preparation and Feature Engineering Pipeline.drawio.pdf` |
| Architecture PDF | `Docs/B-TGPRF Internal Architecture.drawio.pdf` |

## ▣ Technical Scope

`Bayesian modelling` · `time-series forecasting` · `graph feature engineering` · `power-grid analytics` · `probabilistic calibration` · `conformal prediction` · `model validation` · `ablation analysis` · `Jupyter workflows`

## ◈ Reproducibility Notes

1. Download the dataset from Zenodo DOI `10.5281/zenodo.13378476`.
2. Place the required raw files under local `Data/Raw/`.
3. Run notebooks in numeric order from `01` to `06`.
4. Generated large outputs should remain local unless explicitly needed.
