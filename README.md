**Diabetes Prediction Analysis**

## **Introduction**
This project explores diabetes prediction using statistical and machine learning models. The goal is to identify the best classification model to predict the presence of diabetes based on various health-related features. The dataset consists of 100,000 survey responses, and the analysis involves building and comparing models such as logistic regression, decision trees, and Naive Bayes classifiers.

## **Dataset**
The dataset contains the following explanatory variables and response variable:

### **Explanatory Variables**
| Variable             | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| `age`                | Age of the respondent (Quantitative)                                       |
| `bmi`                | Body Mass Index of the respondent (Quantitative)                          |
| `HbA1c_level`        | Average blood glucose concentration over the past 3 months (Quantitative) |
| `blood_glucose_level`| Blood glucose level of the respondent (Quantitative)                      |
| `gender`             | Gender of the respondent (0 = Male, 1 = Female, 2 = Other)                |
| `hypertension`       | Presence of hypertension (0 = No, 1 = Yes)                                |
| `heart_disease`      | Presence of heart disease (0 = No, 1 = Yes)                               |
| `smoking_history`    | Smoking status (0 = Current, 1 = Ever, 2 = Former, 3 = Never, etc.)       |

### **Response Variable**
| Variable     | Description                                              |
|--------------|----------------------------------------------------------|
| `diabetes`   | Indicates whether the respondent has diabetes (0 = No, 1 = Yes) |

---

## **Analysis Workflow**

### **1. Data Exploration and Summary**
- **Summary Statistics**: Descriptive statistics for both quantitative and categorical variables.
- **Visualizations**: Histograms for quantitative variables and bar plots for categorical variables.
- **Associations**: Boxplots and statistical tests to assess the strength of association between predictors and the presence of diabetes.

### **2. Models Tested**
1. **Logistic Regression**:
   - Tested multiple variations by removing insignificant regressors.
   - Final model achieved:
     - **AUC**: 0.9619
     - **FNR**: 0.3761

2. **Decision Tree**:
   - Built with a complexity parameter of 0.1 and split criteria based on information gain.
   - Final model achieved:
     - **AUC**: 0.8360
     - **FNR**: 0.3280

3. **Naive Bayes**:
   - Models tested with and without weakly associated regressors.
   - Final model achieved:
     - **AUC**: 0.9496
     - **FNR**: 0.3583

---

## **Key Findings**
1. **Quantitative Variables**:
   - Age, HbA1c level, and blood glucose level show strong associations with diabetes.
   - BMI shows a weaker association.

2. **Categorical Variables**:
   - Hypertension and heart disease are strongly associated with diabetes.
   - Smoking history and gender show weaker associations.

3. **Model Recommendation**:
   - **Decision Tree** is the recommended model due to its low **False Negative Rate (FNR)** of 0.3280, which minimizes missed diagnoses. This is crucial for early detection and prevention of severe health complications related to diabetes.

---

## **How to Run**
### **Prerequisites**
- **R Environment**: Install R and required libraries (`rpart`, `e1071`, `ROCR`, etc.).
- Dataset: Ensure the `diabetes-dataset.csv` file is in the working directory.

### **Execution Steps**
1. Clone the repository:
   ```bash
   git clone https://github.com/sivaadharsh28/DSA1101_Assignment2.git
   cd DSA1101_Assignment2
   ```
2. Run the R script in the terminal or an IDE:
   ```R
   source("diabetes_analysis.R")
   ```
3. Results, including ROC curves, performance metrics, and visualizations, will be generated.

---

## **Project Structure**
```
DSA1101_Assignment2/
├── diabetes-dataset.csv      # Input dataset
├── diabetes_analysis.R       # R script with analysis
├── figures/                  # Generated visualizations (ROC curves, histograms, etc.)
└── README.md                 # Project documentation
```

---

## **Results**
| Model              | AUC    | FNR    |
|---------------------|--------|--------|
| Logistic Regression | 0.9619 | 0.3761 |
| Decision Tree       | 0.8360 | 0.3280 |
| Naive Bayes         | 0.9496 | 0.3583 |

While logistic regression achieved the highest AUC (0.9619), the **decision tree** was selected as the best model due to its lower FNR (0.3280), making it more suitable for identifying diabetes cases.

---
