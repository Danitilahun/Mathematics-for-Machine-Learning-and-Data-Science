## Population vs. Sample (Statistics)

**Key Concepts:**

*   **Population:** The entire group of individuals/items being studied.
*   **Sample:** A smaller, observable subset of the population.
*   **N:** Population size.
*   **n:** Sample size.

**Why Samples?**

*   Often impossible or impractical to study the entire population.
*   Samples are used to estimate population characteristics.

**Key Considerations for Samples:**

*   **Random Sampling:** Crucial for representativeness. Avoid bias!  Every member of the population should have an equal chance of being selected.
*   **Independence:** Each sample should be independent of other samples.  Sampling with replacement is usually necessary.
*   **Identically Distributed (IID):** The sampling method must be consistent across all samples.  Avoid changing your criteria mid-study.

**Population & Samples in Machine Learning:**

*   **Datasets are samples:** Even large datasets are just a sample of the *infinite* possibilities.
*   **Representative Data:** Datasets must accurately reflect the population's distribution.
*   **Bias in ML:** If your sample is biased (e.g., all cat photos are on grass), the model will be biased.

**Recap (Formal Definitions):**

*   **Population:** Complete set sharing a common characteristic to be studied.
*   **Sample:** Subset of the population used to draw conclusions about the whole population.

## Estimating Population Mean from Samples

**Key Concepts:**

*   **Population Mean (μ):** The average of the entire population.
*   **Sample Mean (x̄):** The average of a sample taken from the population. Used to *estimate* μ.

**Example: Statistopia Island (Heights)**

*   Population size: 10
*   Calculate population mean (μ) = 160 cm.

**Sampling and Estimation:**

*   Take a random sample of size 'n'.
*   Calculate the sample mean (x̄).  This is an estimate of μ.

**Multiple Samples:**

*   Multiple random samples (x̄₁, x̄₂, x̄₃, etc.) can be drawn.
*   Each sample mean is an *estimate* of the population mean.

**Sample Size Matters:**

*   **Larger sample size (n) generally leads to a better estimate of the population mean (μ).**
*   A sample mean from n=6 is likely a better estimate than a sample mean from n=2.
*   Random sampling remains crucial, regardless of sample size, to avoid bias. A larger *biased* sample is still a bad estimate.

**In Summary:**

Sample mean can be used to estimate population mean, but:
* sample must be randomly sampled
* the larger the sample the more accurate the estimation


## Estimating Population Proportion from Samples

**Key Concepts:**

*   **Population Proportion (P):** The proportion of the *entire* population with a specific characteristic.
*   **Sample Proportion (P̂):** The proportion of a *sample* with a specific characteristic.  Used to *estimate* P.

**Example: Statistopia Island (Bicycles)**

*   Population size (N): 10
*   4 people own bicycles.
*   Population Proportion (P) = 4/10 = 40%

**Sampling and Estimation:**

*   Take a random sample of size 'n'.
*   Calculate the Sample Proportion (P̂):
    *   P̂ = (Number of items in sample with the characteristic) / n
*   P̂ is an *estimate* of P.

**Important Note:**

*   Sample proportion (P̂) provides an estimate of population proportion (P).
*   Random sampling is essential for an accurate estimate.


## Estimating Population Variance from Samples

**Key Concepts:**

*   **Variance:** Measure of data spread (how far points are from the mean).
*   **Population Variance (σ²):**  Average squared deviation from the *population* mean (μ).

    *   σ² = Σ(xᵢ - μ)² / N  (where N is population size)

*   **Estimating Variance from a Sample:**  When you only have a sample, you estimate σ².

**Initial (Biased) Sample Variance Estimation (σ̂² or var̂):**

*   Replace population mean (μ) with sample mean (x̄).
*   Replace population size (N) with sample size (n).

    *   σ̂² = Σ(xᵢ - x̄)² / n

*   **Problem:** This estimate tends to *underestimate* the true population variance. It's *biased*.

**Unbiased Sample Variance Estimation (s²):**

*   Corrects for the bias by dividing by `n-1` instead of `n`.

    *   **s² = Σ(xᵢ - x̄)² / (n - 1)**

*   `s²` is the most common and recommended estimator when you need an *unbiased* estimate of the population variance from a sample.

**Why (n-1)?**

*   Using `n-1` accounts for the fact that you're using the *sample* mean (x̄) to estimate the variance, instead of the *population* mean (μ).
*   This correction results in a more accurate estimate of the population variance.

**Degrees of Freedom:**

* The use of `n-1` is often related to the concept of degrees of freedom. With `n` data points and using the sample mean, you only have `n-1` independent pieces of information to estimate the variance.

**Important Considerations:**

*   **Sample Size Matters:** For *large* sample sizes, the difference between dividing by `n` or `n-1` becomes negligible. If the choice of `n` or `n-1` makes a big difference, it suggests your sample is small, and conclusions should be made cautiously.
*   **Other Estimators:** Maximum Likelihood Estimation (MLE) sometimes uses `n` in the denominator. This creates a biased estimator. However, s² (dividing by n-1) is more often preferred in practice due to its unbiased nature.

**In Summary:**

*   When estimating population variance from a sample:
    *   Use the *unbiased* sample variance formula `s² = Σ(xᵢ - x̄)² / (n - 1)`
    *   This corrects for the bias introduced by using the sample mean.


## Law of Large Numbers (LLN)

**Key Idea:** As the sample size increases, the average of the sample will tend to get closer to the average of the entire population

**Core Concept:**

*   If you repeatedly sample from a population, the average of the sample means will converge to the true population mean as the sample size grows.
*   The larger the sample, the closer the sample mean is to the population mean.

**Conditions for LLN:**

1.  **Random Sampling:**  Samples must be drawn *randomly* from the population to avoid bias.

2.  **Sufficiently Large Sample Size:**  The sample size (n) must be large enough. The definition of sufficient is relative; the more variability in the population, the larger 'n' will need to be.

3.  **Independent and Identically Distributed (IID):** The individual observations in the sample must be independent of each other and drawn from the same distribution

**Formal Definition:**

If:

*   X₁, X₂, ..., Xₙ are independent and identically distributed (i.i.d.) random variables.
*   Each Xᵢ has the same distribution as X.
*   E[X] = μ (population mean)

Then:

As n → ∞, (X₁ + X₂ + ... + Xₙ) / n  →  μ

In other words, as 'n' (number of samples) approaches infinity, the sample mean approaches the population mean.


## Central Limit Theorem (CLT)

**Key Idea:**  The distribution of sample means tends towards a normal distribution, regardless of the shape of the population distribution, as the sample size increases.

**Core Concept:**

*   Start with any distribution (skewed, uniform, etc.).
*   Take multiple random samples of the *same size* from that distribution.
*   Calculate the mean of each sample.
*   Plot the distribution of these sample means.
*   **The resulting distribution of sample means will approximate a normal (Gaussian) distribution.**

**Example: Coin Flips (Bernoulli Distribution)**

*   A single coin flip is a Bernoulli variable (Heads = 1, Tails = 0).
*   The sum of 'n' coin flips (number of heads) follows a binomial distribution.
*   As 'n' (number of coin flips) increases, the binomial distribution looks more and more like a normal distribution.
* mean (μ) = np where p is prob of heads and n is the number of coin flips
* Variance = np(1-p)

**Implications:**

*   This is one of the most important results in statistics.
*   It justifies the use of normal distributions in many statistical tests and procedures, even when the underlying population distribution is not normal.


## Central Limit Theorem (CLT) - Continued

**Example: Text Support Line Wait Times**

*   Wait time (X) follows a uniform distribution (0-15 minutes).
*   Objective: Approximate the *mean* wait time.
*   Approach: Average wait times from different numbers of calls (samples).

**Variable Definition:**

*   Yₙ = average wait time for 'n' calls (samples).

**Observations:**

*   **n = 1:** Distribution resembles the uniform distribution (original data).
*   **n = 2:** Distribution starts to resemble a triangle shape (more concentrated around the mean).
*   **n = 3, 4, 5,...:** Distribution looks increasingly bell-shaped (approaching normal), symmetric around the population mean (7.5 minutes), and has lower dispersion.
* Variance is the population variance divided by n, in other words the variance of the mean decreases as n increases

**Key Points:**

*   **Distribution of Yₙ converges to a normal distribution as 'n' increases.**
*   **The normal distribution becomes a better approximation as 'n' gets larger.**
*   **The normal distribution fits around the mean 7.5 = population mean

**Standardization:**

* This makes it easier to compare yn for different values of n because it puts them on the same scale for mean and variance.

**General Guidelines:**

*   A safe rule of thumb is that you need around 30 variables before the bell-shaped distribution becomes apparent. It depends on how skewed the original distribution is

**Formal Definition**
Yₙ approaches normal distribution as n goes to infinity

**In summary:**

Standardizing a sample mean lets you know that even if you do not know the value of the population mean and variance, as n increases the average will have a gaussian distribution.