# Simple Convolutional Neural Network (CNN) README

This README provides a brief overview of the Simple CNN pipeline for image classification.

---

## Overview

The Simple CNN directory follows a structure similar to the Conformer, DNN, and ResNet directories. It includes saved models, metrics, and configurations for lightweight CNN-based image classification.

---

## Directory Structure

The `saved_models` folder contains models saved during training. Naming conventions are as follows:

- **`saved_models_1`, `saved_models_2`, etc.**: Represent different training iterations or configurations.
- **`*_STAR` Suffix**: Indicates the best-performing model for a configuration (e.g., `saved_models_1STAR`).
- **`model_params.txt`**: Located within each configuration folder, it specifies the architecture and hyperparameters for the model.

---

## Outputs

- **Model Checkpoints**: Best-performing models saved as `best_model.pth` in `saved_models`.
- **Plots**:
  - ROC Curve: `roc_curve.png`
  - Training vs Validation Loss: `train_val_loss.png`
  - Training vs Validation Accuracy: `train_val_accuracy.png`
- **Parameters**: Details saved in `model_params.txt`.

---

This README highlights the folder structure and file organization for the Simple CNN, following conventions established in the Conformer, DNN, and ResNet directories. Training details are found in the script and in the report.
