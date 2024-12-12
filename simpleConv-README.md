# Simple Convolutional Neural Network (CNN) README

This README provides a quick overview of a basic CNN pipeline for image classification.

---

## Workflow

### **1. Data**

-   **Dataset**: Located in `../data/balanced_data`.
-   **Augmentations**: Includes random flips, rotations, and crops for training.
-   **Splits**: Train, validation, and test sets.

---

### **2. Model**

-   **Architecture**:
    -   3 convolutional layers with batch normalization, ReLU activation, and dropout.
    -   Global average pooling followed by a fully connected layer for classification.

---

### **3. Hyperparameters**

-   **Batch Size**: 32
-   **Learning Rate**: `1e-4`
-   **Epochs**: 30
-   **Loss Function**: CrossEntropyLoss
-   **Optimizer**: Adam

---

### **4. Training**

-   Tracks training and validation loss/accuracy.
-   Saves the best model to `saved_models/best_model.pth`.

---

### **5. Evaluation**

-   **Metrics**: Accuracy, AUC, pAUC, classification report.
-   **Visualizations**: Training/validation loss, accuracy, and ROC curve.

---

## Results and Files

-   **Model**: Best model saved as `best_model.pth`.
-   **Plots**: Metrics and ROC curve saved in `saved_models/`.
-   **Parameters**: Detailed in `model_params.txt`.

---

This project implements a lightweight, customizable CNN suitable for binary or multiclass image classification tasks.
