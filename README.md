<div align="center">

# 🎯 Expectation Decider

### Probability Analysis of Student Exam Performance

*Practical 1 · Mathematics · Probability & Distributions with Python*

![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerics-013243?logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C)

</div>

---

## 📖 About the Project

**Expectation Decider** applies core probability theory to a real-world style dataset of **200 students**. Using Python, it answers a simple but powerful question:

> *"Given a student's study habits, attendance and past performance, how likely are they to pass the final exam?"*

The notebook walks step by step from **basic probability** to **Bayes' theorem**, with every concept backed by code and real numbers from the data.

---

## 🗂️ Repository Contents

| File | Description |
|------|-------------|
| 📓 `Pr-1_Expectation_Decider.ipynb` | Main notebook with all theory, code and results |
| 📊 `student_dataset.csv` | Dataset of 200 students (5 features) |
| 📝 `README.md` | You are here! |

---

## 📊 Dataset Overview

**200 records · 5 columns · no missing values**

| Column | Type | Description | Range / Values |
|--------|------|-------------|----------------|
| `study_hours` | float | Weekly study hours | 1.0 – 31.4 (mean ≈ 14.2) |
| `attendance` | int | Class attendance (%) | 47 – 100 (mean ≈ 77.2) |
| `group_discussion` | category | Participates in group discussions | `Yes` (140) / `No` (60) |
| `previous_test_score` | int | Score in a previous test | 39 – 98 (mean ≈ 69.4) |
| `final_exam_pass` | category | **Target** – final exam result | `Pass` (109) / `Fail` (91) |

---

## 🔑 Key Takeaways

- ✅ More than **half** of students (54.5%) pass the final exam.
- 📚 Students who study **15+ hours/week** pass more often (**67%** vs 54.5% overall).
- 🗣️ Group-discussion participants have a **higher pass rate** (57.1% vs 48.3% for non-participants).
- 🏫 High attendance raises the estimated chance of passing to ≈ **63.6%**.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **Python** | Core language |
| **Pandas** | Data loading, filtering, crosstabs |
| **NumPy** | Numerical checks (`isclose`, `sqrt`) |
| **Matplotlib** | Visualisation of event counts |
| **math.comb** | Binomial probability calculations |

---

## 📚 Concepts Covered

`Probability` · `Sample Space` · `Empirical vs Theoretical` · `Random Variables` · `Binomial Distribution` · `Mean & Variance` · `Venn Diagrams` · `Joint / Marginal / Conditional Probability` · `Independence` · `Mutually Exclusive Events` · `Bayes' Theorem`

---

## 👨‍💻 Author

**Manav Patel**

📧 manavpatel.tech@gmail.com

🔗 [GitHub](https://github.com/techmanavp)

---
