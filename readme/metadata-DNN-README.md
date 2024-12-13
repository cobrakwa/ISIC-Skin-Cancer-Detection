# Metadata DNN Model README

This README provides a quick overview of training a DNN model on metadata for binary classification.

---

## Overview

The DNN processes metadata features to perform binary classification. It includes two hidden layers with ReLU activation and dropout for regularization. The training framework tracks metrics like accuracy, ROC AUC, and pAUC to evaluate performance.

---

## Data

- **Dataset**: `normalized_metadata.csv`
- **Splits**: Train (80%), validation (10%), test (10%)
- **Features**: Numerical columns (excluding `isic_id` and `target`)
- **Labels**: Encoded if not numeric

---

## Model Configurations

The `saved_models` folder contains models saved during various training runs. The naming convention is as follows:

- **`saved_models_1`, `saved_models_2`, etc.**: Represent different training iterations or configurations.
- **`*_STAR` Suffix**: Indicates the best-performing model for a particular configuration. For example, `saved_models_1STAR` means the first training iteration yielded the best results.

---

## Outputs

- **Model**: Best-performing model (`best_model.pth`). Available on requests or uploaded to edim.
- **Plots**:
  - ROC Curve: `roc_curve.png`
  - Training/Validation Loss: `train_val_loss.png`
  - Training/Validation Accuracy: `train_val_accuracy.png`
- **Parameters**: Saved in `model_params.txt` for reproducibility

---

This README highlights the key details for training and evaluating the DNN model. For detailed workflows, refer to the training scripts in the tabular_model directory.
