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
#### Employee attrition was primarily associated with work-life balance needs and career-growth dynamics rather than department-level differences.
- Work-life balance emerged as the strongest driver of employee attrition, supported by workload-related factors such as project volume, monthly working hours, and the engineered feature `workload_intensity'.
- Career growth and employee lifecycle effects were also associated with attrtion risk, with tenure-related variables consistently demonstrating predictive value across analyses.
- Employee-level factors showed stronger relationships with attrition than department-level characteristics.

## External Validation
### Workload and Employee Attrition
Workload-related variables (`workload_intensity`, `number_project`, and `average_monthly_hours`) emerged as the strongest predictors of employee attrition in this project.
External studies similarly found that excessive workload and work stress increase employee turnover intention through elevated burnout levels. Employees experiencing higher workload and burnout were consistently more likely to consider leaving their organizations. 【1-35793b】【2-0e3096】
### Career Growth and Employee Attrition
Tenure-related variables also demonstrated meaningful predictive value throughout the analysis, suggesting that attrition risk may vary across different stages of an employee's career lifecycle.
Research on career plateau suggests that employees who perceive limited growth or advancement opportunities are more likely to experience lower engagement, higher burnout, and stronger turnover intention. 【3-7d7d7d】【4-c91f3e】【5-53a32d】
This interpretation is also supported by McKinsey research, which found that 41% of employees cited a lack of career development and advancement as a reason for leaving a previous employer. 【6-12b915】【6-f119ab】
### Validation Summary
Both the internal analysis and external research consistently indicate that employee attrition is closely associated with workload-related pressures and career-growth dynamics across different stages of employee tenure.

## Actionable Insights
### Workload Management
The analysis suggests that attrition risk increases at both extremes of employee workload. Employees working more than approximately 220 monthly hours, particularly thos assigned six or more projects, represented a high-risk atrition sgement. Employees working fewer than approximately 150hours per month also exhibited elevated attrition risk. However, the underlying causes cannot be determined from the available data and may relfect factors such as disengagement, reduced utilization, or organizational workforce decisions.
These findings indicate that workload mamagement should focus on manitaining employees within a sustainable workload range rather than simply reducing workload. Organizations may benefit from workload balancing, project assignment, capacity planning, and proactive manager check-ins for both over-utilized and under-utilized employees.
### Career Development Across Employee Tenure
Attrition risk appeared to vary across different stages of employee tenure, suggesting that career-growth needs to be evolved throuout the employee lifecydle.
Organizations may improve retention through tenure-specific initiatives such as structured onboarding for early-tenure employee, career-path planning for mid-tenure employees, and internabl mobility, leadership development, or role expansion opportunities for longer-tenure employees.
Together, these findings suggest that targeted retention strategies may be more effective than one-size-fits-all retention programs.

## Dataset Source:
Synthetic dataset provided by Google/Coursera GAAC
