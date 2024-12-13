# ISIC-Skin-Cancer-Detection

# output_fusion.ipynb

This notebook uses 3 pretrained image classifiers, 5 pre-trained xgboost model as ensemble and requires train.csv to scale the data.
It will predict on test.csv and test.hdf5

To run this notebook, you will need:

1. 5 xgboost.joblib files
2. 3 image classifiers .pt files (Resnet, Eva, Swin)
3. train.csv
4. test.csv
5. test.hdf5 (containing images of the test set)

# train_fusion.ipynb

This notebook uses all available training data to perform a CV of 5folds, to produce an average pAUC score.
You can choose to use attention/gated fusion when initialising the predictor class.

1. merged_output.csv (this consists of all training data)
