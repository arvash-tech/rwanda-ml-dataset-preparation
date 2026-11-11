# Question 1: Rwanda Maize Yield Dataset Preparation

## 1. Project Objective

To inspect, clean, preprocess, and prepare a Rwanda maize-yield dataset for future Machine Learning regression.

**Target variable:** `yield_t_ha` (maize yield in tonnes per hectare).

## 2. Dataset Description

- Original filename: `maize_yield_rwanda_rw.csv`
- Source: Lecturer-provided dataset
- Original records: 1,426
- Original columns: 20
- Time period: 2015–2024

## 3. Initial Data Quality Assessment

The dataset was examined using pandas to identify missing values, duplicates, data types, and possible invalid values.

| Column | Missing values |
|---|---:|
| `rainfall_mm` | 11 |
| `soil_ph` | 14 |
| `pest_incidence_index` | 14 |
| **Total** | **39** |

No exact duplicate rows were identified in the initial inspection.

## 4. Data Cleaning

A copy of the original dataset was created to preserve the source data.

The initial cleaning included:

- Checking for duplicate records.
- Filling missing values in `rainfall_mm`, `soil_ph`, and `pest_incidence_index` using column medians.
- Checking numerical values for possible invalid entries.
- Investigating potential outliers using the interquartile range (IQR) method.

IQR-flagged observations were not automatically deleted because unusual agricultural values may still be valid.

## 5. Machine Learning Preprocessing

**Task:** Supervised regression.

**Target:** `yield_t_ha`.

The preprocessing workflow included:

- Excluding `record_id` from predictive inputs.
- Separating input features from the target.
- Splitting records into 80% training and 20% testing.
- Fitting numerical imputation and scaling using training data only.
- Encoding categorical features with one-hot encoding.
- Applying the fitted transformations to the test set.

**Training records:** 1,140  
**Testing records:** 286

This approach helps prevent test-set information from influencing the fitted preprocessing rules.

## 6. Generated Files

| File | Purpose |
|---|---|
| `maize_yield_rwanda_clean.csv` | Initial cleaned dataset |
| `maize_train_ml_ready.csv` | Prepared training data |
| `maize_test_ml_ready.csv` | Prepared testing data |
| `maize_preprocessor.joblib` | Fitted preprocessing pipeline |
| `01_maize_yield_preprocessing.ipynb` | Reproducible analysis and preprocessing |

## 7. Limitations

- IQR outliers require contextual interpretation.
- Median imputation is a practical baseline and may not capture all relationships in the data.
- The random train/test split does not specifically test prediction on future agricultural seasons.
- The dataset is prepared for Machine Learning; predictive model performance has not yet been evaluated.

## 8. Conclusion

The maize-yield dataset has been inspected, cleaned, and transformed into separate Machine-Learning-ready training and testing datasets.

The resulting data supports future regression experiments to predict maize yield from agricultural and environmental features.