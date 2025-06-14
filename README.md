**Telco Customer Churn Prediction**

This project focuses on predicting customer churn for a telecommunications company. By analyzing customer data and building predictive models, the goal is to identify customers who are likely to discontinue their service. This allows the company to proactively engage with at-risk customers and implement retention strategies.

**Project Overview**
Customer churn is a critical metric for subscription-based businesses. This project walks through the process of building a machine learning model to predict churn based on various customer attributes. The analysis includes data cleaning, exploratory data analysis, feature engineering, and a comparison of several classification models.

**Data**
The dataset used is the Telco Customer Churn dataset, which contains information about customer demographics, services they have signed up for, and churn status.

**Preprocessing**
The data preprocessing steps performed in the notebook include:

Handling Missing Values: Missing TotalCharges were imputed with the mean value.

Data Type Conversion: The TotalCharges column was converted from object to a numeric type.

Label Consolidation: Redundant labels like 'No internet service' and 'No phone service' were consolidated into a single 'No' category for consistency.

**Encoding Categorical Variables:**

One-Hot Encoding: Applied to categorical features like gender, Contract, and PaymentMethod to convert them into a numerical format.

Label Encoding: The target variable Churn was converted to a binary format (Yes=1, No=0).

Handling Class Imbalance: The dataset is imbalanced, with fewer churners than non-churners. The Synthetic Minority Over-sampling TEchnique (SMOTE) was used to balance the class distribution in the training set.

**Exploratory Data Analysis (EDA)**
Gender Distribution: The dataset is well-balanced between male and female customers.

Continuous Features: The distributions of tenure, MonthlyCharges, and TotalCharges were analyzed. TotalCharges showed a right-skewed distribution, which was addressed using a log transformation.

Correlation: A positive correlation was observed between MonthlyCharges and TotalCharges. Higher monthly charges were also associated with a higher likelihood of churn.

**Feature Engineering**
Discretizing Tenure: The tenure feature was binned into ranges (e.g., 0-1 year, 1-2 years) to better capture its relationship with churn. The analysis showed that churn is highest in the first year and decreases as tenure increases.

**Modeling**
Several classification models were trained and evaluated to predict customer churn:

- Logistic Regression: A baseline linear model.

- Support Vector Machine (SVM): A linear SVM was implemented.

- XGBoost: A gradient boosting model, with hyperparameter tuning performed using RandomizedSearchCV.

- Multi-layer Perceptron (MLP): A simple neural network model.

Cross-validation was used to ensure the robustness of the models' performance.

**Results**
The performance of the models was evaluated using metrics such as precision, recall, and F1-score. The classification reports for each model on the test set are summarized below:

**Logistic Regression:**

Accuracy: 80%

F1-score for 'Yes' (Churn): 0.61

**SVM:**

Accuracy: 80%

F1-score for 'Yes' (Churn): 0.60

**XGBoost:**

Accuracy: 78%

F1-score for 'Yes' (Churn): 0.60

**MLP:**

Accuracy: 76%

F1-score for 'Yes' (Churn): 0.56

The models show comparable performance, with Logistic Regression and SVM having a slight edge in this implementation. The confusion matrices provide a detailed look at the true positive and false positive rates for each model.

**Business Insights**
The analysis of the customer churn data provides several actionable insights that can help the telecommunications company improve customer retention:

- Focus on New Customers: The first year is a critical period for customer retention, as the churn rate is highest among customers with a tenure of 0-12 months.

- Recommendation: Implement a robust customer onboarding program, offer loyalty discounts after the first year, and conduct regular satisfaction surveys to address any issues early on.

**Review Pricing and Contract Structures:**

- Month-to-Month Contracts: Customers on these flexible contracts are significantly more likely to churn.

- Recommendation: Incentivize customers to commit to longer-term (one or two-year) contracts by offering exclusive benefits or discounts.

- High Monthly Charges: A clear correlation exists between higher monthly fees and increased churn rates.

- Recommendation: Analyze the value proposition of premium plans. Consider offering personalized, cost-effective bundles or better communicating the value of these services to justify their cost.

**Enhance Value-Added Services:**

- Tech Support & Online Security: Customers who opt out of services like Tech Support and Online Security are more likely to leave. These services increase customer dependency and "stickiness."

- Recommendation: Promote the advantages of these services, possibly by including them in a trial period, to increase adoption and integration into the customer's daily life.

**Optimize Payment Methods:**

- Electronic Checks: This payment method is associated with the highest churn rate, possibly due to payment failures or its preference among less-committed customers.

- Recommendation: Encourage a switch to automatic payment methods like credit cards or bank transfers by offering a small incentive, reducing payment friction and preventing involuntary churn.

**Proactive Retention with Predictive Modeling:** The predictive models, while having room for improvement, provide a solid foundation for identifying at-risk customers.

- Recommendation: Integrate the model's predictions into a Customer Relationship Management (CRM) system. This enables the retention team to proactively engage with high-risk customers, offering tailored support or incentives before they decide to cancel their service.
