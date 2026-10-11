<div align="center">

# 📊 Derivable Judgement
### A Statistical Decision-Making Model

*Using inferential statistics to find out which factors really affect disease occurrence*

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-Statistics-8CAAE6?logo=scipy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Level](https://img.shields.io/badge/Type-Theory%20%2B%20Practical-success)
![Data](https://img.shields.io/badge/Dataset-Synthetic%20(200%20records)-blue)

</div>

---

## 📌 Table of Contents
1. [Project Overview](#-project-overview)
2. [Objectives](#-objectives)
3. [Dataset](#-dataset)
4. [Project Structure](#-project-structure)
5. [Methodology](#-methodology)
6. [Results at a Glance](#-results-at-a-glance)
7. [Key Findings](#-key-findings)
8. [Theory Document](#-theory-document)
9. [Author](#-author)

---

## 🎯 Project Overview

You are a **data analyst at a public health research organization**. Given a dataset of health records (age group, lifestyle habits such as smoking and exercise, and diagnosed diseases such as diabetes and hypertension), the goal is to **derive judgements** about the factors that significantly affect disease occurrence.

Instead of guessing from raw numbers, every claim in this project is backed by a **formal statistical test** with a clear hypothesis, test statistic, critical value, p-value and an Accept / Reject decision.

## 🧭 Objectives

- Apply **inferential statistics** to evaluate multiple hypotheses on a real-looking dataset
- Estimate population values with **confidence intervals**
- Use the **z-test, t-test, chi-square test and ANOVA** in the right situations
- Measure relationships with **covariance and correlation**
- Clearly **state and interpret** the result of every test (Accept / Reject H₀)

## 🗂️ Dataset

`Health_data.csv`: **200 unique, synthetic (AI-generated) health records**, 15 columns, no missing values.

| Field | Type | Description |
|---|---|---|
| `record_id` | UUID/String | Unique identifier for each record |
| `age_group` | String | 18-25, 26-35, 36-45, 46-60, 60+ |
| `age` | Int | Age of the individual |
| `weight` | Int | Weight (kg) |
| `gender` | String | Male / Female / Other |
| `region` | String | North / South / East / West |
| `smoking_status` | String | Smoker / Non-Smoker / Former Smoker |
| `exercise_frequency` | String | Daily / Weekly / Rarely / Never |
| `bmi` | Float | Body Mass Index |
| `blood_pressure` | Float | Systolic blood pressure (mmHg) |
| `diabetes` | Boolean | Has diabetes (True/False) |
| `hypertension` | Boolean | Has hypertension (True/False) |
| `cholesterol_level` | Float | Total cholesterol (mg/dL) |
| `glucose_level` | Float | Fasting glucose (mg/dL) |
| `visit_date` | Date | Date of check-up |


## 📁 Project Structure

```
📦 derivable-judgement
 ┣ 📓 Part-B-_Data_Analysis___Testing_Tasks.ipynb   ← all code, charts and interpretations
 ┣ 📄 Part-A_-_Theoretical_Foundation.pdf           ← theory concepts with definitions
 ┣ 📊 Health_data.csv                                ← dataset (200 records)
 ┣ 📊 results_summary.csv                            ← final table of all 11 tests
 ┗ 📘 README.md
```


## 🔬 Methodology

| # | Task | Method used |
|---|---|---|
| 1 | Formulate hypotheses | H₀ / H₁ for Smoking vs Diabetes and Smoking vs Blood Pressure |
| 2 | Confidence intervals | 95% CI with the t-distribution for age, weight, BMI, BP, cholesterol, glucose |
| 3 | Critical value and p-value | Both decision methods compared for every test |
| 4 | Mean comparison | z-test and t-test (chosen by sample size and knowledge of σ) |
| 5 | Categorical data | Chi-square test of independence (manual and automatic) |
| 6 | Disease rate by age group | One-way ANOVA (manual SSB / SSW and `f_oneway`) |
| 7 | Continuous variables | Covariance, Pearson correlation and its significance test |
| 8 | Final decisions | Summary table with Accept / Reject H₀ for each test |

All tests use a significance level of **α = 0.05**.

## 🏆 Results at a Glance

| # | Test | Statistic | Critical value | p-value | Decision |
|---|---|---|---|---|---|
| 1 | Chi-square: Smoking vs Diabetes | 8.424 | 5.991 | 0.0148 | ❌ Reject H₀ |
| 2 | Chi-square: Smoking vs Hypertension | 0.274 | 5.991 | 0.8722 | ✅ Accept H₀ |
| 3 | z-test: Mean BMI (μ = 24) | 2.609 | ±1.960 | 0.0091 | ❌ Reject H₀ |
| 4 | z-test: Mean BP (μ = 120) | 4.385 | ±1.960 | 0.00001 | ❌ Reject H₀ |
| 5 | t-test: BP, Smoker vs Non-Smoker | 0.451 | ±1.975 | 0.6527 | ✅ Accept H₀ |
| 6 | t-test: BMI, Daily vs Never exercise | −6.124 | ±2.000 | 0.00000007 | ❌ Reject H₀ |
| 7 | t-test: BMI, small sample (n = 15) | 1.831 | ±2.145 | 0.0884 | ✅ Accept H₀ |
| 8 | ANOVA: Hypertension rate by age group | 6.064 | 2.418 | 0.00013 | ❌ Reject H₀ |
| 9 | ANOVA: Diabetes rate by age group | 2.322 | 2.418 | 0.0581 | ✅ Accept H₀ |
| 10 | ANOVA: BMI by age group | 8.617 | 2.418 | 0.000002 | ❌ Reject H₀ |
| 11 | Pearson correlation: Age vs BMI | 5.961 | ±1.972 | 0.00000001 | ❌ Reject H₀ |

**7 tests reject H₀ and 4 do not.** The full table is in [`results_summary.csv`](results_summary.csv).

## 💡 Key Findings

- 🚬 **Smoking and diabetes are linked.** Diabetes prevalence is **6.8%** in non-smokers but **19.0%** in smokers and **22.0%** in former smokers (χ² = 8.42, p = 0.0148).
- 🏃 **Exercise matters.** People who exercise daily have a mean BMI of **22.4**, compared with **27.2** for those who never exercise (p < 0.001).
- 📈 **Age drives health risk.** Hypertension rises from **0%** (18-25) to **44.1%** (60+), and BMI shows a moderate positive correlation with age (r = 0.39).
- 🩺 **No evidence that smoking changes blood pressure or hypertension** in this dataset (p = 0.65 and p = 0.87).
- 🔎 **Sample size matters.** The same claim (mean BMI = 24) is rejected with n = 200 but not with n = 15, because larger samples have more statistical power.


## 📚 Theory Document

[Part-A - Theoretical Foundation](Part-A%20-%20Theoretical%20Foundation.pdf) explains the core concepts with definitions:

| Concept | One-line summary |
|---|---|
| Inferential statistics | Drawing conclusions about a population from a sample |
| Hypothesis testing | Checking a claim with H₀, H₁, α, test statistic and a decision |
| Confidence interval | A range likely to contain the true population value |
| Critical value | The cut-off beyond which H₀ is rejected |
| p-value | Probability of a result at least this extreme if H₀ is true |
| Type I / Type II error | Rejecting a true H₀ / failing to reject a false H₀ |
| z, t, chi-square, ANOVA | Tests for means (known σ), means (unknown σ), categories, and 3+ groups |
| Covariance / Correlation | Direction of co-movement / direction and strength (−1 to +1) |


## 👨‍💻 Author

**Manav Patel**
📧 manavpatel.tech@gmail.com
🔗 [GitHub](https://github.com/techmanavp) 

---

