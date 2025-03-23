# Table of Contents

1.  [Estimation: Point Estimation & Maximum Likelihood Estimation (MLE)](#estimation-point-estimation--maximum-likelihood-estimation-mle)
    *   [Topic Overview](#topic-overview)
2.  [Maximum Likelihood Estimation (MLE): In Detail](#maximum-likelihood-estimation-mle-in-detail)
    *   [Core Idea](#core-idea)
    *   [Analogy: Popcorn on the Floor](#analogy-popcorn-on-the-floor)
    *   [Formal Concept](#formal-concept)
    *   [Connection to Machine Learning](#connection-to-machine-learning)
    *   [Why Does Linear Regression Fit In Here?](#why-does-linear-regression-fit-in-here)
3.  [MLE Example: Coin Toss](#mle-example-coin-toss)
    *   [Scenario](#scenario)
    *   [Step 1: Initial Coin Selection (Discrete Choice)](#step-1-initial-coin-selection-discrete-choice)
    *   [MLE Conclusion (Discrete Choice)](#mle-conclusion-discrete-choice)
    *   [Step 2: Finding the Best Coin (Continuous Optimization)](#step-2-finding-the-best-coin-continuous-optimization)
    *   [Mathematical Optimization](#mathematical-optimization)
    *   [MLE Conclusion (Continuous Optimization)](#mle-conclusion-continuous-optimization)
    *   [General Case](#general-case)
4.  [MLE Example: Gaussian Distribution](#mle-example-gaussian-distribution)
    *   [Scenario](#scenario-1)
    *   [Step 1: Choosing Between Two Distributions](#step-1-choosing-between-two-distributions)
    *   [Step 2: Selecting the Mean](#step-2-selecting-the-mean)
    *   [Step 3: Selecting the Standard Deviation](#step-3-selecting-the-standard-deviation)
    *   [Key Insights](#key-insights)
5.  [MLE for Gaussian Population: Derivation](#mle-for-gaussian-population-derivation)
    *   [Mathematical Formulation](#mathematical-formulation)
    *   [Likelihood Function](#likelihood-function)
    *   [Log-Likelihood Function](#log-likelihood-function)
    *   [Finding the MLE](#finding-the-mle)
    *   [Comparison to Sample Standard Deviation](#comparison-to-sample-standard-deviation)
    *   [Important Note](#important-note)
    *   [Example: Heights of 18-Year-Olds](#example-heights-of-18-year-olds)
6.  [MLE and Linear Regression](#mle-and-linear-regression)
    *   [Recap: MLE in Machine Learning](#recap-mle-in-machine-learning)
    *   [Linear Regression Example](#linear-regression-example)
    *   [How a Line "Generates" Points (Probabilistically)](#how-a-line-generates-points-probabilistically)
    *   [Mathematical Derivation](#mathematical-derivation-1)
    *   [Conclusion](#conclusion)
7.  [Regularization: Avoiding Overfitting](#regularization-avoiding-overfitting)
    *   [Scenario](#scenario-2)
    *   [Overfitting](#overfitting)
    *   [Example](#example-1)
    *   [Regularization (L2 Regularization)](#regularization-l2-regularization)
    *   [Equation](#equation)
    *   [Regularized Error](#regularized-error)
8.  [Beyond MLE: Considering Prior Probabilities](#beyond-mle-considering-prior-probabilities)
    *   [Limitation of MLE](#limitation-of-mle)
    *   [Example: Popcorn on the Floor (Revised)](#example-popcorn-on-the-floor-revised)
    *   [The Problem](#the-problem)
    *   [Bayesian Approach](#bayesian-approach)
9.  [Frequentist vs. Bayesian Approaches to Probability](#frequentist-vs-bayesian-approaches-to-probability)
    *   [Fundamental Difference](#fundamental-difference)
    *   [Story](#story)
    *   [Key Differences](#key-differences)
    *   [Prior Beliefs (The "Prior")](#prior-beliefs-the-prior)
    *   [So Far (MLE)](#so-far-mle)
10. [The Impact of Prior Beliefs on Bayesian Inference](#the-impact-of-prior-beliefs-on-bayesian-inference)
    *   [Scenario](#scenario-3)
    *   [Difference](#difference)
    *   [Experiment](#experiment-1)
    *   [Impact on Beliefs](#impact-on-beliefs)
    *   [Key Concepts](#key-concepts)
    *   [Coin Toss MAP Estimations](#coin-toss-map-estimations)
    *   [Important Implications](#important-implications)
11. [Performing Bayesian Updates: Bayes' Theorem](#performing-bayesian-updates-bayes-theorem)
    *   [Core Idea](#core-idea-1)
    *   [Bayes' Theorem (General Form)](#bayes-theorem-general-form)
    *   [Bayesian Coin Example](#bayesian-coin-example)
    *   [Generalized Notation (PMFs)](#generalized-notation-pmfs)
    *   [Four Cases (Discrete/Continuous Variables)](#four-cases-discretecontinuous-variables)
    *   [Replacing Y with Θ (Parameter)](#replacing-y-with-θ-parameter)
12. [Bayesian Statistics: A Complete Example & Key Concepts](#bayesian-statistics-a-complete-example--key-concepts)
    *   [1. The Bayesian Framework: Updating Beliefs](#1-the-bayesian-framework-updating-beliefs)
    *   [2. Choosing Priors](#2-choosing-priors)
    *   [3. Calculating the Posterior](#3-calculating-the-posterior)
    *   [4. MAP Estimate (Maximum A Posteriori)](#4-map-estimate-maximum-a-posteriori)
    *   [5. Bayesian vs. Frequentist: Key Differences](#5-bayesian-vs-frequentist-key-differences)
    *   [6. Impact of Data & Convergence](#6-impact-of-data--convergence)
    *   [7. When to Use Bayesian Methods](#7-when-to-use-bayesian-methods)
    *   [8. Potential Downsides](#8-potential-downsides)
13. [Combining Maximum Likelihood, MAP Estimation, and Regularization](#combining-maximum-likelihood-map-estimation-and-regularization)
    *   [1. Model Selection and Probability](#1-model-selection-and-probability)
    *   [2. Connecting MLE, Regression, and Regularization](#2-connecting-mle-regression-and-regularization)
    *   [3. Mathematical Equivalence: From Products to Sums](#3-mathematical-equivalence-from-products-to-sums)
    *   [4. Likelihood of a Model](#4-likelihood-of-a-model)
    *   [5. Putting It All Together](#5-putting-it-all-together)
    *   [6. Conclusion](#6-conclusion)

## Estimation: Point Estimation & Maximum Likelihood Estimation (MLE)

**Key Concept:** Estimation is fundamental to statistics and used in many machine learning algorithms

**Topic Overview:**

*   **Point Estimation:** Estimating a population parameter (e.g., mean, variance) with a single value (a "point").
*   **Maximum Likelihood Estimation (MLE):** A common and widely used method for point estimation. It's the main focus of this lesson.
*   **Maximum a Posteriori (MAP) Estimation:** A Bayesian generalization of MLE using Bayes' theorem. The MAP estimator can be thought of as a regularization of an MLE estimator, where regularization is a commonly used method in machine learning to prevent overfitting.


## Maximum Likelihood Estimation (MLE): In Detail

**Core Idea:** Find the scenario (or model) that *most likely* generated the observed data (evidence).  Maximize the *likelihood* of the data given the model.

**Analogy: Popcorn on the Floor**

*   **Evidence:** Popcorn on the floor.
*   **Possible Scenarios:** Watching a movie, playing board games, taking a nap.
*   **MLE:** Infer that watching a movie is the most likely scenario because it maximizes the probability of finding popcorn on the floor.

**Formal Concept:**

*   Maximize the conditional probability: P(Data | Model)
*   Choose the model that makes the observed data most probable.

**Connection to Machine Learning:**

*   You have data and several models that *could* have generated that data.
*   MLE selects the model that gives the *highest probability* of seeing that data.

**Why Does Linear Regression Fit In Here?**
In order to perform linear regression, one would seek to estimate a linear function that most accurately describes the data points.


## MLE Example: Coin Toss

**Scenario:**

*   Toss a coin 10 times.
*   Result: 8 Heads, 2 Tails.
*   Goal: Estimate the probability of the coin landing on heads (P).

**Step 1: Initial Coin Selection (Discrete Choice)**

*   **Coin 1:** P(Heads) = 0.7
*   **Coin 2:** P(Heads) = 0.5 (Fair Coin)
*   **Coin 3:** P(Heads) = 0.3

Calculate the probability of getting 8 Heads and 2 Tails *given* each coin:

*   P(8H, 2T | Coin 1) = (0.7)⁸ * (0.3)² = 0.0051
*   P(8H, 2T | Coin 2) = (0.5)¹⁰ = 0.0010
*   P(8H, 2T | Coin 3) = (0.3)⁸ * (0.7)² = 0.00003

**MLE Conclusion (Discrete Choice):** Coin 1 is the most likely because it maximizes the probability of seeing 8 Heads and 2 Tails.

**Step 2: Finding the Best Coin (Continuous Optimization)**

*   Assume the coin has a probability 'P' of landing on heads.
*   The probability of 8 Heads and 2 Tails is P⁸ * (1 - P)².
*   Goal: Find the value of 'P' that maximizes this likelihood.

**Mathematical Optimization:**

1.  **Log-Likelihood:** Take the logarithm to simplify calculations (convert product to sum):
    *   log(Likelihood) = 8 * log(P) + 2 * log(1 - P)

2.  **Derivative:** Find the derivative of the log-likelihood with respect to P:
    *   d(log(Likelihood))/dP = 8/P - 2/(1 - P)

3.  **Set to Zero and Solve:** Set the derivative to zero and solve for P:
    *   8/P - 2/(1 - P) = 0  =>  P̂ = 8/10 = 0.8

**MLE Conclusion (Continuous Optimization):** The best estimate for the probability of heads is 0.8 (80%). This is because the data has 8 heads and 2 tails.

**General Case**
Let's say you have n coins and k heads and each coin is a Bernoulli variable with parameter P

Then you can take derivative and set to 0 in order to find the optimal value, which is P hat= k/n

**Key Idea:** MLE tries to *maximize the likelihood function*.


## MLE Example: Gaussian Distribution

**Scenario:**

*   Observations: 1 and -1 (two data points)
*   Goal: Estimate the parameters (mean and standard deviation) of the normal distribution that most likely generated these observations.

**Step 1: Choosing Between Two Distributions**

*   **Distribution 1:** Normal with mean 10, standard deviation 1
*   **Distribution 2:** Normal with mean 2, standard deviation 1

The gaussian with mean 2 has a higher likelihood for producing 1 and -1 as points, so it is more likely

**Step 2: Selecting the Mean**

Compare three Gaussian distributions with different means:

*   Gaussian with Mean -1
*   Gaussian with Mean 0
*   Gaussian with Mean 1

**The gaussian with mean 0 is most likely**. The best mean is going to be mean of the data, which in this case is 0

**Step 3: Selecting the Standard Deviation**

Compare three Gaussian distributions with different standard deviations, all with mean 0:

*   Gaussian with Standard Deviation 0.5
*   Gaussian with Standard Deviation 1
*   Gaussian with Standard Deviation 2

Gaussian with mean 0 and standard deviation 1 is the most likely to have generated that data. The variance of the distribution matches with the observations (1)

**Key Insights:**

*   **MLE chooses the distribution that maximizes the likelihood of the observed data.**
*   With a Gaussian distribution, MLE tends to select parameters that align with the data's statistics (mean and variance)
* This is an important concept to understand because MLE is often used to solve for the parameters of a distribution for machine learning problems.


## MLE for Gaussian Population: Derivation

This document outlines the mathematical derivation of Maximum Likelihood Estimation (MLE) for the mean (μ) and variance (σ²) of a Gaussian distribution.

**Mathematical Formulation**

*   Suppose you have *n* i.i.d. samples **X** = (X₁, X₂, …, Xₙ) from a Gaussian distribution:  Xᵢ ∼ᵢ.ᵢ.₀ N(μ, σ²).
*   Goal: Find the MLE for μ and σ.

**Likelihood Function**

*   The likelihood function, given a realization of **X** as **x** = (x₁, x₂, …, xₙ), is:

    L(μ, σ; **x**) = ∏ᵢ₌₁ⁿ fₓᵢ(xᵢ)

*   Since Xᵢ are Gaussian:

    L(μ, σ; **x**) = ∏ᵢ₌₁ⁿ [1/(√(2π)σ)] * exp[-1/2 * ((xᵢ - μ)² / σ²)]

    L(μ, σ; **x**) = [1/(√(2π)ⁿσⁿ)] * exp[-1/2 * (∑ᵢ₌₁ⁿ (xᵢ - μ)² / σ²)]

**Log-Likelihood Function**

*   Maximizing the likelihood is equivalent to maximizing its logarithm (log-likelihood), which simplifies calculations.
*   The log-likelihood function is:

    ℓ(μ, σ) = log(L(μ, σ; **x**))

*   Using logarithm properties (log(a*b) = log(a) + log(b); log(1/a) = -log(a); log(aᵏ) = k*log(a)):

    ℓ(μ, σ) = -n/2 * log(2π) - n * log(σ) - 1/(2σ²) * ∑ᵢ₌₁ⁿ (xᵢ - μ)²

**Finding the MLE**

1.  **Partial Derivatives:**  Take partial derivatives of the log-likelihood with respect to μ and σ and set them equal to zero.

2.  **Partial Derivative with respect to μ:**

    ∂ℓ(μ, σ) / ∂μ = (1/σ²) * (∑ᵢ₌₁ⁿ xᵢ - nμ)

    Setting to zero:  (1/σ²) * (∑ᵢ₌₁ⁿ xᵢ - nμ) = 0

    MLE for μ:  **μ̂ = (∑ᵢ₌₁ⁿ xᵢ) / n = x̄** (the sample mean)

3.  **Partial Derivative with respect to σ:**

    ∂ℓ(μ, σ) / ∂σ = -n/σ + (∑ᵢ₌₁ⁿ (xᵢ - μ)²) / σ³

    Setting to zero:  -n/σ + (∑ᵢ₌₁ⁿ (xᵢ - μ)²) / σ³ = 0

    Replacing μ with its MLE estimate μ̂=x̄

     -n/σ + (∑ᵢ₌₁ⁿ (xᵢ - x̄)²) / σ³ = 0

    MLE for σ²: **σ̂² = (∑ᵢ₌₁ⁿ (xᵢ - x̄)²) / n**

    MLE for σ:  **σ̂ = √[(∑ᵢ₌₁ⁿ (xᵢ - x̄)²) / n]**

**Comparison to Sample Standard Deviation**

*   The MLE for the standard deviation (σ̂) is similar to the sample standard deviation.
*   The difference lies in the normalizing constant:
    *   MLE uses 1/n
    *   Sample standard deviation uses 1/(n-1) (for an unbiased estimate)

**Important Note:**

*   The derivation above finds the *critical points*. A complete proof would require showing that these points are *maximums*.

**Example: Heights of 18-Year-Olds**

*   Suppose you have the following 10 height measurements (in inches):
    66.75, 70.24, 67.19, 67.09, 63.65, 64.64, 69.81, 69.79, 73.52, 71.74

*   MLE Estimation:

    μ̂ = (66.75 + 70.24 + ... + 71.74) / 10 = 68.442

   σ̂ = √[((66.75-68.442)² + (70.24-68.442)² + ... + (71.74 - 68.442)²)/10] = 2.954


## MLE and Linear Regression

**Recap: MLE in Machine Learning**

*   Goal: Find the model that *most likely* generated the data.
*   Method: Calculate P(Data | Model) for each model and choose the one with the highest probability.

**Linear Regression Example:**

1.  **Data:** Set of points (x, y).
2.  **Models:** Different lines (y = mx + b) that could fit the data.

**How a Line "Generates" Points (Probabilistically):**

*   Imagine a line as a "road." Points are like "houses" built near the road.
*   For each x value:
    *   Find the corresponding y value on the line (y = mx + b).
    *   Center a Gaussian distribution vertically at that (x,y) point.
    *   The observed data point is assumed to be a sample from that Gaussian. Points closer to the line are more likely.

**Mathematical Derivation:**

*   Assume the Gaussian has a standard deviation of 1 and mean = 0.
*   Likelihood of Generating One Point:  Given by the Gaussian PDF.
    *   Likelihood ∝ exp(-1/2 * d²) , where 'd' is the vertical distance from the point to the line.

*   Total Likelihood (for n points): Since they're independent, multiply individual likelihoods.

    *   Likelihood ∝ ∏ᵢ₌₁ⁿ exp(-1/2 * dᵢ²)
    *   Likelihood ∝ exp(-1/2 * ∑ᵢ₌₁ⁿ dᵢ²)

*   Maximizing the likelihood is equivalent to maximizing the logarithm:

    *   Maximizing log(Likelihood) is equivalent to *minimizing* ∑ᵢ₌₁ⁿ dᵢ² (the sum of squared distances).

**Conclusion:**

*   Finding the line that *most likely* produced the points using MLE is the *same* as minimizing the least squares error in linear regression.
*   **Linear Regression is a Maximum Likelihood Estimator!**
    *   Linear regression finds the line that is most likely to have generated the data given the assumptions of the data.


## Regularization: Avoiding Overfitting

**Scenario:**

*   Goal:  Find a model that fits the data well but also *generalizes* well to new data.  Avoid overfitting.

**Overfitting:**

*   A model that fits the training data *too* closely may not generalize well. It captures noise in the data.

**Example:**

1.  **Data:** Some scattered points.

2.  **Models:**
    *   Model 1: Linear (Underfits)
    *   Model 2: Quadratic (Good Fit)
    *   Model 3: 10th-degree Polynomial (Overfits)

3.  **Initial Evaluation (Loss):** Model 3 has the lowest loss (fits the data best).

4.  **Problem:** Model 3 is too complex and may not generalize.

**Regularization (L2 Regularization):**

*   Add a penalty term to the loss function based on model complexity.
*   The more complex the model, the higher the penalty.

**Equation:**

*   Let the polynomial have the equation y= ax^(n) + bx^(n-1).....+c
*   L2 Penalty = Sum of squares of all the polynomial coefficients (excluding the constant term "c").

**Regularized Error:**

*   The regularized error is the Log Loss plus the regularization parameter (Lambda) times the L_2 Regularization Error


## Beyond MLE: Considering Prior Probabilities

**Limitation of MLE:**

*   MLE only considers the likelihood of the data *given* the model (P(Data | Model)).
*   It doesn't account for the prior probability of the model itself (P(Model)).

**Example: Popcorn on the Floor (Revised)**

1.  **Evidence:** Popcorn on the floor.

2.  **Scenarios:**
    *   Watching Movies (high P(Popcorn | Movies))
    *   Popcorn Throwing Contest (very high P(Popcorn | Contest))

3.  **The Problem:** MLE would likely choose the contest due to its extremely high likelihood of producing popcorn.

4.  **The Missing Piece:** The probability of the scenario *itself* (before seeing any popcorn).
    *   P(Movies) is high. It's common to watch movies.
    *   P(Contest) is very low. Popcorn throwing contests are rare.

**Bayesian Approach:**

*   Consider the *joint probability* of the scenario *and* the evidence: P(Scenario and Popcorn).
*   Maximize P(Scenario and Popcorn) = P(Popcorn | Scenario) * P(Scenario)
*   This incorporates both the likelihood and the prior probability of the scenario.


## Frequentist vs. Bayesian Approaches to Probability

**Fundamental Difference:** The interpretation of probabilities.

**Story:** A frequentist and a Bayesian find a coin and want to estimate the probability of heads.

*   **Experiment:** Toss the coin 10 times, get 8 heads and 2 tails.

*   **Frequentist:** Probability of heads = 8/10 = 0.8 (based solely on observed frequency).

*   **Bayesian:** Reflects on prior experience, knowing coins are *usually* fair (P(Heads) ≈ 0.5).  Adjusts their belief based on the data, but not drastically, perhaps estimating around 0.52, as this is the average of prior belief and the new evidence

**Key Differences:**

| Feature          | Frequentist                                      | Bayesian                                        |
| :---------------- | :----------------------------------------------- | :---------------------------------------------- |
| Probability       | Long-term frequency of events                  | Degree of belief/certainty                      |
| Prior Beliefs    | No concept of prior beliefs                      | Incorporates prior beliefs (the "prior")        |
| Goal              | Find the model maximizing likelihood of data    | Update prior beliefs based on observations      |

**Prior Beliefs (The "Prior"):**

*   Represents the statistician's initial belief about the model *before* seeing the data.
*   Bayesians use priors to evaluate data, while frequentists don't.
*   If strong evidence contradicts the prior, Bayesians will adjust their belief, but often not completely discarding the prior.

**So Far (MLE):**

*   All point estimation methods seen so far (including MLE) are *frequentist* approaches.


## The Impact of Prior Beliefs on Bayesian Inference

**Scenario:** Three Bayesians want to estimate the probability of a coin landing heads.

**Difference:** They have different prior beliefs about the fairness of the coin.

1.  **Conservative Bayesian:** Strong belief that the coin is fair (prior tightly centered around 0.5).

2.  **Moderate Bayesian:** Believes the coin *should* be fair but is open to the possibility of bias (prior peaked at 0.5, but more spread out).

3.  **Uninformed Bayesian:** Doesn't want to assume anything, assigns equal weight to all possible values (non-informative prior).

**Experiment:** Each Bayesian observes the same data: 8 Heads, 2 Tails.

**Impact on Beliefs:**

*   **Conservative Bayesian:** Barely shifts their belief. Remains strongly convinced the coin is near fair.

*   **Moderate Bayesian:** Updates belief somewhat, shifting towards a higher probability of heads, and also narrows the distribution of belief.

*   **Uninformed Bayesian:** Changes belief significantly, becoming relatively sure the probability of heads is around 0.8.

**Key Concepts:**

*   **Posterior Beliefs:** Updated beliefs *after* seeing the data.

*   **Maximum a Posteriori (MAP) Estimation:** Chooses the value with the *highest probability* in the posterior distribution (the mode of the posterior).

**Coin Toss MAP Estimations:**

*   **Conservative Bayesian:** MAP estimate ≈ 0.501 (remains near the prior).

*   **Moderate Bayesian:** MAP estimate ≈ 0.607 (shifts significantly but not extremely).

*   **Uninformed Bayesian:** MAP estimate ≈ 0.8 (same as the frequentist result).

**Important Implications:**

*   Prior beliefs *strongly* influence the final estimate in Bayesian inference.
*   Using a non-informative prior leads to the *same* result as a frequentist approach (MLE).
*   The strength of the influence of the prior on the posteriors diminishes with larger datasets.
*  Therefore, if you do not have any meaningful beliefs when doing MAP then you are basically doing frequency statistics


## Performing Bayesian Updates: Bayes' Theorem

**Core Idea:** Use Bayes' Theorem to update prior beliefs based on new evidence.

**Bayes' Theorem (General Form):**

P(A | B) = [P(B | A) * P(A)] / P(B)

*   P(A | B):  Posterior probability of event A given event B (evidence). What we're trying to find.
*   P(B | A):  Likelihood of evidence B given event A.
*   P(A): Prior probability of event A (belief *before* seeing evidence B).
*   P(B): Probability of evidence B appearing at all.  Often calculated as P(B) = P(B | A)P(A) + P(B | not A)P(not A).

**Bayesian Coin Example:**

1.  **Mystery Coin:** Either Fair (P(Heads) = 0.5) or Biased (P(Heads) = 0.8).
2.  **Prior Beliefs:** P(Fair Coin) = 0.75, P(Biased Coin) = 0.25
3.  **Evidence:** Flip the coin once, result is Heads (X = 1).

**Variables:**

*   Y: Type of coin (Fair or Biased). Y takes values 0.5 and 0.8
*   X: Result of flip (0 for Tails, 1 for Heads).

**Updating Beliefs (Finding Posterior):**
What is the probability that the coin is fair given that we did one flip to heads?

P(Fair | Heads) = [P(Heads | Fair) * P(Fair)] / P(Heads)

1. P(Heads | Fair)
= 0.5
2. P(Fair)=.75
3. P(Heads)= P(Heads | Fair)+P(Heads | Bias) which is just 0.575

P(Fair | Heads) =  =0.652

*   The probability of 0.652 is our new posterior, the update of belief in the
previous value.
* If we used to think there was a 75 change coin was fair now we believe 65 after flipping heads.

**Generalized Notation (PMFs):**

For discrete random variables X and Y,

P(Y = y | X = x) = [P(X = x | Y = y) * P(Y = y)] / P(X = x)

**Four Cases (Discrete/Continuous Variables):**

The equation varies depending on if X and Y are descrete or continuous

**Replacing Y with Θ (Parameter):**

*   In machine learning, often used to estimate the parameters of a model (Θ).
*   Just replace "Y" with "Θ" in the above equations.

**In summary, Bayes theorem provides a systematic to update from existing beliefs given evidence of new data**


# Bayesian Statistics: A Complete Example & Key Concepts

This note summarizes the key points from the video, focusing on a worked example of Bayesian updating and contrasting it with frequentist approaches.

## 1. The Bayesian Framework: Updating Beliefs

*   **Goal:**  Learn about the probability density function (PDF) of a parameter (e.g., probability of heads on a coin), represented by a random variable *theta*.
*   **Bayes' Theorem:**  Used to update prior beliefs given observed data.  Specifically, the version of Bayes' theorem for continuous parameters and discrete data is used.
    *   `Posterior ∝ Likelihood * Prior`
*   **Data Representation:** Data is represented as a random variable *x*, which contains individual observations *x<sub>i</sub>*. The likelihood is the probability of observing the data *x*, given a specific value of theta.
*   **Example: Coin Flips**
    *   *x<sub>i</sub>*: Each coin flip (1 for heads, 0 for tails), modeled as a Bernoulli distribution given theta.
    *   *Likelihood*:  The probability of observing a specific sequence of heads and tails given a particular value of *theta*. The flips are assumed to be independent so the joint probability is simply the product of the individual probabilities.
*   **Iterative Updating:** The core process of Bayesian statistics.
    1.  Start with a **prior** (PDF) about *theta*.
    2.  Collect **data**.
    3.  Calculate the **likelihood** of the data given *theta*.
    4.  Compute the **posterior** distribution using Bayes' Theorem.
    5.  The posterior becomes the new prior for the next iteration.

## 2. Choosing Priors

*   **Prior:** Your initial belief about the parameter *theta* before seeing any data. Expressed as a PDF.
*   **Uninformative Prior:**  Represents a lack of prior knowledge.  A uniform distribution is often used (every value of theta between 0 and 1 is equally likely).
*   **Informative Prior:**  Reflects existing knowledge or beliefs about *theta*.  Choice significantly influences the posterior, especially with limited data.

## 3. Calculating the Posterior

*   **Posterior:**  The updated belief about *theta* after incorporating the data. A conditional PDF of theta given the observed data.
*   **Ignoring the Constant:**  In many cases, the denominator (probability of the data) is difficult to calculate. Since it's a constant, we can say the posterior is *proportional* to the likelihood times the prior. This simplification is often sufficient for finding the MAP estimate.

## 4. MAP Estimate (Maximum A Posteriori)

*   **Definition:** The value of *theta* that maximizes the posterior distribution (the mode of the posterior).
*   **Finding the MAP:** Usually, calculated using calculus. In the example, the argmax of the posterior gives the MAP estimate. The argmax is the input to a function that maximizes the output of that function.
*   **Significance:**  Summarizes the posterior distribution with a single, most likely value of *theta*.

## 5. Bayesian vs. Frequentist: Key Differences

*   **Uninformative Prior:**  With a non-informative (uniform) prior, the MAP estimate often coincides with the Maximum Likelihood Estimate (MLE) from a frequentist approach. This is because the prior is a constant and doesn't affect the location of the maximum in the posterior.  The MAP is the same as the MLE.
*   **Informative Prior:**  With an informative prior, the MAP estimate will be influenced by the prior, whereas frequentist methods only consider the data.  This is a key distinction.

## 6. Impact of Data & Convergence

*   **Data Chunking:** The order in which you incorporate data doesn't matter. Whether you analyze all data at once or in chunks, the final posterior will be the same.
*   **Convergence:** As you collect more data, the influence of the prior decreases. The posterior, and therefore the MAP estimate, will converge to the true value of *theta*, even with an initially inaccurate prior (assuming the prior isn't wildly incorrect).
*   **Watering Down the Prior:**  The more data you have, the more the initial prior matters.

## 7. When to Use Bayesian Methods

*   **Limited Data:** Bayesian methods are particularly useful when you have a limited amount of data.
*   **Strong Prior Beliefs:**  If you have significant prior knowledge, Bayesian methods allow you to incorporate that into your analysis.
*   **Large Datasets:** For very large datasets, frequentist approaches often perform well and may be computationally simpler.

## 8. Potential Downsides

*   **Wrong Priors:** If your priors are incorrect, they can lead to incorrect conclusions, especially with limited data. The wrong conclusions may result from the priors having strong influence on the conclusions drawn.


# Bayesian Statistics: A Complete Example & Key Concepts

This note summarizes the key points from the video, focusing on a worked example of Bayesian updating and contrasting it with frequentist approaches.

## 1. The Bayesian Framework: Updating Beliefs

*   **Goal:**  Learn about the probability density function (PDF) of a parameter (e.g., probability of heads on a coin), represented by a random variable *theta*.
*   **Bayes' Theorem:**  Used to update prior beliefs given observed data.  Specifically, the version of Bayes' theorem for continuous parameters and discrete data is used.
    *   `Posterior ∝ Likelihood * Prior`
*   **Data Representation:** Data is represented as a random variable *x*, which contains individual observations *x<sub>i</sub>*. The likelihood is the probability of observing the data *x*, given a specific value of theta.
*   **Example: Coin Flips**
    *   *x<sub>i</sub>*: Each coin flip (1 for heads, 0 for tails), modeled as a Bernoulli distribution given theta.
    *   *Likelihood*:  The probability of observing a specific sequence of heads and tails given a particular value of *theta*. The flips are assumed to be independent so the joint probability is simply the product of the individual probabilities.
*   **Iterative Updating:** The core process of Bayesian statistics.
    1.  Start with a **prior** (PDF) about *theta*.
    2.  Collect **data**.
    3.  Calculate the **likelihood** of the data given *theta*.
    4.  Compute the **posterior** distribution using Bayes' Theorem.
    5.  The posterior becomes the new prior for the next iteration.

## 2. Choosing Priors

*   **Prior:** Your initial belief about the parameter *theta* before seeing any data. Expressed as a PDF.
*   **Uninformative Prior:**  Represents a lack of prior knowledge.  A uniform distribution is often used (every value of theta between 0 and 1 is equally likely).
*   **Informative Prior:**  Reflects existing knowledge or beliefs about *theta*.  Choice significantly influences the posterior, especially with limited data.

## 3. Calculating the Posterior

*   **Posterior:**  The updated belief about *theta* after incorporating the data. A conditional PDF of theta given the observed data.
*   **Ignoring the Constant:**  In many cases, the denominator (probability of the data) is difficult to calculate. Since it's a constant, we can say the posterior is *proportional* to the likelihood times the prior. This simplification is often sufficient for finding the MAP estimate.

## 4. MAP Estimate (Maximum A Posteriori)

*   **Definition:** The value of *theta* that maximizes the posterior distribution (the mode of the posterior).
*   **Finding the MAP:** Usually, calculated using calculus. In the example, the argmax of the posterior gives the MAP estimate. The argmax is the input to a function that maximizes the output of that function.
*   **Significance:**  Summarizes the posterior distribution with a single, most likely value of *theta*.

## 5. Bayesian vs. Frequentist: Key Differences

*   **Uninformative Prior:**  With a non-informative (uniform) prior, the MAP estimate often coincides with the Maximum Likelihood Estimate (MLE) from a frequentist approach. This is because the prior is a constant and doesn't affect the location of the maximum in the posterior.  The MAP is the same as the MLE.
*   **Informative Prior:**  With an informative prior, the MAP estimate will be influenced by the prior, whereas frequentist methods only consider the data.  This is a key distinction.

## 6. Impact of Data & Convergence

*   **Data Chunking:** The order in which you incorporate data doesn't matter. Whether you analyze all data at once or in chunks, the final posterior will be the same.
*   **Convergence:** As you collect more data, the influence of the prior decreases. The posterior, and therefore the MAP estimate, will converge to the true value of *theta*, even with an initially inaccurate prior (assuming the prior isn't wildly incorrect).
*   **Watering Down the Prior:**  The more data you have, the more the initial prior matters.

## 7. When to Use Bayesian Methods

*   **Limited Data:** Bayesian methods are particularly useful when you have a limited amount of data.
*   **Strong Prior Beliefs:**  If you have significant prior knowledge, Bayesian methods allow you to incorporate that into your analysis.
*   **Large Datasets:** For very large datasets, frequentist approaches often perform well and may be computationally simpler.

## 8. Potential Downsides

*   **Wrong Priors:** If your priors are incorrect, they can lead to incorrect conclusions, especially with limited data. The wrong conclusions may result from the priors having strong influence on the conclusions drawn.


# Combining Maximum Likelihood, MAP Estimation, and Regularization

This note explains how maximum likelihood estimation (MLE), maximum a posteriori (MAP) estimation, and regularization in machine learning are connected.

## 1. Model Selection and Probability

*   **Problem:** Choosing the best model from a set of potential models to fit given data.
*   **Models and Data Generation:** Each model has a probability of generating the observed data: P(Data | Model).
*   **Model Prior Probability:** Simpler models are more likely to be selected *a priori*.  This is represented as P(Model).
*   **Winning Model:** The model that maximizes P(Data | Model) * P(Model) is the chosen one. It balances data fit with model complexity.  Simply selecting for the maximum likelihood is insufficient.

## 2. Connecting MLE, Regression, and Regularization

*   **MLE:** Maximizes the probability that the data was created by a given model: maximize P(Data | Model). In regression, involves minimizing a loss function (e.g., squared loss).
*   **Bayesian Extension:** In Bayesian approach, multiply the likelihood by the probability of the model: maximize P(Data | Model) * P(Model). This is equivalent to using Maximum a Posteriori (MAP) estimation.
*   **Regularized Regression:** Adds a regularization term to the loss function.

## 3. Mathematical Equivalence: From Products to Sums

*   Taking the logarithm transforms products of probabilities into sums of loss and regularization terms.
    *   maximize(P(Data | Model) * P(Model)) becomes minimize(Loss + Regularization Term).

## 4. Likelihood of a Model

*   **Probability of a Model:**  This is crucial.
*   **Coefficient Selection:**  Assume model coefficients are drawn from a probability distribution, (e.g., a standard normal distribution N(0,1)).
*   **Model Likelihood Calculation:**
    *   Likelihood of a single coefficient *a<sub>i</sub>*:  Given a standard normal distribution, use the Gaussian probability formula to calculate it.
    *   Likelihood of the entire model:  The product of the likelihoods of all its coefficients.  Since the coefficients are assumed to be independent, the joint distribution is simple the product of each individual PDF.

## 5. Putting it All Together

*   **Goal:** Maximize P(Data | Model) * P(Model).
*   **P(Data | Model):** Based on distances (errors) between the model's predictions and the actual data points. Model creates a Gaussian at every point on the line and generates points close to that line.
*   **P(Model):** The product of the likelihoods of each coefficient (assuming they are selected from a standard normal distribution).
*   **Maximization and Simplification:**
    1.  Write out the full expression for P(Data | Model) * P(Model).
    2.  Take the logarithm (turns product into a sum).
    3.  Drop constants (since they don't affect the location of the maximum/minimum).
    4.  The result is proportional to the negative sum of squared errors (squared loss) plus the negative sum of squared coefficients (regularization term).
    5.  Maximizing the product is then equivalent to *minimizing* the sum of squared loss and the regularization term.

## 6. Conclusion

*   Maximizing the probability of the model (picking coefficients from a distribution) is equivalent to minimizing the sum of squares of the coefficients (regularization).
*   Maximizing the conditional probability of the data given the model is equivalent to minimizing the squared loss.
*   Regularized models can be trained by minimizing the combined loss function (loss + regularization).
* The loss function is the sum of the loss due to the model not perfectly fitting the training data and the complexity penalty of using a non-simple model.