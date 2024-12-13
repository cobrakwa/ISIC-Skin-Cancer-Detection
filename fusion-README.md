# Fusion Model README

This README provides a brief overview of the Fusion Model for image and metadata-based binary classification.

---

## Overview

The Fusion Model combines features from multiple pretrained models (Conformer, Vision Transformer, ResNet, and a metadata DNN) to improve classification performance. It leverages diverse input modalities, including image and metadata features, through a unified architecture.

---

## Model Configurations

The Fusion Model is available in the following variants, each stored in a dedicated subfolder under `fusion_models`:

1. **`conformer_e2e`**  
   - Combines metadata and Conformer features, with both trained end-to-end.  
   - Produced by `metaconformer_e2e.ipynb`.

2. **`conformer_freezing`**  
   - Similar to `conformer_e2e`, but only the classification head is trained, with the Conformer model frozen.  
   - Produced by `metaconformer.ipynb`.

3. **`metares18conformer`**  
   - Combines metadata, ResNet-18, and Conformer features.  
   - Produced by `metares18conformer.ipynb`.

4. **`metares50conformer`**  
   - Similar to `metares18conformer`, but uses ResNet-50 instead of ResNet-18.  
   - Produced by `metares50conformer.ipynb`.

5. **`vmrc`**  
   - Combines Vision Transformer (ViT), metadata, ResNet-50, and Conformer features.  
   - Produced by `vitresmetaconformer.ipynb`.

Each variant has its own folder, containing saved models, parameters, and plots from the corresponding training configuration.

---

## Directory Structure

Each variant folder within `fusion_models` follows this structure:

- **Saved Models**: Contains checkpoints for the trained models.
- **`model_params.txt`**: Specifies the architecture and fine-tuning details for the Fusion Model variant.
- **Plots**:
  - `roc_curve.png`: ROC curve with performance metrics.
  - `train_val_loss.png`: Training vs Validation Loss.
  - `train_val_accuracy.png`: Training vs Validation Accuracy.

---

## Outputs

- **Best Models**: Saved as `best_model.pth` in the respective variant folder.
- **Performance Metrics**:
  - Accuracy
  - ROC AUC
  - Partial AUC (pAUC)
  - Classification Report
- **Visualizations**: Include ROC Curve, training vs validation loss, and accuracy plots.

---

This README highlights the folder structure and file organization for the Fusion Model, tailored for different fusion strategies. It follows conventions established in the Conformer, DNN, ResNet, and Vision Transformer directories. Do note that training details are found in the script and in the report
