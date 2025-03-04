# Lead Scoring Case Study

## Problem Statement

An education company named **X Education** sells online courses to industry professionals. The company generates leads through various marketing efforts, such as Google ads and referrals. When a potential lead fills out a form on the website, they are classified as a lead. The sales team then contacts these leads, but only about **30%** of them convert into paying customers. The company aims to improve this conversion rate to **80%** by identifying the most promising leads.

The goal of this case study is to build a **logistic regression model** to assign a lead score between **0 and 100** to each lead. Leads with higher scores should have a higher likelihood of conversion, while those with lower scores should have a lower likelihood.

---

## Steps in the Analysis

1. **Read and Understand the Data**
   - Load the dataset and inspect its structure, columns, and summary statistics.
   - Identify the types of variables (categorical, numerical) and check for missing values.

2. **Data Cleaning**
   - Handle missing values by dropping columns with a high percentage of null values.
   - Remove columns with a single dominant value (e.g., columns where almost all values are "No").
   - Drop irrelevant columns like `City` and `Country`.
   - Handle the "Select" level in categorical variables, which indicates that the user did not select an option.

3. **Data Preparation for Model Building**
   - Encode categorical variables using dummy variables.
   - Split the data into training and testing sets.
   - Scale numerical features if necessary.

4. **Model Building**
   - Build a logistic regression model to predict the likelihood of lead conversion.
   - Use features like `TotalVisits`, `Total Time Spent on Website`, `Page Views Per Visit`, and other relevant variables.

5. **Model Evaluation**
   - Evaluate the model using metrics like **accuracy**, **precision**, **recall**, and **ROC-AUC**.
   - Ensure the model achieves the target lead conversion rate of **80%**.

6. **Making Predictions on the Test Set**
   - Assign lead scores to each lead in the test set.
   - Identify the most promising leads based on the assigned scores.

---

## Data Cleaning and Preparation

### Key Steps:
- **Dropped Columns with High Missing Values**: Columns with more than 3000 missing values were removed.
- **Removed Irrelevant Columns**: Columns like `City`, `Country`, and `What matters most to you in choosing a course` were dropped.
- **Handled "Select" Levels**: Columns like `Lead Profile` and `How did you hear about X Education` had a significant number of "Select" values, which were dropped.
- **Dropped Single-Dominant Columns**: Columns like `Do Not Call`, `Magazine`, `Newspaper Article`, etc., were removed as they had almost all values as "No".

---

## Model Building

### Logistic Regression Model
- The target variable is `Converted`, which indicates whether a lead was converted (1) or not (0).
- The model will predict the probability of conversion, which will be used to assign a lead score between 0 and 100.

### Key Features:
- `TotalVisits`: Number of visits to the website.
- `Total Time Spent on Website`: Total time spent on the website.
- `Page Views Per Visit`: Average number of page views per visit.
- `Lead Source`: Source of the lead (e.g., Google, Direct Traffic).
- `Specialization`: Area of interest of the lead.
- `What is your current occupation`: Current occupation of the lead.

---

## Model Evaluation

The model will be evaluated using the following metrics:
- **Accuracy**: Percentage of correctly classified leads.
- **Precision**: Proportion of predicted conversions that are actual conversions.
- **Recall**: Proportion of actual conversions that are correctly predicted.
- **ROC-AUC**: Area under the ROC curve, which measures the model's ability to distinguish between classes.

The goal is to achieve a high precision and recall, ensuring that the model identifies the most promising leads without missing too many potential conversions.

---

## Making Predictions

Once the model is trained and evaluated, it will be used to assign lead scores to each lead in the test set. Leads with higher scores will be prioritized by the sales team for follow-up, aiming to achieve the target conversion rate of **80%**.

---

## Repository Structure

- **Summary PDF**: Brief summary of the process, analysis and results.
- **Subjective QnA**: This file contains answers to the subjective questions.
- **Lead_Scoring_Case_Study.ipynb**: Jupyter notebook containing the code for data cleaning, model building, and evaluation.
- **Presentation**: A PowerPoint Presentation, highlighting our analysis and trends we uncovered.
- **README.md**: This file, providing an overview of the case study.

---
