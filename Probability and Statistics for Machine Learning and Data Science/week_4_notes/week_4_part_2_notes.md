# Introduction to Hypothesis Testing

## Goal

*   Determine if a belief about a population is likely to be true or false.
*   Learn about A/B testing.

## Example: Email Spam Detector

*   **Objective:** Classify emails as either Ham (not spam) or Spam.

*   **Default Assumption (Null Hypothesis):**  All emails are Ham. Why?  Deleting a good email is worse than receiving spam.

### Hypotheses

*   **Null Hypothesis (H0):** Email is Ham (baseline assumption). The base case we can safely assume is true.
*   **Alternative Hypothesis (H1):** Email is Spam (what we want to identify).

### Key Characteristics of Hypotheses

*   **Mutually Exclusive:**  An email cannot be both Ham and Spam at the same time. The questions being asked must have a true or false answer.

### Logic of Hypothesis Testing

*   **Strong Evidence Against H0:**  Reject H0; accept H1 (email is Spam).

*   **Insufficient Evidence Against H0:** Fail to reject H0, The conclusion that the email is Ham is not valid, because the only valid reason is to fail to reject the null hypothesis.

### General Principles

*   **Propose Hypotheses:**
    *   H0: Baseline assumption.
    *   H1: Competing statement (usually the one you want to prove).
*   **Goal:** Decide between H0 and H1 based on data/evidence.

### Evidence

*   **Spam Example:** Sender, attachments, email size, keywords, etc.

### Intuition

*   If the sample provides strong evidence *against* H0, then reject H0 and accept H1.

### Trigger Phrases (Spam Example)

*   "Earn extra cash," "Risk free," "Dear friend," "Act immediately," "Apply now," "Winner!"

*   These phrases are *unlikely* under the Null Hypothesis (email is Ham).

*   Therefore, reject H0 and send the email to Spam.


# Errors in Hypothesis Testing

## The Reality

*   Perfect decisions are impossible due to randomness and partial information.

## Possible Outcomes of the Spam Test

*   Send email to spam box.
*   Send email to regular inbox.

## Types of Errors

*   **Type I Error (False Positive):** Reject H0 when H0 is *true*.
    *   Send a *ham* email to the spam box.
*   **Type II Error (False Negative):** Fail to reject H0 when H0 is *false*.
    *   Send a *spam* email to the regular inbox.

## Key Point

*   You *cannot* know if you are right or wrong in your decision because you don't know the "ground truth" (actual status of the email).

## Decision Table

| Decision           | H0 True (Ham)          | H1 True (Spam)         |
| ------------------ | ---------------------- | ---------------------- |
| Reject H0          | Type I Error (False Positive) | Correct Decision     |
| Fail to Reject H0 | Correct Decision     | Type II Error (False Negative) |

## Impact of Errors

*   Type I and Type II errors have *different* impacts.
*   In the email example, Type I errors (missing a good email) are generally considered *more severe* than Type II errors (receiving spam).

## Significance Level (alpha)

*   **Definition:** Maximum probability of a Type I error that you are willing to tolerate. Also the maximum probability of rejecting H0 when it is actually true.
*   **Range:** 0 to 1.
*   **Interpretation:** The maximum percentage of the time you're willing to incorrectly classify a ham email as spam.
*   **Typical Values:** 0.05 (5%) or 0.01 (1%).

### Extremes

*   **alpha = 0:** Never reject H0. Never a Type I error, but every email is considered ham.
*   **alpha = 1:** Always reject H0. Always a Type I error, every email is considered spam.

## Tradeoff

*   Reducing the probability of Type I error can *increase* the probability of Type II error (for a fixed sample size).

## Alpha as a Design Criterion

*   Alpha determines the threshold for deciding whether to reject H0.


# Hypothesis Testing for a Population Mean

## Objective

*   Learn how to perform hypothesis tests for a population mean.
*   Explore both cases:
    *   Known population standard deviation (sigma).
    *   Unknown population standard deviation (sigma) – using the t-distribution.
*   Understand the concept of the p-value.

## Example: Average Height of 18-Year-Olds in the US

*   Goal: Investigate the average height of 18-year-olds in the US.
*   Data: Sample of 10 people (heights in inches). Same dataset from Week 2.
*   Sample Mean: 68.442 inches.

## Data Quality Considerations

*   **Reliability:** The data needs to be reliable for accurate decision-making.
*   **Representativeness:** Each sample must represent the population. Data should be completely randomized.
    *   Avoid bias: e.g., sampling only from basketball teams would skew results.
*   **Sample Size:** Is the sample size large enough?
    *   Rule of thumb: Consider 30 samples or more.

## Historical Data and Hypothesis Formulation

*   Historical Data (1970s): Mean height of 18-year-olds was 66.7 inches.
*   Question: Has the mean height increased?
*   Hypotheses:
    *   **H0 (Null):** Population mean (mu) = 66.7 inches (no change).
    *   **H1 (Alternative):** Population mean (mu) > 66.7 inches (height has increased). Note that hypothesis are always formulated in terms of the population and must not involve samples.

## Test Statistic

*   **Definition:** Function of the random samples that provides information about the population parameter being studied.

*Sample Mean: The average value for the random samples from population *Xi.*.
*   **Example:** In this case, the sample mean will be the test statistic to determine a test for the population mean.
*   **Observed Statistic:** The specific value of the test statistic calculated from your data (e.g., 68.442 inches).
*   **Non-Uniqueness:** Test statistics are not unique (different functions could be used).

## Types of Hypothesis Tests (Tail Tests)

1.  **Right-Tailed Test:**
    *   Question: Has the population height *increased*?
    *   H0: mu = 66.7
    *   H1: mu > 66.7
    *   Reject H0 if the sample mean is *much greater* than 66.7. This test is also equivalent if you phrase it as "H0 states that Mu is less than or equal to 66.7"

2.  **Left-Tailed Test:**
    *   Question: Has the population height *decreased*?
    *   H0: mu = 66.7
    *   H1: mu < 66.7
    *   Reject H0 if the sample mean is *much less* than 66.7.
 * This test is also equivalent if you phrase it as "H0 states that Mu is greater than or equal to 66.7"

3.  **Two-Tailed Test:**
    *   Question: Has the population height *changed* (either increased or decreased)?
    *   H0: mu = 66.7
    *   H1: mu != 66.7
    *   Reject H0 if the sample mean *deviates a lot* from 66.7 in *either* direction. To measure this deviation, simply use the absolute value of the difference between the sample mean and 66.7

## Errors for Each Test Type

The specific wording will vary.
*   A type I error will be determining that the opposite happened, when it did not.
*   A type II error occurs when it did happen, and you were unable to detect it.


# Significance (alpha) and P-Value for Hypothesis Testing

## Key Idea: Reject H0 if the Sample Mean is "Too Far"

*   "Too Far": Requires a precise definition based on probability.

## Example: Right-Tailed Test for Population Mean

*   H0: Population Mean (mu) = 66.7 inches (from previous example)
*   Assumption: Standard Deviation (sigma) = 3 inches (known)
*   Sample Size: n = 10
*   If H0 is true, the sample mean follows a normal distribution:
    *   Mean: mu = 66.7 inches
    *   Variance: sigma^2 / n = 3^2 / 10
    *   Distribution = gaussian gaussian distribution with the above parameters

## Answering the Key Question

*   "How likely was your sample IF H0 is true?" If the sample is very unlikely under H0, it's evidence to reject H0.

## Making a Decision with a Controlled Type I Error

*   Goal: Keep the probability of a Type I error (alpha) at or below 0.05.
*   Type I Error: Determining that the population mean has increased when it is actually still 66.7 inches.

## Rejection Criteria

*   If the observed sample mean is 68.442, then we'd also reject H0 if the sample mean were *greater* than 68.442.

## Calculating Type I Error Probability

*   The probability of committing a Type I error is the probability of observing a sample mean greater than 68.442 GIVEN that the true population mean (mu) is 66.7.
*   This probability (the shaded area) is 0.0332 (found using statistical methods).

## Decision

*   Since 0.0332 < 0.05 (alpha), the maximum probability of a Type I error is *below* the acceptable threshold.
*   **Therefore, reject the null hypothesis (H0).**

## The P-Value

*   **Definition:** Assuming H0 is true, the probability that the test statistic takes on a value *as extreme as or more extreme than* the value observed.
*   Move in the direction of H1 from your observation.

## P-Value Example (Right-Tailed Test)

*   Probability of observing a sample mean >= 68.442 given that mu = 66.7.

## Interpreting the P-Value

*   Measures how well the sample data supports the null hypothesis.
*   **Small p-value:** The sample is unlikely to have occurred if H0 is true (strong evidence *against* H0).
*   **Large p-value:** The sample is reasonably likely to have occurred if H0 is true (weak evidence against H0).

## Decision Rule Based on P-Value

*   **If p-value < alpha:** Reject H0; accept H1.
*   **If p-value > alpha:** Fail to reject H0.

## P-Values for Different Test Types

*   t observed = observed value of the statistics

1.  **Right-Tailed Test:**
    *   P-value = P(Test Statistic >= t observed | H0 is true)

2.  **Two-Tailed Test:**
    *   P-value = P(|Test Statistic - mu| >= |t observed| | H0 is true)

3.  **Left-Tailed Test:**
    *   P-value = P(Test Statistic <= t observed | H0 is true)

## Example: Revisit Previous Test with Different Scenarios

*   Original sample: 68.442 mean (right-tailed test).
*   Let's analyze some other tests, such as the two-tailed and left-tailed tests, and their outcomes.

## The Z-Statistic: Standardizing the Test Statistic

*   **Alternative Approach:** Use the z-statistic, which is the standardized version of the sample mean.
*   Z = (X-bar - mu_0) / (sigma / sqrt(n)
*   Under H0, the z-statistic follows a standard normal distribution (mean=0, variance=1).
*   The hypothesis and the type I error interpretation need to remain the same.
*   Also, your sample data doesn't change

## Example: Transforming the Right-Tailed Test to a Z-Statistic Test

*   Keep the original test: looking at the right-tail test for the population mean

*   **New z-Statistic Calculation:**
    *   The *observed* z-statistic is: (68.442 - 66.7) / (3 / sqrt(10)) = 1.837

*   How to formulate the same problem in terms of the z-statistic,

*   The z statistic will turn the sample pdf from an x-bar with a gaussian distribution, into a z-statistic with a standard normal distribution

*   How do you transform the event X bar bigger than 68.442 so that the probability of type 1 errors is stated in terms of the z-statistic and its observed value? You subtract the population mean from H0 from both sides, and they scale everything by 3 divided by square root 10.

*  Of course, the result of the p-value has to be the same because you're performing the same test over the same data and you're just standardizing the statistic.


# Calculating P-Value (Right-Tailed Test, Sigma Known)

**Goal:** Calculate the p-value for a right-tailed test with known population standard deviation (sigma).

**Scenario:**

*   Null Hypothesis (H0): Population mean (μ₀) = 66.7 inches
*   Alternative Hypothesis (H1): Population mean (μ) > 66.7 inches
*   Sample Mean (x̄): 68.442 inches
*   Population Standard Deviation (σ): 3 inches
*   Sample Size (n): 10

**Steps:**

1.  **Calculate the Standard Error (SE):**

    *   SE = σ / √n
    *   SE = 3 / √10
    *   SE ≈ 0.9487

2.  **Calculate the Z-Score:**

    *   Z = (x̄ - μ₀) / SE
    *   Z = (68.442 - 66.7) / 0.9487
    *   Z ≈ 1.836

3.  **Find the P-Value:**

    *   P-value = P(Z > 1.836)  (probability of observing a Z-score as extreme or more extreme than 1.836, *assuming H0 is true*)

    *   Use a standard normal (Z) table or statistical function.  Z-tables typically show P(Z < z) (the area to the *left*).  To find the area to the *right*, subtract from 1:

        *   P(Z > 1.836) = 1 - P(Z < 1.836)
        *   P(Z > 1.836) ≈ 1 - 0.9668
        *   P-value ≈ 0.0332

**Interpretation:**

*   The p-value is approximately 0.0332.  This means there is a 3.32% chance of observing a sample mean as high as 68.442 (or higher) if the true population mean is 66.7.

*   Compare the p-value to the significance level (alpha).  If p-value < alpha, reject the null hypothesis.


# Critical Values in Hypothesis Testing

## Motivation

*   You know how to make decisions based on the p-value of the *observed* statistic.

*   Question: What is the *most extreme* sample you could observe and *still* reject H0? This will correspond to having a P-value of exactly alpha.

## Critical Value (K_alpha)

*   **Definition:** The value of the test statistic that results in a p-value *exactly equal* to the significance level (alpha). This depends on the value you choose for alpha. Different alpha's determined different critical values.
*   Any observed statistic *more extreme* than the critical value will have a p-value *less than* alpha (and therefore lead to rejection of H0).

## Decision Rule Based on Critical Value

*   Reject H0 if the observed test statistic is more extreme than the critical value.

## Example: Right-Tailed Test, Revisited

*   H0: mu = 66.7
*   H1: mu > 66.7
*   n = 10
*   sigma = 3
*   alpha = 0.05

1.  **Find K_{0.05}:**

    *   Value that leaves an area of 0.05 to the *right* under the distribution of the test statistic (sample mean) assuming H0 is true.
    *   K_{0.05} is the 1-0.05 = 0.95 quantile of the sample mean's distribution.

2.  **Distribution of Sample Mean (under H0):**

    *   Gaussian (Normal) with mean 66.7 and standard deviation 3 / √10

3.  **Calculate Critical Value (K_{0.05}):**  The critical value is 68.26

4.  **Decision Rule:**

    *   Reject H0 if the observed sample mean is greater than 68.26.

5.  **Example Conclusion with Observed Data:**

    *   Observed sample mean = 68.442
    *   68.442 > 68.26
    *   Therefore, reject H0 (same conclusion as using the p-value method with alpha = 0.05).

6. **Changing alpha:**

* if you changed the alpha of 0.05 to .01, then you cannot reject the null hypothesis using your data. Since you will now reject the null hypothesis if the observed sample mean is greater than 68.91.

## Advantage of Critical Values

*   The decision rule can be defined *before* collecting data.
*   After data collection, calculate the observed statistic and make a decision based on the pre-defined rule.

## Critical Values for Different Test Types

1.  **Right-Tailed Test:**

    *   K_alpha: Value leaving area alpha to its *right*. The critical value is the quantile, one minus Alpha of the statistic distribution when a zero is true.
    *   Reject H0 if the observed statistic > K_alpha

2.  **Left-Tailed Test:**

    *   K_alpha: Value leaving area alpha to its *left*.  The critical value to the quantile Alpha.
    *   Reject H0 if the observed statistic < K_alpha

3.  **Two-Tailed Test:**

    *   Two Critical Values:
        *   K_{alpha/2}: Value leaving area alpha/2 to its *left* (quantile alpha/2)
        *   K_{1 - alpha/2}: Value leaving area alpha/2 to its *right* (quantile 1 - alpha/2)
    *   Reject H0 if the observed statistic > K_{1 - alpha/2} OR the observed statistic < K_{alpha/2}

## Summary

*   **Critical Value Method:** The P-value method and the critical value method must always lead you to the same conclusion.

    *   Define decision criteria *before* data collection. This makes it possible to determine the type 2 error probabilities.

*   A new way to determine the type II error probabilities using the design criteria.


# Type II Errors and Power of a Hypothesis Test

## Review

*   **Type I Error:** Reject H0 when H0 is *true* (controlled by alpha).
*   Goal is to test for type I error
*   **Type II Error:** Fail to reject H0 when H0 is *false* (what we're focusing on now).

## Example: Testing Population Mean Increase

*   H0: Population mean (mu) was 66.7 inches (height of 18-year-olds in the 70s).

*   Rejection Criteria using a right tailed test. If true value of sample mean fell above 68.26

## Probability of a Type II Error (beta)
*   This value varies for all different possibilities in H1
    *   What is the probability of type II error
* This is the probably that does not exist due to the significance level from the type 1 error

## Calculation of Type II error probability
### Type II error does not depends on the sample mean itself

*   Not reject the null hypothesis, in order to do this,
*   Probaility of of mean falling below some value, when that true mean of that value is 70, not 66.7, This would look like beta.
*   Distribution follows distribution but this time with 70 mean and the same standard variation
*   From what you can see, you can calculate for any value on mu in the alternative hypothesis

## Goal
* Goal to define each population and measure their likelihood for a power test

## Type Test

*   In the test that are most appropriate
*   This means, test tells us how well we would be able to determine if they had more data
*   Probability test with the function to tell if the right decision when H0 is 0
*   How to test

## Graph Analysis

*   This probability corresponds to the complement so it depends on how great or not the null hypothesis is
*    For mu 0 68 is there value on 68 and the curve
*   Same thing when true 70 the height on this graph
*    Increases closer to on the horizontal axis, this also means the distribution of value of the value of the decreasing number
        * As mus increases, you lower the probability

## See the Power of testing


*   The trade offs with the different alpha

* the more likely you are to make a type II error in a fixed distribution. More restrictive = higher probability of type II error


# Steps in Hypothesis Testing and Common Misconceptions

## The Four Steps

1.  **State Your Hypothesis:**
    *   **Null Hypothesis (H0):** Baseline assumption. (e.g., population mean height = 66.7)
    *   **Alternative Hypothesis (H1):** The statement you want to prove. (e.g., population mean height > 66.7)

2.  **Design the Test:**
    *   **Test Statistic:** What statistic will you use? (e.g., sample mean)
    *   **Significance Level (Alpha):** Maximum acceptable probability of a Type I error. (e.g., Alpha = 0.05).  Must always be small.

3.  **Compute the Observed Statistic:**
    *   Calculate the value of the test statistic based on your sample data. (e.g., observed sample mean = 68.442)

4.  **Decision-Making:**
    *   Use the data to make a decision about rejecting or failing to reject H0.
    *   **P-Value Method:** If p-value < alpha, reject H0 and accept H1.

## Review of Errors

*   **Type I Error:** Reject H0 when H0 is actually true (false positive).
*   **Type II Error:** Fail to reject H0 when H0 is actually false (false negative).
*   Alpha: Maximum probability of making a Type I error.
*   **Tradeoff:** For a fixed sample size, reducing the probability of a Type I error (smaller alpha) can increase the probability of a Type II error. It’s also possible to reach alpha and be as small as you want and do beta as small as you want to

## Common Misconceptions

1.  **Misconception about P-Values:** "P-value is the probability of H0 being true." **FALSE**
    *   **Correct:** The p-value is the probability of observing the *data* (or more extreme data) if H0 were true. A small p-value suggests that H0 is not a good model for the data. Basically, a small p-value tells you that the null hypothesis is not a good model for your data because the chances of observing it are small.

2.  **Misconception about Conclusions:** "Failing to reject H0 means that H0 is true." **FALSE**
    *   **Correct:** Failing to reject H0 simply means that there is *not enough evidence* to reject it.  It does *not* prove that H0 is true. Remember the spam example, you don't really say that the email is ham, the most you can guarantee is that there was not enough evidence to show that the email was spam.


# t-Distribution in Hypothesis Testing (Unknown Sigma)

## Review: Gaussian Data and Sample Mean

*   Population: Heights modeled as a Gaussian distribution with mean (mu) and standard deviation (sigma).
*   Sample: n samples drawn from the population
*   Sample Mean: Has a Gaussian distribution with mean mu and standard deviation sigma / √n (if mu and sigma *known*).

## Scenario: Sigma Unknown

*   If both mu and sigma were known, you could calculate z
*   Z = (sample mean - mu) / (sigma / sqrt(n)) follows standard normal distribution.

* The fact we don't know sigma presents a problem that must be overcome
        * You can still use the equation but, s instead of sigma
        * s almost equals varaince sample except divided by n-1
                * the square root of this
 * * This is called a T statistic and also turns out to not follow a normal normal
### *This creates a student T distribution*

## Use the Student's t-Distribution (t-Distribution)

*   When sigma is unknown, replace sigma with s (sample standard deviation) in the standardization formula:
    * Follows a distribution called the 'student T'
    * Why? In heavier tails and helps account for the replacing of with the population mean
 * To find parameters, called 'Degrees of Freedom' with the value of 'Nu' which you can call with the Greek letter

*   Resulting Statistic (t-statistic): (x̄ - μ) / (s / √n)

## Characteristics of the t-Distribution

*   Bell-shaped, similar to the Gaussian.
*   Heavier tails compared to the standard normal distribution.
 * Is similar to Gaussian but when comparing you'll notice that it has a heavier weight meaning the uncertainty is high.

*   Accounts for the uncertainty of estimating sigma with s.

## Degrees of Freedom (nu)

*   Only one parameter: degrees of freedom (ν or nu).
*  The smaller the new will create higher tail in the distribution
        *  If compare new to 1 you need more distribution
        *  if degrees of freedom is 5. You need smaller tail to distribution
        *  when you go to more than ten degrees, they distribution almost have identical properties and a more stable standard deviation

*   Controls the heaviness of the tails.

*   X ~ t(ν) (X follows a t-distribution with ν degrees of freedom)

## Example Revisited: n = 10

*   t-statistic: (x̄ - μ) / (s / √10)  follows a t-distribution with ν degrees of freedom.

*The new distribution is now 10 - 1*

* The larger it gets, the distribution looks more and more normal

* You will know it is normally distributed when u gets 30 samples it looks close to
**What should the value of Nu be*

*   Nu = 10 - 1 = 9 (number of samples minus 1).

*   In general, ν = n - 1.

## Summary

*   t-statistic is used when:

    *   The population has a Gaussian distribution (or is approximately Gaussian)

    *   Sigma, the population standard deviation is *unknown*.


# Hypothesis Testing with Unknown Population Standard Deviation (σ)

**Scenario:** We want to test hypotheses about the population mean (μ) of a Gaussian distribution when the population standard deviation (σ) is unknown.

**Key Difference from Known σ:**  When σ is unknown, we use the t-statistic and the t-distribution instead of the z-statistic and the normal distribution.

**1. The t-Statistic:**

*   **Formula:**  `t = (x̄ - μ₀) / (s / √n)`
    *   `x̄`: Sample mean
    *   `μ₀`:  Mean under the null hypothesis (H0)
    *   `s`: Sample standard deviation
    *   `n`: Sample size

*   **Distribution:**  Under H0, the t-statistic follows a t-distribution with `n-1` degrees of freedom.

**2. Hypothesis Testing Procedure:**

*   **Step 1: State the Hypotheses:**
    *   Right-tailed test:  H0: μ = μ₀,  H1: μ > μ₀
    *   Left-tailed test:   H0: μ = μ₀,  H1: μ < μ₀
    *   Two-tailed test:  H0: μ = μ₀,  H1: μ ≠ μ₀

*   **Step 2: Calculate the t-statistic:**  Use the formula above.

*   **Step 3: Determine the p-value:**
    *   **Right-tailed test:** P(t > t_observed | H0 is true)  (Area to the right of t_observed)
    *   **Left-tailed test:**  P(t < t_observed | H0 is true) (Area to the left of t_observed)
    *   **Two-tailed test:** P(|t| > |t_observed| | H0 is true) = 2 * P(t > |t_observed|)  (Sum of areas in both tails, considering the absolute value)

*   **Step 4: Make a Decision:**
    *   If p-value ≤ α (significance level, e.g., 0.05), reject H0.
    *   If p-value > α, do not reject H0.

**Example Calculations (from the video):**

*   **Data:**  n = 10,  μ₀ = 66.7

    *   **Example 1 (Right-tailed):**
        *   x̄ = 68.442,  s² = 3.113 (sample variance), s = sqrt(3.113) = 1.764
        *   t = (68.442 - 66.7) / (1.764 / √10) = 1.771
        *   p-value = P(t > 1.771) = 0.0552  (df = 9)
        *   Conclusion: Do not reject H0 (since 0.0552 > 0.05)

    *   **Example 2 (Two-tailed):** Using the same x̄, s, and t from example 1
        *   p-value = 2 * P(t > 1.771) = 2 * 0.0552 = 0.1103
        *   Conclusion: Do not reject H0 (since 0.1103 > 0.05)

    *   **Example 3 (Left-tailed):**
        *   x̄ = 64.252,  s² = 3.113 (sample variance)
        *   t = (64.252 - 66.7) / (1.764 / √10) = -2.487
        *   p-value = P(t < -2.487) = 0.0173 (df = 9)
        *   Conclusion: Reject H0 (since 0.0173 < 0.05)

**Important Notes:**

*   The t-distribution has heavier tails than the normal distribution, especially with small sample sizes.  This means that the p-values will generally be larger when using the t-distribution compared to the normal distribution (when σ is known).
*   Therefore, not knowing σ introduces more uncertainty, making it harder to reject the null hypothesis.
*   For a two-tailed test, the p-value is double the p-value of a corresponding one-tailed test (when t_observed is positive, otherwise consider the absolute value).


# Two-Sample Hypothesis Testing: Comparing Population Means

**Scenario:** Comparing means of two independent populations (e.g., heights of 18-year-olds in the US vs. Argentina).

**Assumptions:**

1.  Samples are independent (no individuals in both groups).
2.  Measurements within each sample are independent.
3.  Populations are normally distributed:
    *   US: X ~ N(μ_US, σ_US)
    *   Argentina: Y ~ N(μ_Argentina, σ_Argentina)

**Notation:**

*   US:  `x_1, ..., x_n` (n = 10), sample mean `x̄`, sample standard deviation `s_x`
*   Argentina: `y_1, ..., y_m` (m = 9), sample mean `ȳ`, sample standard deviation `s_y`

**Hypotheses:**

*   **Null Hypothesis (H0):**  μ_US = μ_Argentina  (or μ_US - μ_Argentina = 0)
*   **Alternative Hypotheses (H1):**
    *   Right-tailed:  μ_US > μ_Argentina (μ_US - μ_Argentina > 0)
    *   Left-tailed:  μ_US < μ_Argentina (μ_US - μ_Argentina < 0)
    *   Two-tailed:  μ_US ≠ μ_Argentina (μ_US - μ_Argentina ≠ 0)

**Distribution of the Difference of Sample Means (x̄ - ȳ):**

*   The difference (x̄ - ȳ) is also normally distributed.
*   Mean: E[x̄ - ȳ] = μ_US - μ_Argentina
*   Variance: Var[x̄ - ȳ] = σ_US²/n + σ_Argentina²/m
*   Standard Deviation: √(σ_US²/n + σ_Argentina²/m)

**Test Statistic (t-statistic):**

*   Since population standard deviations (σ_US, σ_Argentina) are unknown, we use a t-statistic:

    `t = (x̄ - ȳ - (μ_US - μ_Argentina)) / √(s_x²/n + s_y²/m)`

    Under H0 (μ_US - μ_Argentina = 0):

    `t = (x̄ - ȳ) / √(s_x²/n + s_y²/m)`

*   This t-statistic follows a t-distribution. The degrees of freedom are calculated using a complex formula. Software packages can calculate this.

**Example Calculation:**

*   US: n = 10, x̄ = 68.442, s_x = 3.113
*   Argentina: m = 9, ȳ = 65.949, s_y = 3.106

*Software determined* Degrees of freedom (df) ≈ 16.8

*   **Right-Tailed Test:**

    *   H0: μ_US = μ_Argentina
    *   H1: μ_US > μ_Argentina
    *   α = 0.05 (significance level)
    *   Calculate t:
        `t = (68.442 - 65.949) / √((3.113)²/10 + (3.106)²/9) = 2.493 /  √((9.69)/10 + (9.65)/9) = 2.493 / √ (0.97 + 1.07) = 2.493 / √(2.04) = 2.493/1.428 = 1.7459`
    *   p-value = P(t > 1.7459 | df = 16.8) = 0.0495
    *   Decision: Reject H0 (since 0.0495 < 0.05).  Conclude that the population mean height in the US is greater than in Argentina.

*   **Two-Tailed Test:**

    *   H0: μ_US = μ_Argentina
    *   H1: μ_US ≠ μ_Argentina
    *   α = 0.05
    *   t = 1.7459 (same as above)
    *   p-value = 2 * P(t > 1.7459 | df = 16.8) = 2 * 0.0495 = 0.0991
    *   Decision: Do not reject H0 (since 0.0991 > 0.05).  Insufficient evidence to conclude that the population means are different.


# Paired Two-Sample t-Test

**Scenario:** Comparing two related samples (e.g., weight *before* and *after* a training program for the *same* individuals). The groups are *dependent*.

**Key Idea:** Analyze the *difference* between each pair of observations.

**1. Define the Difference:**

*   `D_i = X_i - Y_i`  where:
    *   `X_i`:  Observation for individual *i* in the first sample (e.g., weight before)
    *   `Y_i`:  Observation for the *same* individual *i* in the second sample (e.g., weight after)
*   Calculate the sample mean of the differences: `D̄ = (Σ D_i) / n`
*   Calculate the sample standard deviation of the differences: `s_D`

**2. Assumptions:**

*   The differences (D_i) are normally distributed.

**3. Hypotheses:**

*   **Null Hypothesis (H0):** μ_D = 0  (No average difference between the two conditions)
*   **Alternative Hypotheses (H1):**
    *   Right-tailed: μ_D > 0  (Average difference is positive)
    *   Left-tailed: μ_D < 0  (Average difference is negative)
    *   Two-tailed: μ_D ≠ 0  (Average difference is not zero)

**4. Test Statistic (t-statistic):**

*   `t = (D̄ - μ_D) / (s_D / √n)`
*   Under H0 (μ_D = 0):
    `t = D̄ / (s_D / √n)`
*   The t-statistic follows a t-distribution with `n - 1` degrees of freedom, where `n` is the number of *pairs* (which is also the number of observations in each sample).

**5. Procedure:**

1.  Calculate the differences `D_i`.
2.  Calculate the sample mean `D̄` and sample standard deviation `s_D` of the differences.
3.  Calculate the t-statistic.
4.  Determine the p-value based on the chosen alternative hypothesis (right, left, or two-tailed) and the t-distribution with `n - 1` degrees of freedom.
5.  Compare the p-value to the significance level (α).
6.  Make a decision (reject or fail to reject H0).

**Example (Weight Loss Program):**

*   Measurements: 10 weights before (X_i) and 10 weights after (Y_i).
*   Calculated differences: D_1, D_2, ..., D_10
*   D̄ = 1.09 (average weight loss)
*   s_D = 1.485 (standard deviation of the weight differences)

*   **Right-Tailed Test:**
    *   H0: μ_D = 0
    *   H1: μ_D > 0 (training program is effective for weight loss)
    *   α = 0.05
    *   `t = 1.09 / (1.485 / √10) = 1.09 / (1.485 / 3.162) = 1.09 / 0.469 = 2.321`
    *   df = 10 - 1 = 9
    *   p-value = P(t > 2.321 | df = 9) = 0.0227
    *   Decision: Reject H0 (since 0.0227 < 0.05). Conclude that the training program is effective for weight loss.

**Key Point:**

*   Once you calculate the differences (D_i), the paired t-test essentially becomes a one-sample t-test on the differences.  All the one-sample t-test results are applicable.  This simplifies the analysis.



# A/B Testing: Applying Two-Sample Hypothesis Testing

**A/B Testing Overview:**

*   A methodology for comparing two versions (A and B) of something (e.g., a web page design) to determine which performs better.
*   Involves:
    *   Proposing a variation (B) to test against a control (A).
    *   Randomly splitting subjects into two groups.
    *   Presenting each group with a different variation.
    *   Measuring outcomes using defined metrics (e.g., conversion rate, purchase amount).
    *   Using statistical tools (e.g., t-tests) to make a decision based on data.

**A/B Testing vs. T-tests:**

*   A/B testing is a broader methodology.  T-tests are statistical tools *used within* A/B testing.

**Example 1: Comparing Mean Purchase Amounts (Gaussian Assumption)**

*   **Goal:** Determine if a new "buy now" button placement (Strategy B) leads to higher purchase amounts.
*   **Design:**
    *   Group A (Control): 80 customers, average purchase $50, sample standard deviation $10
    *   Group B (Treatment): 20 customers, average purchase $55, sample standard deviation $15
*   **Hypotheses:**
    *   H0: μ_A = μ_B
    *   H1: μ_B > μ_A (Right-tailed test)
*   **Significance Level:** α = 0.05
*   **Assumption:** Purchase amounts follow a Gaussian distribution.
*   **Test:** Two-sample t-test (assuming independent samples).
*   **Results:**
    *   Degrees of freedom (df) ≈ 23.38
    *   Observed t-statistic = -1.414
    *   p-value = P(t < -1.414) = 0.085
    *   Decision: Do not reject H0 (since 0.085 > 0.05). Insufficient evidence to conclude that strategy B leads to higher purchase amounts.

**Example 2: Comparing Conversion Rates (Proportions)**

*   **Goal:** Determine if a new website design (Version B) has a higher conversion rate (proportion of visitors making a purchase).
*   **Design:**
    *   Group A (Control): 80 customers, 20 conversions (purchases)
    *   Group B (Treatment): 20 customers, 8 conversions
*   **Hypotheses:**
    *   H0: p_A = p_B (Conversion rates are the same)
    *   H1: p_B > p_A (Version B has a higher conversion rate) (Right-tailed test)
*   **Significance Level:** α = 0.05
*   **Distribution:** Conversions follow binomial distributions.
    *   Group A: Binomial(n_A, p_A)
    *   Group B: Binomial(n_B, p_B)
*   **Test Statistic:** Approximated using a normal distribution
  `p̂ = (X + Y)/(nA + nB)`
  `z = (x/nA - y/nB) / sqrt(p̂(1-p̂)(1/nA + 1/nB))`
*   **Results:**
    * Observed z-statistic = -1.336
    * p-value = P(z < -1.336) = 0.091
    * Decision: Do not reject H0 (since 0.091 > 0.05). Insufficient evidence to conclude that version B has a higher conversion rate.

**Key Concepts and Derivations (Conversion Rate Example):**

*   `x` = Number of conversions in Group A
*   `y` = Number of conversions in Group B
*   `n_A` = Number of visitors in Group A
*   `n_B` = Number of visitors in Group B
*   By the Law of Large Numbers: `x/n_A ≈ p_A` and `y/n_B ≈ p_B`
*   By the Central Limit Theorem: `x/n_A` and `y/n_B` are approximately normally distributed.
*   Therefore, `(x/n_A) - (y/n_B)` is also approximately normally distributed.
*   Mean of the difference: `μ = p_A - p_B`
*   Variance of the difference: `σ² = (p_A(1-p_A) / n_A) + (p_B(1-p_B) / n_B)`
*   Standardize the difference: `z = ((x/n_A) - (y/n_B) - (p_A - p_B)) / sqrt((p_A(1-p_A) / n_A) + (p_B(1-p_B) / n_B))`
*   Under H0 (p_A = p_B = p):  `z = ((x/n_A) - (y/n_B)) / sqrt(p(1-p) * (1/n_A + 1/n_B))`
*   Estimate `p` with `p̂ = (x + y) / (n_A + n_B)`
*   Final test statistic:
    `z = ((x/n_A) - (y/n_B)) / sqrt(p̂(1-p̂) * (1/n_A + 1/n_B))`

**A/B Testing - Key Takeaways:**

* A/B testing goes beyond the calculations and statistics. It’s a broader framework for decision-making.
* Understanding the underlying distributions (Gaussian, Binomial, etc.) is crucial for choosing the correct statistical test.
* The choice of metric (conversion rate, purchase amount) dictates the relevant statistical test.