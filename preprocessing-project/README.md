# Data Preprocessing in Python

This is the first project in the course meant to practice data pre-processing skills in Python.

Click **[here](https://nbviewer.org/github/shirarua/practicum-projects/blob/main/preprocessing-project/data_preprocessing_final.ipynb)** to view the notebook using **[nbviewer](https://nbviewer.org)**.

## Project Overview
### Objective
The bank's loan division is seeking to build an internal credit scoring system that evaluates a potential customer's ability to repay a loan. Determine which factors are likely to impact a customer's chance of defaulting on a loan based on previous customer data. This report will be used to more accurately assess future customers' credit worthiness in order to reduce the overall default rate on loans.

### Data description
***credit_scoring_eng.csv***: Data on previous customers' credit worthiness and features.
- children: the number of children in the family
- days_employed: how long the customer has been working
- dob_years: the customer’s age
- education: the customer’s education level
- education_id: identifier for the customer’s education
- family_status: the customer’s marital status
- family_status_id: identifier for the customer’s marital status
- gender: the customer’s gender
- income_type: the customer’s income type
- debt: whether the customer has ever defaulted on a loan
- total_income: monthly income
- purpose: reason for taking out a loan

### Methodology

1. Cleaned data: handle various types of missing values, anomolous data, & duplicated data.
2. Categorized customers by into income brackets based on overall income distribution.
3. Categorized loan purposes by identifying common word stems, and assigning them manually to common categories.
4. Explore the default rates according to each of the features provided.

### Summary
All features appeared to have an effect on credit-worthiness and seemed to have more complex interactions with each other. Loan purpose and income level appear to have the strongest effect.

However, this dataset contained many problems and did not include data on loan size. Before building a predictive model, an attempt should be made to reconcile the issues detailed in the notebook.
