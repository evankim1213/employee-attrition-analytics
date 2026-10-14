## Context
Employee attrition remains a significant challenge for organizations across industries. Employees leave companies for various reasons, including workload, work-life balance, career opportunities, cultural mismatch, and organizational changes. 
To better understand and manage attrition risk, this project applies machine learning techniques to:
1. Predict employee attrition
2. Identify key drivers of turnover
3. Generate actionable insights for workforce optimization and retention strategies
The ultimate goal is to help organizations make informed, data-driven decisions to improve employee retention and workforce planning.

## Project Overview
- Predict employee attrition using machine learning models
- Identify key drivers of employee attrition
- Provide actionable insights for workforce optimization strategies
### Workflow
1. Exploratory Data Analysis(EDA)
2. Feature Engineering
3. Modeling
4. Model Evaluation
5. Model Interpretation(PDP&SHAP)
6. Business Insights
7. External Validation

## Dataset
- 14,999 rows and 10 columns
- Target variable: attrition (0 = Stay, 1 = Left)
- The variables `satisfaction_level` and `last_evaluation` were excluded from modeling because they may not be consistently available in real-world HR information systems. This decision was made to improve the practicality of the model.
- The variable 'work_accident' was also excluded as exploratory analysis suggested limited predictive value and no meaningful relationship with attrition.

## Repository Structure
- `data/` - HR dataset(synthetic, provided by GAAC Capstone project)
- `notebook/` - Google Colab notebook containing full analysis
- `src/` - Modularized machine learning pipeline code
- `artifacts/` - visualizations and model outputs

## Tech Stack
- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- Seaborn
- SHAP
- Google Colab
- GitHub

## Modeling Strategy: Why Recall?
Employee attrition prediction was evaluated using a recall-focused approach.
From a business perspective, failing to identify an employee who is likely to leave (False Negative) may result in employee replacement costs, training costs, productivity loss, and business disruption.
Given these opportunity costs, recall was selected as the primary evaluation metric while comparing model performance.

## Key Results
### Employee attrition was primarily associated with work-life balance needs and career-growth dynamics rather than department-level differences.
- Work-life balance emerged as the strongest driver of employee attrition, supported by workload-related factors such as project volume, monthly working hours, and the engineered feature `workload_intensity'.
- Career growth and employee lifecycle effects were also associated with attrtion risk, with tenure-related variables consistently demonstrating predictive value across analyses.
- Employee-level factors showed stronger relationships with attrition than department-level characteristics.

## Business Impact
- Influences to increase overall performance of company P&L through labor efficiency
- Provides actionable insights for HR decision-making
- Helps reduce attrition-related costs
- Enables proactive workforce planning and guideline development

## Dataset Source:
Synthetic dataset provided by Google/Coursera GAAC
