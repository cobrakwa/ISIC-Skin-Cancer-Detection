# Vision Transformer (ViT) README

This README provides a quick overview of the Vision Transformer (ViT) models for image classification, focusing on fine-tuning strategies and directory organization.

---

## Overview

The Vision Transformer (ViT) directory follows a structure similar to the Conformer, DNN, and ResNet directories. It contains configurations for various fine-tuning strategies, saved checkpoints, and corresponding training information.

---

## Model Configurations

The ViT models provide flexibility for experimentation with fine-tuning strategies:

- **Full Fine-tuning**: All layers are trainable.
- **Partial Fine-tuning**:
  - Only the final 3 encoder layers are trainable.
  - Only the final encoder layer is trainable.
  - Only the fully connected (classification) layer is trainable.

---

## Directory Structure

The `saved_models` folder contains models saved during different fine-tuning experiments. Naming conventions are as follows:

- **`saved_models_1`, `saved_models_2`, etc.**: Represent different fine-tuning iterations or configurations.
- **`*_STAR` Suffix**: Indicates the best-performing model for a particular configuration (e.g., `saved_models_1STAR`).
- **`model_params.txt`**: Located within each configuration folder, it specifies the architecture and fine-tuning details for the model.

---

## Outputs

- **Model Checkpoints**: Best-performing models saved as `best_model.pth` in `saved_models`.
- **Plots**:
  - ROC Curve: `roc_curve.png`
  - Training vs Validation Loss: `train_val_loss.png`
  - Training vs Validation Accuracy: `train_val_accuracy.png`
- **Parameters**: Details saved in `model_params.txt`.

---

This README highlights the folder structure and file organization for ViT models, following conventions established in the Conformer, DNN, and ResNet directories. Training details are found in the script and in the report.
