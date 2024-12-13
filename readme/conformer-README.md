# Conformer Model README

This README provides a brief overview of the Conformer model for image classification, along with key information about dependencies, data paths, and usage.

---

## Overview

The lightweight Conformer model combines convolutional layers and a Transformer encoder for robust image classification. 
There are a lot of variants here in the conformer folder, let's go through the folders:

1) pretrained: this folder contains saved models from conformer_pretrain.ipynb. Initially, due to the lack of dataset (because of dataset imbalance), there was an exploratory plan to first pretrain on domain specific data. In this case, we tried to pretrain the conformer to predict the region of the tumour (as given in the metadata csv file). Then, these pretrained models will be used for downstream finetuning as described in (2).
2) finetuned: this folder contains saved models from conformer_finetune.ipynb. It's the downstream finetuning of the pretrained models into our main binary classification task. 
3) scratch: this folder contains saved models from conformer_from_scratch.ipynb. It's where the conformer was trained end-to-end without transfer learning. However, this notebook seemed to have data leak because it used augment data, and augmentation was applied to all train/validate/test split. 
4) scratch_augmentless: this folder contains saved models from conformer_from_scratch_augmentless.ipynb. It's the same as scratch, except that this time, the models are trained without augmenting the data at all.
5) scratch_test_augmentless: this folder contains saved models from conformer_from_scratch_test_augmentless.ipynb. It's the same as (4), except that this time, only train and validate sets are augmented, leaving the test set original as it is.
6) scratch_test_augmentless_kfold: this folder contains saved models from conformer_from_scratch_test_augmentless_kfold.ipynb. It has the same data setup as (5), it's just that this time, we trained 5 conformer models on 5 folds and then averaged the probabilities to get our output, instead of training a single model.

In the folders above, saved models are saved in the naming format saved_models_1, saved_models_2, etc. Each of these represents a model/training configuration that we tried, and for the most part, it's model architecture is also defined inside the folder as model_params.txt. The best peforming model for each configuration has a _STAR suffix to its folder, like for instance in scratch_test_augmentless, the 4th iteration gave us the best results, so it has the name saved_models_4STAR.

Note that not all of these notebooks/files reflect our latest training process. For the conformer, our final, most important notebook is the conformer_from_scratch_test_augmentless.ipynb, which gave us the best results given that there is no data leak.
Note also that the weights are not uploaded in the folders above due to size constraints. Only the best performing ones are considered, in this case, that is (5) and (6), the model files will also be uploaded to edimension. 

---

## Data Path

- **Dataset Directory**: `../data/balanced_data`

Our filtered dataset will be provided on request and uploaded on edimensions.
---

## Dependencies

Install the following Python libraries before running the code:

- `torch`
- `torchvision`
- `matplotlib`
- `numpy`
- `scikit-learn`
- `scipy`

and some other basic machine learning libraries, as needed.
