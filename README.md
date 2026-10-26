# Bank Marketing Prediction Using Machine Learning

## Project Overview

This project compares four supervised machine learning classification algorithms to predict whether a customer will subscribe to a bank term deposit based on customer and marketing campaign information.

The project uses the Bank Marketing dataset containing 45,211 records and 17 columns. Exploratory Data Analysis (EDA), data preprocessing, model training, and evaluation are performed to identify a suitable classification model.

## Objectives

- Understand and explore the Bank Marketing dataset.
- Perform data preprocessing and exploratory data analysis.
- Analyze customer subscription patterns.
- Train and compare four classification algorithms.
- Evaluate models using accuracy, precision, recall, F1-score, and ROC-AUC.
- Identify a suitable model for predicting term-deposit subscriptions.
- Provide business recommendations based on the results.

## Dataset

The dataset contains customer information and details about bank marketing campaigns.

- **Total records:** 45,211
- **Total columns:** 17
- **Target variable:** `y`
- **Target classes:** `yes` and `no`

The target variable indicates whether a customer subscribed to a term deposit.

### Target Distribution

| Outcome | Number of Customers | Percentage |
|---|---:|---:|
| No subscription | 39,922 | 88.3% |
| Subscription | 5,289 | 11.7% |

The dataset has an imbalanced target distribution, so multiple evaluation metrics are used rather than relying on accuracy alone.

## Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Methodology

### 1. Data Understanding and Preprocessing

- Inspected dataset dimensions, column names, data types, and descriptive statistics.
- Checked missing values, unknown categorical values, and duplicate records.
- Separated input features from the target variable.
- Encoded categorical features using one-hot encoding.
- Standardized numerical features where appropriate.
- Split the data into training and testing sets using an 80:20 ratio with stratification.

The `duration` feature was excluded from model inputs because call duration is known only after a call has taken place. This supports the objective of predicting potential subscribers before contacting them.

### 2. Exploratory Data Analysis

The analysis examines:

- Target-class distribution.
- Subscription rates across job categories.
- Subscription rates across marital-status categories.
- Subscription rates across education categories.
- Patterns associated with customer subscription outcomes.

### 3. Machine Learning Algorithms

Four classification algorithms were trained and evaluated:

1. Logistic Regression
2. Decision Tree Classifier
3. K-Nearest Neighbors (KNN)
4. Random Forest Classifier

### 4. Evaluation Metrics

The models were compared using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

Confusion matrices and ROC curves were also used to analyze classification performance.

## Results

The following results were obtained from the test dataset.

| Model | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 0.8933 | 0.6632 | 0.1786 | 0.2815 | 0.7717 |
| Decision Tree | 0.8309 | 0.2982 | 0.3289 | 0.3128 | 0.6132 |
| KNN | 0.8874 | 0.5529 | 0.1975 | 0.2911 | 0.7027 |
| Random Forest | **0.8954** | 0.6373 | 0.2457 | **0.3547** | **0.7888** |

### Key Findings

- Random Forest achieved the highest accuracy, F1-score, and ROC-AUC among the evaluated models.
- Logistic Regression achieved the highest precision.
- Decision Tree achieved the highest recall at the evaluated classification threshold.
- The imbalanced target distribution makes recall and F1-score important for assessing subscriber identification.
- Random Forest is the strongest overall candidate based on the evaluated metrics, although its recall indicates room for improvement.

## Business Recommendations

- Use model predictions to prioritize potential customers for marketing campaigns.
- Evaluate alternative classification thresholds to improve subscriber identification while considering campaign costs.
- Monitor model performance and retrain using updated data when appropriate.

## Limitations

- The target classes are imbalanced.
- The evaluated models do not identify all actual subscribers.
- Historical customer patterns may not represent future campaigns.
- Additional models, threshold tuning, and validation on newer data may improve performance.

## Project Structure

```text
Bank-Marketing-Prediction/
├── bank_marketing_classification.ipynb
├── bank-full.csv
├── README.md
└── requirements.txt
```

*Update the filenames in this structure if your actual files use different names.*

## Installation and Usage

### Prerequisites

Install Python 3 and Jupyter Notebook.

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd Bank-Marketing-Prediction
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open the notebook, ensure `bank-full.csv` is in the expected location, and run the cells in order.

## Conclusion

This project demonstrates how supervised machine learning can support bank marketing by predicting customer subscription outcomes. Random Forest provided the strongest overall results among the four evaluated algorithms, but further improvements in recall and validation on newer data are recommended before practical deployment.

## Author

**Student Project — Fundamentals of Data Science**

