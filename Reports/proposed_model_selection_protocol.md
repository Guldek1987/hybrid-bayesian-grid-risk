# Proposed Model Selection Protocol

## Model Name
B-TGPRF: Bayesian Temporal Graph Probabilistic Risk Forecaster.

## Validation-Only Selection
All architecture choices are selected using validation data only. Test and strict external-test partitions are evaluated after the configuration is fixed and are not used for thresholds, calibration, component weights, or selection.

## Candidate Components
The search evaluates point-forecasting backbone choice, graph/topology/operating-regime feature representation, residual correction, calibration method, Bayesian posterior-style risk layer, and interval strategy.

## Composite Objective
The final configuration maximizes an equal-family validation score:
1. Safety/risk detection: Macro-F1, Balanced Accuracy, Recall, and false-negative reduction.
2. Forecasting accuracy: MAE, RMSE, R2, and normalized RMSE.
3. Calibration and uncertainty: Brier Score, Expected Calibration Error, pinball loss, and interval calibration error.
4. Efficiency: fit time and inference time.

Equal family weighting avoids arbitrary post-hoc emphasis after observing test or external-test metrics.

## Selected Configuration
backbone,forecast_cols,risk_source,feature_profile,residual_strategy,calibration,interval_strategy,use_bayesian,forecast_weight_rule,model,model_group,selected_using,critical_threshold,warning_threshold,feature_count,residual_correction_alpha
Validation-weighted forecast fusion,ExtraTreesRegressor | RandomForestRegressor | HistGradientBoostingRegressor | XGBoost Regressor | Ridge | ElasticNet,MLPClassifier,full,near_threshold_weighted,platt,residual_conformal,True,nonnegative weights fitted on validation calibration by constrained mean-squared error,B-TGPRF,Proposed,validation calibration and assessment only,0.6137184866282172,0.009962131358022734,27,1.0


## Forecast Component Weights
forecast_component,validation_weight
HistGradientBoostingRegressor,0.48511294003114447
ExtraTreesRegressor,0.30308814107755
RandomForestRegressor,0.21179891889130553
XGBoost Regressor,6.288878403900047e-17
ElasticNet,4.9841314921507795e-17
Ridge,2.887112698005775e-17

