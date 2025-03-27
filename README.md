# HR Analytics: Predicting Employee Turnover

## Project Overview
For my capstone project at the Google Advanced Data Analytics Certificate, I developed a machine learning solution for Salifort Motors to predict and reduce employee turnover. Using HR analytics, I identified key factors contributing to employee departures and created a predictive model with personalized retention strategies.

## Business Problem
Salifort Motors was experiencing significant employee turnover issues. Employee turnover is costly in terms of:
- Recruitment and training expenses (50-200% of annual salary)
- Lost productivity
- Institutional knowledge loss
- Team morale impact

By predicting which employees are likely to leave and why, HR departments can implement targeted retention strategies and improve overall workforce stability.

## Data
I analyzed a comprehensive HR dataset with 14,999 employee records containing various features:
- Satisfaction levels (0-1 scale)
- Performance evaluation scores (0-1 scale)
- Number of projects assigned
- Average monthly working hours
- Tenure at the company
- Work accident history
- Promotions in last 5 years
- Department
- Salary level (low, medium, high)

The dataset was clean with no missing values but required feature engineering to capture complex relationships between variables.

## Technical Approach

### Data Exploration & Feature Engineering
Created 10 engineered features to better capture employee behavior patterns:
- `work_intensity`: Monthly hours divided by number of projects
- `relative_hours`: Monthly hours relative to company average
- `overworked`: Binary indicator for employees with above-average hours and high project count
- `poor_work_life_balance`: Binary indicator for employees working excessive hours (>200/month)
- `productivity`: Evaluation score per project
- `satisfaction_per_hour`: Satisfaction level normalized by working hours
- `underutilized`: High performers with few projects
- `burnout_risk`: Combination of high hours, many projects, and low satisfaction
- `flight_risk`: Low satisfaction despite high performance and tenure
- `high_performer_risk`: High performers without recent promotion

### Model Development
- Built and compared multiple models (Logistic Regression, Random Forest, XGBoost)
- Employed SMOTE to address class imbalance
- Used feature selection to identify most predictive variables
- Optimized hyperparameters through grid search and cross-validation
- Analyzed learning curves to diagnose bias/variance trade-offs
- Optimized classification threshold based on business requirements
- Assessed model calibration to ensure reliable probability estimates

## Key Findings

### Turnover Patterns
- Approximately 16.6% of employees left the company
- Three distinct groups of employees at high risk:
  1. Overworked high performers (many projects, long hours)
  2. Undervalued experienced employees (good evaluation, no promotion)
  3. Dissatisfied employees with poor work-life balance

### Primary Turnover Drivers
- **Satisfaction level**: By far the strongest predictor (23.6% importance)
- **Work overload**: Employees with 7+ projects had nearly 100% turnover
- **Work underload**: Employees with only 2 projects showed 55% turnover
- **Hour extremes**: Both overworked (250+ hours) and underworked (130-150 hours) employees were at high risk
- **Tenure impact**: Employees at 5-year tenure had highest turnover (45%), suggesting a critical career milestone
- **Unrecognized talent**: High performers without promotion showed 58% higher turnover risk

### Model Performance
The Random Forest model achieved exceptional results:
- 98.4% accuracy
- 97% F1 score on test data
- Outstanding ROC-AUC of 0.98

## Turnover Risk Prediction System
I developed a complete end-to-end prediction system that:
1. Takes an employee's data as input
2. Performs feature engineering and preprocessing
3. Generates a turnover risk probability and classification (Low/Medium/High)
4. Identifies specific risk factors for that employee
5. Recommends personalized retention actions based on identified risk factors

## Strategic Recommendations

### Workload Management
- Implement project caps to limit concurrent projects to a maximum of 5 per employee
- Set up alerts for employees consistently working over 200 hours monthly
- Ensure project distribution avoids both overwork and underutilization

### Career Development
- Create clear advancement pathways, especially for employees approaching the 3-5 year tenure mark
- Establish regular promotion reviews to ensure high performers aren't overlooked
- Develop lateral move opportunities when vertical promotion isn't available

### Compensation Reviews
- Conduct targeted salary audits focusing on high performers in low salary classifications
- Develop clear compensation growth plans tied to performance metrics
- Ensure compensation is competitive, particularly in high-risk departments

### Department-Specific Strategies
- Create customized retention plans for departments with the highest turnover rates
- Address department-specific issues through targeted interventions and management training

### Prediction System Integration
- Implement the turnover prediction model as a proactive management tool
- Establish intervention protocols for employees flagged as high-risk
- Conduct quarterly risk assessments

## Expected Business Impact
Based on model projections and similar HR interventions, implementing these recommendations would likely result in:
- 20-30% reduction in turnover within 12 months
- Potential 15-20% reduction in annual recruitment and training costs
- 15% increase in employee satisfaction scores across high-risk departments
- 8% productivity improvement from better workload management
- Enhanced knowledge retention from keeping experienced employees

## Technical Skills Demonstrated
This project showcased my abilities in:
- Advanced feature engineering
- Machine learning pipeline development
- Classification modeling
- Hyperparameter tuning
- Class imbalance handling
- Data visualization
- Business analysis and recommendation development

## Conclusion
This project demonstrates how advanced analytics can transform HR from reactive to proactive talent management. By identifying at-risk employees early and recommending targeted interventions, organizations can significantly improve retention, reduce costs, and maintain institutional knowledge.
