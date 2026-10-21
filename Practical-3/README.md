<h1 align="center">📊 Spread Locator</h1>
<h3 align="center">A Statistical Distribution Analysis Model</h3>

<p align="center">
  Finding out which probability distributions describe customer transactions on an e-commerce platform.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white" alt="Jupyter">
  <img src="https://img.shields.io/badge/SciPy-Statistics-8CAAE6?logo=scipy&logoColor=white" alt="SciPy">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/Status-Completed-brightgreen" alt="Status">
</p>

<p align="center">
  <a href="https://drive.google.com/file/d/15UIdIp7gF6DvbeXlHkFHSd80Cc3kEpbp/view?usp=sharing">
    <img src="assets/video_thumbnail.png" alt="Watch the project walkthrough" width="650">
  </a>
  <br>
  <b>▶ <a href="https://drive.google.com/file/d/15UIdIp7gF6DvbeXlHkFHSd80Cc3kEpbp/view?usp=sharing">Watch the 8-minute project walkthrough</a></b>
</p>

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Dataset](#-dataset)
- [Tools Used](#-tools-used)
- [Analysis and Results](#-analysis-and-results)
- [Key Insights](#-key-insights)
- [Theory Covered](#-theory-covered)
- [Author](#-author)

---

## 🎯 Overview

An e-commerce platform wants to understand how its customers shop. Management asks three questions:

1. Do transactions follow a known statistical distribution?
2. How should skewed transaction data be handled?
3. What probability insights can be drawn from it?

This project answers them by fitting and testing several distributions on **220 transactions** (January 2023), and by transforming the skewed transaction amounts so they can be modelled properly.

The project has two parts:

| Part | What it contains | File |
|---|---|---|
| **Part A: Theory** | Short notes on 11 concepts: distributions, Q-Q plot, Bernoulli, Binomial, Poisson, Log-Normal, Power Law, Box-Cox, Z-score, PDF and CDF | `Spread_Locator_Part_A_Theory.ipynb` |
| **Part B: Practical** | 8 analysis tasks in Python, with charts and an interpretation under each result | `Spread_Locator_Part_B.ipynb` |

---

## 🗂 Dataset

File: `spread_locator_dataset.xlsx` (220 rows, 7 columns, no missing values, 1 Jan to 31 Jan 2023)

| Column | Type | Description |
|---|---|---|
| `transaction_id` | String | Unique ID of each transaction |
| `customer_id` | String | Unique ID of each customer |
| `transaction_amount` | Float | Transaction amount in ₹ |
| `transaction_date` | Date | Date of the transaction |
| `transaction_count` | Int | Number of transactions by a customer in a given week |
| `region` | String | North, South, East or West |
| `transaction_status` | String | Success or Fail |

**First look at the data:** the average transaction is about ₹3,365, the largest is ₹20,463, and the skewness is about **3.76**. A few very large purchases pull the data to the right, which is why distribution choice and transformation matter here.

---

## 🛠 Tools Used

- **Python** for the whole analysis
- **NumPy and Pandas** for data handling
- **SciPy** for distribution fitting, KS test, Shapiro test and Box-Cox
- **Statsmodels** for Q-Q plots
- **Matplotlib and Seaborn** for charts
- **Jupyter Notebook** for code, charts and interpretations together


---

## 📈 Analysis and Results

### Summary of all tasks

| # | Task | Main result |
|---|---|---|
| 1 | Bernoulli and Binomial | P(Success) = **0.4455**, P(Fail) = 0.5545. Binomial fit with n = 9, p = 0.317 |
| 2 | Poisson (transactions per day) | λ = **7.1** per day, variance 5.29 |
| 3 | Log-Normal and Power Law | Log-Normal fits well (KS p = **0.90**). Power Law is rejected |
| 4 | Q-Q Plot | Original amounts are not normal. Their logarithm is approximately normal (Shapiro p = 0.106) |
| 5 | Box-Cox | λ = **-0.18**, skewness drops from 3.73 to about -0.01 |
| 6 | Z-scores and P(amount > ₹5000) | Z(5000) = 0.82. Probability: 20.5% (Normal), 13.8% (Log-Normal), **11.4% actual** |
| 7 | PDF and CDF | About **86%** of transactions are ₹5000 or less |
| 8 | Best fit | **Log-Normal** has the lowest AIC (about 3821) and the best KS result |

---

## 💡 Key Insights

- **Spending is Log-Normal.** Most customers spend a moderate amount, while a small group makes very large purchases. These high-value customers deserve their own offers.
- **Transform before modelling.** Use the log or Box-Cox transform before any method that expects normal data.
- **Use the right probability model.** About 11 to 14% of transactions exceed ₹5000. Assuming a Normal distribution would overstate this at 20.5%. This matters for premium-customer thresholds and fraud-check limits.
- **Demand is predictable.** Daily transaction counts follow Poisson at around 7 per day, which helps with capacity and stock planning.
- **Failures are the biggest opportunity.** Over 55% of transactions fail. Improving payment success would help the business more than any other finding here.

---

## 📚 Theory Covered

`Spread_Locator_Part_A_Theory.ipynb` explains these concepts with definitions, formulas and examples:

Statistical distributions · Q-Q plot · Discrete vs continuous distributions · Bernoulli · Binomial · Log-Normal · Power Law · Box-Cox transform · Poisson · Z-score probability · PDF vs CDF

---

## 👨‍💻 Author

**Manav Patel**
📧 manavpatel.tech@gmail.com
🔗 [GitHub](https://github.com/techmanavp) 
