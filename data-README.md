# Data README

The data folder contains the data csv and metadata files required for training and inference.

---

## Files

1. **`balanced_train_metadata.csv`**  
   - CSV file containing balanced training data metadata.

2. **`normalized_metadata.csv`**  
   - Metadata processed with normalization applied to the training set.

3. **`normalization_params.json`**  
   - JSON file storing normalization parameters (e.g., min, max, median) calculated from the training set.  
   - **Required for inference** to ensure data is processed in the same way as during training.

These files are outputs of `data_explorer.ipynb`. The notebook performs the following steps:

- **Metadata Processing**: Cleans the original `balanced_train_metadata.csv` by dropping irrelevant columns, handling missing values, and encoding categorical variables into numerical formats.
- **Normalization**: Normalizes numerical features to a [0, 1] range using their minimum and maximum values, storing the parameters in `normalization_params.json` for reproducibility.
- **Outputs**: Produces `normalized_metadata.csv` for training and ensures consistent preprocessing during inference using the normalization parameters.


---

## Notes

- Always use `normalization_params.json` during inference to maintain consistency in data preprocessing.
