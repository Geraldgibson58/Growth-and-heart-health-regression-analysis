# Growth and Cardiovascular Health: Statistical Analysis and Regression Modeling

## Project Overview

This project applies statistical analysis, hypothesis testing, and regression modeling to investigate childhood growth patterns and cardiovascular health indicators.

Using Python, the analysis examines how childhood physical measurements relate to body weight at age 18 and evaluates relationships involving cholesterol, blood pressure, and demographic characteristics.

The project demonstrates how exploratory data analysis, independent-sample t-tests, and multiple linear regression can be applied to health-related datasets to identify statistical relationships and compare model performance.

## Research Objectives

- Examine correlations among childhood height, weight, and physical growth measurements.
- Develop separate regression models predicting weight at age 18 for males and females.
- Identify statistically significant predictors of adolescent body weight.
- Test differences in cholesterol and diastolic blood pressure between males and females.
- Develop simple and multiple regression models to explain cholesterol levels.
- Evaluate model performance using R², adjusted R², F-statistics, t-statistics, and root mean squared error (RMSE).

## Datasets

Two datasets were used in this project.

### 1. Berkeley Guidance Dataset

**File:** `HW2_BGALL.csv`

Contains 136 observations with childhood and adolescent physical growth measurements.

Key variables include:

- Sex
- Weight at age 2 (WT2)
- Height at age 2 (HT2)
- Weight at age 9 (WT9)
- Height at age 9 (HT9)
- Strength measurement at age 9 (ST9)
- Weight at age 18 (WT18)
- Height at age 18 (HT18)

### 2. Heart Health Dataset

**File:** `HW2_HW3_HEART.csv`

Contains 5,209 observations with demographic and cardiovascular measurements.

Key variables include:

- Sex
- Age at study enrollment
- Cholesterol
- Systolic blood pressure
- Diastolic blood pressure
- Height and weight
- Smoking
- Relative weight measurements
- Age at coronary heart disease diagnosis

## Methodology

### 1. Exploratory Data Analysis

Generated scatterplot matrices and correlation tables to evaluate relationships among childhood and adolescent growth measurements.

Observations were grouped by gender to examine differences in growth patterns.

**Key correlations:**

| Variables | Correlation |
|---|---:|
| Weight at age 9 and leg measurement at age 9 | 0.920 |
| Weight at age 18 and leg measurement at age 18 | 0.793 |
| Weight at age 18 and height at age 18 | 0.624 |
| Weight at age 18 and weight at age 9 | 0.581 |

The results demonstrated positive relationships among several physical growth measurements.

### 2. Gender-Specific Weight Regression

Developed separate multiple linear regression models to predict weight at age 18 using childhood measurements.

**Model:**

WT18 = f(HT2, WT2, HT9, WT9, ST9)

**Regression Results:**

| Metric | Male Model | Female Model |
|---|---:|---:|
| Observations | 66 | 70 |
| R² | 0.444 | 0.577 |
| Adjusted R² | 0.398 | 0.544 |
| F-statistic | 9.596 | 17.46 |
| Model p-value | < 0.001 | < 0.001 |

**Key Findings:**

- The male regression model explained approximately 44.4% of variation in weight at age 18.
- The female regression model explained approximately 57.7% of variation.
- Weight at age 9 was a statistically significant predictor in both models.
- Height at age 9 and strength at age 9 were additional statistically significant predictors in the female model.

These results suggest that childhood measurements provide useful statistical information about adolescent weight, although the relationships differ between the two groups.

### 3. Hypothesis Testing: Cardiovascular Measurements

Performed independent-sample Welch's t-tests to evaluate differences in cholesterol and diastolic blood pressure between males and females.

**Significance level:** α = 0.05

| Variable | Male Mean | Female Mean | p-value |
|---|---:|---:|---:|
| Cholesterol | 226.05 | 228.54 | 0.0476 |
| Diastolic Blood Pressure | 86.23 | 84.65 | < 0.001 |

**Statistical Conclusions:**

- Cholesterol levels demonstrated a statistically significant difference between males and females.
- Diastolic blood pressure also demonstrated a statistically significant difference.
- Both null hypotheses of equal group means were rejected at the 0.05 significance level.

Statistical significance does not necessarily indicate a clinically meaningful difference.

### 4. Simple Linear Regression: Cholesterol

Developed two simple linear regression models to evaluate relationships between cholesterol and continuous predictor variables.

The variables with the strongest absolute correlations with cholesterol were:

- Age at study enrollment: r = 0.273
- Systolic blood pressure: r = 0.199

**Model Comparison:**

| Metric | Age Model | Systolic Model |
|---|---:|---:|
| R² | 0.0748 | 0.0397 |
| Adjusted R² | 0.0746 | 0.0396 |
| F-statistic | 408.42 | 209.20 |
| RMSE | 43.219 | 44.029 |

Both models were statistically significant.

The age-based model demonstrated stronger explanatory performance, although neither model explained a large proportion of cholesterol variation.

### 5. Multiple Linear Regression: Cholesterol

Developed a multiple linear regression model incorporating all available numerical predictors, including age, height, weight, blood pressure, smoking, and other cardiovascular variables.

**Model Results:**

- Observations: 864
- R²: 0.0367
- Adjusted R²: 0.0265
- F-statistic: 3.612
- Model p-value: 0.000197
- RMSE: 47.602

The model was statistically significant overall, but demonstrated limited explanatory power.

Among the individual coefficients, age at coronary heart disease diagnosis was statistically significant at the 0.05 level.

The full model used fewer observations because rows with missing predictor values were excluded.

### 6. Model Comparison

A separate two-predictor model was constructed using age at study enrollment and systolic blood pressure.

The notebook's written interpretation reported an R² of approximately 0.0854 for this model.

However, the two-predictor model used substantially more observations than the full multiple regression model.

This difference in sample sizes limits direct comparison of model performance. A stronger evaluation would fit competing models to the same observations and assess their performance on held-out data.

## Technologies Used

- **Python:** Statistical analysis and data processing
- **Jupyter Notebook:** Interactive analysis and documentation
- **pandas:** Data cleaning and manipulation
- **NumPy:** Numerical computations
- **Matplotlib:** Data visualization
- **seaborn:** Scatterplot matrices and statistical graphics
- **SciPy:** Independent-sample t-tests
- **statsmodels:** Linear regression and statistical inference

## Key Findings

1. Childhood body measurements demonstrated meaningful statistical associations with weight at age 18.
2. The female weight regression model achieved a higher R² than the male model.
3. Weight at age 9 was a statistically significant predictor of weight at age 18 in both gender-specific models.
4. Cholesterol and diastolic blood pressure differed significantly between males and females in the Heart dataset.
5. Age at study enrollment demonstrated a stronger simple linear relationship with cholesterol than systolic blood pressure.
6. The cholesterol regression models explained relatively little variation, indicating that additional factors may be necessary for stronger predictive performance.
7. Missing data substantially reduced the sample available for the full cholesterol regression model.

## Conclusion

This project demonstrates the application of statistical inference and regression modeling to health-related data.

The Berkeley Guidance analysis illustrates how childhood physical measurements can be used to investigate variation in adolescent body weight. The Heart dataset analysis demonstrates how hypothesis testing and regression techniques can identify statistical differences and relationships involving cardiovascular measurements.

The project also highlights the importance of evaluating statistical significance, explanatory power, missing data, and model complexity when interpreting regression results.

## Limitations and Future Improvements

- The Berkeley Guidance dataset contains a relatively small sample.
- Regression models were evaluated primarily using in-sample statistics.
- Missing values substantially reduced the number of observations available for the full cholesterol model.
- Different sample sizes limit direct comparisons between regression models.
- Additional predictors and nonlinear modeling methods could be investigated.
- Future analysis could implement cross-validation, diagnostic testing, and improved missing-data strategies.
- The observed relationships are statistical associations and should not be interpreted as causal effects.
- Variables such as age at death or age at coronary heart disease diagnosis would require special care in any prospective prediction study.

## Repository Contents

- `growth_heart_health_regression.ipynb` — Statistical analysis and regression models
- `HW2_BGALL.csv` — Berkeley Guidance growth dataset
- `HW2_HW3_HEART.csv` — Cardiovascular health dataset
- `README.md` — Project documentation

## How to Run

1. Clone or download the repository.
2. Install Python and Jupyter Notebook or JupyterLab.
3. Install the required libraries: pandas, NumPy, Matplotlib, seaborn, SciPy, and statsmodels.
4. Place both CSV datasets in the same directory as the Jupyter notebook.
5. Open `growth_heart_health_regression.ipynb`.
6. Execute the analysis cells sequentially.

**Note:** The original notebook requires some text-only cells to be converted from Python code cells to Markdown. The model-comparison display statements should also be moved into executable code cells, and the final written model comparison should be checked against the regression outputs.

## Academic Context

Developed as part of ANA620 graduate-level Data Science coursework, emphasizing statistical inference, hypothesis testing, regression modeling, and analysis of health-related datasets.
