## Executive Summary
The project developed a machine learning model to predict employee attrition and identify the primary drivers of turnover. Model interpretation, external validation, and scneario analysis indicated that employees attrition was more strongly associated with work-life balances needs and career-growth dynamics than department-level differences.

Workload-related facotrs, including project volumne, monthly working hours, and workload intensity, emerged as the strongest predictors of attrition. Tenure-related variables also demonstrated meaningful predictive value, highlighting the importance of career development across different stages of the employee lifecycle.

Scenario analysis further suggested that reducing excessive working hours and project loads could substantially lower perdicted attrition risk, with a combined workload-management strategy improving retention by an estimated 883 employees.

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
1. Exploratory Data Analysis (EDA)
2. Feature Engineering
3. Modeling
4. Model Evaluation
5. Model Interpretation (PDP & SHAP)
6. External Validation
7. Actionable Insights
8. Scenario Analysis

## Dataset
- Original dataset: 14,999 rows and 10 columns
- Final modeling dataset: 11,991 rows after duplicate removal
- Target variable: `left` (0 = Stay, 1 = Left)
- The variables `satisfaction_level` and `last_evaluation` were excluded from modeling because they may not be consistently available in real-world HR information systems. This decision was made to improve the practicality of the model.
- The variable `work_accident` was also excluded as exploratory analysis suggested limited predictive value and no meaningful relationship with attrition.

## Repository Structure
- `data/` - Synthetic HR dataset provided through the GAAC Capstone project
- `notebook/` - Google Colab notebook containing full analysis
- `src/` - Modularized machine learning pipeline code
- `artifacts/` - visualizations and model outputs

## Tech Stack
CategoryToolsData AnalysisPandas, NumPyMachine LearningScikit-learn, XGBoostVisualizationMatplotlib, Seaborn, SHAPDevelopmentPython, Google Colab, GitHub


## Modeling Strategy: Why Recall?
Employee attrition prediction was evaluated using a recall-focused approach.
From a business perspective, failing to identify an employee who is likely to leave (False Negative) may result in employee replacement costs, training costs, productivity loss, and business disruption.
Given these opportunity costs, recall was selected as the primary evaluation metric while comparing model performance.

## Key Results
#### Employee attrition was primarily associated with work-life balance needs and career-growth dynamics rather than department-level differences.
- Work-life balance emerged as the strongest driver of employee attrition, supported by workload-related factors such as project volume, monthly working hours, and the engineered feature `workload_intensity`.
- Career growth and employee lifecycle effects were also associated with attrition risk, with tenure-related variables consistently demonstrating predictive value across analyses.
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
The analysis suggests that attrition risk increases at both extremes of employee workload. Employees working more than approximately 220 monthly hours, particularly those assigned six or more projects, represented a high-risk attrition segment. Employees working fewer than approximately 150 hours per month also exhibited elevated attrition risk. However, the underlying causes cannot be determined from the available data and may reflect factors such as disengagement, reduced utilization, or organizational workforce decisions.
These findings indicate that workload management should focus on maintaining employees within a sustainable workload range rather than simply reducing workload. Organizations may benefit from workload balancing, project assignment, capacity planning, and proactive manager check-ins for both over-utilized and under-utilized employees.
### Career Development Across Employee Tenure
Attrition risk appeared to vary across different stages of employee tenure, suggesting that career-growth needs evolve throughout the employee lifecycle.
Organizations may improve retention through tenure-specific initiatives such as structured onboarding for early-tenure employees, career-path planning for mid-tenure employees, and internal mobility, leadership development, or role expansion opportunities for longer-tenure employees.
Together, these findings suggest that targeted retention strategies may be more effective than one-size-fits-all retention programs.

## Scenario Analysis
To evaluate the potential impact of targeted retention initiatives, three workload-management scenarios were simulated by modifying identified high-risk conditions and re-scoring employees using the trained Random Forest model.
### Scenario A: Project Load Optimization
This scenario evaluates the potential retention impact of reducing excessive project loads among employees assigned six or more projects.
- 6 projects → 5 projects
- 7 projects → 5 projects
### Scenario B: Working Hours Optimization
This scenario evaluates the potential retention impact of reducing excessive working hours among employees working more than 220 hours per month.
- 220+ monthly hours → 200 monthly hours
### Scenario C: Combined Workload Strategy
This scenario evaluates the potential retention impact of reducing excessive project loads and working hours among high-risk workload segments.
- 6 projects → 5 projects
- 7 projects → 5 projects
- 220+ monthly hours → 200 monthly hours
### Results
| Scenario   | Expected Attrition Cases | Expected Attrition Rate | Estimated Employees Retained |
| ---------- | ------------------------: | -----------------------: | ---------------------------: |
| Baseline   |                  1,993.58 |                   16.63% |                            - |
| Scenario A |                  1,871.09 |                   15.60% |                          122 |
| Scenario B |                  1,248.52 |                   10.41% |                          745 |
| Scenario C |                  1,111.02 |                    9.27% |                          883 |
<img width="790" height="490" alt="image" src="https://github.com/user-attachments/assets/cde25428-6a2c-450d-9cb5-ad948b5ad6a7" />

### Key Takeaways
- Reducing excessive project loads alone resulted in an estimated retention improvement of 122 employees.
- Optimizing excessive working hours produced a substantially larger impact, with an estimated retention improvement of 745 employees.
- Combining both strategies yielded the strongest result, reducing the expected attrition rate from 16.63% to 9.27% while improving retention by approximately 883 employees.
- The overall results suggest that excessive working hours may represent the most actionable workload-related attrition driver identified by the model, while project load optimization provides additional benefit.

## References
### Dataset Source
- Google Advanced Data Analytics (GAAC), Coursera
### External Validation Sources
- McKinsey & Company (2023). The Future of Career Development: A Leader's Guide.
- Bai et al. (2023). Career Plateau, Burnout, Work Engagement, and Turnover Intention.
- Polat et al. (2025). Hierarchical Career Plateau and Turnover Intention.
