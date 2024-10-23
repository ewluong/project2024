# Bank Marketing Campaign Analysis

## Project Overview

This project focuses on predicting whether clients will subscribe to a term deposit using data from a Portuguese banking institution's marketing campaigns. The objective was to develop a predictive model to enhance the efficiency of marketing efforts by identifying potential clients more likely to subscribe. The project was conducted following the CRISP-DM framework, ensuring a structured approach from data understanding to modeling and results interpretation.

## Dataset

The dataset originates from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/bank+marketing) and encompasses data from 17 marketing campaigns conducted between 2008 and 2013. It includes 20 input features capturing client demographics, previous marketing interactions, and economic indicators, along with a target variable indicating whether the client subscribed to a term deposit.

**Key Features:**

- **Client Information:** Age, job, marital status, education, default status, housing loan, personal loan.
- **Contact Information:** Contact communication type, last contact month and day.
- **Campaign Information:** Number of contacts during the campaign, days since last contact, previous campaign outcome.
- **Economic Indicators:** Employment variation rate, consumer price index, consumer confidence index, euribor 3-month rate, number of employees.

## Data Understanding and Preparation

Initial data exploration revealed:

- **Class Imbalance:** A significant imbalance with the majority of clients not subscribing to a term deposit.
- **Missing Values:** Instances of 'unknown' values in categorical features.
- **Feature Importance:** Variables like previous campaign outcome, contact type, and economic indicators showed potential influence on the target variable.

**Data Preparation Steps:**

1. **Data Cleaning:**
   - Replaced 'unknown' entries with `NaN` and removed missing values.
   - Dropped the 'duration' feature, as it is not available prior to the call and directly affects the target variable.

2. **Encoding Categorical Variables:**
   - Ordinal encoding for 'education' based on education level.
   - One-hot encoding for other categorical variables such as job, marital status, and contact type.

3. **Feature Scaling:**
   - Standardized numerical features using `StandardScaler` to normalize the data.

4. **Handling Class Imbalance:**
   - Adjusted class weights in models that support it to handle the imbalance between the classes.

## Modeling

Several classification models were employed to predict client subscription:

1. **Logistic Regression:**
   - Both basic and tuned versions were tested.
   - Hyperparameter tuning using `RandomizedSearchCV` improved recall significantly.

2. **K-Nearest Neighbors (KNN):**
   - Tuned hyperparameters such as the number of neighbors and distance metrics.
   - Moderate performance with lower recall compared to logistic regression.

3. **Decision Tree:**
   - Tuned parameters like max depth and minimum samples per leaf.
   - Achieved high recall but slightly lower overall performance.

4. **Support Vector Machine (SVM):**
   - Used `LinearSVC` for faster computation.
   - Balanced precision and recall but did not outperform the tuned logistic regression.

**Evaluation Metrics:**

- **Precision:** The accuracy of positive predictions.
- **Recall:** The ability to find all positive instances.
- **F1-Score:** The harmonic mean of precision and recall.
- **ROC AUC:** Measures the ability of the model to distinguish between classes.

## Key Findings

- **Tuned Logistic Regression Model:**
  - Improved **recall** to **64.77%** from **26.17%** in the basic model.
  - **F1-Score** increased to **46.30%**, indicating a better balance between precision and recall.
  - **ROC AUC** slightly improved to **0.7890**, suggesting better discrimination between subscribers and non-subscribers.

- **Feature Importance:**
  - Previous campaign outcomes, contact type, and economic indicators were significant predictors of client subscription.
  - Adjusting class weights helped address class imbalance, enhancing the model's ability to identify actual subscribers.

## Recommendations

- **Implement the Tuned Logistic Regression Model:**
  - Deploy the model to focus marketing efforts on clients more likely to subscribe.
  - Utilize the model's predictions to optimize resource allocation and campaign strategies.

- **Enhance Marketing Strategies:**
  - Leverage insights from significant features to tailor marketing messages.
  - Personalize communication based on client demographics and previous interactions.

- **Continuous Improvement:**
  - Regularly update the model with new data to maintain and improve performance.
  - Explore additional features or data sources to further enhance predictive capabilities.

## Conclusion

This project successfully developed a predictive model to identify potential clients likely to subscribe to a term deposit, providing actionable insights to optimize the bank's marketing campaigns. By applying the recommendations derived from this analysis, the bank can improve campaign efficiency, reduce costs, and increase the success rate of term deposit subscriptions.

## Jupyter Notebook

For more detailed analysis and the complete code, you can view the Jupyter Notebook [here](bank.ipynb).

---
