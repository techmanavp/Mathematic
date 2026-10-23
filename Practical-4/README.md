<div align="center">

# 📐 Calculative Foundation

### Linear Algebra for Data Analysis: Vectors, Matrices, Geometry & Eigen Decomposition

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Linear%20Algebra-013243?logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data-150458?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visuals-11557c)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Type](https://img.shields.io/badge/Type-Theory%20%2B%20Practical-success)

**Duration:** 6 Hours &nbsp;|&nbsp; **Type:** Theory + Practical &nbsp;|&nbsp; **Dataset:** 15 students × 5 subjects

</div>

---

## 📖 Table of Contents

1. [Project Overview](#-project-overview)
2. [Dataset](#-dataset)
3. [Part A: Vector Fundamentals](#-part-a-vector-fundamentals)
4. [Part B: Matrix Operations](#-part-b-matrix-operations)
5. [Part C: Linear Transformations & Geometry](#-part-c-linear-transformations--geometry)
6. [Part D: Eigenvalues & Decomposition](#-part-d-eigenvalues--decomposition)
7. [Key Insights](#-key-insights)
8. [Verification](#-verification-theory-vs-python)
9. [Learning Outcomes](#-learning-outcomes)
10. [Author]

---

## 🎯 Project Overview

A research institute shared a dataset of **students' performance scores across multiple subjects**. As a data analyst, the goal is to apply **Linear Algebra** to represent, manipulate and interpret this data, both **theoretically (handwritten rough work)** and **practically (Python)**.

| Area | Concepts used |
|------|---------------|
| Vectors | Norm-1, Norm-2, dot product, angle, cross product, projection |
| Matrices | Addition, multiplication, transpose, determinant, inverse |
| Geometry | Line, plane, hyperplane, 2D → 3D → 5D |
| Decomposition | Covariance matrix, eigenvalues, eigenvectors, variance explained |

---

## 📊 Dataset

File: [`student_scores.csv`](student_scores.csv)

- **Students:** 15 (rows)
- **Subjects:** 5 (columns): Maths, Physics, Chemistry, English, Computer
- **Score matrix shape:** `(15, 5)`, and one student's vector has shape `(5,)`

<p align="center">
  <img src="images/01_dataset_heatmap.png" alt="Dataset heatmap" width="600">
</p>

| Subject | Average marks |
|---------|:-------------:|
| Maths | 75.33 |
| Physics | 74.87 |
| Chemistry | 74.93 |
| English | 75.67 |
| Computer | 76.20 |

---

## 🧮 Part A: Vector Fundamentals

Two students are used for the vector tasks:

| Student | Vector |
|---------|--------|
| **A: Aarav** (row 1) | `[85, 78, 82, 74, 90]` |
| **B: Diya** (row 2) | `[92, 88, 85, 80, 95]` |

<p align="center">
  <img src="images/02_vectors_A_vs_B.png" alt="Vector A vs B" width="600">
</p>

### Norms

| Norm | Formula | A (Aarav) | B (Diya) |
|------|---------|:---------:|:--------:|
| **L1** | Σ \|xᵢ\| | **409** | **440** |
| **L2** | √(Σ xᵢ²) | **183.33** (√33609) | **197.12** (√38858) |

### Dot Product and Angle

```text
A · B = 7820 + 6864 + 6970 + 5920 + 8550 = 36124
cos θ = 36124 / (183.33 × 197.12) = 0.99960
θ     = cos⁻¹(0.99960) = 1.61°
```

> The angle is very small, so both students have almost the same performance pattern.

### Cross Product (3D: Maths, Physics, Chemistry)

```text
A = (85, 78, 82)      B = (92, 88, 85)

A × B = [ A2B3 − A3B2 ,  A3B1 − A1B3 ,  A1B2 − A2B1 ]
      = [ 6630 − 7216 ,  7544 − 7225 ,  7480 − 7176 ]
      = [ −586 , 319 , 304 ]
```

| Check | Calculation | Result |
|-------|-------------|:------:|
| A · (A × B) | −49810 + 24882 + 24928 | **0** ✅ |
| B · (A × B) | −53912 + 28072 + 25840 | **0** ✅ |

### Vector Projection (A onto B)

```text
proj_B A = (A·B / ‖B‖²) × B = (36124 / 38858) × B = 0.92964 × B
         = [85.53, 81.81, 79.02, 74.37, 88.32]
```

<p align="center">
  <img src="images/03_projection.png" alt="Projection" width="600">
</p>

---

## 🧱 Part B: Matrix Operations

The full score matrix **A** has shape `15 × 5`. For hand calculation, a `2 × 2` matrix is built from the Maths and Physics marks of two students:

```text
A = | 85  78 |
    | 92  88 |
```

| Operation | Result |
|-----------|--------|
| **Addition** `A + A = 2A` | `[[170, 156], [184, 176]]` |
| **Multiplication** `A × A` | `[[14401, 13494], [15916, 14920]]` |
| **Transpose** `Aᵀ` | `[[85, 92], [78, 88]]` |
| **Determinant** `ad − bc` | 7480 − 7176 = **304** |
| **Inverse** `A⁻¹` | `[[0.28947, −0.25658], [−0.30263, 0.27961]]` |

> Determinant ≠ 0, so the inverse exists.

### In Python (full 15 × 5 data)

| Operation | What was done |
|-----------|---------------|
| Addition | `A + B`, where B adds 5 grace marks to every cell |
| Multiplication | `A @ W`, a weighted score with weights `[0.3, 0.2, 0.2, 0.1, 0.2]` |
| Transpose | `Aᵀ` has shape `(5, 15)` |
| Determinant / Inverse | A is not square, so `S = AᵀA` (5 × 5) is used. `det(S) ≈ 1.5058 × 10¹⁴ ≠ 0`, so the inverse exists and `S · S⁻¹ = I` ✅ |

---

## 🌐 Part C: Linear Transformations & Geometry

| Space | Object | Equation | Dimension |
|-------|--------|----------|:---------:|
| 2D (Maths, Physics) | **Line** | `y = mx + c` | 1D |
| 3D (Maths, Physics, Chemistry) | **Plane** | `ax + by + cz + d = 0` | 2D |
| 5D (all subjects) | **Hyperplane** | `w₁x₁ + w₂x₂ + … + w₅x₅ + b = 0` | 4D |

> A hyperplane always has **n − 1** dimensions. Each student is a point in 5D space.

<table align="center">
  <tr>
    <td align="center"><b>2D: Line</b> (Maths + Physics = 150)<br><img src="images/Fig1_2D_Line_Maths_vs_Physics.png" width="380"></td>
    <td align="center"><b>3D: Plane</b> (Maths + Physics + Chemistry = 240)<br><img src="images/Fig2_3D_Plane_Maths_Physics_Chemistry.png" width="380"></td>
  </tr>
</table>

---

## 🔬 Part D: Eigenvalues & Decomposition

### Covariance

```text
cov(x, y) = Σ (xᵢ − x̄)(yᵢ − ȳ) / (n − 1)
```

| Quantity | Value |
|----------|:-----:|
| Maths variance | 166.52 |
| Physics variance | 138.12 |
| Covariance (Maths, Physics) | 144.19 |

<p align="center">
  <img src="images/04_covariance_heatmap.png" alt="Covariance matrix" width="460">
</p>

### Eigenvalues of the 5 × 5 Covariance Matrix

| Eigenvalue | Value | Variance explained |
|:----------:|------:|-------------------:|
| λ₁ | **685.28** | **94.21 %** |
| λ₂ | 19.41 | 2.67 % |
| λ₃ | 10.94 | 1.50 % |
| λ₄ | 9.62 | 1.32 % |
| λ₅ | 2.16 | 0.30 % |

```text
Total variance = 166.52 + 138.12 + 142.35 + 77.67 + 202.74 = 727.41
Variance explained by λ₁ = (685.28 / 727.41) × 100 = 94.21 %
```

<p align="center">
  <img src="images/05_eigenvalues.png" alt="Eigenvalues" width="760">
</p>

The first eigenvector is `[−0.489, −0.436, −0.443, −0.301, −0.533]`. All its weights have the same sign, so it behaves like an **"overall performance"** axis.

<p align="center">
  <img src="images/06_pca_projection.png" alt="PCA projection" width="560">
</p>

---

## 💡 Key Insights

- ✅ **One dominant direction:** λ₁ alone explains **94.21 %** of the variance, which is overall academic performance.
- ✅ Students who score high in one subject tend to score high in all subjects (e.g. Maths vs Computer correlation ≈ 0.98).
- ✅ The remaining four eigenvalues are small, so the 5 subjects can be reduced to **1–2 dimensions** with very little information loss (PCA).
- ✅ Aarav and Diya have almost parallel score vectors (**1.61°**), so their performance patterns are nearly identical.

---

## ✔️ Verification: Theory vs Python

Every handwritten result was checked against the notebook output.

| Task | Handwritten | Python | Match |
|------|-------------|--------|:-----:|
| L1 norm (A) | 409 | 409 | ✅ |
| L2 norm (A) | 183.33 | 183.3276 | ✅ |
| Dot product | 36124 | 36124 | ✅ |
| Angle | 1.61° | 1.6133° | ✅ |
| Cross product | [−586, 319, 304] | [−586, 319, 304] | ✅ |
| Projection | [85.53, 81.81, 79.02, 74.37, 88.32] | [85.527, 81.808, 79.02, 74.371, 88.316] | ✅ |
| Largest eigenvalue | 685.28 | 685.284 | ✅ |
| Variance explained by λ₁ | 94.21 % | 94.21 % | ✅ |

---

## 🏁 Learning Outcomes

By completing this project, I was able to:

- Understand **vector and matrix manipulation** in real-world data.
- Apply **norms, dot/cross products and projections** to performance data.
- Gain insight into **eigenvalues and eigenvectors** and their meaning.
- Build confidence in using **linear algebra foundations** in applied statistics and machine learning.

---

<div align="center">

## 👨‍💻 Author

**Manav Patel**
📧 manavpatel.tech@gmail.com
🔗 [GitHub](https://github.com/techmanavp) 

---


</div>
