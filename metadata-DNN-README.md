# Metadata DNN Model README

This README outlines the workflow for training a deep neural network (DNN) on metadata for binary classification.

---

## Workflow

### **1. Data**

-   **Dataset**: Metadata loaded from `normalized_metadata.csv`.
-   **Splits**: Train (80%), validation (10%), test (10%).
-   **Features**: Numerical columns after dropping `isic_id` and `target`.
-   **Labels**: Encoded if not numeric.

---

### **2. Model**

-   **Architecture**:
    -   Input layer matching feature dimensions.
    -   2 hidden layers (ReLU, Dropout).
    -   Output layer with softmax activation.
-   **Dropout**: 0.5 for regularization.

---

### **3. Hyperparameters**

-   **Batch Size**: 64
-   **Learning Rate**: 0.001
-   **Epochs**: 50
-   **Loss Function**: CrossEntropyLoss
-   **Optimizer**: Adam

---

### **4. Training**

-   Tracks train/validation loss and accuracy.
-   Saves the best model as `best_model.pth`.

---

### **5. Evaluation**

-   **Metrics**:
    -   Accuracy
    -   ROC AUC
    -   Partial AUC (pAUC)
    -   Classification Report
-   **Plots**:
    -   ROC Curve
    -   Train vs Validation Loss
    -   Train vs Validation Accuracy

---

## Results and Files

-   **Model**: Best-performing model saved in `saved_models/best_model.pth`.
-   **Plots**:
    -   `roc_curve.png`: ROC curve and pAUC highlights.
    -   `train_val_loss.png`: Training vs Validation Loss.
    -   `train_val_accuracy.png`: Training vs Validation Accuracy.
-   **Parameters**: Stored in `model_params.txt`.

---

This DNN framework efficiently handles metadata for classification, providing insights through robust evaluation and visualizations.
