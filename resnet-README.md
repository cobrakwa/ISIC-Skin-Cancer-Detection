# ResNet (18 & 50 Variants) README

This README provides a concise guide for training, validating, and testing ResNet-18 and ResNet-50 models for image classification tasks using PyTorch.

---

## Workflow Overview

### **1. Imports**

Key libraries include:

-   **PyTorch**: Model training and evaluation.
-   **Torchvision**: Pretrained ResNet models and dataset utilities.
-   **Matplotlib**: Visualizations.
-   **Scikit-learn**: Evaluation metrics (e.g., AUC, ROC curves).

---

### **2. Model Variants**

-   **ResNet-18**: Lightweight model, suitable for smaller datasets or limited resources.
-   **ResNet-50**: Deeper architecture, better for larger datasets and more complex tasks.

Each model is fine-tuned to update only:

1. The **fully connected layer (fc)**.
2. The **last residual block** (`layer4`) for better adaptation.

---

### **3. Data Processing**

-   **Transforms**: Resize, normalization, and augmentations for robustness.
-   **Splits**: Stratified train, validation, and test sets to ensure balanced class distributions.
-   **Augmented Dataset**: Combines augmented and original images for training.

---

### **4. Training**

-   **Loss Function**: `CrossEntropyLoss`.
-   **Optimizer**: Adam with a learning rate of `5e-6`.
-   **Epochs**: 50.
-   **Batch Size**: 32.
-   **Best Model**: Automatically saved based on validation loss.

---

### **5. Evaluation**

-   **Metrics**:
    -   Accuracy
    -   AUC
    -   Partial AUC (pAUC)
    -   Classification Report
-   **Visualizations**:
    -   Training vs Validation Loss
    -   Training vs Validation Accuracy
    -   ROC Curve with pAUC highlights

---

### **6. Model Saving**

-   **Best Model**: Saved as `best_model.pth`.
-   **Plots**: Saved as `.png` files in `saved_models/`.
-   **Parameters**: Stored in `model_params.txt` for reproducibility.

---

## How to Use

1. **Dataset Setup**: Place images in the `../data/balanced_data` directory.
2. **Select Model**: Choose ResNet-18 or ResNet-50 and load pretrained weights.
3. **Train**: Run the training script to fine-tune the model.
4. **Evaluate**: Use the best saved model for testing and generate metrics/plots.
5. **Review Results**: Check saved plots, classification reports, and logs in `saved_models/`.

---

## Key Files

-   **`best_model.pth`**: Best-performing model checkpoint.
-   **`roc_curve_with_pauc.png`**: ROC curve highlighting pAUC.
-   **`training_vs_validation_loss.png`**: Train vs Validation loss.
-   **`training_vs_validation_accuracy.png`**: Train vs Validation accuracy.
-   **`model_params.txt`**: Hyperparameters and architecture.

---

This guide helps you efficiently use ResNet-18 or ResNet-50 for your classification tasks with pretrained weights and fine-tuning strategies.
