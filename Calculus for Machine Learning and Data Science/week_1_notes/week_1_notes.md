## Calculus for Machine Learning and Data Science (Course 2 Overview)

**Focus:** Calculus concepts essential for machine learning, particularly derivatives and optimization techniques.

**Key Concepts Covered:**

*   **Derivatives:** Understanding what derivatives mean, how they work, and their applications in machine learning.
*   **Optimization:** Maximizing and minimizing functions (cost functions) – a central task in machine learning.
*   **Gradients:** Using gradients to find the direction of steepest descent for optimization.
*   **High-Dimensional Spaces:** Understanding derivatives and calculus in very high-dimensional spaces (thousands or millions of dimensions), common in machine learning.
*   **Second Derivatives:** Learning about second derivatives and their connection to the curvature of the space (using matrices).
*   **Newton's Method:** A powerful optimization technique that can converge to a minimum much faster than gradient descent in some cases (but not universally applicable).

**Why Calculus is Important for Machine Learning:**

*   **Cost Function Minimization:** Machine learning models are trained by defining a cost function (measuring the error) and then minimizing it using calculus-based techniques.
*   **Algorithm Intuition:** Understanding the calculus behind optimization algorithms (like gradient descent) provides a deeper understanding of how these algorithms work and why they make the decisions they do.
*   **Direction Guidance:** Derivatives (gradients) provide the direction for taking small steps towards lower (or higher) values of a function.

**Benefits of the Course:**

*   **Conceptual Understanding:**  Gain a solid grasp of the fundamental concepts of calculus.
*   **Practical Implementation:**  Run code labs and notebooks to see calculus concepts working in real-time.
*   **Code Snippets:**  Develop a library of code snippets that can be used in your own machine learning projects.
*   **Toolkit of Techniques:** Learn about various optimization methods (gradient descent, Newton's method) to have a flexible toolkit for different scenarios.


## Calculus for Machine Learning: Week 1 Overview

**Focus:** Intuition behind derivatives, basic functions, derivative rules, and optimization in machine learning.

**Topics Covered:**

*   **Speedometer Example:** Introduction to the derivative concept using velocity.
*   **Derivatives of Basic Functions:**
    *   Constant function
    *   Linear functions
    *   Quadratic polynomials
    *   Exponential functions
    *   Logarithmic functions
*   **Derivative Rules:**
    *   Sum rule
    *   Product rule
    *   Chain rule
    *   Multiplication by scalars
*   **Optimization:**
    *   Maximize and minimize functions using derivatives.
    *   Finding the maximum and minimum values of a function.
*   **Loss Functions:**
    *   Calculating a loss function to assess the performance of a model.
    *   Minimizing the loss function to find the best model fit.
*   **Examples of Minimizing Functions:**
    *   Temperature example
    *   Square loss
    *   Log loss

**Motivating Examples:**

1.  **Linear Regression (House Price Prediction):**

    *   **Problem:** Predict the price of a house based on the number of bedrooms.
    *   **Data:** Number of bedrooms and corresponding house prices (training data).
    *   **Missing Data:** A house with nine bedrooms is missing its price.
    *   **Model Training:** The machine learning model learns a relationship (a line) that best fits the training data.
    *   **Prediction:** After training, the model predicts the price of the nine-bedroom house.
    *   **Model Representation:** A line on a graph (number of bedrooms vs. price).
    *   **Goal:** Find the line that goes as close as possible to all the data points.
    *   **Training Process:** Starting with a random line, tweaking the results to optimize the best possible prediction.
    *   **Outcome:** Predicting that a house with 9 bedrooms will cost $950,000.

2.  **Sentiment Analysis (Alien Mood Classification):**

    *   **Problem:** Determine if an alien is happy or sad based on their sentences ("aack," "beep").
    *   **Data:** Sentences, frequency of words "aack" and "beep," and the alien's mood (happy or sad).
    *   **Goal:** Classify sentences as happy or sad.
    *   **Model Representation:** A line that splits apart the happy points and the sad points on the graph.
    *   **Process:** Training the model to find the ideal line that best separates the happy and sad data points.
    *   **Classification:** A new sentence is classified based on which area it falls into (happy or sad).
    *   **Potential Errors:** The model may make mistakes, but it generally performs well based on training data.

**Key Mathematical Concepts Driving Model Training:**

*   Gradients
*   Derivatives
*   Optimization
*   Loss and Cost Functions
*   Gradient Descent

**Application of Concepts:**

*   Model Training
*   Optimization
*   Core Mathematical Techniques
*   Used in Various Machine Learning Algorithms (e.g., neural networks)

## Derivatives: The Velocity Example

**Core Idea:** A derivative is the instantaneous rate of change of a function.

**The Speedometer Scenario:**

1.  **Average Velocity:** Traveling 100 kilometers in 1 hour results in an *average* velocity of 100 km/h. This doesn't account for variations in speed over the hour.

2.  **Instantaneous Velocity:** The velocity at a *specific instant* in time. This is what the derivative calculates.

**Detailed Example:**

*   Driving a car on a straight road.
*   Speedometer breaks, but you have an app showing distance traveled.
*   Collecting data on distance traveled every 5 seconds for 1 minute.

**Quiz 1: Constant Speed?**

*   **Question:** Is the car moving at a constant speed?
*   **Answer:** No. The distance traveled in each 5-second interval varies.

**Quiz 2: Velocity at t=12.5 seconds?**

*   **Question:** Can you determine the *exact* velocity at t=12.5 seconds using the data?
*   **Answer:** No. You can only find the *average* velocity over a time interval. You don't know what happened at that precise moment.

**Quiz 3: Average Velocity (10-15 seconds)**

*   **Question:** What was the average velocity of the car in the interval from 10-15 seconds?
*   **Explanation:**
    *   The average velocity is represented by the slope of the line joining the data points for those two times on a distance-vs-time graph.
    *   `Velocity = Distance / Time = Rise / Run`
    *   Distance at 15 seconds: 202 meters
    *   Distance at 10 seconds: 122 meters
    *   Time Interval: 5 seconds
    *   Change in distance (Rise): 202 - 122 = 80 meters
    *   Average Velocity (Slope): 80 / 5 = 16 meters per second

**Improving the Estimate:**

*   Having more data points (distance traveled every second) provides a better estimate.
*   The average velocity between 12 seconds and 13 seconds offers a more precise approximation of the instantaneous velocity at t=12.5 seconds.
*   **Formula:** `Velocity = (Distance at 13 - Distance at 12) / (Time at 13 - Time at 12)`
*   Using the new data yields a slope of 15 meters per second, closer to the actual velocity at that specific instant.

**Derivative and Finer Intervals:**

*   Take finer and finer intervals. The better the smaller time intervals, the better the estimate of instantaneous velocity.
*   Ultimately, this leads to the derivative concept, which calculates the velocity for time intervals that approach zero, as opposed to the time intervals of one or five that were used here.

## Derivatives: Instantaneous Rate of Change

**Building on the Velocity Example:**

*   Previous video: Calculating *average* velocity over an interval.
*   This video: Defining *instantaneous* velocity at a specific point (t=12.5 seconds).

**Estimating Instantaneous Velocity:**

1.  **Average Velocity Over Intervals:**
    *   Take a point to the *right* of t=12.5 and calculate the average velocity over that interval (slope of the line connecting the two points).
    *   `Average Velocity = Delta x / Delta t` (change in distance / change in time)
    *   This is *not* the instantaneous velocity at t=12.5, but an approximation.

2.  **Smaller Intervals, Better Estimates:**
    *   Make the interval smaller by taking points closer to t=12.5.
    *   The average velocity of the *new, smaller* interval is a better estimate of the instantaneous velocity.
    *   Repeat the process with even smaller intervals.

3.  **The Limit (The Derivative):**
    *   Imagine making the interval so small that you can barely distinguish the two points.
    *   Take the *limit* as the interval size approaches zero.
    *   This limit is expressed as `dx / dt`.

4.  **Tangent Line:**
    *   The limit `dx / dt` is precisely the slope of the *tangent line* to the distance-vs-time curve at t=12.5.

**Formal Definition of the Derivative:**

*   The instantaneous rate of change of a function.
*   The measure of how fast the relationship between two variables is changing at any given point.
*   Imagine a tiny change in x (dx) over a tiny change in t (dt).
*   The derivative is also called the *instantaneous rate of change*.
*   The derivative of a function *at a point* is the slope of the tangent line *at that point*.

## Derivatives: Finding Maximums and Minimums

**Key Observation:** The derivative can help find maximum and minimum values of a function.

**Revisiting the Velocity Example:**

*   Examining the data between 19 and 20 seconds: distance at 19 seconds = distance at 20 seconds = 265 meters.
*   This indicates that, during that interval, the car did not move.
*   **Graphical Representation:** The line connecting these two points on a distance-vs-time graph is a horizontal line.
*   **Slope of Horizontal Line:** Slope = 0 (no change in distance).

**Slope Calculation:**

*   `Slope = (Change in Distance) / (Change in Time)`
*   `Slope = (265 - 265) / 1 = 0/1 = 0 meters per second`

**Car Trajectory and Zero Velocity:**

*   A graph of the car's trajectory (forward, stops, backward, etc.) is presented.
*   **Quiz Question 1:** Where was the velocity of the car zero?
*   **Answer:** At any point where the tangent line to the curve is horizontal (slope = 0).
*   In this example, there are five such points where the car was stopped.

**Maximum Distance and Zero Velocity:**

*   **Quiz Question 2:** At what time was the car farthest from its starting point?
*   **Answer:** At the point where the distance was 50.
*   **Important Observation:** The point where the distance was the farthest is *also* a point where the car was stopped (derivative = 0).

**Key Insight: Derivatives and Optimization**

*   **If the car is moving, it could just go further.** Therefore, the maximum or minimum distance occurs when the car is *not* moving.
*   **General Principle:** The maximum or minimum value of a function occurs at points where the derivative is zero.
*   This is because derivatives measure the gradient of a function. Once the derivative is zero, the function is at the maximum or minimum height.
*   **In other words:** The maximum and minimum are points where the tangent line is horizontal.


## Derivative Notation: Leibniz vs. Lagrange

**Concept:** Different ways to express the derivative mathematically.

**1. Leibniz Notation**

*   Builds upon the idea of slope as the "change in distance over the change in time" (`Delta x / Delta t`).
*   **From Secant to Tangent:**
    *   Start with a large interval (a secant line).
    *   Calculate `Delta x / Delta t` (the slope of the secant).
    *   Make the interval smaller and smaller.
    *   As the interval approaches zero, the secant becomes the tangent line.
*   **Infinitesimal Changes:**
    *   The slope of the tangent line is written as `dx / dt`.
    *   `dx` and `dt` represent infinitesimal (infinitely small) changes in the x and t directions.
*   **General Form:**
    *   With x on the horizontal axis and y on the vertical axis, the derivative is generally expressed as `dy / dx`.
    *   If the function is f(x)=y, `dy/dx` can be written as `d/dx f(x)`

**2. Lagrange Notation**

*   Uses a prime symbol (') to denote the derivative.
*   If `y = f(x)`, then the derivative is written as `f'(x)`.
*   `f'(x)` represents the slope of the tangent line to the function f at the point x.

**Summary and Usage**

*   **Leibniz Notation:** `dy / dx` or `d/dx f(x)`
*   **Lagrange Notation:** `f'(x)`
*   Both notations express the same concept: the derivative of the function.
*   The course will use both notations interchangeably, choosing the more convenient one in each context.


## Derivatives of Simple Functions: Lines

**1. Constant Functions (Horizontal Lines)**

*   **Form:** f(x) = c (where c is a constant).  Example: f(x) = 5
*   **Property:** The height of the line is always the same, regardless of the x-value.
*   **Derivative:** 0

**Explanation:**

*   The slope (derivative) of a tangent line at any point on a horizontal line is always zero.
*   `Delta y / Delta x = 0 / Delta x = 0` because the change in y (Delta y) is always zero.

**2. Generic Lines (Non-Horizontal)**

*   **Form:** f(x) = ax + b (where 'a' is the slope and 'b' is the y-intercept).  Example: f(x) = 2x + 3
*   **Derivative:** a (the slope of the line)

**Explanation:**

*   The slope of the tangent line at any point on a straight line is the *same as the slope of the entire line*.
*   Consider two points on the line: (x, ax + b) and (x + Delta x, a(x + Delta x) + b).
*   **Slope Calculation:**
    *   `Delta y / Delta x = [a(x + Delta x) + b - (ax + b)] / Delta x`
    *   `= (ax + a Delta x + b - ax - b) / Delta x`
    *   `= (a Delta x) / Delta x = a`
*   The derivative (slope) is 'a', the coefficient of x in the line's equation.

## Derivatives of Quadratic Functions: y = x^2

**Simplest Quadratic: f(x) = x^2** (a parabola)

*   **Observations:**
    *   To the left of the y-axis, the slopes (derivatives) are negative.
    *   To the right of the y-axis, the slopes (derivatives) are positive.
*   **Goal:** Determine the derivative (instantaneous rate of change) of f(x) = x^2.
*  ** Derivative's Formula**: Delta f/ delta x as delta x goes to zero, this is equivalent to (x+ delta x)^2 -x^2 /delta x as delta x goes to zero.

**Example at x = 1**

1.  **f(1) = 1^2 = 1**
2.  **Calculating Slopes of Secants:**
    *   Take various values for Delta x, one at a time.
    *   Calculate Delta f (change in y) and Delta x (change in x).
    *   Calculate the slope (Delta f / Delta x).

| Delta x | Delta f = f(x+Delta x) - f(x) | Slope (Delta f / Delta x) |
|---------|------------------------------|----------------------------|
| 1       | (1+1)^2 - 1^2 = 3              | 3 / 1 = 3                |
| 1/2     | (1+0.5)^2 - 1^2 = 1.25         | 1.25 / (1/2) = 2.5         |
| 1/4     | (1+0.25)^2 - 1^2 = 0.5625         | 0.5625 / (1/4) = 2.25        |
| 1/8     |  | 2.125 |
| 1/16      |   | 2.065                 |
| 1/1000   |   | 2.001                  |

*   **Trend:** As Delta x gets smaller, the slope approaches 2.
*   **Conclusion:** The slope of the tangent at x = 1 is 2.

**Formal Calculation of the Derivative**

*   **Delta f / Delta x =  [(x + Delta x)^2 - x^2] / Delta x**
*   Expanding the numerator: `[x^2 + 2x Delta x + (Delta x)^2 - x^2] / Delta x`
*   Simplifying: `[2x Delta x + (Delta x)^2] / Delta x`
*   Factoring out Delta x: `Delta x (2x + Delta x) / Delta x`
*   Canceling Delta x: `2x + Delta x`
*   Taking the limit as Delta x approaches 0: `2x + 0 = 2x`

**Result**
Therefore, given a function f(x) = x^2, its derivative f prime(x) = 2x


## Derivatives of Cubic Functions: y = x^3

**Simplest Cubic: f(x) = x^3**

*   **Goal:** Determine the derivative of f(x) = x^3.
*   **Derivative Formula:** Delta f/ delta x as delta x goes to zero, this is equivalent to (x+ delta x)^3 -x^3 /delta x as delta x goes to zero.

**Example at x = 0.5**

1.  **f(0.5) = (0.5)^3 = 1/8**

2.  **Calculating Slopes of Secant Lines:**

| Delta x | f(x + Delta x) = (0.5 + Delta x)^3 | Delta f = f(x+Delta x) - f(x) | Slope (Delta f / Delta x) |
|---------|---------------------------------------|------------------------------|----------------------------|
| 1       | (1.5)^3 = 27/8 = 3.375               | 3.375 - 0.125 = 3.25         | 3.25 / 1 = 3.25           |
| 1/2     | (1)^3 = 1                             | 1 - 0.125 = 0.875          | 0.875 / (1/2) = 1.75        |
| 1/4     |                                       | 0.3                           | 1.188                        |
| 1/8     |                                       | 0.12                          | 0.95                           |
| 1/16    |                                       |                               | 0.85                           |
| 1/1000  |                                       |                               | 0.752                           |

*   **Trend:** As Delta x gets smaller, the slope approaches 0.75.
*   **Conclusion:** The slope of the tangent at x = 0.5 is 0.75.

**Formal Calculation of the Derivative**

*   **Delta f / Delta x = [(x + Delta x)^3 - x^3] / Delta x**

*   Expanding the numerator:
   `[x^3 + 3x^2 Delta x + 3x (Delta x)^2 + (Delta x)^3 - x^3] / Delta x`

*   Simplifying:
    `[3x^2 Delta x + 3x (Delta x)^2 + (Delta x)^3] / Delta x`

*   Dividing by Delta x:
    `3x^2 + 3x Delta x + (Delta x)^2`

*   Taking the limit as Delta x approaches 0:
     `3x^2 + 0 + 0 = 3x^2`

**Result**
Therefore, given a function f(x) = x^3, its derivative f prime(x) = 3x^2.


## Derivatives: Power Rule

**Function: f(x) = 1/x (Hyperbola)**

*   **Goal:** Determine the derivative of f(x) = 1/x (or x^-1).
*   **Formula**: Delta f/ delta x as delta x goes to zero, this is equivalent to 1/x+delta x - 1/x all over delta x as delta x goes to zero.
**Example at x = 1**

1.  **y = f(1) = 1/1 = 1**

2.  **Calculating Slopes of Secant Lines:**

| Delta x | f(x + Delta x) = 1/(1 + Delta x) | Delta f = f(x+Delta x) - f(x) | Slope (Delta f / Delta x) |
|---------|---------------------------------------|------------------------------|----------------------------|
| 1       | 1/(1+1) = 1/2 = 0.5                 | 0.5 - 1 = -0.5               | -0.5 / 1 = -0.5           |
| 1/2     | 1/(1+0.5) = 1/(3/2) = 2/3            | 2/3 - 1 = -1/3               | (-1/3) / (1/2) = -2/3 ~ -0.67       |
| 1/4     |      | -0.8      |
| 1/8    |       | -0.89                 |
| 1/16     |      | -0.94                          |
| 1/1000    |       | -0.999                                |

*   **Trend:** As Delta x gets smaller, the slope approaches -1.
*   **Conclusion:** The slope of the tangent at x = 1 is -1.

**Formal Calculation of the Derivative**

*   **Delta f / Delta x = [1/(x + Delta x) - 1/x] / Delta x**
*   Combining the fractions in the numerator:
   `[x - (x + Delta x)] / [(x + Delta x) * x * Delta x] = -Delta x / [((x + Delta x) * x * Delta x)]`
*   Simplifying:
     `-Delta x / [(x^2 + Delta x *x ) * Delta x]`
* Dividing by delta x results in:
     `-1 /(x^2 + Delta x *x )`

*   Taking the limit as Delta x approaches 0:
     `-1 /(x^2 ) = -1x^-2`

**Result**
Therefore, given a function f(x) = x^-1 (or x inverse), its derivative f prime(x) = -1x^-2 (negative 1 times x to the minus 2).

**General Power Rule**

*   **Observed Patterns:**
    *   f(x) = x^2  => f'(x) = 2x^1
    *   f(x) = x^3  => f'(x) = 3x^2
    *   f(x) = x^-1 => f'(x) = -1x^-2
*   **General Rule: Power Rule for Derivatives**
    *   If f(x) = x^n, then f'(x) = nx^(n-1)

**Examples:**

*   f(x) = x^100 => f'(x) = 100x^99
*   f(x) = x^-100 => f'(x) = -100x^-101

## Derivatives: Inverse Functions

**Key Idea:** Inverse functions "undo" each other, and their derivatives are closely related.

**1. Inverse Function Definition**

*   If function *f* sends a number *x* to a number *y*, then its inverse function *g* sends *y* back to *x*.
*   *g* does the opposite of what *f* does.
*   Mental Image: If *f* puts a hat on someone, *g* takes it off.
*   Mathematical Example:
    *   *f(x) = x^2*  (squares the input)
    *   *g(x) = sqrt(x)* (takes the square root; positive root only for x>0)

**2. Notation**

*   If *g(x)* and *f(x)* are inverses, we write:
    *   `g(x) = f^-1(x)` (Note: This is *not* 1/f(x); it's just notation)
*   **Composition:** `g(f(x)) = x` (g undoes what f does, returning you to the original input).

**3. Inverse Function and Reflection**

*   When plotting a function, a point with coordinates a,b appears if the function is at a slope.
*   Take two inverse function plots with a generic coordinate x and its square root, the two plots are simply reflection of the same function.

**4. Relationship Between Derivatives of Inverses**

*Let g be the inverse function of f. Then the relationship between their derivative is given by:
   *  g prime (x) = 1/ f prime (y)
   or
   * delta g over delta y = 1/ delta f over delta x

## Derivatives: Trigonometric Functions (Sine and Cosine)

**1. Derivative of Sine(x)**

*   If `f(x) = sin(x)`, then `f'(x) = cos(x)`

**Explanation through Comparison:**

*   **Consider specific points:** -π/2, 0, π/2
*   **Values of sin(x) at these points:** -1, 0, 1
*   **Slopes of tangents to sin(x) at these points:** 0, 1, 0
*   **Values of cos(x) at these points:** 0, 1, 0
*   The values of cos(x) match the slopes of sin(x) at the corresponding points.

**2. Derivative of Cosine(x)**

*   If `f(x) = cos(x)`, then `f'(x) = -sin(x)`

**Explanation through Comparison:**

*   **Consider specific points:** -π, -π/2, 0, π/2
*   **Values of cos(x) at these points:** -1, 0, 1, 0
*   **Slopes of tangents to cos(x) at these points:** 0, 1, 0, -1
*   **Values of -sin(x) at these points:** 0, 1, 0, -1
*   The values of -sin(x) match the slopes of cos(x) at the corresponding points.

**Geometric Intuition (Unit Circle)**

1.  **Setup:**
    *   Draw a unit circle (radius = 1).
    *   `x`: Angle between the horizontal axis and a radial line.
    *   `cos(x)`: Projection of the radial line onto the x-axis.
    *   `sin(x)`: Projection of the radial line onto the y-axis.
2.  **Slight Angle Change:**
    *   Increase the angle by a small amount `Delta x`.
    *   Now: `cos(x + Delta x)` is the new projection on the x-axis, `sin(x + Delta x)` is the new projection on the y-axis.
3.  **Analyzing the Orange Triangle:**
    *   This triangle is formed by the change in the projections due to `Delta x`.
    *   Sides of the triangle: `|Delta cos(x)|` (change in x-projection), `Delta sin(x)` (change in y-projection).
4.  **Trigonometric Relationships (Triangle):**
    *   Let `h` be the hypotenuse of the triangle, and `phi` be the angle at the center.
    *   `cos(phi) = Delta sin(x) / h  => Delta sin(x) = h * cos(phi)`
    *   `sin(phi) = -Delta cos(x) / h => -Delta cos(x) = h * sin(phi)`
5.  **Limit as Delta x approaches zero:**
    *   As `Delta x` gets smaller, the hypotenuse `h` approaches the arc length of the circle (`Delta x`).
    *   The angle `phi` approaches `x`.
6.  **The results**:

* The limit value of `(Delta sin(x)/ Delta(x)) as delta x -> 0 = cos (x)`
* The limit value of `(Delta cos(x)/ Delta(x)) as delta x -> 0 = -sin (x)`

**Key Results from Geometric Reasoning:**

*   `sin'(x) = cos(x)`
*   `cos'(x) = -sin(x)`


## Derivatives: Exponential Function and Euler's Number (e)

**Euler's Number (e)**

*   **Definition 1 (Numerical):** An irrational number approximately equal to 2.71828182...
*   **Definition 2 (Limit):** Can be defined using the expression `lim (n->∞) (1 + 1/n)^n`
    *   `n=1: (1 + 1/1)^1 = 2`
    *   `n=10: (1 + 1/10)^10 = 2.594`
    *   `n=100: (1 + 1/100)^100 = 2.705`
    *   As n increases, the expression converges to *e*.

**Exponential Function: f(x) = e^x**

*   **Key Property:** The exponential function is its own derivative!  `f'(x) = e^x`
*   This property makes *e* ubiquitous in science, statistics, and probability.

**Defining *e* through Interest Rates: The Bank Analogy**

*   **Objective:** Find the best bank to deposit money.

*   **Bank Options:**

    *   **Bank 1:** 100% interest once a year.

    *   **Bank 2:** 50% interest every 6 months (twice a year).

    *   **Bank 3:** 33% interest every 4 months (three times a year).

*   **Which bank is best?** Bank 3

**Calculation and Explanation:**

| Bank  | Interest Rate | Compounding Frequency | Amount After 1 Year (with $1 initial) |
|-------|---------------|-----------------------|---------------------------------------|
| Bank 1 | 100%          | 1 time/year          | 1 + 1/1 = 2                            |
| Bank 2 | 50%           | 2 times/year          | (1 + 1/2)^2 = 2.25                        |
| Bank 3 | 33%           | 3 times/year          | (1 + 1/3)^3 = 2.37                        |

**Why Higher Compounding is Better:**

*   Accrued interest earns *more interest*. You earn interest on interests in the next periods.

*   As n approaches infinity.

**Generalization to Bank *n***

*   Bank *n* gives 1/*n* of your money *n* times a year.

*   Amount after 1 year: `(1 + 1/n)^n`

**The Ultimate Bank: Bank Infinity**

* The best bank gives you an infinitesimal portion of your money an infinite number of times in the year.
*It gives you interest instantaneously.

**Reaching Euler's Number (e)**

*   As *n* approaches infinity,  `(1 + 1/n)^n` converges to *e* (approximately 2.71828...).
* In other words, e is "what you get at the end of the year in bank infinity" because the derivative is equal to the function itself.

## Derivatives: Exponential Function Derivative (f(x) = e^x)

**Key Property:** The function *f(x) = e^x* is its own derivative.
`f'(x) = e^x`

**Explanation:**

*   **Geometric Interpretation:** At any point (x, e^x) on the graph of y = e^x, the slope of the tangent line at that point is *equal* to e^x.

**Numerical Verification**

*   Taking measurements to approximate derivatives of f(x) = e^x
*   Using small distances (delta x) to determine slope.
*   Take an example at x= 2 which gives f(x) =7.39 which is e squared.
| Delta x | f(x + Delta x) = (e^x+delta x) | Delta f = f(x+Delta x) - f(x) | Slope (Delta f / Delta x) |
|---------|---------------------------------------|------------------------------|----------------------------|
| 1      | 20.09          | 12.70               | 12.70       |
| 1/2     |     | 4.79|        9.59   |
| 1/4     |      | 2.1        | 8.39                  |
| 1/8    |       |             | 7.87                          |
| 1/16     |      |               | 7.62                          |
| 1/1000    |       |    |  7.39                               |

* It approaches f(x)=7.39 which is e squared.
* These values approach the y value.

**Confirmation:** The slope of the tangent line at the point (2, e^2) is approximately e^2 (7.39).

**Generalization:** This relationship holds true at *every* point on the graph of f(x) = e^x. The function is its own slope everywhere.


## Derivatives: Logarithmic Function

**Goal:** Find the derivative of the logarithmic function using the exponential function (e^x) and the inverse function rule.

**1. Logarithm Definition**

*   The logarithm (base e, or natural logarithm) is the *inverse* of the exponential function.

*  In short, ln(a) = b implies e^b=a

*  logarithm(x): Find the number such that *e* raised to that number equals *x*.

**2. Functions**

* f(x) = e^x
* g(x) = Ln (y)

**3. Formula for the derivative**
*  `g prime (x) = 1/ f prime (y)`
  or
* delta g over delta y = 1/ delta f over delta x

**3. Relationship between Exponential and Logarithmic Functions**

*   The inverse of the exponential function equals the logarithm with respect to each other such that
    *   `e^(ln(x)) = x`
    *   `ln(e^y) = y`
*   Therefore,`e^x` to ln^y and back are inverse functions.

**4. Logarithm of y Derivative**
* The slop of each tangent at the inverse function has the inverse ratio.
* Given * ln prime(y) = 1/ e ^x and f'(2)= 7.39 , then the inverse g' 7.39 = inverse of 7.39*
* It's actually very small and goes closer to 0.

**Putting it all together**
* If you take the logarithm function and you take the derivative with respect to y, then you get 1 over f prime of f inverse of y. f prime is e^x and f inverse of y is logarithm of y, so you get 1 over y. In other words, the derivative of logarithm of y is 1 over y.
* d over dy Ln of y  = 1 / y


## Non-Differentiable Functions

**Key Idea:** Not all functions have a derivative at every point. These are called non-differentiable functions.

**Differentiability:**

*   A function is *differentiable at a point* if the derivative exists at that point.
*   The derivative exists if you can draw a *unique tangent line* to the curve at that point.
*   A function is *differentiable over an interval* if the derivative exists for every point in that interval.

**Non-Differentiable Functions: Three Types**

1.  **Corners or Cusps**

    *   **Example:** `f(x) = |x|` (absolute value of x)
    *   Defined as:
        *   x for x >= 0
        *   -x for x < 0
    *   **Problem:** At x=0, you cannot draw a unique tangent line. Multiple lines could potentially be tangents. The gradient is 0.
    *   The function derivative does not exist. The corner doesn't allow us to differentiate.
   It means that you must stop the function to draw the function.

   *It means that it's not differentiable at a given point, or that it's a function is no differentiable everywhere.

    *Example of an other one: If you give me this function, can you tell me at which point is this function not differentiable?
    *If you said that the derivative does not exist at x equals 1, then you were correct, because here we can draw multiple lines and neither one of them is well defined as the derivative at that point.

2.  **Jump Discontinuities**

    *   **Example:** Piecewise function with a "jump."
    * The jump function or piece wise function has a  jump discontinuity function if it's not continue on a  point.

    *   **Problem:**  At the jump, you have to "lift your pencil" to draw the graph.

    *At point where the function jump, the derivative does not exist. The line cannot be used at that point.

    *   **Rule:** Any function with a discontinuity is not differentiable at that point because the derivative cannot be defined.


3.  **Vertical Tangents**

    *   **Example:** `f(x) = x^(1/3)` (cube root of x)
    *   **Problem:** At x=0, the tangent line is vertical, meaning it's the tangent to the y axis. This value doesn't have a defined slope as vertical line doesn't have a gradient.
     You can't define the numbers due to x / 0 = infinity (undefined). The vertical line doesn't allow us to defined the derivative.
     *If the function a vertical tangent, then the function is not differentiable.

**Summary of Non-Differentiable Cases:**

*   **Corners and Cusps: Bad**
*   **Jump Discontinuities: Bad**
*   **Vertical Tangents: Bad**


## Derivative Rules: Multiplication by a Scalar

**Key Idea:** This rule simplifies finding the derivative of a function multiplied by a constant.

**The Rule:**

*   If `f(x) = c * g(x)`, where `c` is a constant, then `f'(x) = c * g'(x)`

**In words:** The derivative of a constant times a function is the constant times the derivative of the function.

**Explanation:**

Let's walk through all the functions at y=x^2

1.  f(x)=  y =x^2, is a function, but now f(x) =2x^2
    As you can see is getting doubled, or stretch by factor of c.
2.  Pick an inverse relationship
    We will start looking to our function of  y =x^2 with 1, 1 and y= 2x^2 which is 1, 2.
The points on the right will also get doubled.
So calculate the gradient. We need to look for the point with gradient and with scalar.
With 2, 4 we found y= 2x^2. With the gradient is the same the number are the double.
4. In the new function at y =2x^2 which can be calculated like that dy / dx =6 and y =Scalar 2  = original dy/dx

5.  What happen? Well, the points on the right will also get doubled.
 It multiply everything by to.
  *We do this because of the multiplication scalar rule.*

 **What are the step by step calculation of Multiplication**
*First, find all function.*
*Second, find the scaler by the value in our function.*
*Third, we see that on scalar if the Y multiply for any scale the  delta y  (gradient)  of the functions will multiple by the same values.*

* In short, if the value increase it does on derivative function too.

**Geometric Explanation:**

*   If you multiply a function by a constant `c`, you are essentially stretching the graph vertically by a factor of `c`.
*   The height of the data multiply by  `c`
*   Since the slope is directly related to the vertical change, all the slopes (derivatives) are also multiplied by `c`.


## Derivative Rules: Sum Rule

**Key Idea:** This rule allows you to find the derivative of a sum of functions easily.

**The Rule:**

*   If `f(x) = g(x) + h(x)`, then `f'(x) = g'(x) + h'(x)`

**In words:** The derivative of a sum is the sum of the derivatives.

**Intuitive Explanation (Boat and Child Analogy)**

*   **Scenario:** A child is moving inside a boat, and the boat is also moving.
*   `XB`: Distance the boat moves.
*   `XC`: Distance the child moves *inside the boat*.
*   `X_total`: Total distance the child moves with respect to the earth.
*   **Relationship:** `X_total = XB + XC`

**Quiz:**

*   Boat speed = 0.6 meters/second
*   Child speed (inside boat) = 0.05 meters/second
*   What is the speed of the child with respect to the earth?
*   **Answer:** 0.65 meters/second (0.6 + 0.05). Velocities add in the same direction.

**Connection to Functions and Derivatives:**

*   If distances can be added (like `X_total = XB + XC`), then velocities (which are derivatives of distances) can also be added.
*   If functions can be added, then their derivatives can be added.

**Geometric Explanation:**

1.  **Plots:**
    *   Time (horizontal axis) vs. Distance (vertical axis)
    *   Plot of the child's movement *inside* the boat.
    *   Plot of the boat's movement.
    *   Plot of the *sum* (child's movement with respect to earth).
2.  **Average Velocity:**
    *   Consider a small interval `Delta t`.
    *   `VC`: Average velocity of the child (inside boat) over `Delta t`.
    *   `VB`: Average velocity of the boat over `Delta t`.
    *   `V_total`: Average velocity of the child (with respect to earth) over `Delta t`.
3.  **Adding Velocities:**
    *   Since `X_total = XB + XC`, and you divide all values by `Delta t` then `V_total = VB + VC`
4.  **Taking the Limit:** As `Delta t` approaches zero, the average velocities become instantaneous velocities (derivatives).
5.  **Result:**

* If three functions are named for: a child(f1), a boat(f2), and the sum of these functions (f1 + f2)
* Then the derivative of the function f is equal to f prime = slope function of boat (f2 prime ) + slope function of the child (f1 prime)
**Conclusion:** The derivative of a sum of functions is the sum of their derivatives.

## Derivative Rules: Product Rule

**Key Idea:** This rule helps find the derivative of a function that is the *product* of two other functions.

**The Rule:**

*   If `f(x) = g(x) * h(x)`, then `f'(x) = g'(x) * h(x) + g(x) * h'(x)`

**In words:** The derivative of a product is the derivative of the first function times the second function, plus the first function times the derivative of the second function.

**Mnemonic (Hammer Analogy):**

*   Imagine the derivative as hitting the function with a hammer.
*   To find f', you hit `g` with the hammer *while leaving `h` alone*, *then* you hit `h` with the hammer while leaving `g` alone, and add the results.

**Intuitive Explanation (House Building Analogy)**

1.  **Scenario:** You're building a house.

    *   `g(t)`: Length of the side wall as a function of time *t*.
    *   `h(t)`: Length of the front wall as a function of time *t*.
    *   `f(t)`: Area of the house as a function of time *t*.
    *   Therefore,`f(t) = g(t)*h(t)`
2.  **Area Change:**
    *   The change in side wall is *Delta g*.
    * The change in front wall is delta h.
    * The area is  *f(t)
    *The change in are is is delta f ( t)

3.  **Analyzing the Area Increase:**

Delta f equal to total sum of a, b,c that are rectangle.

* This is Delta of G of t times at of h.
* b G of t *delta h.
* and the small C that is *delta g of t *Delta h of t..

4. Now find delta f of t over  delta  t by this we have:
delta gt over Delta t times h of t plus Delta ht over Delta t times g of t plus Delta g of t Delta h of t divided by Delta t.

Now do some derivatives by this formula with delta gt, gprime t h prime and h of t and you founds the product value.


**In other words:**

F prime of (t)  is g prime (t )+ * h(t+ the values of the g times + of th prime of T*

## Derivative Rules: Chain Rule

**Key Idea:** This rule is used to find the derivative of a *composite function* (a function within a function).

**The Rule:**

*   If `f(x) = g(h(x))`, then `f'(x) = g'(h(x)) * h'(x)`

**In words:** The derivative of a composite function is the derivative of the *outer* function (evaluated at the *inner* function) multiplied by the derivative of the *inner* function.

**Memorize Rule:** 3:55
Chain Rule (d/dx(f(g(x)) =f' (g(x))* g'(x)

**Understanding the Composition:**

1.  Start with an input *t*.
2.  Apply the function *h*: result is *h(t)*.
3.  Apply the function *g* to the result from step 2: `g(h(t))`. This is the composite function.

**More Complex Chain**
This is easy when there are only a few functions. What happens with more that one function?
*If you want to add 3 derivatives, what is the composition?
*You need to know the derivates to use them,

*f'(g(h))* g'(h) *h'

**Why is it called the Chain Rule?**

*   You can keep composing more functions, creating a "chain."
*   The derivative of the chain is a product of terms, one for each link in the chain.

**Chain Rule with Leibniz Notation (Clearer):**

*   If `w = g(v)` and `v = h(t)`, then `dw/dt = (dw/dv) * (dv/dt)`

**Chain Rule with Lagrange Notation (Tricky):**

1.  *h'(t)*
2. What does g prime means? Well, all we have to d is input the right equation into the g such as h.
* It mean that g(prime (x)) = g Prime (h(t)) .
3. Just input the three variable functions by applying chain of rule.

*f prime (g(h))) * g prime (h) *h* is chain of value

**Intuitive Explanation (Car Trip Up a Mountain):**

1.  **Scenario:** You're driving up a mountain.
    *   `T`: Temperature
    *   `h`: Height above sea level
    *   `t`: Time

2.  **Rates of Change:**
*We said that the derivate with respect to T is dependent to heat change or distance to the change over high
   *It's the reason we say that the temperature is equal to dT over DH

*The heat with relation to the over time  = dh over dt

3.  **Putting it Together:**
*As times runs out the mountain gets cold
*We need all  related the heat from high to derivatives and get D over dt.
If you are at the D over Dh with derivative times then to derivative that that gets D T 