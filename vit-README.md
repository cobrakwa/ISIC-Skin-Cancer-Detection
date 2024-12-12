# Vision Transformer (ViT) README

This README provides an overview of how to utilize Vision Transformer (ViT) models for image classification tasks. The project includes several notebook implementations focusing on different fine-tuning strategies, such as tuning specific encoder layers, focusing on the final layer, or only modifying the classification head.

---

## Key Components and Workflow

### **1. Imports**

Essential libraries for this project include:

-   **PyTorch** for deep learning model implementation and training.
-   **Torchvision** for pretrained Vision Transformer models and dataset utilities.
-   **Scikit-learn** for evaluation metrics like `classification_report` and ROC curves.
-   **Matplotlib** for visualization of model performance.

---

### **2. Function Definitions**

-   **Custom Metric**: Implements a partial Area Under the Curve (pAUC) metric focusing on TPR thresholds to evaluate model performance more granularly.
-   **Model Loading**: Loads the ViT model with options to freeze layers and replace the classification head based on the number of classes.

---

### **3. Model Configurations**

The project provides flexibility in how the Vision Transformer model is fine-tuned:

-   **Full Fine-tuning**: All layers are trainable.
-   **Partial Fine-tuning**:
    -   Only the final 3 encoder layers are trainable.
    -   Only the final encoder layer is trainable.
    -   Only the fully connected (classification) layer is trainable.

Each approach allows for experimentation to balance between computational efficiency and model accuracy.

---

### **4. Hyperparameters**

The default settings for training include:

-   **Batch Size**: 32
-   **Learning Rate**: \(5 \times 10^{-6}\)
-   **Number of Epochs**: 50
-   **Dropout Rate**: 0.4
-   **Optimizer**: Adam
-   **Loss Function**: CrossEntropyLoss

---

### **5. Dataset Preprocessing**

-   **Augmentations**: Includes resizing, normalization, random rotations, and horizontal flips to enhance generalization.
-   **Dataset Splits**: Uses stratified train, validation, and test splits to ensure balanced class distributions.
-   **Custom Datasets**: Combines augmented and non-augmented datasets for a more robust training process.

---

### **6. Training Process**

-   Tracks training and validation loss/accuracy for each epoch.
-   Saves the best model based on validation loss.

---

### **7. Evaluation**

-   **Testing**: Evaluates the model on the test set using:
    -   Loss
    -   Accuracy
    -   Classification Report
    -   Partial AUC (pAUC)
-   **Visualizations**:
    -   ROC Curve with pAUC highlights.
    -   Training vs. Validation Loss plot with Test Loss annotation.
    -   Training vs. Validation Accuracy plot with Test Accuracy annotation.

---

### **8. Model Saving**

-   **Best Model Checkpoint**: Saved as `best_model.pth`.
-   **Plots**: ROC curve and performance metrics saved as PNG files in `saved_models/`.
-   **Model Parameters**: Saved in `model_params.txt` for reproducibility.

---

## Running the Notebooks

1. **Dataset Preparation**: Ensure the dataset is located in the `../../data/balanced_data/` directory.
2. **Choose a Notebook**: Select the appropriate notebook based on your fine-tuning requirements:
    - Full fine-tuning.
    - Fine-tuning the last few encoder layers.
    - Fine-tuning only the classification head.
3. **Train the Model**: Execute the cells to preprocess the data, train the model, and evaluate its performance.
4. **Save Results**: Generated plots and model parameters will be stored in the `saved_models/` directory.

---

## Customizing Fine-Tuning

To experiment with different fine-tuning approaches, modify the `load_pretrained_vit` function:

-   Adjust `requires_grad` for specific layers.
-   Replace the classification head with a custom architecture if necessary.

---

## Example Notebooks

The repository includes several notebooks for Vision Transformer fine-tuning:

1. **Fine-tune Full Model**: Train all layers of the ViT model.
2. **Focus on Final Layers**: Train only the last 3 encoder layers.
3. **Minimal Fine-Tuning**: Train only the classification head for efficient adaptation.

---

## Results and Logs

-   Best model checkpoints, training logs, and visualizations are saved for each experiment.
-   Use the `model_params.txt` file to reproduce any experiment setup.

---

This README is a guide to quickly understand and utilize the provided notebooks for ViT-based image classification. Choose the fine-tuning approach based on your computational resources and dataset size for optimal results.
