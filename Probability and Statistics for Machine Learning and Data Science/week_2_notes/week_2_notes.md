# Table of Contents

1.  [Describing the Center of a Distribution: The Mean (Expected Value)](#describing-the-center-of-a-distribution-the-mean-expected-value)
    *   Intuitive Meaning: Balancing Point
    *   Calculating the Mean (Discrete Data)
    *   Formal Notation
    *   Expected Payoff in Games
    *   Expected Value (Discrete Random Variable)
    *   Expected Value (Continuous Random Variable)
    *   Common Misconception: Mean vs. Median

2.  [Measures of Central Tendency: Mean, Median, and Mode](#measures-of-central-tendency-mean-median-and-mode)
    *   The Challenge with the Mean: Outliers
    *   The Median: A Robust Alternative
    *   Calculating the Median
    *   The Mode: The Most Frequent Value
    *   Real Example: Binomial Distribution
    *   Example: Normal Distribution

3.  [Expected Value of a Function of a Random Variable](#expected-value-of-a-function-of-a-random-variable)
    *   The Setup
    *   Standard Expected Value
    *   Expected Value of a Function g(X)
    *   Example: Rolling a Dice
    *   Linearity of Expectation

4.  [Sum of Expectations: A Powerful Tool](#sum-of-expectations-a-powerful-tool)
    *   Example: Coin Toss and Dice Roll
    *   The Matching Names Problem
    *   Using Sum of Expectations
    *   Generalizing
    *   Linearity of Expectation: The Rule

5.  [Measuring the Spread: Variance](#measuring-the-spread-variance)
    *   The Need for Variance
    *   Deviations from the Mean
    *   Average Deviation: Not Useful
    *   Absolute Deviation
    *   Squared Deviations: Variance
    *   Variance Formula
    *   The Alternative Formula

6.  [Putting Spread in the Right Units: Standard Deviation](#putting-spread-in-the-right-units-standard-deviation)
    *   The Problem with Variance
    *   Solution: Standard Deviation
    *   Benefits of Standard Deviation
    *   Normal Distribution and Standard Deviation

7.  [Adding Gaussian Distributions](#adding-gaussian-distributions)
    *   Scenario: Total Response Time
    *   Modeling Processing Time and Network Latency
    *   Assumptions
    *   Simulation
    *   The Result
    *   Parameters of the Resulting Gaussian Distribution
    *   Generalization: Linear Combination of Gaussian Variables

8.  [Standardizing Distributions: Centering and Scaling](#standardizing-distributions-centering-and-scaling)
    *   Why Standardize?
    *   Centering a Distribution
    *   Scaling a Distribution
    *   Process For Standardization

9.  [Moments of a Distribution](#moments-of-a-distribution)
    *   Beyond Expectation and Variance
    *   Moments Defined
    *   Calculation

10. [Telling Apart Distributions: Skewness (The Third Moment)](#telling-apart-distributions-skewness-the-third-moment)
    *   Problem: Identical Mean and Variance
    *   Solution: The Third Moment
    *   Positive Skew
    *   Negative Skew
    *   Zero Skew
    *   Standardized Skewness

11. [Understanding Tail Behavior: Kurtosis (The Fourth Moment)](#understanding-tail-behavior-kurtosis-the-fourth-moment)
    *   What it is
    *   Why it's Important
    *   High Kurtosis (Leptokurtic)
    *   Low Kurtosis (Platykurtic)

12. [Visualizing Data: Quantiles](#visualizing-data-quantiles)
    *   What it is
    *   Why it's Important
    *   How it Works
    *   Common Quantiles

13. [Visualizing Data: Box Plots (Box and Whiskers)](#visualizing-data-box-plots-box-and-whiskers)
    *   What it is
    *   Why it's Important
    *   How to Create a Box Plot
    *   Box Plot Interpretation

14. [Visualizing Data: Kernel Density Estimation (KDE)](#visualizing-data-kernel-density-estimation-kde)
    *   What it is
    *   Why it's Important
    *   How it Works
    *   Advantages of KDE over Histograms

15. [Visualizing Data: Violin Plots](#visualizing-data-violin-plots)
    *   What it is
    *   Why it's Important
    *   How it Works
    *   Advantages of Violin Plots

16. [Checking for Normality: QQ Plots](#checking-for-normality-qq-plots)
    *   What it is
    *   Why it's Important
    *   How it Works
    *   Interpretation


## Mean (Expected Value): Describing the Center of a Distribution

This part reviews the concept of the mean, also known as the expected value, and demonstrates how it describes the center of a probability distribution.

**Intuitive Meaning: Balancing Point**

*   The mean is the point where a distribution would balance if placed on a scale.

**Calculating the Mean (Discrete Data):**

*   Sum all the values and divide by the number of values.
*   Another perspective: Weighted average of the values, where the weights are the probabilities of each value.

**Example: Ages of Kids**

*   3 kids of age 0, 2 kids of age 1, 4 kids of age 2, 1 kid of age 3 (total of 10 kids).
*   Mean = (3*0 + 2*1 + 4*2 + 1*3) / 10 = 1.3
*   Expected value = (3/10)*0 + (2/10)*1 + (4/10)*2 + (1/10)*3 = 1.3

**Formal Notation (Expected Value):**

*   If X is a random variable, the expected value is written as E[X].

**Expected Payoff in Games:**

*   Used to determine a fair price to pay for a game.
*   Example: Flip a coin; win $10 if heads, $0 if tails.
*   Expected payoff = 0.5 * $10 + 0.5 * $0 = $5
*   You should be willing to pay up to $5 to play this game, or you will go bankrupt.

**Expected Value (Discrete Random Variable):**

*   Formula: E[X] = Summation of (x * P(x)) for all possible values of x.
*   P(x) is the probability mass function (PMF) at value x.
*   Remember P(a)+P(b)+P(C) =1 in a probability.

**Expected Value (Continuous Random Variable):**

*   Involves integration (calculus).
*   The symbolic expression for the mean and expected value are the same.

**Balancing a Continuous Distribution:**

*   The same way as a discrete function, expect that it is used to determine which side the distribution lands on
*   Analogy: Balancing the weight of infinitesimally narrow bars.

**Example: Uniform Distribution**

*   Uniform distribution between a and b: The expected value is at the midpoint, (a+b)/2.

**Common Misconception:**

*   The mean is *not* always the point that splits the data in half. That point is called the median.
*   An extreme value (even with low probability) can significantly shift the mean.

**Summary:**

*   The expected value, E[X], is the mean of a probability distribution.
*   Visually, it is the balancing point of the distribution.
*   It is defined for both discrete and continuous variables.
*   Think of it as the weighted average of the PMF or PDF of the random variable.

## Mean, Median, and Mode: Measures of Central Tendency

This part introduces three key measures of central tendency: mean, median, and mode. It explains when each measure is most appropriate and how they can provide different insights into the center of a distribution.

**The Challenge with the Mean:**

*   The mean can be misleading if the data is skewed by outliers.

**Example: University of North Carolina Geography Graduates**

*   In the 1980s, the average starting salary was $250,000, significantly higher than the national average of $22,000.
*   Cause: Michael Jordan graduated from the program and earned a very high salary, skewing the average upwards.

**The Median: A Robust Alternative**

*   The median is the middle value when the data is sorted in order.
*   It is less sensitive to outliers than the mean.

**Calculating the Median:**

*   Sort the data.
*   If there is an odd number of values, the median is the middle value.
*   If there is an even number of values, the median is the average of the two middle values.

**When to Use the Median:**

*   When the average is deceiving, use the median.

**The Mode: The Most Frequent Value**

*   The mode is the value that occurs most often in the dataset.
*   In a continuous distribution, the mode is the peak of the probability density function.
*   The mode is simply the values at which the distribution has the highest probability
*   Multimodal distribution: When a maximum value is repeated.
*   In places like uniform distribution, everything is a mode.

**Real Example: Binomial Distribution**

*   *It is always good to look at the three, in order to see if the center of the data is true*
*   Binomial distribution with 5 trials, probability of 1/2.
    *   Mean: 2.5
    *   Median: 2.5
    *   Modes: 2 and 3
*   Binomial distribution with 5 trials, probability of 0.3.
    *   Mean: 1.5
    *   Median: ~1.5
    *   Mode: 1

**Example: Normal Distribution**

*   The distribution: the three values match.
*   Mean: Center of the symmetrical distribution.
*   Median: Also the center.
*   Mode: Peak of the distribution.

**Key Takeaway:**

The mean, median, and mode are important tools for describing the center of a dataset. They can provide different insights, and it's often helpful to consider all three to get a comprehensive understanding of the data.

## Expected Value of a Function of a Random Variable

This part explains how to calculate the expected value of a function of a random variable, extending the concept of expected value beyond the variable itself.

**The Setup:**

*   You have a random variable X with possible outcomes x1, x2, x3, x4, and corresponding probabilities p(x1), p(x2), p(x3), p(x4).

**Standard Expected Value:**

*   The expected value of X is calculated as:
    *   E[X] = x1*p(x1) + x2*p(x2) + x3*p(x3) + x4*p(x4) + ...

**Expected Value of a Function g(X):**

*   If you are interested in the expected value of some function g(X) (e.g., g(X) = X^2, g(X) = X^3), the calculation is similar:
    *   E[g(X)] = g(x1)*p(x1) + g(x2)*p(x2) + g(x3)*p(x3) + g(x4)*p(x4) + ...
*   Simply replace x with g(x), keeping the probabilities the same.

**Example: Rolling a Dice and Winning the Square of the Roll**

*   You roll a dice, and your friend pays you the square of the number rolled.
*   Possible payoffs: 1, 4, 9, 16, 25, 36.
*   Probabilities: Each number has a 1/6 probability of occurring.
*   Fair price to pay to play the game is the expected value of the square of the roll:
    *   E[X^2] = (1/6)*1 + (1/6)*4 + (1/6)*9 + (1/6)*16 + (1/6)*25 + (1/6)*36 = 91/6
*   This is the value of the variable is nothing harder than a problem you already now.

**Example: New Rules in the Game**

*   Friend now pays you 2 times the number rolled, but you must pay $5 to play.
*   Your wins are -3, -2, -1, 0, 1, 2.
* The game has 6 * -5/6, which groups it together.
*   The average -3/6 which = -0.5.

**Linearity of Expectation:**

*   A key property:
    *   E[aX + b] = a * E[X] + b, where a and b are constants.
*   This means the expectation is a linear operator.
*   Two more takeaways

>  If they do not have a distribution, there is a high chance they do.
>  The constant cannot be there.

**Key Properties Derived:**

*   E[aX] = a * E[X] (scaling the random variable)
*   E[b] = b (the expected value of a constant is the constant itself)


## Sum of Expectations: A Powerful Tool

This part explains that the expected value of the sum of two or more random variables is equal to the sum of their individual expected values. This property, known as linearity of expectation, is a powerful tool for solving problems, even when the variables are not independent.

**Example: Coin Toss and Dice Roll**

*   Game: Flip a coin (win $1 if heads, $0 if tails) AND roll a die (win the value of the roll).

*   Coin Toss:
    *   X_coin = result of the coin toss game
    *   E[X_coin] = 0.5

*   Dice Roll:
    *   X_dice = result of the dice game
    *   E[X_dice] = 3.5

*   Combined Game:
    *   Total earnings = X_coin + X_dice
    *   E[Total earnings] = E[X_coin] + E[X_dice] = 0.5 + 3.5 = $4

*  **Key Property: If you have two variables and you add them, the expectation of the sum of the variables equals the sum of the expectations.**

**The Matching Names Problem:**

*   Problem: You have a bag with the names of every person in the world. Each person randomly receives a name from the bag. What is the expected number of people who will receive their own name?

*   Counterintuitive Result: The expected number of correct assignments is 1, regardless of the number of people.

**Simplified Example: Three People (Aisha, Beto, Cameron)**

1. List of six people.
2. The results of the people sum up to 6/6 = 1

*   Possible assignments:
    *   ABC (3 correct)
    *   ACB (1 correct)
    *   BAC (1 correct)
    *   BCA (0 correct)
    *   CAB (0 correct)
    *   CBA (1 correct)
*   Average number of correct assignments: (3 + 1 + 1 + 0 + 0 + 1) / 6 = 1

**Using Sum of Expectations:**

1.  For one variable, if there are three numbers, each variable is 1/3 of being correct.

2.  Define indicator variables:
    *   A = number of correct assignments for Aisha
    *   B = number of correct assignments for Beto
    *   C = number of correct assignments for Cameron

3.  Calculate individual expected values:
    *   E[A] = 1/3 (probability of Aisha getting her own name)
    *   E[B] = 1/3
    *   E[C] = 1/3

4.  Total expected matches:
    *   E[Matches] = E[A] + E[B] + E[C] = 1/3 + 1/3 + 1/3 = 1
In other words, **their expected values also add together. **

**Generalizing to Eight Billion People:**

1.  Let there be P1, P2, ... P8 billion in total, then: 1 / P1, plus 1/ P2
2.  The expected value for all people, divided by eight billion = 1.
3.  It always holds.

**Linearity of Expectation: The Rule**

> In general you have that the expected value of a sum of n variables is the sum of their expected values.

This means that the result is valid regardless of how many there are (this also doesn't depend on distribution either.)


## Variance: Measuring the Spread of a Distribution

This part introduces the concept of variance, which quantifies the spread or dispersion of a probability distribution.

**The Need for Variance:**

*   The expected value (mean) alone does not provide a complete picture of a distribution.
*   Two distributions can have the same mean but very different spreads.

**Example: Two Games with Expected Value of Zero**

1.  Game 1: Win/Lose $1 with equal probability.
2.  Game 2: Win/Lose $100 with equal probability.
 The answer is that 0 is the correct answer.

**Comparing The Distributions**

*   X1: They have the same expected value
*   X2: is the average of two which creates the 0 of expected values.

**Deviations from the Mean:**

*   Deviation: The difference between each value and the expected value.

**Average Deviation: Not Useful**

*   The average deviation is always zero because positive and negative deviations cancel each other out.

**Absolute Deviation:**

*   The formula: abs(x-u).
*   Use absolute value to make all the deviations positive.
*   However: This approach is not commonly used because absolute values are messy for mathematical properties.

**Squared Deviations: Variance**

*   Square the deviations instead of taking the absolute value: (x - E[X])^2
*   These values are all positive, without creating complicated operations for mathematical properties.

**Variance Formula:**

*   The expected squared deviation: The average value has the variance.

>*Remember, it always means that you are actually finding an average value.*

The formula contains for steps
find mean of x, then find the deviation. Then perform variance and then finally perform weighted deviation.
These are all the expected, and this shows the squared value between deviation and mean.

*   If the outcomes are weighted, make sure you use the probability distribution as weight.

**Example:**

*   If you have a similar value, this variance does the measure for the spread.
*   Game 1: Win/Lose $2 with equal probability
*   Game 2: -1 Dollar with one probability or +3 with equal probability.
You have a variance, however in game 1, its always going to be zero. Where games that happen in the future, where are some great areas of opportunity, are on what you know and learn in the past.

**The Alternative Formula: Easy Mathematical Function**

*   If you square in your mind the function, it equals to: E[x²]-(E[x])^2. This results in the linear outcome.

The steps are easy
e of x +1 equal e of x + B
Pulls the content side the expression.
e of x + 1
1 equal the outer and removes terms. This was an identity that most people forget over time.

**An important property by Variance:**

*  A relationship with Identity: 1/4 - E/x.
*  The random variables and are related to is why the variance will always be true.

**Takeaways from the Identity**
For the new random variable why will force is that 4 times as big: is always going to be. So what happens?

*  If all your deviations are bigger - the variance for the variable is four times as big. So in short;
*  *If you add - to the the value, there is variance*
*   *If they give it a value, it will have a big variance.*

**Final Conclusion from Variance**
 The variable that is in effect, is always squared, it is used for the following variance: you.
The explanation is to explain what what we are using a measuring point. And we need to start working on these concepts.

## Standard Deviation: Putting Spread in the Right Units

This part introduces the concept of standard deviation and its relationship to variance. Standard deviation provides a measure of spread that is in the same units as the original data.

**The Problem with Variance:**

*   Variance measures the spread of a distribution, but its units are squared (e.g., meters squared, feet squared).
*   This can be difficult to interpret.

**Solution: Standard Deviation**

*   Take the square root of the variance.
*   Standard Deviation (σ) = sqrt(Variance(X))
*   The formula for variance of X is: Square root (E (X- MEAN SQUARED))
*   In which can also be written as: 1 E(X SQUARED) - E(x).

**Benefits of Standard Deviation:**

*   The same units as the original data (e.g., meters, feet).
*   Easier to interpret.

**Normal Distribution and Standard Deviation:**

*   For a normal distribution:
   In an easy way, the numbers go high, but will also decrease as you approach a low score

*   If it is in a normal variable: it can do a sum with E from from x and y. However we need to measure both as well.

**Key Relationships:**

*   68% of the data falls within one standard deviation of the mean (μ ± σ).
*   95% of the data falls within two standard deviations of the mean (μ ± 2σ).
*   99.7% of the data falls within three standard deviations of the mean (μ ± 3σ).
*   All are measured for the deviation in certain points.

**More Specific Numbers:**
With all these numbers, we know how the measure is to provide how the spread to provide standard to work with.
These have to be the values when talking from statistics is the most useful
*   *68.2% falls within one standard deviation.*

*   *13.5% are all on intervals.*
*   *2.35% is on the point.*
*   *0.15% the tail.*

**Summary:**

Standard deviation provides a more interpretable measure of the spread of a distribution by expressing the spread in the same units as the original data. It is particularly useful for understanding the shape and characteristics of the normal distribution.

*  The final points need to extend which gives the variable data, it needs to be used.


## Adding Gaussian Distributions

This part explains what happens when you add two or more Gaussian distributions together, focusing on how the mean and variance of the resulting distribution are related to the means and variances of the original distributions.

**Scenario: Total Response Time of a Computer System**

*   Total Response Time (R) = Processing Time (T) + Network Latency (L)

**Modeling Processing Time and Network Latency:**

*   Processing Time (T): Gaussian distribution with mean μT = 10 milliseconds and standard deviation σT = 2 milliseconds.
*   Network Latency (L): Gaussian distribution with mean μL = 5 milliseconds and standard deviation σL = 1 millisecond.
* The total time is the amount of the time.

**Assumptions:**

*   T and L are independent of each other.

**Simulation:**

*   Sample 10,000 values from each Gaussian distribution (T and L).
*   Create a new dataset by adding each pair of sampled values (R = T + L).
*  Gaussian works with 10K variables and the amount of each.

**The Result:**

*   The histogram of the resulting R values (total response time) is also approximately Gaussian.

**Parameters of the Resulting Gaussian Distribution (R):**

1.  **Mean (μR):**
    *   E[R] = E[T + L]
    *   Since expectation is linear: E[R] = E[T] + E[L] = μT + μL = 10 + 5 = 15 milliseconds

2.  **Standard Deviation (σR):**
    *   Variance(R) = Variance(T + L)
    *   Since T and L are *independent*: Variance(T + L) = Variance(T) + Variance(L)
    *   σR = sqrt(Variance(T) + Variance(L)) = sqrt(σT^2 + σL^2) = sqrt(2^2 + 1^2) = sqrt(5) ≈ 2.236 milliseconds
Square the number = 4 then one the function, then add them to result the 2 power is added.
There is an assault for variables.

**Generalization: Linear Combination of Gaussian Variables**

*   If X and Y are independent Gaussian random variables with parameters (μX, σX) and (μY, σY), respectively, and a and b are constants:
* X and Y is to generate the result the is needed

  Then:

    *   Z = aX + bY follows a Gaussian distribution with:
    *   Mean (μZ) = aμX + bμY
    *   Variance (σZ^2) = a^2σX^2 + b^2σY^2
    *  A great formula to get the same results is (x^(A μ))/b = 2 X y is equal the parameters



## Centering and Scaling: Standardizing Distributions

This part explains how to standardize a distribution, transforming it to have a mean of zero and a standard deviation of one.

**Why Standardize?**

*   It is always a benefit, for a number variable if the variables have similar rates
*   Simplified form, always does better

**Centering a Distribution:**

1.  Starting a function as x = u is way easier
2.  Subtract the mean (μ) from each value: X - μ
3.  This creates a new distribution with a mean of zero.

**The Proof:**
if the function follows it's way to linear path, the expected value will equal zero.

**Scaling a Distribution:**
Having a distribution equal zero, you have the chance to make a function of 1.

*  If a function is at + Sigma/2 = - Signa/2 = it can take these function in the equation 0+1.

**Formula**
X - mu / signa

**Scaling in distribution**
If x has distribution Signa has a standard

The math works by following to:
The variant where to have. A constant.
Where e * 1 equal the outer.
Therefore, if a number with e is on a equal point, to know the deviation.
The variable where as it would work with any formula.

> Therefore you can see the number - -
**Final Conclusion from Function:** The constant value should be equal.

**Final Process For Standardization: A Distribution**
Therefore the data has the chance to improve its function.
These all function of the values:
Make a mean and scale it with 0. (Therefore it comes scaling)


## Moments of a Distribution

*   **Beyond Expectation and Variance:**  While expectation and variance give a good overview, they don't capture all subtleties of a distribution (e.g., skewness, kurtosis).

*   **Moments Defined:**
    *   The *k*th moment of a random variable *X* is the expected value of *X* raised to the power of *k*:  E[*X*<sup>*k*</sup>].
    *   **First Moment:** E[*X*] (the expected value or mean).
    *   **Second Moment:** E[*X*<sup>2</sup>] (related to the variance).
    *   **Third Moment:** E[*X*<sup>3</sup>] and so on.

*   **Calculation:**  For a discrete random variable with values *x<sub>i</sub>* and probabilities *p<sub>i</sub>*:
    *   *k*th moment = Σ (*p<sub>i</sub>* *x<sub>i</sub>*<sup>*k*</sup>) (sum over all *i*)

*   **Upcoming Use:**  Moments will be used to analyze distribution characteristics like skewness and kurtosis later.



# Skewness: Telling Apart Distributions with Same Mean and Variance

*   **Problem:**  Expected value (mean) and variance can be identical for vastly different probability distributions (e.g., lottery vs. insurance).

*   **Solution:** Use the third moment, E[X^3], to detect skewness.

*   **Skewness:**
    *   **Positive Skew:** Distribution has values far to the right (e.g., lottery). E[X^3] is large and positive.
    *   **Negative Skew:** Distribution has values far to the left (e.g., car insurance). E[X^3] is large and negative.
    *   **Zero Skew:** Distribution is symmetric. E[X^3] is close to zero.

*   **Standardized Skewness:** E[ (X - μ) / σ ]^3 measures skewness more precisely by centering and scaling the data.

**Example:**

*   **Lottery vs. Insurance:**

    *   **Lottery:** Small probability of a large gain (positive skew).
    *   **Insurance:** Small probability of a large loss (negative skew).

    Even if the expected value and variance are the same for both scenarios, skewness differentiates them. The lottery winnings are skew to the right and losses for insurance are skew to the left.

# Kurtosis: The Fourth Moment

**What it is:** Kurtosis measures the "tailedness" of a probability distribution, specifically how prone it is to producing outliers. It uses the fourth moment to quantify the presence of extreme values.

**Why it's important:** Even if distributions share the same mean, variance, and skewness, kurtosis can differentiate them based on tail thickness.

**How it works:**

*   **High Kurtosis (Leptokurtic):**  "Thick tails," meaning more frequent and extreme outliers.
*   **Low Kurtosis (Platykurtic):**  "Thin tails," meaning fewer and less extreme outliers.

**Example:**

*   **Game 1:** Win or lose $1 with 50% probability.
*   **Game 2:** High probability of small wins/losses (±$0.10), with a small probability of large wins/losses (±$10).

    Games 1 and 2 may have the same mean, variance, and skewness. However, Game 2 has a higher kurtosis because it is more likely to produce extreme values due to the ±$10 outcomes. This highlights how kurtosis captures the tail behavior.

# Visualizing Data: Quantiles

**What it is:** Quantiles divide a dataset into segments based on percentile values. This allows for a more detailed understanding of data distribution beyond simple averages.

**Why it's important:** Quantiles provide a way to summarize and visualize how data is spread, highlighting key values like the median and quartiles.

**How it works:**

1.  **Sort the Data:** Arrange the data in ascending order.

2.  **Determine the Quantile:**  The *k*% quantile (q<sub>k/100</sub>) is the value that has *k*% of the data below it and (100-*k*%) above it.

**Common Quantiles:**

*   **Q1 (First Quartile or 25th Percentile):** Separates the bottom 25% from the top 75%.
*   **Q2 (Second Quartile or 50th Percentile or Median):** Separates the bottom 50% from the top 50%.
*   **Q3 (Third Quartile or 75th Percentile):** Separates the bottom 75% from the top 25%.

**Example:**

*Newspaper Ad Budget (12 samples, sorted)*: 5, 10, 12, 15, 18, 19, 20, 28, 30, 32, 35, 40

*   **Median (Q2):** (19 + 20) / 2 = 19.5
*   **Q1:** (12 + 15) / 2 = 13.5
*   **Q3:** (30 + 32) / 2 = 31


# Visualizing Data: Box Plots (Box and Whiskers)

**What it is:** A standardized way to visualize the distribution of data using five key statistics: minimum, maximum, median (Q2), first quartile (Q1), and third quartile (Q3).

**Why it's important:** Box plots quickly show the spread, center, and skewness of data, while also identifying potential outliers.

**How to create a Box Plot:**

1.  **Calculate Quartiles:** Find Q1, Q2 (median), and Q3.
2.  **Calculate Interquartile Range (IQR):** IQR = Q3 - Q1
3.  **Draw the Box:** The box extends from Q1 to Q3. Draw a line inside the box at the median (Q2).
4.  **Draw the Whiskers:**
    *   Lower Whisker: Extends from Q1 to the smallest value within 1.5 * IQR below Q1. If no data point exists within that range, the whisker extends to the minimum value in the dataset.
    *   Upper Whisker: Extends from Q3 to the largest value within 1.5 * IQR above Q3. If no data point exists within that range, the whisker extends to the maximum value in the dataset.
5.  **Identify Outliers:** Data points outside the whiskers are considered outliers.

**Example:**

*Newspaper Ad Budget (Full dataset)*:

*   Minimum: 0.3
*   Maximum: 114
*   Q1:  ...
*   Q2:  ...
*   Q3:  ...
*   IQR: ...
* Outlier limit:  Q3 + 1.5 * IQR = 93.626
* So if the largest point in data set is greater than 93.626 then that point is outlier.

*Box Plot Interpretation:*

*   **Skewness:** Unequal distances between Q1-Q2 and Q2-Q3 indicate skewness.
*   **Dispersion:** Length of the box and whiskers represents data spread.
*   **Outliers:** Points outside the whiskers signal potential anomalies.

# Visualizing Data: Kernel Density Estimation (KDE)

**What it is:** A non-parametric method to estimate the probability density function (PDF) of a continuous random variable from a dataset. It creates a smooth curve that represents the underlying distribution of the data.

**Why it's important:** KDE provides a smoother and potentially more accurate representation of the PDF compared to histograms, especially when dealing with limited data.

**How it works:**

1.  **Choose a Kernel:** Select a kernel function (e.g., Gaussian). This function determines the shape of the "mountain" placed at each data point.

2.  **Kernel Placement:**  Place a kernel function centered at each data point in the dataset.  The "bandwidth" (σ in the case of a Gaussian kernel) controls the spread of each kernel.  Smaller bandwidths result in more peaked densities, while larger bandwidths result in smoother densities.

3.  **Sum and Normalize:** Sum all the kernels and divide by the number of data points (n) to normalize the result. This ensures the area under the resulting curve is equal to one, fulfilling the PDF property.

**Example:**

*Newspaper Ad Budget*: Instead of a histogram, KDE would place a "Gaussian mountain" centered on each newspaper ad budget data point. A higher data density results in a taller estimated PDF, indicating more frequent values in that region.  The bandwidth controls how wide each Gaussian curve is, impacting the smoothness of the final KDE estimate.

**Advantages of KDE over Histograms:**

*   **Smoothness:**  KDE produces a smooth, continuous estimate of the PDF, unlike the step-like appearance of histograms.
*   **Less Sensitive to Binning:** KDE doesn't require choosing specific bin sizes, which can influence the appearance of histograms.

# Visualizing Data: Violin Plots

**What it is:** A hybrid visualization that combines the benefits of kernel density estimation (KDE) and box plots.

**Why it's important:** Violin plots provide a richer understanding of data distribution compared to either KDE or box plots alone. They show both the shape of the distribution (like KDE) and key statistics like quartiles and outliers (like box plots).

**How it works:**

A violin plot essentially displays a KDE plot mirrored on both sides of a box plot. The components of a violin plot are:

1.  **KDE Plot:** Shows the estimated probability density of the data (similar to a KDE visualization). The width of the violin represents the density of data points at that value.

2.  **Box Plot:** Displays the median, quartiles (Q1 and Q3), and whiskers (as in a standard box plot).

**Example:**

Imagine a violin plot of newspaper ad budgets. The wide parts of the "violin" indicate regions where the data is more densely concentrated. The box plot in the middle reveals the median, quartiles, and potential outliers.

**Advantages of Violin Plots:**

*   **Comprehensive View:** Combines shape, center, spread, and outliers.
*   **Easy Comparison:**  Allows for easy comparison of distributions across different groups or categories.
*   **Reveals Modality:** Shows whether the distribution is unimodal (one peak), bimodal (two peaks), or multimodal (multiple peaks), which can be missed by box plots alone.

# Checking for Normality: QQ Plots

**What it is:** Quantile-Quantile plots (QQ plots) are a graphical tool to assess whether a dataset follows a normal (Gaussian) distribution.

**Why it's important:** Many statistical models and tests assume data is normally distributed. QQ plots provide a visual way to check this assumption.

**How it works:**

1.  **Standardize Data:** Subtract the mean and divide by the standard deviation to standardize the dataset.
2.  **Calculate Quantiles:** Determine the quantiles of the standardized data.
3.  **Theoretical Quantiles:** Calculate the corresponding quantiles from a standard normal distribution (mean=0, standard deviation=1).
4.  **Scatter Plot:** Create a scatter plot with theoretical quantiles on the x-axis and the sample quantiles on the y-axis.

**Interpretation:**

*   **Normally Distributed Data:** If the data is normally distributed, the points on the QQ plot will fall close to a straight diagonal line (often shown in orange).
*   **Deviations from Normality:** Deviations from the straight line indicate departures from normality. Patterns in these deviations can reveal skewness, heavy tails, or other non-normal characteristics.

**Example:**

*Newspaper Budget Data*: The QQ plot might show points deviating significantly from the diagonal line, especially in the tails, suggesting the newspaper budget data is NOT normally distributed. Skewness might also be evident by the concentration of data points on one side than the other of that orange line.

*Sales Data*: A QQ plot of the sales data shows the quantiles closely aligned with the diagonal line, indicating the sales data is likely Gaussian.