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

## Repository Structure
- `data/` - HR dataset(synthetic, provided by GAAC Capstone project)
- `notebook/` - Google Colab notebook containing full analysis
- `src/` - Modularized machine learning pipeline code
- `artifacts/` - visualizations and model outputs

Tech Stack
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

## Key Results
- 
-
-
-

## Business Impact
- Influences to increase overall performance of company P&L through labor efficiency
- Provides actionable insights for HR decision-making
- Helps reduce attrition-related costs
- Enables proactive workforce planning and guideline development

## Dataset Source:
Synthetic dataset provided by Google/Coursera GAAC
