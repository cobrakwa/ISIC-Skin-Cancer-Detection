# Conformer Model README

This README provides a quick overview of training, validating, and testing a lightweight Conformer model for image classification tasks using PyTorch.

---

## Workflow Overview

### **1. Imports**

Key libraries:

-   **PyTorch**: Model building, training, and evaluation.
-   **Torchvision**: Data loading and transformations.
-   **Matplotlib**: Visualization of metrics.

---

### **2. Data Loading**

-   Dataset: Images are loaded from the `../data/balanced_data` directory.
-   Augmentations: Applied during training for robustness.
-   Splits: Stratified train, validation, and test splits to ensure balanced class distribution.
-   Class Distributions: Automatically checked for each split.

---

### **3. Model Architecture**

The Conformer model consists of:

1. **Convolutional layers**: Extract spatial features.
2. **Transformer encoder**: Capture long-range dependencies.
3. **Fully connected layer**: Perform classification.

Parameters like embedding dimension, number of heads, and transformer layers are configurable.

---

### **4. Training Process**

-   Loss Function: `CrossEntropyLoss`
-   Optimizer: `Adam` with a learning rate of `1e-4`.
-   Best Model: Automatically saved based on validation loss.

---

### **5. Evaluation**

-   Metrics: AUC, partial AUC (pAUC), ROC curves, accuracy, and classification report.
-   Results: Plots and metrics saved to `scratch_test_augmentless/saved_models`.

---

### **6. Visualizations**

-   **Loss**: Train vs validation.
-   **Accuracy**: Train vs validation.
-   **ROC Curve**: Highlights AUC and pAUC performance.
-   **Combined Metrics**: Includes AUC, pAUC, loss, and accuracy.

---

### **7. Model Saving**

-   Best Model: Saved with epoch info.
-   Plots: Saved as `.png` files for reference.
-   Parameters: Stored in `model_params.txt` for reproducibility.

---

## Running the Code

1. Prepare the dataset in `../data/balanced_data`.
2. Configure parameters in the notebook/script.
3. Train and validate the model.
4. Evaluate the best model on the test set.
5. Review saved plots and reports in `saved_models`.

---

## Key Files

-   **`best_model_epoch*.pth`**: Best model checkpoint.
-   **`classification_report.txt`**: Test classification performance.
-   **`combined_metrics.png`**: Overview of training and evaluation metrics.
-   **`model_params.txt`**: Detailed model architecture and parameters.

---

This concise guide helps you quickly set up and run the Conformer model for your classification task!
