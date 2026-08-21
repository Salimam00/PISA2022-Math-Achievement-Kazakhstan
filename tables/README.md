
# Manuscript Tables

This directory contains all tabular data used in the research manuscript, saved in clean, version-controlled CSV format. Each table can be imported directly into Python/R or compiled into LaTeX using pandas (`df.to_latex()`).

| File Name | Description / Title in Paper | Key Content / Notes |
| :--- | :--- | :--- |
| `data.csv` | Sample Characteristics and Survey Parameters | Students ($N=19,769$), schools, weights, gender split |
| `constructs.csv` | Overview of Constructs, Variables, and Analytical Roles | Cognitive test, scales, predictors, controls |
| `missing_data.csv` | Missing Data Analysis and Treatment Strategy | Percentage of missing values and exclusion/retained status |
| `performance_by_gender.csv` | Mathematical Literacy Performance and Subscales by Gender | Means, standard errors, and 95% CIs (Total, Female, Male) |
| `regression_results.csv` | Multiple Regression Results for ICT Predictors | $b$ coefficients, SE, 95% CI, $\beta$, and $p$-values |
| `regression_extended_model.csv` | Extended Regression Model Including School-Level Factors | Full model with school climate, resources, and policy variables |

## Usage Example (Python)

To load any table and automatically convert it to a LaTeX code snippet for your paper:

```python
import pandas as pd

# Load the extended regression model
df = pd.read_csv("tables/regression_extended_model.csv")

# Generate LaTeX table string
latex_output = df.to_latex(
    index=False,
    escape=False,
    column_format="p{4.5cm}p{2.5cm}p{2.5cm}p{1.2cm}p{1.2cm}",
    caption="Extended Regression Model Including School-Level Factors",
    label="tab:regression_extended"
)

print(latex_output)
