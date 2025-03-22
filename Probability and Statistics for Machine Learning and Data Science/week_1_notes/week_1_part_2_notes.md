# Table of Contents

1.  [Random Variables: A Key Concept in Probability](#random-variables-a-key-concept-in-probability)
    *   [What is a Random Variable?](#what-is-a-random-variable)
    *   [Examples](#examples)
    *   [Types of Random Variables](#types-of-random-variables)
    *   [Why are Random Variables Important?](#why-are-random-variables-important)
    *   [Examples of Random Variables](#examples-of-random-variables-1)
    *   [Illustrative Example: Coin Flipping](#illustrative-example-coin-flipping)
    *   [Random Variable: Modeling Experiments](#random-variable-modeling-experiments)
    *   [Types of Random Variables (Reiterated)](#types-of-random-variables-reiterated)
    *   [Deterministic vs. Random Variables (Table)](#deterministic-vs-random-variables-table)

2.  [Probability Distributions: Understanding Random Variable Behavior](#probability-distributions-understanding-random-variable-behavior)
    *   [Building Blocks: Random Variables and Their Outcomes](#building-blocks-random-variables-and-their-outcomes)
    *   [Connecting Outcomes to Probabilities](#connecting-outcomes-to-probabilities)
    *   [Visualizing Probabilities: Histograms](#visualizing-probabilities-histograms)
    *   [Extending the Experiment](#extending-the-experiment)
    *   [Probability Mass Function (PMF) for Discrete Random Variables](#probability-mass-function-pmf-for-discrete-random-variables)
    *   [Requirements for a PMF](#requirements-for-a-pmf)
    *   [The Binomial Distribution](#the-binomial-distribution)

3.  [The Binomial Distribution: Modeling Successes in Trials](#the-binomial-distribution-modeling-successes-in-trials)
    *   [Coin Toss Example: Building Intuition](#coin-toss-example-building-intuition)
    *   [Probability of a Specific Sequence](#probability-of-a-specific-sequence)
    *   [Combinations: Counting Possible Arrangements](#combinations-counting-possible-arrangements)
    *   [Binomial Coefficient](#binomial-coefficient)
    *   [Generalizing to Biased Coins](#generalizing-to-biased-coins)
    *   [Binomial Distribution Parameters](#binomial-distribution-parameters)
    *   [PMF of the Binomial Distribution](#pmf-of-the-binomial-distribution)
    *   [Dice Example](#dice-example)
    *   [Another Dice Example](#another-dice-example)

4.  [Deriving the Binomial Coefficient & Biased Coins](#deriving-the-binomial-coefficient--biased-coins)
    *   [Understanding "n choose k" (Binomial Coefficient)](#understanding-n-choose-k-binomial-coefficient)
    *   [Derivation](#derivation)
    *   [Example: n = 5, k = 4](#example-n-5-k-4)
    *   [Biased (Unfair) Coins](#biased-unfair-coins)
    *   [Applying the Binomial Distribution](#applying-the-binomial-distribution)

5.  [The Bernoulli Distribution: A Single Trial](#the-bernoulli-distribution-a-single-trial)
    *   [Coin-Flipping Setup (Again)](#coin-flipping-setup-again)
    *   [Success and Failure](#success-and-failure)
    *   [Generalizing Success/Failure](#generalizing-successfailure)
    *   [Bernoulli Distribution](#bernoulli-distribution-1)

6.  [Continuous Probability Distributions](#continuous-probability-distributions)
    *   [Discrete vs. Continuous](#discrete-vs-continuous)
    *   [The Paradox of Exact Values in Continuous Distributions](#the-paradox-of-exact-values-in-continuous-distributions)
    *   [Describing Continuous Distributions with Windows](#describing-continuous-distributions-with-windows)
    *   [Continuous Distribution as a Limit](#continuous-distribution-as-a-limit)
    *   [Key Properties of Continuous Probability Distributions](#key-properties-of-continuous-probability-distributions)

7.  [Probability Density Functions (PDFs) for Continuous Variables](#probability-density-functions-pdfs-for-continuous-variables)
    *   [The Issue with Point Probabilities](#the-issue-with-point-probabilities)
    *   [Probability Density Function (PDF)](#probability-density-function-pdf)
    *   [Calculating Probabilities with PDFs](#calculating-probabilities-with-pdfs)
    *   [Example: Call Center Wait Times](#example-call-center-wait-times)
    *   [Requirements for a Function to Be a Valid PDF](#requirements-for-a-function-to-be-a-valid-pdf)
    *   [Summary: Discrete vs. Continuous Random Variables (Table)](#summary-discrete-vs-continuous-random-variables-table)

8.  [Cumulative Distribution Functions (CDFs)](#cumulative-distribution-functions-cdfs)
    *   [Motivation for CDFs](#motivation-for-cdfs)
    *   [Cumulative Probability](#cumulative-probability)
    *   [Building the CDF (Discrete Case)](#building-the-cdf-discrete-case)
    *   [Properties of the CDF](#properties-of-the-cdf)
    *   [CDFs for Continuous Distributions](#cdfs-for-continuous-distributions)
    *   [Benefits of Using a CDF](#benefits-of-using-a-cdf)
    *   [Formal Definition](#formal-definition)
    *   [CDF Properties](#cdf-properties)
    *   [Visual Summary](#visual-summary)

9.  [The Uniform Distribution: Equal Probability Across an Interval](#the-uniform-distribution-equal-probability-across-an-interval)
    *   [Bus Wait Time Example](#bus-wait-time-example)
    *   [Support Call Center Example](#support-call-center-example)
    *   [PDF (Probability Density Function)](#pdf-probability-density-function-1)
    *   [General Definition of the Uniform Distribution](#general-definition-of-the-uniform-distribution)
    *   [CDF (Cumulative Distribution Function)](#cdf-cumulative-distribution-function-1)

10. [The Normal (Gaussian) Distribution: A Ubiquitous Model](#the-normal-gaussian-distribution-a-ubiquitous-model)
    *   [Motivation: From Binomial to Normal](#motivation-from-binomial-to-normal)
    *   [The Gaussian Distribution](#the-gaussian-distribution)
    *   [Formula for the PDF (Probability Density Function)](#formula-for-the-pdf-probability-density-function)
    *   [Key Properties](#key-properties)
    *   [Notation](#notation)
    *   [The Standard Normal Distribution](#the-standard-normal-distribution)
    *   [Standardization: Converting to the Standard Normal](#standardization-converting-to-the-standard-normal)
    *   [CDF (Cumulative Distribution Function)](#cdf-cumulative-distribution-function)
    *   [Applications of the Normal Distribution](#applications-of-the-normal-distribution)

11. [The Chi-Squared Distribution: Summing Squared Gaussians](#the-chi-squared-distribution-summing-squared-gaussians)
    *   [Scenario: Bit Transmission with Noise](#scenario-bit-transmission-with-noise)
    *   [Assumptions about Noise (Z)](#assumptions-about-noise-z)
    *   [Noise Power (W)](#noise-power-w)
    *   [What is the Distribution of W?](#what-is-the-distribution-of-w)
    *   [Chi-Squared Distribution with One Degree of Freedom](#chi-squared-distribution-with-one-degree-of-freedom)
    *   [Accumulating Noise Power](#accumulating-noise-power)
    *   [Generalizing to k Transmissions](#generalizing-to-k-transmissions)

12. [Sampling Probability Distributions: Generating Synthetic Data](#sampling-probability-distributions-generating-synthetic-data)
    *   [Motivation](#motivation-1)
    *   [Generating Synthetic Data by Sampling](#generating-synthetic-data-by-sampling)
    *   [Sampling from a Discrete Distribution](#sampling-from-a-discrete-distribution)
    *   [Sampling from a Continuous Distribution](#sampling-from-a-continuous-distribution)
    *   [Summary](#summary)

## Random Variables: A Key Concept in Probability

**What is a Random Variable?**

*   Unlike algebraic variables (e.g., x = 3), which have a fixed value, random variables can take on multiple values.
*   These values are associated with uncertain outcomes.

# Random Variable

A **random variable** is a variable whose value is a numerical outcome of a random phenomenon.

Here's a more detailed breakdown:

*   **Variable:** A symbol (usually a letter like X, Y, or Z) that represents a quantity that can vary.
*   **Random:** The outcome is determined by chance or a random process. You can't predict the exact value beforehand.
*   **Numerical Outcome:** The value that the variable takes on must be a number. This is the key distinction from other types of variables. We need to be able to do mathematical operations (like averaging) on the values.
*   **Random Phenomenon:** An experiment or process whose outcome is uncertain.

**Think of it this way:** A random variable is a way to map the possible outcomes of a random event to numbers.

**Examples:**

1.  **Coin Toss:**
    *   Random phenomenon: Tossing a coin.
    *   Possible outcomes: Heads (H) or Tails (T).
    *   Random variable (X): We can define X as:
        *   X = 1 if the outcome is Heads (H)
        *   X = 0 if the outcome is Tails (T)

2.  **Rolling a Die:**
    *   Random phenomenon: Rolling a standard six-sided die.
    *   Possible outcomes: 1, 2, 3, 4, 5, 6.
    *   Random variable (Y): Y is the number that shows up on the die. So Y can take on the values 1, 2, 3, 4, 5, or 6.

3.  **Number of Customers Arriving at a Store:**
    *   Random phenomenon: Counting the number of customers that arrive at a store in an hour.
    *   Possible outcomes: 0, 1, 2, 3, ... (could be any non-negative integer).
    *   Random variable (N): N is the number of customers that arrive.

4.  **Height of a Randomly Selected Person:**
    *   Random phenomenon: Selecting a person at random and measuring their height.
    *   Possible outcomes: Any value within a plausible range of heights (e.g., 0 to 8 feet).
    *   Random variable (H): H is the height of the person in inches or centimeters.

**Types of Random Variables:**

*   **Discrete Random Variable:** A variable that can only take on a finite number of values or a countably infinite number of values. Usually integers. Examples: Coin toss, rolling a die, number of customers arriving.

*   **Continuous Random Variable:** A variable that can take on any value within a given range. Examples: Height, weight, temperature.

**Why are Random Variables Important?**

*   **Quantifying Uncertainty:** They allow us to express uncertainty in a numerical way, which is essential for mathematical analysis.
*   **Modeling Real-World Phenomena:** Many real-world situations involve randomness. Random variables provide a way to model these situations mathematically.
*   **Statistical Analysis:** They are the foundation of many statistical techniques, such as hypothesis testing and regression analysis. We use random variables to represent the data we collect and analyze.
*   **Probability Distributions:** They allow us to calculate the probabilities of different outcomes. The values of a random variable, along with their associated probabilities, form a probability distribution.

**Examples of Random Variables:**

*   Temperature
*   Number of heads obtained when tossing a coin multiple times
*   Wait time until a bus arrives
*   Height of a gymnast's jump
*   Number of defective products in a shipment
*   Millimeters of rain in November

**Illustrative Example: Coin Flipping**

*   Flip a coin once.
*   Define X as the number of heads obtained.
*   If you get heads, X = 1.
*   If you get tails, X = 0.
*   P(X = 1) = 0.5 (probability of getting heads)
*   P(X = 0) = 0.5 (probability of getting tails)
*   X is a random variable because its value depends on the random outcome of the coin flip.

**Random Variable: Modeling Experiments**

*   Flip a coin 10 times. Define X as the number of heads obtained.
*   Possible outcomes: X can be 0, 1, 2, ..., 10.
*   Histogram: Shows the frequency of each value of X after repeating the experiment many times.

**Types of Random Variables:**

1.  **Discrete Random Variables:**
    *   Can take on a countable number of values.
    *   Values can be listed (even if the list is infinite).
    *   Examples:
        *   Number of 1s when rolling dice
        *   Number of heads when flipping coins
        *   Number of kids with a specific height.
        *   Number of flips until getting heads (can be infinite but countable).
2.  **Continuous Random Variables:**
    *   Can take on any value within a given interval.
    *   Values cannot be listed as a countable sequence.
    *   Examples:
        *   Wait time until the next bus arrives
        *   Height of a gymnast's jump
        *   Number of millimeters of rain in a month

**Deterministic vs. Random Variables:**

| Feature            | Deterministic Variable   | Random Variable                      |
| :----------------- | :----------------------- | :----------------------------------- |
| Value              | Fixed                    | Uncertain; multiple possible values |
| Outcome            | Certain                  | Uncertain                              |
| Example            | x = 2, input of f(x)=x^2 | Number of heads in a coin flip     |

**In summary:** Random variables are used to model scenarios with uncertain outcomes.

## Probability Distributions: Understanding Random Variable Behavior

This part introduces the concept of probability distributions, which describe how probability is distributed across the possible values of a random variable.

**Building Blocks: Random Variables and Their Outcomes**

*   Imagine tossing three coins and focusing on the number of heads obtained (random variable).
*   List all possible outcomes:
    *   No heads (TTT)
    *   One head (HTT, THT, TTH)
    *   Two heads (HHT, HTH, THH)
    *   Three heads (HHH)
*   Notice: some outcomes are more likely to occur than others. This is due to there being more possible options

**Connecting Outcomes to Probabilities:**

*   Total possible outcomes for three coin tosses: 8.
*   Number of ways to get each outcome:
    *   0 heads: 1 way (TTT)
    *   1 head: 3 ways (HTT, THT, TTH)
    *   2 heads: 3 ways (HHT, HTH, THH)
    *   3 heads: 1 way (HHH)
*   Probabilities:
    *   P(0 heads) = 1/8
    *   P(1 head) = 3/8
    *   P(2 heads) = 3/8
    *   P(3 heads) = 1/8

**Visualizing Probabilities: Histograms**

*   Create a histogram:
    *   X-axis: Number of heads (0, 1, 2, 3)
    *   Y-axis: Probability of each outcome

**Extending the Experiment:**

*   Repeat the process with four coin tosses and five coin tosses.
*   Observe similar patterns in the distribution of probabilities.

**Probability Mass Function (PMF) for Discrete Random Variables:**

*   A PMF provides a complete description of a discrete random variable.
*   It specifies the probability that the random variable takes on each of its possible values.
*   The PMF is represented by lowercase p.
*   Each bar in the histogram is represented by the possible values x3, and they represent the probability the X3 is X.
*   Example: The probabilities of X3 are represented using a PMF

**Requirements for a PMF:**

1.  **Non-negativity:** p(x) >= 0 for all x (probabilities cannot be negative).
2.  **Normalization:** Sum of p(x) over all possible values of x must equal 1 (all possible outcomes must be accounted for).

**The Binomial Distribution:**

*   The variables X1, X2, and X3 (number of heads in a fixed number of coin tosses) all share similarities in their probability distributions.
*   The next video will introduce the binomial distribution, which provides a single model to represent these types of random variables.


## The Binomial Distribution: Modeling Successes in Trials

This part introduces the binomial distribution, a fundamental probability distribution used to model the number of successes in a fixed number of independent trials.

**Coin Toss Example: Building Intuition**

*   Toss a coin 10 times.
*   The number of heads you can get (0 to 10) follows a binomial distribution.
*   Each outcome has a specific probability.

**Probability of a Specific Sequence**

*   What is the probability of getting exactly two heads when flipping a coin five times?
*   Consider the sequence HHTTT.  The probability of this exact sequence is (1/2) * (1/2) * (1/2) * (1/2) *(1/2) = (1/2)^5 = 1/32.
*   However, there are multiple ways to get two heads in five flips.

**Combinations: Counting Possible Arrangements**

*   There are 10 different ways to arrange two heads and three tails in a sequence of five flips. (HHTTT, HTHTT, HTTHT...).

**Binomial Coefficient:**

*   A mathematical formula to calculate the number of combinations (orderings):
    *   n choose k = n! / (k! * (n-k)!)
    *   Where n! (n factorial) is the product of all positive integers up to n (e.g., 5! = 5 * 4 * 3 * 2 * 1).
*   "n choose k" counts the number of ways to choose k items from a set of n items.
*   In our case, 5 choose 2 = 5! / (2! * 3!) = 10, confirming the number of combinations.
*   Obtaining k heads is the same as obtaining n-k tails, so n choose k is the same as n choose n-k.

**Generalizing to Biased Coins:**

*   Let p be the probability of getting heads on a single flip.
*   Probability of getting exactly x heads in five flips (and thus 5-x tails):
    *   P(X = x) = (5 choose x) * p^x * (1-p)^(5-x)
    *   (5 choose x) counts the number of possible orderings of the heads and tails.
    *   p^x is the probability of getting x heads.
    *   (1-p)^(5-x) is the probability of getting 5-x tails.
*   X follows a binomial distribution: X ~ Binomial(5, p)

**Binomial Distribution Parameters:**

*   n: The number of trials (e.g., number of coin flips).
*   p: The probability of success on a single trial (e.g., probability of getting heads).

**PMF of the Binomial Distribution:**

*   P(X = x) = (n choose x) * p^x * (1-p)^(n-x) for x = 0, 1, 2, ..., n

**Dice Example:**

*   What is the probability of throwing a die five times and getting three ones?
*   This can be modeled as a binomial distribution with:
    *   n = 5 (number of throws)
    *   p = 1/6 (probability of getting a 1 on a single throw)
*   The question can be reinterpreted as a "biased coin", with the probability of heads as the same as getting a one.

**Another Dice Example:**

*   Throwing a dice 10 times and calculating the PMF and Histogram.
*   Binomial Distribution with:
    *   n = 10 (number of dice throws)
    *   p = 1/6 (probability of obtaining a 1)
*   The parameters of the PMF are 10 and 0.1666.


## Deriving the Binomial Coefficient & Biased Coins

This part delves deeper into the binomial coefficient and explores the binomial distribution when dealing with biased (unfair) coins.

**Understanding "n choose k" (Binomial Coefficient)**

*   "n choose k" represents the number of ways to choose k items from a set of n items, *without* regard to order (unordered sets).

**Derivation:**

1.  **Ordered Selection:**
    *   Start by picking the first element (n choices).
    *   Pick the second element (n-1 choices).
    *   Continue until you've picked k elements (n-k+1 choices).
    *   Total number of ordered selections: n * (n-1) * (n-2) * ... * (n-k+1)
2.  **Accounting for Duplicates (Order Matters!):**
    *   The above calculation counts each *unordered* set multiple times, once for each possible *ordering* of the selected k elements.
    *   The number of ways to order k elements is k! (k factorial).  k! = k * (k-1) * (k-2) * ... * 1
3.  **Removing Duplicates:**
    *   To get the number of *unordered* sets, divide the number of *ordered* selections by the number of ways to order each set:
        *   (n * (n-1) * (n-2) * ... * (n-k+1)) / k!
4.  **Rewriting the Expression:**
    *   The expression can be rewritten using factorials:
        *   n! / (k! * (n-k)!)
        *  **n! is the product of n all the way to 1**
        *  **If dividing by n-k, that is dividing the product of n-k all the way to 1**
        *  This is a commonly used formula that matches the definition of "n choose k."
5.  **Number of ways to pick 0 things out of n is 1**
    *   Anything choose zero is always 1.
        * It's the number of ways of picking zero things out of zero and there's only one way to do that which is not picking any.

**Example: n = 5, k = 4:**
If there's a set of 5 items (1, 2, 3, 4, 5), and there are 4 ways to arrange them, the total numbers would be 4! = 4 * 3 * 2 * 1, that is 24.
This leads to K factorial, an important property in probability.

**Biased (Unfair) Coins:**

*   If the coin is biased, with a probability p of landing on heads (and 1-p of landing on tails), the probabilities of each outcome in the binomial distribution are no longer equal.
*   Let's say we are counting the outcomes and have 5 coins, where it will be 0 heads, 1 heads, all the way to five heads.
*   If we account 30% of the time, the coin lands on heads, and 70% the coin lands on tails, these have different probabilities.
*   Each k heads out of n coin tosses have a different possibility (n C k )0.7n-k 0.3k

**Formula for the binomial distribution**
(k C n)qkpn-k
This formula is used if there is a probability other than 50%.

**Applying the Binomial Distribution:**
* You now have the tools to calculate the histogram and binomial distribution.



## The Bernoulli Distribution: A Single Trial

This part introduces the Bernoulli distribution, a fundamental probability distribution that describes the probability of success or failure in a single trial of a random experiment.

**Coin-Flipping Setup (Again):**

*   Flip a coin once.
*   X = number of heads (random variable).
*   Two possible outcomes:
    *   Heads (X = 1) with probability 0.5
    *   Tails (X = 0) with probability 0.5

**Success and Failure:**

*   Define "success" as landing on heads.
*   Define "failure" as landing on tails.

**Generalizing Success/Failure:**

*   The idea of success and failure can be applied to various experiments:
    *   **Rolling a Die:**
        *   Success: Rolling a 1.
        *   Failure: Rolling any other number (2, 3, 4, 5, 6).
        *   P(Success) = 1/6
        *   P(Failure) = 5/6
    *   **Patient Health:**
        *   Success: Patient is sick (slightly counterintuitive, but it is the event you are counting).
        *   Failure: Patient is healthy.
        *   P(Success) = p (probability of being sick)
        *   P(Failure) = 1 - p

**Bernoulli Distribution**

*   These are all examples of the Bernoulli distribution.
*   It models a single trial with two possible outcomes (success or failure).
*   The distribution has a single parameter:
    *   p: The probability of success. The probability of failure is (1-p).

## Continuous Probability Distributions

This part introduces the concept of continuous probability distributions and contrasts them with discrete distributions.

**Discrete vs. Continuous**

*   **Discrete:**
    *   Events can be listed (finite or infinite).
    *   Example: Number of heads in coin flips, number of people in a town.
*   **Continuous:**
    *   Events fall within an interval.
    *   Cannot be listed.
    *   Example: Amount of time waiting on the phone, wait time for a bus.

**The Paradox of Exact Values in Continuous Distributions:**

*   Question: What's the probability that a call takes exactly 1 minute (to the exact second)?
*   Answer: Essentially zero. There are uncountably many possible durations (e.g., 1.000000... minutes) making the precise event infinitely unlikely.

**Describing Continuous Distributions with Windows:**

1.  Instead of exact values, consider probability within intervals (windows).
2.  Divide the interval into segments (e.g., 0-1 minute, 1-2 minutes, 2-3 minutes).
3.  Assign a probability (represented by a bar height) to each segment.
4.  This forms a discrete probability distribution where the sum of the bar heights (area under the bars) equals 1.
5.  Make the interval increments more granular (30 seconds, 15 seconds).

**Continuous Distribution as a Limit:**

*   As the interval width approaches zero, the discrete distribution becomes a continuous curve.
*   The area under the curve equals 1.

**Key Properties of Continuous Probability Distributions:**

*   Probabilities are defined over intervals, not at single points.
*   The area under the curve represents the total probability, which must equal 1.


## Probability Density Functions (PDFs) for Continuous Variables

**The Issue with Point Probabilities:**

*   In continuous distributions, the probability of a random variable taking a *specific, exact* value is zero. (e.g., P(call lasting exactly 2 minutes) = 0).
*   Instead, we focus on probabilities within *intervals*.

**Probability Density Function (PDF)**

*   Analogous to the Probability Mass Function (PMF) for discrete variables, but for continuous variables.
*   Denoted by a lowercase f (often with a subscript fX(x)).
*   The PDF describes the *relative likelihood* of a random variable taking on a value within a given range. It does **not** give you the probability of a specific point.
*   The PDF has to be positive to ensure non-negative probability. The opposite of positive is negative.
*   The PDF has to equal the sum of one. It must be a certain event.

**Calculating Probabilities with PDFs:**

*   To find the probability that a continuous random variable falls within a certain interval (between points A and B), calculate the area under the PDF curve between A and B. This is the integral from A to B of the PDF.

**Example: Call Center Wait Times**

*   Scenario: Call center answers calls with equal probability between 0 and 5 minutes.
*   Probability of a call lasting between 2 and 3 minutes = 0.2 (one-fifth of the total area).
*   Probability of a call lasting between 2 and 2.5 minutes = 0.1 (one-tenth of the total area).

**Requirements for a Function to Be a Valid PDF:**

1.  **Defined for All Real Numbers:** The PDF must be defined for all x on the real number line (although it may be zero outside of a specific interval).
2.  **Non-Negative:** f(x) >= 0 for all x (the PDF cannot have negative values).
3.  **Area Under the Curve Equals 1:** The total area under the PDF curve (from negative infinity to positive infinity) must equal 1. This ensures that the total probability of all possible outcomes is 1.

**Summary: Discrete vs. Continuous Random Variables**

| Feature                 | Discrete Random Variable                                  | Continuous Random Variable                                      |
| :---------------------- | :-------------------------------------------------------- | :-------------------------------------------------------------- |
| Possible Values         | Finite or countably infinite                               | Any value within an interval                                    |
| Probability             | Probability Mass Function (PMF)                           | Probability Density Function (PDF)                                |
| Probability of a Point | Non-zero                                                  | Always 0                                                          |
| Probability of Events   | The sum of the probabilities to take a particular value. | Calculated from the area of where the PDF's curve is underneath |


## Cumulative Distribution Functions (CDFs)

This part introduces cumulative distribution functions (CDFs) and contrasts them with PMFs and PDFs.

**Motivation for CDFs:**

*   Calculating areas under a PDF curve (to find probabilities) can be cumbersome.
*   CDFs provide a more convenient way to determine the probability that a random variable is less than or equal to a specific value.

**Cumulative Probability:**

*   Cumulative probability tells you the probability that an event happened before some reference point.

**Building the CDF (Discrete Case):**

1.  Start with a discrete probability distribution (e.g., call lengths in minutes: 0-1, 1-2, 2-3, 3-4, 4-5).
2.  The cumulative probability for 0-1 is the same.
3.  The cumulative probability between 0-2 is the probabilities from steps 1 and 2 added together.
4.  And so on

**Properties of the CDF:**

*   Always starts at 0 (at the left endpoint). Cumulative is 0 up to the point we expect no outcomes.
*   Always ends at 1 (at the right endpoint).
*   The graph is the sum of areas from the beginning (left) to the point of interest.

**CDFs for Continuous Distributions:**

*   Conceptually similar to the discrete case, but involves summing the area under the PDF curve from the beginning (left) to a specific point.
*   The resulting CDF is a smooth, continuous curve.

**Benefits of Using a CDF:**

*   Simplifies probability calculations. Instead of calculating areas, you simply look up a value on the CDF curve.
*   Provides a comprehensive view of how probabilities accumulate across the entire range of possible values.
*   In other words:

> These two curves give us the same information except written different.
> On the left, we have to calculate areas to find probabilities and on the right we simply have to look at heights.

**Formal Definition:**

*   F(x) = P(X <= x)
    *   F(x) is the CDF value at x.
    *   P(X <= x) is the probability that the random variable X takes on a value less than or equal to x.
*   Defined for all values on the real number line (from negative infinity to positive infinity).
*   Uses the notation that the function is normal denoted with capital F, while the function for PDFs is written as small f.

**CDF Properties:**

1.  **Range:** 0 <= F(x) <= 1 for all x.
2.  **Left Endpoint:** lim (x -> -infinity) F(x) = 0 (CDF starts at 0). In some cases the variable cannot have a negative value, so this equals to 0.
3.  **Right Endpoint:** lim (x -> +infinity) F(x) = 1 (CDF approaches 1). The right endpoint is one, where all probability accumulates to.
4.  **Non-Decreasing:** F(x1) <= F(x2) if x1 < x2 (CDF can never decrease).

**Visual Summary:**

*   PDF:
    *   Function f(x)
    *   Always positive (or zero).
    *   Total area under the curve equals 1.
*   CDF:
    *   Function F(x)
    *   Ranges from 0 to 1.
    *   Always increasing (or constant).

## The Uniform Distribution: Equal Probability Across an Interval

This part introduces the uniform distribution, the simplest continuous probability distribution, where all values within a given interval are equally likely.

**Bus Wait Time Example:**

*   A bus arrives every 10 minutes, but you don't know the exact schedule.
*   You walk outside and wait.
*   The time you wait is roughly uniformly distributed between 0 and 10 minutes.
*   Each minute is roughly equally likely to wait for.

**Support Call Center Example:**

*   Call center answers calls within 0-15 minutes with equal probability.
*   Record wait times for 200 calls.
*   The points are more or less equally distributed over the y-axis.
*   The time in the call (the variable), T, is considered. The value between 0 and 15 has the same frequency as occurrences.

**PDF (Probability Density Function):**

*   Since all values between 0 and 15 are equally likely, the PDF is constant.
*   Area under the PDF curve must equal 1.
*   Height of the PDF curve = 1 / (length of interval) = 1/15 ≈ 0.0667.
*   The constant for the value is between a and b.

**General Definition of the Uniform Distribution:**

*   A continuous random variable follows a uniform distribution if all possible values have the same frequency of occurrence.
*   Parameters:
    *   a: The beginning of the interval.
    *   b: The end of the interval.
*   PDF:
    *   f(x) = 1 / (b - a) for a <= x <= b (constant within the interval)
    *   f(x) = 0 otherwise (zero outside the interval)
*   Smaller intervals make the height of the pdf higher, and quickly decrease as the interval gets shorter.

**CDF (Cumulative Distribution Function):**

*   Example: Uniform distribution between 0 and 1.
*   For x < 0: CDF(x) = 0 (no probability accumulated yet).
*   For 0 <= x <= 1: CDF(x) = x (linear increase from 0 to 1). The probability of a variable being smaller than x.
*   For x > 1: CDF(x) = 1 (all probability has been accumulated).
*   General Uniform Distribution Between a and b.
    *   F(x) = 0 for x < a
    *   F(x) = (x-a) / (b-a) for a <= x <= b
    *   F(x) = 1 for x > b. Since every value of x has already gathered, the probability is 1.

## The Normal (Gaussian) Distribution: A Ubiquitous Model

This part introduces the normal (or Gaussian) distribution, one of the most widely used probability distributions in statistics, science, and machine learning.

**Motivation: From Binomial to Normal**

1.  Recall the binomial distribution: describes the number of successes in a fixed number of trials (e.g., coin flips).
2.  As the number of trials (n) in the binomial distribution increases, the shape of the probability mass function starts to resemble a bell curve.

**The Gaussian Distribution:**

*   The bell-shaped curve that approximates the binomial distribution for large n is called the normal or Gaussian distribution.
*   It is symmetrical

**Building the Formula**

1.   e^(-x^2 /2) resembles the bell curve. It is symmetrical over the x axis and therefore needs to be moved so it has the right center.
2.  e^((-(x-2)^2) / 2) = this data is centered around two.
3.  e^((-(x-2)^2) / 3) = it needs to be widened.
4. The exponent then gets divided by 3. 3 is standard deviation.
5. The height of the graph is much larger to account to probability distribution: it requires to be divided by (3 X square root of 2π.

**Formula for the PDF (Probability Density Function):**

*   f(x) = (1 / (σ * sqrt(2π))) * exp(-(x - μ)^2 / (2σ^2))
    *   μ (mu): The mean (average) of the distribution, representing the center of the bell curve.
    *   σ (sigma): The standard deviation, measuring the spread or width of the curve.
*   Here is a breakdown:

> e is the square root of 2π
> The square root is a scaling constant.

**Key Properties:**

*   Symmetrical around the mean (μ).
*   The spread or width of the curve is determined by the standard deviation (σ).
*   Range: All real numbers (from negative infinity to positive infinity).
*   The PDF is always positive, although can be very small for very large and negative numbers.

**Notation:**

*   If a random variable X follows a normal distribution with mean μ and standard deviation σ, we write:
    *   X ~ N(μ, σ^2)
    *   "X is distributed as normal with mean mu and variance sigma squared"
    *   Remember that sigma is the standard deviation.
    *   Sigma squared is called the variance.

**The Standard Normal Distribution:**

*   A special case of the normal distribution with:
    *   Mean (μ) = 0
    *   Standard Deviation (σ) = 1

**Standardization: Converting to the Standard Normal**

*   Any normal distribution can be transformed into the standard normal distribution by:
    *   Z = (X - μ) / σ
    *   Subtracting the mean (centering the distribution)
    *   Dividing by the standard deviation (scaling the distribution)

**CDF (Cumulative Distribution Function):**

*   CDF(x) gives the probability that the random variable X is less than or equal to x.
*   The shape of the distribution:

> As usual, it starts at 0 on the very left, which is now the point at infinity, and ends at 1 at the very right, which is a point at plus infinity

*   Areas under the curve are hard to compute, in the old days they were computed via table.

**Applications of the Normal Distribution:**

*   Heights and weights of people
*   IQ scores
*   Noise in communication channels
*   Variables that can be modelled as the sum of many independent processes.
*   Common assumption in many machine learning models.


## The Chi-Squared Distribution: Summing Squared Gaussians

This part introduces the Chi-squared distribution, which arises when summing the squares of independent standard normal (Gaussian) random variables. This distribution is significant in various fields, including wireless communications.

**Scenario: Bit Transmission with Noise**

1.  Transmitting a message (e.g., 10010) between antennas.
2.  The signal travels through a communication channel.
3.  Noise (Z) affects the signal during transmission.
4.  Received message = Original message + Noise (Z).

**Assumptions about Noise (Z):**

*   Z has a Gaussian distribution with a mean of 0 (standard normal distribution).
*   Important information: The noise will have a Gaussian distribution with mu = 0.

**Noise Power (W):**

*   Noise power = Z^2 (square of the noise).
*   Represents the variance or dispersion of the noise.
*   Determines how difficult it is to interpret the received signal correctly.

**What is the Distribution of W?**

*   The distribution of W (the square of a standard normal variable) is called the Chi-squared distribution with one degree of freedom.

**Chi-Squared Distribution with One Degree of Freedom:**

*   CDF curve grows quickly due to gaussian distributions converging around zero.
*   Formula:

> Each value of W can be achieved with two different values of Z, which are negative square root of W, and square root of W, even more, the probability that capital W's and W is the area under the PDF curve on the Gaussian between these two numbers.

*   PDF can be obtained by differentiating the CDF.

**Accumulating Noise Power:**

*   Noise power over two transmissions: W = Z1^2 + Z2^2, where Z1 and Z2 are independent standard normal variables.
    *   Follows a Chi-squared distribution with *two* degrees of freedom.

*   Noise power over five transmissions: W = Z1^2 + Z2^2 + Z3^2 + Z4^2 + Z5^2
    *   Follows a Chi-squared distribution with *five* degrees of freedom.

**Generalizing to k Transmissions:**

*   W = Z1^2 + Z2^2 + ... + Zk^2
    *   Follows a Chi-squared distribution with *k* degrees of freedom.
*   As k increases, the PDF becomes more spread out and symmetrical.


## Sampling Probability Distributions: Generating Synthetic Data

This part introduces the concept of sampling probability distributions, a valuable technique for generating synthetic data that mimics a real dataset.

**Motivation:**

*   Sometimes, you need a larger dataset than you have available.
*   Collecting more data can be expensive or impractical.
*   Solution: Create synthetic data that resembles the original data.

**Generating Synthetic Data by Sampling:**

1.  **Construct a distribution from your existing data.**

2.  **Sample from that distribution:**
    *   Pick points according to the probabilities defined by the distribution.

**Sampling from a Discrete Distribution:**

1.  **Example:** Colors (green, blue, orange) with probabilities 0.3, 0.5, and 0.2, respectively.

2.  **The Process:**
    *   Represent the probabilities as a continuous strip from 0 to 1.
    *   The numbers add up to one, and the probabilities can be constructed to a continuous strip.
    *   Generate a uniform random number between 0 and 1.
    *   Determine which interval the random number falls into.
        The probabilities will now represent given data as these three colors.

3.  **Alternative Visualization:**
    1. Graphically rearrange and draw the line for cumalative destribution.
    2. Sample uniformly from vertical interval.
    3. Read out to value in horizontal axis.

**Sampling from a Continuous Distribution:**

1.  Leverage the CDF (Cumulative Distribution Function):

>  It's not easy because calculating areas is hard. But if you take a look at the CDF on the right, and then you pick uniformly from that gray interval, the interval from 0 to 1, that's vertical

2.  The Process:
    *   Pick a uniform random number between 0 and 1 (vertical axis).
    *   Map that value to the corresponding value on the x-axis using the inverse CDF.
    *   If you take a look at CDF and sample numbers, these numbers are evenly distributed.
3. Pick the numbers through hit.

> So these points over here are actually distributed based on the normal distribution on the left. As you can see, this is the distribution that these points are taken from. And when you look at them on the left, that's the exact distribution that they're taken from.

**Summary:**

*   CDFs (both discrete and continuous) provide a powerful method for sampling from a distribution.
*   The CDF is vertical.
*   The sampling method relies on uniformly picking something from a specific point.

The method is:
Generate data and follow this distribution, where you follow these instructions:

1.  Create Random Data.
2.  Analysis Data.
3.  Determine main Key Features.