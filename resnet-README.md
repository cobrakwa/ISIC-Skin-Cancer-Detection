# ResNet (18 & 50 Variants) README

This README provides a brief overview of training and evaluating ResNet-18 and ResNet-50 models for image classification.

---

## Overview

The ResNet directory follows a structure similar to the Conformer and DNN directories. It contains configurations for ResNet-18 and ResNet-50 models, with saved checkpoints and corresponding training information.

---

## Directory Structure

The `saved_models` folder contains models saved during training. Naming conventions are as follows:

- **`saved_models_1`, `saved_models_2`, etc.**: Represent different training iterations or configurations.
- **`*_STAR` Suffix**: Indicates the best-performing model for a configuration. For example, `saved_models_1STAR` signifies the best model from the first iteration.
- **`model_params.txt`**: Located within each configuration folder, it specifies the hyperparameters and architecture of the model.

---

## Outputs

- **Model Checkpoints**: Best-performing models saved as `best_model.pth` in `saved_models`.
- **Plots**:
  - ROC Curve: `roc_curve_with_pauc.png`
  - Training vs Validation Loss: `training_vs_validation_loss.png`
  - Training vs Validation Accuracy: `training_vs_validation_accuracy.png`
- **Parameters**: Details saved in `model_params.txt`.

---

This README highlights the folder structure and file organization for ResNet models, aligning with the conventions used in the Conformer and DNN directories. Details of training are found in the script and the report.
