# O-type FMDV specific antibody classifier based on machine learning model
O_FMDV_ML is based on machine learning models to predict O-type FMDV-specific antibodies.

## Args:

```
-i, AbAg project input directory (contains sample.csv, model pkl files and feature name fasta files).
  --input dir
     --sample.csv (raw input data for feature extraction)
     --lgbm_model.pkl (base learner model 1)
     --rf_model.pkl (base learner model 2)
     --xgb_model.pkl (base learner model 3)
     --stack_model.pkl (meta learner model)
     --LGBM.fasta (feature name set for LGBM model)
     --randomforest.fasta (feature name set for RandomForest model)
     --XGBoost.fasta (feature name set for XGBoost model)
-o, AbAg project output directory (save feature files and prediction results).
  --output dir
     --data_feature.csv (extracted full feature file from sample.csv)
     --LGBM_feature.csv (model-specific feature subset for LGBM)
     --randomforest_feature.csv (model-specific feature subset for RandomForest) 
     --XGBoost_feature.csv (model-specific feature subset for XGBoost)
     --lgbm_predictions.csv (prediction probabilities of LGBM base learner)
     --random_predictions.csv (prediction probabilities of RandomForest base learner)
     --xgb_predictions.csv (prediction probabilities of XGBoost base learner)
     --stracking.csv (merged prediction probabilities of base learners, used for training the meta stack model)
     --stack_predictions.csv (final prediction probabilities of meta stack learner)
--remove_redandunt, default=True,
   True or False. It is faster when running on non-redandunt data.
--format, csv. Output file format of feature and prediction results. 
--cpu, Specify how many cores to use for feature calculation and prediction, default=1
--skip_feature, default=False,
   True or False. Skip feature extraction (use existing feature files in output dir) when running model prediction.
--model_dir, The absolute path of base/meta learner pkl files, default is the same as input dir.
--fasta_dir, The absolute path of feature name fasta files for models, default is the same as input dir.
--run_mode, feature_only or predict_only or full, default="full"
   feature_only: Only run data_feature.py to generate feature files.
   predict_only: Only run model_train.py (require pre-generated feature files).
   full: Run data_feature.py first, then model_train.py (complete workflow).
--antigen_names, The antigen names corresponding to sample data, split by ',', default="fmdv"
```

## Requirements:

```
Linux environment
python 3.9.25
pandas              : 2.3.3
Bio (Biopython)     : 1.85
joblib              : 1.5.2
```
