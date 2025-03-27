# HR Analytics: Predicting Employee Turnover

## Project Overview
This project analyzes HR data to build a predictive model for employee turnover, helping identify which employees are at risk of leaving and understanding key factors contributing to turnover. The solution includes a complete end-to-end pipeline for making predictions on individual employees and recommending targeted interventions.

## Business Problem
Employee turnover is costly for organizations in terms of:
- Recruitment and training expenses
- Lost productivity
- Institutional knowledge loss
- Team morale impact

By predicting which employees are likely to leave and why, HR departments can implement targeted retention strategies and improve overall workforce stability.

## Data
The dataset contains information about:
- Satisfaction levels
- Performance evaluation scores
- Number of projects assigned
- Average monthly working hours
- Tenure at the company
- Work accidents
- Promotions in the last 5 years
- Department and salary information

## Approach

### 1. Data Exploration and Preparation
- Conducted comprehensive data quality assessments
- Visualized relationships between key variables and turnover
- Prepared data for modeling with proper preprocessing pipelines

### 2. Feature Engineering
Created advanced engineered features to better capture employee experience:
- `work_intensity`: Measures time-intensity per project
- `relative_hours`: Normalizes hours worked against company average
- `poor_work_life_balance`: Identifies excessive working hours
- `productivity`: Measures performance efficiency per project
- `satisfaction_per_hour`: Evaluates satisfaction relative to workload
- `burnout_risk`: Identifies employees showing burnout signals
- `flight_risk`: Spots talented employees who may be disengaged
- `high_performer_risk`: Finds top performers who haven't been promoted

### 3. Model Development
- Built and compared multiple models (Logistic Regression, Random Forest, XGBoost)
- Employed SMOTE to address class imbalance
- Used feature selection to identify most predictive variables
- Optimized hyperparameters through grid search and cross-validation

### 4. Model Evaluation
- Analyzed learning curves to diagnose bias/variance trade-offs
- Optimized classification threshold based on business requirements
- Assessed model calibration to ensure reliable probability estimates
- Evaluated feature importance through permutation methods

### 5. Deployment Solution
- Created an end-to-end pipeline combining preprocessing and prediction
- Developed functions for individual employee risk assessment
- Built recommendation engine to suggest specific interventions based on risk factors

## Key Findings

### Turnover Patterns
- Approximately 16.6% of employees left the company
- Three distinct groups of employees at high risk:
  1. Overworked high performers (many projects, long hours)
  2. Undervalued experienced employees (good evaluation, no promotion)
  3. Dissatisfied employees with poor work-life balance

### Most Important Factors
1. Number of projects (excessive workload)
2. Monthly hours (overwork)
3. Tenure at company (particularly years 3-4)
4. Evaluation scores (high performers without recognition)
5. Satisfaction per hour (diminishing satisfaction with overwork)

### Department and Salary Insights
- Higher turnover rates in technical departments
- Employees with low salaries but high performance metrics show increased risk
- Work intensity varies significantly across departments

## Recommendations

### Workload Management
- Limit projects to maximum of 5 per employee
- Review workload for employees exceeding 200 hours/month
- Implement workload distribution analysis across teams

### Career Development
- Create promotion pathways for high performers
- Implement regular career development check-ins at 3-4 year tenure mark
- Review compensation alignment with performance metrics

### Work-Life Balance
- Develop programs to encourage proper work hours
- Implement time tracking to identify consistently overworked employees
- Create recognition systems beyond promotion and salary

### Management Training
- Train managers to identify burnout warning signs
- Develop standardized check-in procedures for at-risk employees
- Establish clear expectations for project scoping and time allocation

## Technical Implementation

### Technologies Used
- Python (Pandas, NumPy, Scikit-learn)
- Machine Learning (XGBoost, Random Forest)
- Data Visualization (Matplotlib, Seaborn)
- Model Deployment (Joblib, Pipeline)

### Model Performance
The final model achieves:
- 92% accuracy
- 90% precision
- 91% recall
- 0.94 ROC-AUC score

### Risk Assessment System
The implemented solution can:
1. Process new employee data through feature engineering
2. Predict turnover probability
3. Identify specific risk factors
4. Recommend targeted interventions
5. Integrate into existing HR systems

## Future Work
- Incorporate time-series analysis for temporal patterns
- Develop interactive dashboard for HR departments
- Implement A/B testing framework for intervention effectiveness
- Integrate additional data sources (performance reviews, survey feedback)

## Conclusion
This project demonstrates how advanced analytics can transform HR from reactive to proactive talent management. By identifying at-risk employees early and recommending targeted interventions, organizations can significantly improve retention, reduce costs, and maintain institutional knowledge.
