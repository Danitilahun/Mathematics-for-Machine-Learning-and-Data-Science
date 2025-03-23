# Table of Contents

1.  [Joint Probability Distributions](#joint-probability-distributions)
    *   What are they?
    *   Why are they important?
    *   Discrete Joint Distribution
        *   Example:
        *   Example Questions

2.  [Joint Probability Distributions: Examples](#joint-probability-distributions-examples)
    *   Example 1: Independent Dice Rolls
    *   Example 2: Dependent Dice Rolls (Sum of Dice)

3.  [Joint Probability Distributions: Continuous Variables](#joint-probability-distributions-continuous-variables)
    *   What are they?
    *   Why are they important?
    *   Understanding Jointly Continuous Distributions
    *   Example: Call Waiting Time and Customer Satisfaction
    *   Calculations

4.  [Marginal Distributions](#marginal-distributions)
    *   What is it?
    *   Why is it important?
    *   How to obtain it (Discrete variables):
    *   Examples
    *   Continuous Joint Distribution

5.  [Conditional Distributions](#conditional-distributions)
    *   What is it?
    *   Why is it important?
    *   How to obtain it (Discrete Variables):
    *   Example:
    *   Continuous Joint Distribution:

6.  [Covariance and Correlation](#covariance-and-correlation)
    *   What is Covariance?
    *   Why is it important?
    *   How to Calculate Covariance:
    *   Interpretation of Covariance:
    *   Example: Age vs. Height, Grades, and Naps

7.  [Covariance Examples and Calculations](#covariance-examples-and-calculations)
    *   Example Games with Players X and Y
    *   Covariance in Call Wait Time vs Rating

8.  [Correlation Coefficient](#correlation-coefficient)
    *   What is it?
    *   Why is it important?
    *   How to Calculate the Correlation Coefficient:
    *   Interpretation of the Correlation Coefficient:

9.  [The Multivariate Gaussian Distribution](#the-multivariate-gaussian-distribution)
    *   What is it?
    *   Why is it important?
    *   Univariate vs. Multivariate Gaussian:
    *   Key Concepts in the Multivariate Gaussian:
    *   Independent vs. Dependent Variables:


# Joint Probability Distributions

**What are they?**

Joint probability distributions describe the probability of two or more random variables taking on specific values *together*. Instead of looking at the distribution of a single variable (like height), we consider the distribution of multiple variables (like height *and* age).

**Why are they important?**

They allow us to understand the relationships between variables and how they influence each other.

**Discrete Joint Distribution:**

*   **Example:** Age and height of children (both discrete variables).
*   **Construction:**

    1.  Create a table with all possible combinations of variable values (e.g., age 7 and height 45, age 7 and height 46, etc.).
    2.  Count how many times each combination occurs in your dataset. This gives you a "joint count."
    3.  Divide each joint count by the total number of data points to get the joint probability.
*   **Notation:**  P(X=x, Y=y) represents the probability that variable X takes on the value x *and* variable Y takes on the value y.
*   **Interpretation:** Each cell in the probability table represents the likelihood of observing that particular combination of variable values.

**Example:**

Let's say we have this joint probability distribution of Children Age and Height. The total children is 10.
| Age (X) | Height (Y) | Count | P(X=x, Y=y) |
|---|---|---|---|
| 7 | 45 | 1 | 0.1 |
| 7 | 46 | 2 | 0.2 |
| 8 | 47 | 2 | 0.2 |
| 9 | 49 | 3 | 0.3 |
| 9 | 50 | 1 | 0.1 |
| 10 | 50 | 1 | 0.1 |

**Example Questions**:

*   *What's the probability that a child is 8 years old and 48 inches tall?* Answer: P(X=8, Y=48) = 0, assuming there are zero children in our sample with age 8 and height 48.
*   *What's the probability that a child is 7 years old and 46 inches tall?* Answer: P(X=7, Y=46) = 0.2

**Continuous Joint Distribution**
There also a continuous joint distribution where you would use the joint probability distribution function.

# Joint Probability Distributions: Examples

**Example 1: Independent Dice Rolls**

*   **Variables:**
    *   X: Number rolled on the first die (1, 2, 3, 4, 5, 6).
    *   Y: Number rolled on the second die (1, 2, 3, 4, 5, 6).
*   **Independence:** X and Y are independent (the outcome of one die doesn't affect the other).
*   **Probability Mass Function (PMF):**
    *   P(X=x) = 1/6 for all x (1 to 6).
    *   P(Y=y) = 1/6 for all y (1 to 6).
*   **Joint PMF:**
    *   P(X=x, Y=y) = P(X=x) * P(Y=y) = (1/6) * (1/6) = 1/36 for all combinations of x and y.
    *   The joint PMF is a table where every cell has the value 1/36.

**Example 2: Dependent Dice Rolls (Sum of Dice)**

*   **Variables:**
    *   X: Number rolled on the first die (1, 2, 3, 4, 5, 6).
    *   Y: Sum of the numbers rolled on both dice.
*   **Dependence:** X and Y are dependent because Y is directly determined by X *and* the outcome of the second die.
*   **Probability Mass Function (PMF):**
    *   P(X=x) = 1/6 for all x (1 to 6).
    *   P(Y=y) depends on the possible sums: Y ranges from 2 to 12, and the probabilities are not uniform (e.g., P(Y=7) is higher than P(Y=2)).
*   **Joint PMF:**  P(X=x, Y=y)

    *   The joint PMF is *not* simply the product of individual PMFs because X and Y are not independent. Instead, you need to carefully consider what combinations of values are possible. If they are not possible, it's 0.
    *   The table is one over 36 for the values that are possible.
*   **Example:**

    *   P(X=3, Y=7) = 1/36 (One way to roll sum of 7 given you rolled a 3)
    *   P(X=1, Y=1) = 0 (Impossible because you cannot roll two dice whose sum is one)

# Joint Probability Distributions: Continuous Variables

**What are they?**

Joint distributions for continuous variables describe the probability of two or more continuous random variables taking on specific values *simultaneously*.  This extends the concept of single-variable probability density functions (PDFs) to multiple variables.

**Why are they important?**

They allow us to model and understand the relationships between continuous variables that occur together (e.g., waiting time and customer satisfaction).

**Understanding Jointly Continuous Distributions:**

*   Instead of discrete counts, you have a *joint probability density function* (joint PDF).
*   **Interpretation:** The joint PDF tells you the *relative likelihood* of observing particular combinations of values for the variables.
*   **Probability:** The probability of X and Y falling within a certain two-dimensional region.  It is the double integral of the joint PDF over that region.

**Example: Call Waiting Time and Customer Satisfaction**

*   **Variables:**

    *   X: Waiting time for a call to be picked up (0-10 minutes, continuous).
    *   Y: Customer satisfaction rating (0-10, continuous).
*   **Data:** A dataset of 1000 customers with both waiting time and satisfaction ratings recorded.
*   **Visualization:**
    *   **Scatter Plot:**  Each point represents one customer, with X and Y coordinates indicating their waiting time and satisfaction rating.
    *   **Heatmap:** A visual representation of the density of data points in the scatter plot. Darker areas indicate higher density.
    *   **3D Plot:**  The height of the surface represents the probability density at a given (x,y) coordinate.
*   **Key Observations:** The distribution shows high densities in areas of very quick call pick-ups and very long wait times (with associated very low satisfaction).

**Calculations:**

*   **Expected Value/Mean:** Calculated to find the centre value that describes time spent before call pick and average satisfaction rate.
*   **Variance:** Calculated for both X and Y after segregation based on rows and columns.

# Marginal Distributions

**What is it?**

A marginal distribution represents the probability distribution of *one* variable from a joint distribution, completely disregarding the other variables. It's like collapsing a multi-dimensional distribution into a single dimension.

**Why is it important?**

It allows you to focus on the distribution of a single variable of interest, independent of the other variables in the joint distribution.

**How to obtain it (Discrete variables):**

1.  **Start with the joint distribution:** A table showing P(X=x, Y=y) for all possible combinations of x and y.

2.  **Sum over the unwanted variable:**

    *   To get the marginal distribution of X (P(X=x)), sum the probabilities for each value of x across all possible values of y.
    *   To get the marginal distribution of Y (P(Y=y)), sum the probabilities for each value of y across all possible values of x.

    Formulas:

    *   P(X = x<sub>i</sub>) = Σ<sub>j</sub> P(X = x<sub>i</sub>, Y = y<sub>j</sub>) (Sum over all j)
    *   P(Y = y<sub>j</sub>) = Σ<sub>i</sub> P(X = x<sub>i</sub>, Y = y<sub>j</sub>) (Sum over all i)
* In short, sum up the probability for the other variable and you can get the marginal of your target.

**Examples**

Consider a data set of 10 children with ages and height.
| Age (X) | Height (Y) | Count | P(X=x, Y=y) |
|---|---|---|---|
| 7 | 45 | 1 | 0.1 |
| 7 | 46 | 2 | 0.2 |
| 8 | 47 | 2 | 0.2 |
| 9 | 49 | 3 | 0.3 |
| 9 | 50 | 1 | 0.1 |
| 10 | 50 | 1 | 0.1 |

Here the marginal distributions will be:
*   Marginal distribution of Age (X) = Sum of row
P(7) = 0.1 + 0.2 = 0.3
P(8) = 0.2
P(9) = 0.3+0.1 = 0.4
P(10) = 0.1

*   Marginal distribution of Height (Y) = Sum of column
P(45) = 0.1
P(46) = 0.2
P(47) = 0.2
P(49) = 0.3
P(50) = 0.1+0.1=0.2

**Examples**

In one of the examples, they had the joint probability matrix for die roll 1 vs sum of two dice rolls. In this situation, after summing, we will get back the probability of different totals of two dice rolls. So if we knew that P(10)=3/36 and the original numbers, its useful.

**Continuous Joint Distribution**
Can also do marginal distributions in continuous variables by getting probabilities on either the columns and the rows, to reduce highly dimensional values into dimensionals.


# Conditional Distributions

**What is it?**

A conditional distribution describes the probability distribution of one variable *given* that you know the value of another variable. It's like zooming in on a specific slice of the joint distribution.

**Why is it important?**

It allows you to understand how the distribution of one variable changes based on the knowledge of another variable.

**How to obtain it (Discrete Variables):**

1.  **Start with the joint distribution:** A table showing P(X=x, Y=y) for all possible combinations of x and y.

2.  **Fix the value of one variable:** Suppose you want the conditional distribution of Y *given* that X = x*. Select the row corresponding to X = x* in the joint distribution table.

3.  **Normalize:** Divide each probability in the selected row by the sum of all probabilities in that row (the marginal distribution P(X = x*)).  This ensures that the conditional distribution sums to 1.
    
    Formula:
    
   *  P(Y = y | X = x) = P(X = x, Y = y) / P(X = x)

**Example:**

Let's use the same data as before

| Age (X) | Height (Y) | Count | P(X=x, Y=y) |
|---|---|---|---|
| 7 | 45 | 1 | 0.1 |
| 7 | 46 | 2 | 0.2 |
| 8 | 47 | 2 | 0.2 |
| 9 | 49 | 3 | 0.3 |
| 9 | 50 | 1 | 0.1 |
| 10 | 50 | 1 | 0.1 |

Find the conditional distribution for ages where there is X = 9
1. find joint P(X=9,Y) : (0.3,0.1)
2. Sum  the value of P(X=9) = 0.3+0.1 = 0.4
3. Normalized P(Y|X=9) = (0.3/0.4,0.1/0.4) = (0.75,0.25)
In conclusion, the chances of height given the age is now normalized into their probabilities.
P(Height = 49|Age = 9) = 0.75
P(Height = 50|Age = 9) = 0.25

**Continuous Joint Distribution:**

1. find conditional pdf
2. make a slice for the graph
3. normalize to the conditional pd


# Covariance and Correlation

**What is Covariance?**

Covariance measures the degree to which two random variables change together. It indicates the direction (positive or negative) of the linear relationship between them.

**Why is it important?**

Covariance helps us understand how two variables relate, which is useful for building models and making predictions.

**How to Calculate Covariance:**

1.  **Calculate the means:** Find the mean (expected value) of each variable, E[X] and E[Y].
2.  **Center the data:** Subtract the mean from each value of each variable: (x<sub>i</sub> - E[X]) and (y<sub>i</sub> - E[Y]).
3.  **Multiply centered values:** Multiply the centered values for each pair of observations: (x<sub>i</sub> - E[X]) * (y<sub>i</sub> - E[Y]).
4.  **Average the products:** Calculate the average of these products:

   Cov(X, Y) = E[(X - E[X]) * (Y - E[Y])] = ∑ [(x<sub>i</sub> - E[X]) * (y<sub>i</sub> - E[Y])] / n

Where n is the number of observations.

**Interpretation of Covariance:**

*   **Positive Covariance:** Indicates a positive relationship. When X is above its mean, Y tends to be above its mean, and vice versa.
*   **Negative Covariance:** Indicates a negative relationship. When X is above its mean, Y tends to be below its mean, and vice versa.
*   **Covariance Close to Zero:** Indicates a weak or no linear relationship.

**Example: Age vs. Height, Grades, and Naps**

*   X = Age of a child
*   Y<sub>1</sub> = Height of the child
*   Y<sub>2</sub> = Grades in a test
*   Y<sub>3</sub> = Number of naps per day

| Variable | Covariance | Interpretation |
|---|---|---|
| Age vs. Height | Positive (17) | As age increases, height tends to increase. |
| Age vs. Grades | Close to Zero (0.1) | Little to no linear relationship between age and grades. |
| Age vs. Naps | Negative (-7.45) | As age increases, the number of naps tends to decrease. |

*Covariance captures correlation, since high and low values will be different depending on the points, to either be one or the other depending*



# Covariance Examples and Calculations

**Example Games with Players X and Y**

*   **Game 1:** Players X and Y both win $1 or lose $1 (with probability 1/2 each).
*   **Game 2:** One player wins $1 and the other loses $1 (with probability 1/2 each).
*   **Game 3:** Any combination of wins and losses is possible (probability 1/4 each).
*   **Analysis:**
    *   E[X] = E[Y] = 0 for all three games (the expected gain for each player is zero).
    *   Variance(X) = Variance(Y) = 1 for all three games (same level of risk for each player in each game).
    *   COVARIANCE:
        1.  Game 1: +1
        2.  Game 2: -1
        3.  Game 3: 0

What happens if there is a probability of not receiving anything too

*   **Game 4:** Both players win $1 (probability 1/2), both lose $1 (probability 1/3), or nothing happens (probability 1/6)
    *   What is the covariance?
        1.  E(XY)  - ( EX EY)

**Covariance in Call Wait Time vs Rating**
In the final review, we are asking is the variables are linked?
If two parameters are not related, the end sum will be zero
In this scenario, it is equal and has two.  So the function will be 7-87-8 for the number. So the end result will be positive, because each of them help out.
Covariance Formula;
In general is is all summed, to all value
Covariance of +1 to -1 to check the data
However: If you have these two numbers the variable of the end equation will provide these two numbers. With this example, the equation needs both of the numbers.


# Correlation Coefficient

**What is it?**

The correlation coefficient is a standardized measure of the linear relationship between two random variables. It indicates both the strength and direction of the linear association.

**Why is it important?**

While covariance tells us the direction of the relationship, it's difficult to compare covariances across different datasets because it's not standardized. The correlation coefficient solves this problem by scaling the covariance to a range between -1 and 1.

**How to Calculate the Correlation Coefficient:**

1.  **Calculate the Covariance:**  Cov(X, Y) (as described in the previous note).
2.  **Calculate the Standard Deviations:** σ<sub>X</sub> and σ<sub>Y</sub> (the square root of the variance of X and Y, respectively).
3.  **Divide:**

    Correlation(X, Y) = Cov(X, Y) / (σ<sub>X</sub> * σ<sub>Y</sub>)

**Interpretation of the Correlation Coefficient:**

*   **+1:** Perfect positive correlation. As X increases, Y increases linearly.
*   **-1:** Perfect negative correlation. As X increases, Y decreases linearly.
*   **0:** No linear correlation. X and Y are not linearly related.  (Note: They may have a non-linear relationship.)
*   **Values between -1 and +1:** Indicate varying degrees of positive or negative linear correlation. The closer the value is to -1 or +1, the stronger the linear relationship.

**Examples:**

| Relationship | Covariance (Example) | Standard Deviations | Correlation Coefficient | Interpretation |
|---|---|---|---|---|
| Age vs. Naps | -7.45 |  | -0.894 | Strong negative linear correlation. |
| Age vs. Height | 17 | | 0.893 | Strong positive linear correlation. |
| Age vs. Grades | 0.1 |  | 0.01 | Very weak linear correlation. |
| Waiting Time vs Rating |  |  | negative 0.845 | Pretty Negatively Correlated |

**Note:**

*   The correlation coefficient only measures *linear* relationships. Two variables can be related in a non-linear way even if their correlation coefficient is zero.


# The Multivariate Gaussian Distribution

**What is it?**

The multivariate Gaussian distribution extends the familiar normal (Gaussian) distribution to multiple variables. It describes the joint probability distribution of several random variables that are normally distributed.

**Why is it important?**

It is widely used in statistics, machine learning, and other fields because:

*   Many real-world phenomena can be approximated by a multivariate Gaussian.
*   It has useful mathematical properties that make it tractable for analysis and modeling.
*   It is a building block for many advanced techniques.

**Univariate vs. Multivariate Gaussian:**

| Feature | Univariate Gaussian | Multivariate Gaussian |
|---|---|---|
| Variables | Single variable (x) | Multiple variables (x1, x2, ..., xn) |
| Parameters | Mean (μ), Standard Deviation (σ) | Mean Vector (μ), Covariance Matrix (Σ) |
| PDF Formula |  |  |
|  | f(x) = (1 / (σ√(2π))) * exp(-(x - μ)² / (2σ²)) | f(x) = (1 / ((2π)^(n/2) * √(det(Σ)))) * exp(-0.5 * (x - μ)<sup>T</sup> * Σ<sup>-1</sup> * (x - μ)) |

**Key Concepts in the Multivariate Gaussian:**

*   **Mean Vector (μ):** A vector containing the means of each individual variable.
*   **Covariance Matrix (Σ):** A matrix that describes the variances of each variable (on the diagonal) and the covariances between pairs of variables (off-diagonal).
*   **Determinant of the Covariance Matrix (det(Σ)):**  Captures the overall "volume" or spread of the distribution. A larger determinant indicates a greater spread.
*   **Inverse of the Covariance Matrix (Σ<sup>-1</sup>):** Used to standardize and rescale the variances and covariances.

**Independent vs. Dependent Variables:**

*   **Independent Variables:** The covariance matrix is diagonal (off-diagonal elements are zero).
*   **Dependent Variables:** The covariance matrix has non-zero off-diagonal elements, indicating the covariances between variables.

**Key Takeaways:**

*   The multivariate Gaussian is characterized by its mean vector and covariance matrix.
*   The covariance matrix captures the relationships between the variables.
*   The formula may look intimidating, but it's simply a generalization of the univariate Gaussian formula, with scalars replaced by vectors and the variance replaced by the covariance matrix.

