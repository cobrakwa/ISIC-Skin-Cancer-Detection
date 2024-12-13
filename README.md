# Vision Transformer (ViT) for ISIC 2024 Challenge

This repository is part of the ISIC-Skin-Cancer-Detection project. It provides pipelines, models, and resources to solve the binary classification problem for skin lesion images as benign or malignant using various machine learning and deep learning techniques.

---

## **Project Components**

### **1. Purpose**
The primary objective is to implement and fine-tune Vision Transformer (ViT) models for binary classification tasks. The repository supports flexible workflows for data preprocessing, training, evaluation, and visualization.

### **2. Key Features**
- **Data Preprocessing and Augmentation**:
  - Balanced datasets with 393 benign and 393 malignant samples.
  - Image augmentation techniques for improved generalization.
- **Vision Transformer (ViT)**:
  - Utilizes pre-trained ViT models from `timm`.
  - Custom classifier head for binary classification.
  - Options for freezing or fine-tuning layers.
- **Metrics**:
  - Evaluates model performance using Full AUC and Partial AUC (pAUC).
  - Highlights pAUC region on the ROC curve for TPR ≥ 80%.
- **Visualization**:
  - Plots ROC curves with shaded pAUC regions.

### **3. Usage Instructions**

#### **Setup**
- Install dependencies such as `torch`, `timm`, `scikit-learn`, `Pillow`, and `matplotlib`.
- Prepare the balanced dataset from Kaggle competition
