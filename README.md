# ISIC-Skin-Cancer-Detection

This repository contains a collection of pipelines, models, and resources for solving a binary classification problem using various machine learning and deep learning techniques. The directory is organized into different components, each focused on a specific aspect of the project.

---

## Project Components

### **1. Data**

- **Purpose**: Data preprocessing, normalization, and metadata preparation for training models.
- **Key Resources**:
  - `data-README.md`: Explains the structure of the data folder, including metadata files like `normalized_metadata.csv` and `normalization_params.json`.
  - `data_explorer.ipynb`: Notebook for processing and normalizing the metadata.

---

### **2. Conformer**

- **Purpose**: Implements lightweight Conformer models for image classification.
- **Key Features**:
  - Pretraining on domain-specific tasks (e.g., tumor region prediction).
  - Fine-tuning and end-to-end training options.
  - Various configurations for handling data augmentation and k-fold cross-validation.
- **Key Resources**:
  - `conformer-README.md`: Provides details about the folder structure and configurations for Conformer models.

---

### **3. Metadata DNN**

- **Purpose**: A simple feedforward neural network for metadata-based binary classification.
- **Key Features**:
  - Lightweight architecture with two hidden layers.
  - Focused on metadata features for classification.
- **Key Resources**:
  - `metadata-DNN-README.md`: Explains the directory structure, configurations, and usage of the metadata-based DNN.

---

### **4. ResNet (18 & 50 Variants)**

- **Purpose**: Fine-tunes ResNet-18 and ResNet-50 for image classification tasks.
- **Key Features**:
  - Fine-tuning options for fully connected layers and the last residual block.
- **Key Resources**:
  - `resnet-README.md`: Describes the folder structure and saved models for ResNet-based models.

---

### **5. Simple CNN**

- **Purpose**: Implements a lightweight convolutional neural network (CNN) for image classification.
- **Key Resources**:
  - `simpleConv-README.md`: Covers the directory structure and usage of the simple CNN.

---

### **6. Vision Transformer (ViT)**

- **Purpose**: Implements and fine-tunes Vision Transformer (ViT) models for image classification.
- **Key Features**:
  - Flexible fine-tuning strategies (e.g., full fine-tuning, partial layer tuning).
- **Key Resources**:
  - `vit-README.md`: Explains the configurations and folder structure for ViT-based models.

---

### **7. Fusion Models**

- **Purpose**: Combines features from multiple modalities (images, metadata) and pretrained models (Conformer, ResNet, ViT) for enhanced performance.
- **Key Variants**:
  1. **`conformer_e2e`**: Metadata + Conformer, trained end-to-end (`metaconformer_e2e.ipynb`).
  2. **`conformer_freezing`**: Metadata + Conformer, with Conformer frozen (`metaconformer.ipynb`).
  3. **`metares18conformer`**: Metadata + ResNet-18 + Conformer (`metares18conformer.ipynb`).
  4. **`metares50conformer`**: Metadata + ResNet-50 + Conformer (`metares50conformer.ipynb`).
  5. **`vmrc`**: Vision Transformer + Metadata + ResNet-50 + Conformer (`vitresmetaconformer.ipynb`).

**Our primary model of interest is `fusion_models/vitresmetaconformer.ipynb`, which achieved the best performance**. This notebook combines Vision Transformer, metadata, ResNet-50, and Conformer features for classification.

- **Key Resources**:
  - `fusion-README.md`: Details the folder structure and the five Fusion Model variants.

---

### **8. Additional Notebooks**

In the gated_cross_attn directory:
- **`output_fusion.ipynb`**: Uses an ensemble of pretrained image classifiers and XGBoost models to generate predictions on the test set.
- **`train_fusion.ipynb`**: Performs 5-fold cross-validation to produce average pAUC scores.

The directory also contains a readme for more information.

---

## Dataset Requirements

To ensure exact reproducibility, the project requires a balanced dataset in the following structure:

- **Data Files**:
  - `normalized_metadata.csv`: Preprocessed metadata.
  - `normalization_params.json`: Normalization parameters for metadata features.
  - Image files organized by labels (`1/` and `0/` folders).

This dataset can be obtained on request or through the edimension platform. Ensure all data files are placed in the `../data/balanced_data` directory.

---

## Dependency Requirements

Install the required Python libraries before running the code:

```bash
pip install torch torchvision matplotlib numpy scikit-learn scipy pandas timm
