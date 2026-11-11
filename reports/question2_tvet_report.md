# Question 2: Rwandan TVET Student Performance Dataset Preparation

## 1. Project Title

**Predicting Student Academic Pass/Fail Outcomes in a Rwandan TVET Institution Using Machine Learning**

## 2. Problem Statement

Student academic performance is an important area of educational research. Factors such as attendance, study time, previous academic performance, and access to learning resources may be associated with student outcomes.

This project prepares a synthetic dataset for demonstrating how Machine Learning could be used to classify student outcomes as Pass or Fail.

## 3. Project Objectives

- Generate 1,000 synthetic student records.
- Include at least 8 predictive input features.
- Inspect and validate the dataset.
- Clean and preprocess the data.
- Encode categorical variables.
- Prepare separate training and testing datasets.
- Document the preprocessing workflow.

## 4. Dataset Description

**Dataset name:** `tvet_student_performance_synthetic_raw.csv`

**Data source:** Artificially generated using Python, NumPy, and pandas.

**Number of records:** 1,000

**Number of columns:** 12

**Predictive input features:** 10

**Target variable:** `pass_fail`

**Machine Learning task:** Supervised binary classification.

### Dataset Features

| Feature | Description |
|---|---|
| `student_id` | Fictional, unique student identifier |
| `district` | Illustrative Rwandan district |
| `tvet_level` | Fictional student's TVET level |
| `department` | Area of technical study |
| `attendance_rate` | Attendance percentage |
| `study_hours_per_week` | Weekly study hours |
| `assignment_average` | Assignment score percentage |
| `previous_term_mark` | Previous academic term mark |
| `internet_access` | Yes or No |
| `distance_to_school_km` | Distance to school in kilometres |
| `continuous_assessment_average` | Continuous assessment percentage |
| `pass_fail` | Classification target: Pass or Fail |

The `student_id` column is an identifier, not a predictive feature.

## 5. Synthetic Data Generation

The dataset was generated using NumPy's random number generator with a fixed seed of 42.

Numerical values were sampled from predefined illustrative ranges, while categorical values were selected from predefined categories.

Pass/Fail outcomes were generated using an artificial scoring formula combining attendance, study hours, assignment performance, previous-term marks, continuous assessment, and random variation.

**Important:** The formula is not an official Rwandan TVET grading policy. The records are fictional and do not represent actual students.

## 6. Data Inspection and Cleaning

The dataset was inspected for:

- Missing values.
- Duplicate records and student identifiers.
- Invalid numerical ranges.
- Incorrect data types.
- Unexpected target labels.

The raw dataset was preserved, and a separate cleaned dataset was saved.

## 7. Machine Learning Preprocessing

The `student_id` identifier was excluded from predictive inputs.

The dataset was divided into:

- **Training set:** 800 records (80%).
- **Testing set:** 200 records (20%).

A stratified split was used to preserve the approximate Pass/Fail proportions.

Numerical features were processed using median imputation and standard scaling.

Categorical features were processed using most-frequent imputation and one-hot encoding.

The preprocessing transformations were fitted on the training data and then applied to the testing data to prevent test-set leakage.

## 8. Generated Files

| File | Purpose |
|---|---|
| `tvet_student_performance_synthetic_raw.csv` | Original generated dataset |
| `tvet_student_performance_clean.csv` | Cleaned dataset |
| `tvet_train_ml_ready.csv` | ML-ready training dataset |
| `tvet_test_ml_ready.csv` | ML-ready testing dataset |
| `tvet_preprocessor.joblib` | Saved fitted preprocessing pipeline |
| `02_tvet_student_performance.ipynb` | Reproducible Jupyter Notebook |

## 9. Limitations

- The dataset is synthetic rather than collected from real students.
- The generated values and relationships are assumptions made for educational demonstration.
- The target labels are based on an artificial scoring mechanism.
- Any model trained on this dataset would learn synthetic patterns rather than validated real-world relationships.
- The dataset should not be used to make actual decisions about student performance.

## 10. Conclusion

A synthetic dataset containing 1,000 records and 10 predictive features was generated, inspected, cleaned, and transformed into training and testing datasets suitable for demonstrating binary classification.

The project demonstrates reproducible dataset preparation, categorical encoding, numerical preprocessing, and train/test separation.

**Data provenance:** Synthetic data — educational demonstration only.