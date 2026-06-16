# Final Analysis Summary

The project was rerun end-to-end using existing conda environments. Raw longitude and latitude fields are retained only as metadata for final physical visualization and are excluded from all trainable feature matrices. The final result tables are decomposed by metric family to avoid hidden columns in notebook display.

## Final Proposed Model Snapshot
model,split,MAE,RMSE,Macro-F1,Balanced Accuracy,Recall,False Negative Rate,Brier Score,Expected Calibration Error,interval_coverage_probability,mean_prediction_interval_width
B-TGPRF,validation,0.3492059765951439,0.5482732951053356,0.9135517727931768,0.8828841216398939,0.76920137562094,0.2307986243790599,0.0093713993498088,0.0040237251164407,0.8654644244070735,1.389125940077834
B-TGPRF,test,0.4101793416820612,0.6007237418115005,0.8278067879443456,0.7627792483146868,0.5283815150875713,0.4716184849124287,0.0280112839666086,0.029301501189828,0.8136468941149019,1.389125940077834
B-TGPRF,external_test,0.3650275095691107,0.5477591380099959,0.8959805124424085,0.8746774813514324,0.7567567567567568,0.2432432432432431,0.0147191209208759,0.0063946741884017,0.8493641560692679,1.389125940077834


## Coordinate-Safe Feature Protocol
- Coordinate metadata columns: from_longitude, from_latitude, to_longitude, to_latitude.
- Feature dictionary role: metadata.
- Training feature inclusion: none.
