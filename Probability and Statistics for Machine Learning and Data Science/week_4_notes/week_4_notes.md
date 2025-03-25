# Confidence Intervals Explained

*   **Problem:** Estimating population mean (mu) from samples when you can't measure everyone.
*   **Solution:** Confidence Intervals - range of values likely to contain the true population parameter (mu) with a specified degree of certainty.

## Analogy: Finding Lost Keys

*   **Key = True Population Mean (mu):** Unknown, but fixed location.
*   **Search Area = Confidence Interval:** Calculated range with lower & upper limits.
*   **Parking Spot (Best Guess) = Sample Mean:** Randomly generated starting point for the interval.  The randomness comes from the sample.
*   **Search Distance = Margin of Error:** Added on either side of the sample mean.
*   **Confidence Level:** Probability that the search will find the key. Bigger area, higher confidence, but wider interval.
*   **Important Note:** It's wrong to say "50% of keys fall inside the interval."  The key (mu) is fixed.  Instead, say "50% of *guesses* (sample means) are within a search distance of the key."

## Confidence Intervals with Probability Distributions

*   **Scenario:** Heights in Statistopia are normally distributed with unknown mean (mu) and *known* variance (sigma squared).  Later we'll handle unknown variance.
*   **Goal:** Estimate mu by taking a random sample.
*   **Simplified Case:** Sample size of one (n=1).
*   **X-bar (Sample Mean):**  The height of your one person, used to estimate population mean.  Has same mean as the population.
*   **Margin of Error & Confidence Level:**
    *   **Significance Level (alpha):** Probability sample mean is *outside* the margin of error (e.g., alpha = 0.05 is a common choice).
    *   **Confidence Level (1 - alpha):** Probability sample mean is *within* the margin of error (e.g., 1 - 0.05 = 0.95 or 95%).
    *   Set alpha, then increase the margins of error until (1-alpha)% of all sample means fall within the range.

## Confidence Interval Formula

*   **Confidence Interval = Sample Mean (x-bar)  +/-  Margin of Error**

## Interpretation

*   If your sample mean is within 95% of all sample means, then mu is close to your sample mean.

## Illustration

*   Repeatedly generate confidence intervals from different samples.
*   With a 95% confidence level, ~95% of those intervals will contain the *true* population mean (mu). The other 5% would not.
*   You only generate *one* interval in practice.  You don't know if it contains mu, but the *process* used to create it is reliable 95% of the time.


# Refining Confidence Intervals: Sample Size and Confidence Level

## Review: Sampling Distribution of the Sample Mean

*   **X-bar (Sampling Distribution):** Normally distributed with mean (mu) and standard deviation (sigma / sqrt(n)).
*   **E[X-bar] = mu:** The expected value of the sample mean *always* equals the population mean.
*   **Standard Deviation of X-bar (sigma_xbar):** sigma / sqrt(n). *Decreases* as sample size (n) increases.

## Impact of Sample Size (n)

*   **Increasing n:**
    *   Distribution of sample means becomes taller and narrower (less variance).
    *   Margin of error *shrinks*.
    *   Confidence interval *shrinks* (more precise estimate).
    *   Larger samples lead to greater accuracy.
*   **Constant Confidence Level:** Maintain confidence while getting a more precise result.

## Impact of Confidence Level

*   **Lower Confidence Level:** Smaller margins of error, narrower interval, but *lower* probability of capturing mu.
*   **Higher Confidence Level:** Larger margins of error, wider interval, *higher* probability of capturing mu.
*   **Tradeoff:** Higher confidence requires a larger interval.

## Key Takeaways

*   Confidence intervals are based on:
    *   Randomly generated sample mean
    *   Margin of error.
*   **Confidence Level:** Probability the interval contains mu (e.g., 95%).
*   **Ideal:** High confidence level AND narrow interval.
*   **Shrinking the Interval:**
    *   **Increase Sample Size (n):** Most straightforward way.  Reduces variance in the sampling distribution.
    *   **Lower Confidence Level:** Less desirable, rarely see levels below 90%.
*   **Next Steps:** Learn how to *calculate* the margin of error and, therefore, the confidence interval.


# Constructing Confidence Intervals: Calculating the Margin of Error

## Recap: Confidence Interval Components

*   **Sample Mean (x-bar):** Already known how to calculate.
*   **Margin of Error:**  The focus of this video.

## Scenario: Normally Distributed Population

*   Population (X):  Normally distributed with known mu and sigma squared.
*   Goal: Estimate mu.
*   Sample: Take a sample of size n and calculate x-bar.
*   X-bar Distribution: Normally distributed with mean mu and variance sigma squared / n.

## The Challenge

*   You don't know mu.
*   You only have x-bar and (assumed) sigma.

## Z-Scores and the Standard Normal Distribution

*   **Z-Score:** Number of standard deviations a point is from the mean.
*   **Standard Normal (Z-Distribution):** Mean = 0, Variance = 1.
    *   Can convert any normal distribution to standard normal: (X - mu) / sigma
*   **Critical Values:** Z-scores that cut off a specific percentage of the distribution.
    *   Example: For 95% confidence, the critical values are approximately -1.96 and 1.96.
*   **Finding Critical Values:** Use a lookup table or software library.

## Critical Value Notation

*   `z_{alpha/2}`:  Z-score with alpha/2 of the distribution to its *left*.
*   `z_{1 - alpha/2}`: Z-score with (1 - alpha/2) of the distribution to its *left*.

## Margin of Error Calculation

1.  **Standard Error:** Estimate of the standard deviation of the sample mean
    *   sigma / sqrt(n)  (population standard deviation divided by the square root of the sample size)

2.  **Margin of Error:**  `z_{1 - alpha/2}` * (sigma / sqrt(n))  (critical value times the standard error)

## Building the Confidence Interval

1.  You want to know the probability the true mean lands inside your confidence interval
2.  Starting Point:  P( -critical value <= (x-bar - mu) / (sigma / sqrt(n)) <= critical value)
3.  Manipulate the inequality (subtract x-bar, multiply by -1) to isolate mu in the middle. This will yield the formula to obtain your upper and lower bounds.

## Final Confidence Interval

*   **Confidence Interval = x-bar  +/-  Margin of Error**

## Central Limit Theorem to the Rescue

*   What if the population is *not* normally distributed?
*   **Central Limit Theorem (CLT):** If n is large enough, the distribution of x-bar will *still* be approximately normal, even if the population isn't.
*   Therefore, the confidence interval construction method still works if n is large enough.

# Calculation Steps for Confidence Intervals

1.  **Calculate Sample Mean (x-bar):** Average of your sample data.
2.  **Define Desired Confidence Level (1 - alpha):** e.g., 95%
3.  **Find Critical Value:** The z-score corresponding to the confidence level.  (e.g., for 95%, z = 1.96). Denoted `z_{1 - alpha/2}`
4.  **Find Standard Error (SE):**  Standard deviation of the sampling distribution of the sample mean.
    *   SE = sigma / sqrt(n) (Population standard deviation divided by the square root of the sample size)
5.  **Calculate Margin of Error (ME):**
    *   ME = Critical Value * Standard Error  (`z_{1 - alpha/2}` * SE)
6.  **Construct Confidence Interval:**
    *   Lower Limit: x-bar - ME
    *   Upper Limit: x-bar + ME

## Assumptions for Using This Method

1.  **Random Sample:** The sample must be randomly selected from the population.
2.  **Sample Size:**
    *   n > 30 (sample size is greater than 30)
    *   OR
    *   The population is approximately normally distributed.


# Example: Calculating a Confidence Interval for Statistopia Heights

## Scenario

*   Estimating average height of the world's population (general example). The true mean may be different than the sample mean.
*   Specific example: Estimating average height of 6,000 adults on Statistopia.
*   Sample: Randomly selected 49 adults (n = 49).
*   Sample Mean: 170 cm (1 meter, 70 centimeters).
*   Population Standard Deviation (sigma): 25 cm.
*   Desired Confidence Level: 95%.

## Calculation

1.  **Critical Value (z_{1 - alpha/2}):** 1.96 (for 95% confidence).
2.  **Margin of Error (ME):**
    *   ME = `z_{1 - alpha/2}` * (sigma / sqrt(n))
    *   ME = 1.96 * (25 / sqrt(49))
    *   ME = 1.96 * (25 / 7)
    *   ME = 1.96 * 3.57
    *   ME = 7 cm

3.  **Confidence Interval:**
    *   Lower Limit: x-bar - ME = 170 cm - 7 cm = 163 cm
    *   Upper Limit: x-bar + ME = 170 cm + 7 cm = 177 cm

## Conclusion

*   95% confidence interval for the average height of adults on Statistopia:  **163 cm to 177 cm.**


# Determining Sample Size for a Desired Margin of Error

## Problem

*   Previous example: 95% CI with margin of error of 7 cm.  Want a *smaller* margin of error (e.g., 3 cm).
*   Question: What sample size (n) is needed to achieve this desired margin of error?

## Setup

*   Goal: Margin of Error <= 3 cm
*   Known: `z_{1 - alpha/2}` = 1.96 (for 95% confidence), sigma = 25 cm

## Calculation

1.  **Start with Margin of Error Formula:**
    *   ME = `z_{1 - alpha/2}` * (sigma / sqrt(n))

2.  **Substitute and Solve for n:**
    *   3 >= 1.96 * (25 / sqrt(n))  (ME is the *maximum* allowable, so we want it less than or equal to 3)
    *   sqrt(n) >= (1.96 * 25) / 3
    *   n >= ((1.96 * 25) / 3)^2
    *   n >= 266.777...

3.  **Round Up:**
    *   n = 267 (since we need a whole number of people)

## Conclusion

*   A sample size of at least **267** adults is required to achieve a margin of error of 3 cm with 95% confidence.

## General Formula for Sample Size

*   Let `moe` represent the desired margin of error.

*   **Formula:**
    *   n >= (`z_{1 - alpha/2}` * sigma / moe)^2


# Misinterpretations of Confidence Intervals

## Common Incorrect Interpretation

*   "There is a 95% probability that the population parameter falls within *this* confidence interval."  **INCORRECT**

## Correct Interpretation (and Why the Other is Wrong)

*   "This confidence interval was constructed using a method that contains the true population parameter 95% of the time, across *repeated* sampling."

## Key Difference: Fixed vs. Random

*   **Population Parameter (mu):**
    *   Fixed but unknown value.
    *   *Does not* have a probability distribution.  It's a single, unchanging value.
    *   For a given interval, mu *either is or is not* within it.  It doesn't "fall" within it with a certain probability.
*   **Sample Mean (x-bar):**
    *   Has a probability distribution (the sampling distribution).
    *   *Varies* depending on the sample taken.
    *   The concept of the confidence interval is tied to the randomness of the sample mean.

## Explaining the 95% Confidence Level

*   The 95% confidence level refers to the *process* of constructing the interval, not to any *specific* interval.
*   If you repeat the sampling experiment many times, generating a different confidence interval each time, 95% of those intervals will contain the true population mean.
*   The confidence level is the success rate of the interval construction method.

## In Simple Terms

*   You can't say the population mean has a 95% chance of being in your interval because your true mean is either within your interval or it is not. Your true mean isn't moving around like a random variable. The confidence percentage refers to the likelihood of your method of gathering a sample and computing the interval will yield an interval that actually contains the population mean.


# Confidence Intervals with Unknown Population Standard Deviation (sigma): Introducing the t-Distribution

## The Problem

*   Previous methods assumed knowledge of population standard deviation (sigma).
*   Often, sigma is *unknown*.

## Solution: Use Sample Standard Deviation (s) and the t-Distribution

1.  **Replace sigma with s:**
    *   Use the sample standard deviation (s) in the formula (calculated from your sample).

2.  **Sampling Distribution Changes:**
    *   The quantity (x-bar - mu) / (s / sqrt(n)) no longer follows a normal distribution.
    *   It follows the **Student's t-Distribution**.

## Characteristics of the t-Distribution

*   Similar to normal distribution, but with **fatter tails**.
*   **Fatter tails:** Means more probability in the extremes (outliers).  Sampling from the t-distribution is more likely to give you results far from the center compared to the normal distribution.

## Adjusting for the t-Distribution

*   The scaling factor (critical value) from the normal distribution (z-score) is no longer appropriate.

*   **Use t-Scores:**
    *   Replace the z-score with a **t-score**.
    *   Use t-scores appropriate for the t-distribution.

## Confidence Interval Formulas Compared

*   **Known sigma:**  x-bar +/-  `z_{1 - alpha/2}` * (sigma / sqrt(n))
*   **Unknown sigma:**  x-bar +/-  `t_{1 - alpha/2, df}` * (s / sqrt(n))
    *   `t_{1 - alpha/2, df}` represents the t-score.
    *   `df` stands for degrees of freedom.

## Degrees of Freedom (df)

*   Each t-distribution is defined by its degrees of freedom.
*   **Formula:** df = n - 1 (sample size minus 1)

## Effect of Degrees of Freedom on the t-Distribution

*   Low df (e.g., df = 1):  Fatter tails, more variability.
*   Higher df (e.g., df = 10): Tails become smaller, distribution approaches a normal distribution.
*   As n increases, s becomes a better estimate of sigma, and the t-distribution approaches the normal distribution. As such, the scaling factor in the student's t is always bigger or equal to the scaling factor in the normal distribution because the student's t has higher tails than the normal distribution.


# Confidence Intervals for Proportions

## The Shift

*   Previous lesson: Confidence intervals for sample *means* (e.g., average height).
*   This lesson: Confidence intervals for *proportions* (e.g., proportion of adults owning a car).

## Example Problem

*   Goal: Estimate the proportion of adults in Statistopia who own a car.
*   Sample: n = 30 adults.
*   Result: x = 24 adults own a car.
*   Sample Proportion (p-hat): 24 / 30 = 0.80 (80%).

## Confidence Interval Formula

*   Confidence Interval = p-hat +/- Margin of Error

## Calculating the Margin of Error (Key Difference)

*   **Margin of Error = Critical Value * Standard Error**

*   The critical value is still found based on the given confidence (e.g., z-score = 1.96 for 95% confidence). The main difference lies in the standard error.

*   **Standard Error for Proportions:** sqrt( (p-hat * (1 - p-hat)) / n )

## Summary of Formulas

*   Margin of Error = `z_{1 - alpha/2}` * sqrt( (p-hat * (1 - p-hat)) / n )

## Back to the Example

*   p-hat = 0.80
*   n = 30
*   95% Confidence => `z_{1 - alpha/2}` = 1.96

1.  **Calculate Standard Error:**
    *   sqrt( (0.80 * (1 - 0.80)) / 30 ) = sqrt( (0.80 * 0.20) / 30 ) = sqrt(0.16 / 30) = sqrt(0.005333) = 0.073
2.  **Calculate Margin of Error:**
    *   1.96 * 0.073 = 0.14

3.  **Construct Confidence Interval:**
    *   Lower Limit: 0.80 - 0.14 = 0.66
    *   Upper Limit: 0.80 + 0.14 = 0.94

## Conclusion

*   95% confident that the true population proportion of adults in Statistopia who own a car is between **66% and 94%.**