# 📌 Probability & Statistics Cheatsheet: Laws, Formulas & When to Use Them

---

## **1️⃣ Conditional Probability**
**Formula:**  
`P(A | B) = P(A ∩ B) / P(B)`

**Use When:** You need to find the probability of an event **A given B has already occurred**. Used in medical testing, Bayesian inference, and reliability analysis.

**Limitations:** Assumes that event **B has nonzero probability** (i.e., `P(B) > 0`). Cannot be used when prior information about B is unavailable.

---

## **2️⃣ Law of Total Probability**
**Formula:**  
`P(A) = Σ P(A | B_i) P(B_i)` for all i

**Use When:** The probability of event A needs to be determined by considering all possible ways it can happen. Used in risk assessment, Bayesian modeling, and decision analysis.

**Limitations:** Requires a **mutually exclusive and exhaustive partition** of sample space. If the partitions overlap or do not fully cover A, results are incorrect.

---

## **3️⃣ Bayes’ Theorem**
**Formula:**  
`P(A | B) = P(B | A) P(A) / P(B)`

**Use When:** You need to update prior probabilities based on new evidence (e.g., medical diagnosis, spam filtering, machine learning).

**Limitations:** Requires an accurate prior probability **`P(A)`** and **`P(B) > 0`**. Sensitive to poor prior estimates.

---

## **4️⃣ Independent Events**
**Formula:**  
`P(A ∩ B) = P(A) P(B)`

**Use When:** Two events **do not influence each other** (e.g., rolling two dice, independent experiments).

**Limitations:** Does not apply to dependent events. Wrongly assuming independence can lead to incorrect conclusions.

---

## **5️⃣ Expectation (Mean) & Variance**
**Formulas:**  
- **Expectation:** `E[X] = Σ x P(X=x)` (Discrete), `E[X] = ∫ x f(x) dx` (Continuous)
- **Variance:** `Var(X) = E[(X - E[X])^2]`

**Use When:** You need the **average value** (expectation) or **spread** (variance) of a random variable. Used in finance, quality control, and statistics.

**Limitations:** Assumes existence of **finite mean and variance**. **Heavy-tailed distributions (e.g., Cauchy)** may not have finite variance.

---

## **6️⃣ Moment Generating Functions (MGFs)**
**Formula:**  
`M_X(t) = E[e^(tX)]`

**Use When:** Finding **all moments (mean, variance, etc.)** of a distribution efficiently. Used in statistical proofs and CLT applications.

**Limitations:** Not all distributions have MGFs (e.g., Cauchy distribution). Requires convergence for all t.

---

## **7️⃣ Chi-square, t, and F Distributions**
✔ **Chi-square (`χ²_n`)**: Used in **hypothesis testing**, goodness-of-fit tests.  
✔ **t-distribution (`t_n`)**: Used when **sample size is small**, and population variance is unknown.  
✔ **F-distribution (`F_{m,n}`)**: Used to compare **two variances** (ANOVA, regression).

**Limitations:** Requires normality assumptions for accurate results. Sensitive to outliers and sample size.

---

## **8️⃣ Probability Distributions Overview**
| **Distribution** | **Type** | **Formula Highlights** | **When to Use** | **Limitations** |
|---|---|---|---|---|
| **Bernoulli** | Discrete | One trial, 2 outcomes (success/failure) | Single event success/failure (coin toss) | Only valid for binary outcomes |
| **Binomial** | Discrete | `P(X = k) = C(n, k) p^k (1 - p)^(n - k)` | Number of successes in n trials | Assumes **independent** trials |
| **Poisson** | Discrete | `P(X = k) = (e^(-λ) λ^k) / k!` | Rare event occurrences (calls in an hour) | Assumes independent events, constant rate |
| **Normal** | Continuous | `N(μ, σ²)` | CLT, real-world processes (heights, errors) | Sensitive to outliers |
| **Exponential** | Continuous | `P(X ≤ x) = 1 - e^(-λx)` | Time until next event (reliability, queues) | Assumes memoryless property |
| **Gamma** | Continuous | Generalization of exponential | Waiting times, reliability | Only valid for positive values |
| **t-distribution** | Continuous | `t = Z / sqrt(U/n)` | Small sample hypothesis testing | Heavy tails, sensitive to small samples |
| **Chi-square** | Continuous | Sum of squared normal variables | Variance testing, goodness-of-fit | Requires normality assumption |
| **F-distribution** | Continuous | Ratio of two `χ²` distributions | Comparing variances, ANOVA | Highly skewed, sensitive to sample size |

---

## **📌 Summary: How to Choose the Right Law/Formula?**
- **Bayes’ Theorem** → If new information updates probability.
- **Conditional Probability** → If you need P(A) given B already occurred.
- **Law of Total Probability** → If event A happens via multiple pathways.
- **Expectation/Variance** → If summarizing average behavior and spread.
- **Chi-square/t/F-distribution** → If testing hypotheses about variances, means, or independence.
- **Binomial/Poisson/Normal** → If modeling specific probability events.

🚀 **Tip:** Use the **Flowchart of Distributions** for deeper understanding of relationships between these concepts!
## **Distribution Flowchart**
![Distribution Flowchart](https://github.com/Kaielijah/StatisMod_DataSci_Foundation/blob/main/images/distribution-flowchart.png)