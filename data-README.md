# Data README

The data folder contains the data csv and metadata files required for training and inference.

---

## Files

1. **`balanced_train_metadata.csv`**  
   - CSV file containing balanced training data metadata.

2. **`normalized_metadata.csv`**  
   - Metadata processed with normalization applied to the training set.

3. **`normalization_params.json`**  
   - JSON file storing normalization parameters (e.g., mean, std) calculated from the training set.  
   - **Required for inference** to ensure data is processed in the same way as during training.

---

## Notes

- Always use `normalization_params.json` during inference to maintain consistency in data preprocessing.
