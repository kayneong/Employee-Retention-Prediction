# Saliford Motors Employee Retention-project
## Project title
Logistic Regression and Tree-based modeling of employees' retention data

## Project Overview
The goal of this project is to conduct EDA on the employee dataset provided by the HR department and construct binary classification models (Logistic regression, decision trees, Random Forests and XGBoost) that can classify whether an employee would leave or stay in the fictional company, Saliford Motors. 
The final random forest model had an accuracy of 96%, f1-score of 92% and ROC-AUC of 0.942 allowing identification of important features that contribute to employee retention. Based on the model, the employee's last evaluation score, number of projects they worked on, tenure period
and whether they were overworked were most influential in determining whether they would stay or leave the company. 

## Business Understanding
It is expensive and time-consuming to find, interview and train new employees. Hence, it is important to understand the factors that lead to employees leaving the company and provide data-driven suggestions to increase employee retention for the benefit of Saliford Motors. 

## Data Understanding 
The employees dataset provided by the HR department came from [Kaggle HR Job Prediction](https://www.kaggle.com/datasets/mfaisalqureshi/hr-analytics-and-job-prediction?select=HR_comma_sep.csv). The dataset contained data of 14999 employees displayed as rows with 9 features and 1 outcome variable as columns. 
The features included information on the average number of hours worked per month,  number of years spent in the company, salary, last evaluation score, number of projects contributed and whether the employee was promoted in the last 5 years. 3008 rows were duplicates in the dataset and dropped.
The remaining 11991 unique employees consist of ~83% who are still with the company and ~17% who have left. Categorical columns like salary and department were ordinal encoded and converted to dummy variables respectively for the regression model. Due to data leakage concerns, 
the satisfaction feature was dropped in the second round of training and evaluation of the models. Meanwhile, average_monthly_hours was extracted to create a new feature, overworked that roughly captures whether an employee was overworked or not. 

## Modeling and Evaluation
A random forest model comprising 300 trees was used as the champion model to predict whether an employee would stay or leave the company. Additionally, it identified the important features that were most predictive of an employee's retention status. The plot below shows that 
last evaluation score, number of projects contributed, tenure and whether the employee was overworked were the top features in determining whether an employee would leave. The champion model had an accuracy of 96%, f1-score of 92% and ROC-AUC of 0.942 when evaluated against the test set. 
      
  ![image](https://github.com/kayneong/TikTok-videos-claims-project/assets/150570357/0abc1946-de70-47ce-88a5-ddb5bf45110f)


## Conclusion
The champion random forest model was subsequently trained with the entire dataset (training, validation and test sets together) to prepare for future possible deployment. The EDA conducted, models and feature importances affirmed that employees were indeed overworked. 
Recommendations such as capping the number of projects employees can work on, addressing work culture, workload and time off expectations were suggested to stakeholders to improve employee retention rates. 
