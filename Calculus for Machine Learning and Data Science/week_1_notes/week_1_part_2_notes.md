## Derivatives: Optimization (Minimizing and Maximizing Functions)

**Core Idea:** Derivatives are used to find the maximum or minimum values of a function (optimization). This is crucial in machine learning for finding the model that best fits the data.

**Application in Machine Learning:**

1.  **Model Training:**
    *   Goal: Find the best model that fits a dataset.
    *   Approach: Define an error function (loss function) that measures how far the current model is from the ideal model.
    *   Optimization: Minimize the error function to obtain the best model parameters.

**Example: Finding the Coldest Spot in a Sauna**

1.  **Scenario:** You're in a sauna and want to find the coldest spot on a bench.
    *   You have a thermometer.
    *   You move around, taking temperature measurements.
2.  **Actions:**
    *   Initial temperature: 85°C.
    *   Move left: Temperature increases to 90°C (bad).
    *   Move right: Temperature decreases to 80°C (good).
    *   Continue moving right, finding colder and colder spots.
    *   Eventually, you reach a spot where *any* movement (left or right) results in a higher temperature.
    *   You conclude that this must be the coldest spot in the sauna.

**Connection to Derivatives:**

1.  **Graphical Representation:**
    *   Draw a curve representing the temperature at each point on the bench.
    *   Your initial point, first move (bad), second move (good), and the final "coldest" spot are marked.
2.  **Slope Analysis:**
    *   Points where moving right leads to a colder spot: Slope of the tangent line is *less than zero*.
    *   Points where moving left leads to a colder spot: Slope of the tangent line is *greater than zero*.
    *   At the coldest spot (no matter which way you move you get hotter): Slope of the tangent line is *zero*.

**Conclusion about Max and Min's**

The tangent lines is always zero for all value.

*   Important Properties: Local and Global Minima
        * Those points are called local minima(are candidates) and Absolute minima for  (is called global minima).

**Local vs. Global Minima:**

*   **Local Minima:** A point where the function value is smaller than the function values at all nearby points. But it is not minimum.
* There are multiple minima functions that equal to zero.
All points where the tangent is 0 slope = 0 are minima.
*   **Global Minimum:** The point where the function value is the smallest over the *entire* domain of the function (the absolute coldest spot). To reach it, you may have to try them all.

**Key Principle:**

*   If a function is differentiable everywhere, then the candidates for the maximum and minimum are points where the derivative is equal to zero.

*Function and differentiable are the point. *Candidates max is when the derivate is 0*
*You can found many candidates, but you can have multiple or candidates max and the function can be very small and it takes you a point where the derivative is set.
You can get minimum or points, but reduce it with small numbers.
These are *Local Minima and called global Minima. *If the function is differentiable always is the candidates is when derivate is zero. *
*We need to select and point them that have the derivative.*The candidates may be zero for candidates.

## Optimization Example: Minimizing Power Line Connection Costs

**Problem:**
*   Locate a house to minimize the cost of connecting to several power lines.
*   The cost of connecting to a power line is proportional to the *square* of the distance.
This is a similar example where a squared error occurs.

**Importance:**
*   The function being minimized (squared cost) is similar to the *squared error* used in machine learning.
*   Squared error is used to train linear regression models and some neural networks.

**Setup:**
*   Several power lines are located in an area.
*   A house needs to be built.
*   Connecting the house to the power lines has a cost associated.
*   Goal to minimize: The cost to connect to all power lines.

**Assumptions:**
*   Connecting to power grids is expensive.
*   The greater the distance between the house and a power line, the longer/wider the cable needed.
*   Cost of connecting to a power line = (distance to the power line)^2

**Simple Case (One Power Line):**
*Put the power line on the distance, therefore the answer is zero because the power needs a minimum cost to operate. *

*  Where should you build your house to minimize the cost?
    *If your house has a distance of zero to operate. That is the lowest minimum. Because 0^2 is the only minimum*
*  Answer: Build the house *right next to* the power line. In that point of zero is always better for a good connection and a lower the cost.
*If a power line connection is equal to zero in the points, it makes everything easier.

* Cost = 0^2 = 0

*We are done, let's go with a more complicated power line. *


## Optimization Example: Minimizing Power Line Connection Costs (Two Power Lines)

**Setup:**

*   Two power lines: Blue and Orange.
* Origin for references
*   Distance from the blue power line to the origin: 'a' meters.
*   Distance from the orange power line to the origin: 'b' meters.
*   House location distance to the origin'x' meters.

**Goal:**

*   Find the optimal location for the house (*x*) to minimize the total connection cost.

**Cost Calculations:**

*   Distance from house to the blue power line:  `|x - a|` .

*   Distance from house to the orange power line: `|b - x|`

* Cost of connecting to the blue power line: `(x - a)^2`

*   Cost of connecting to the orange power line:  `(b - x)^2 = (x - b)^2`

*It turns out that the solution to is to put on  each mid point between of the power lines to reduce.
If you put it to much on left side then the area are always small and you get that perfect point on that connection.*

*   Total cost function: `C(x) = (x - a)^2 + (x - b)^2`

**Visualization:**
To be minimize all the cost function we can see as an visualization to check the correct spot and is similar to a quadrative function with:
*  Area of squared = (X -A ) ^ 2 + (X - B) ^2 are more bigger if are on the left and has the area to large on blue. So the answer needs to be on an perfect point to minimize the costs.*

**Finding the Optimal Location (Minimizing the Cost Function):**

1.  **Recognize Quadratic Shape:**  The total cost function `C(x)` is a quadratic (parabola) that opens upward (positive coefficient of x^2).
2.  **Find Minimum Point:**The minimum value needs to be derived as slope of the tangent at 0. *Horizontal Tangeant.*
3.  **Take the Derivative:**
   `d/dx C(x)= d/dx (x-a)2+d/dx(x-b)2`  equal to the derivative and take  that is equal to zero to reach the maximum function to derivative.

4. Simplify chain rule
` d/ dx *(2(x-1) + 2 * (x * b) = 0.

5. Simplify divide by 2

`( x- 1) plus ( * x - b)  = 0
2x + a +b = 0.
x - A+ minus.
Divide by -2

*x Equal to A and B divided by 2 that gives you the value 2a/2 to find the minimum cost.
  The is correct and now A is plus B then we have that the point is the right place to put a minimum cost.

**Key Conclusion** 
The best cost and minimal function to get a minimize code is *x equal and B dived by Two*
*The best solution has the put the house on the most in a equal area as well as in the best connection from all the powers*
*There is a relation of three of more power lines to put more.*

## Optimization Example: Minimizing Power Line Connection Costs (Three+ Power Lines)

**Setup:**

* Three power lines: a,b, and c (coordinates from the origin)
* The goal is still to minimized the code with connect more than three plus.

**Goal:**

*The house are found to the minimum code. It equals all functions that were founded.*
*   Find the optimal location for the house (*x*) to minimize the total connection cost.

**Extending the Solution with Three+
*The power lines needs all in connect in 3+ areas to make to the house work at less minimum.
*  Here the formula for that solution for  is* *A+ B plus C divided tree is the formula for this reason*

**Cost Calculations:**

*The calculations for the squared power from:
*The functions will be in squared and are in total equal. Then we will see where to get the less minimum.*

* Cost of connecting to the blue power line: `(x - a)^2`
* Cost of connecting to the orange power line:  `(x - b)^2`
* Cost of connecting to the green power line:  `(x - c)^2`

*   Total cost function: `C(x) = (x - a)^2 + (x - b)^2 + (x - c)^2`

*   What to do? Try the math to try to use geometry and find this correct number.


**Finding the Optimal Location (Minimizing the Cost Function):**

*We can use to get with minimum code with functions but at points is hard to create good derivatives to this*

*   Take the derivative of the cost function and set it equal to zero:

   `dC/dx = d/dx [(x - a)^2 + (x - b)^2 + (x - c)^2] = 0`

*Then you can do that to calculate 3x -a-b-c =0 because there are a equal functions then if we look for X is equal and a and B are divided by 3`

*   Solve for *x*:

    *   `2(x - a) + 2(x - b) + 2(x - c) = 0`
    * `2x = a+b+ c
    *   `3x = a + b + c`
    *   `x = (a + b + c) / 3`

**What that X means?**
*What that function to that minimum function to get all data to a less minimum code and connect to the 3+ powers*

**Result:** The best house location to get any power is the A PLUS C EQUAL 3 is:
*Average of 3, we can add that if we are any power code.
*That is A number, then the result from one coordinate of one functions, to 3 funtcions.
* Then, you reduce that with very high numbers, then the code was the right one and you create minimums with good numbers.

##The Square Function from Machine Leaning

*  General Formulate: Power lines are related to a n
* The formula is A 1 squared is equal the function one the same with A to to an so the equal point is.
    (A_1* A squared) /(3)

*In the square are related to square lost formula so that code function can be founded to be used later.*
*   The optimal solution is to put the house at the *average* of the coordinates of all the power lines.

*   This is an example of the *square loss*, a key concept in machine learning.
*   It provides the way from machine leaning with one example of minimizing all power code.


## Optimization Example: Log Loss (and the Coin Flip Game)

**Setting the Stage (The Coin Flip Game)**

*   I'm tossing a coin 10 times.

*   Goal: Get 7 heads followed by 3 tails to win money.
*   Challenge : Which coin maximizes the chances of landing 7 heads first them three tails.
*  Goal: Choose the coin that mazimize the probability of winning for getting 7 + 3 on the game, to land a win situation.

*   The probability of getting 7 head then the same.
* You will use that function to get to know the values to max and mint.
* You can't used 1 or 2 then they will now land seven and 3 tail functions to max. *

*   Available Coins:

    *   Coin 1: 70% heads, 30% tails
    *   Coin 2: 50% heads, 50% tails (fair coin)
    *   Coin 3: 30% heads, 70% tails

* Quiz : Which one of the three coins is the best coin. *

* Calculate and the functions with code, make sure to divide or mult to have functions.

* The function says that coin to is best , that helps more to the 7 Head then the 3 tailes one.

**Probability of Winning with Each Coin:**

| Coin  | P(Heads) | P(Tails) | Probability of Winning (7H + 3T) |
|-------|----------|----------|------------------------------------|
| Coin 1 | 0.7      | 0.3      | (0.7^7) * (0.3^3) = 0.00222       |
| Coin 2 | 0.5      | 0.5      | (0.5^7) * (0.5^3) = 0.00097       |
| Coin 3 | 0.3      | 0.7      | (0.3^7) * (0.7^3) = 0.00008       |

*Conclusion: Coin 1 gives the best odds of winning.

  *But is Coin 1 truly the BEST possible coin or just the best given that limited example.

**Finding the Optimal Coin (Using Calculus)**

*   Let *p* be the probability of heads.

*   Therefore, the probability of tails is (1 - *p*).
The formula P^7 * 1- P ^3
*  The objective and target is to maz this and find calculus.

1.  **Define Winning Probability Function:**

   *G of P equal that with calculus to maz and create this
2.  **The derivative of g with respect to P. (to calculate more easy the formula).
*Take the derivatives and add and  a function to P7 AND - P3

3.  The calculate to create this derivatives to see that's works and to add, in that case: you get it 7 p by six function derivative and in the second part
We need to check and to have the formula to know a bit more of calculus. And that number goes to one is equal to one

*   Where are the minimum values of this function,  to find 0 function to know a real point.

* Is this all?  Does that means is correct and are the numbers?
  Well what I want to show you is a formula to know to 0. 7 number and it helps you with a logarithm
* Taking the Logarithm it actually simplifies.

  * The idea to change the functions is to the *logarithm function.
     The probability is G equals the logarithm at that function to max*
*   If you set the logarithm into to have the function that you want it
The logarithm functions creates something and you can the easy way from the function to know it
*    Log P7 into this function 7 prime  minus to plus.
This function is one to help it because is the one in minus.
*   Then it gives what we want and know at  1/7 plus it give 1 the derivative with P equal to one
   If a lot of times is zero so that is always an better option for them.

*   We have the same as that in the  Logarithmic *

Taking a Logarithmic
*It simplifies the problem but then, is that the solution because the logarithm says the same and  to help the math to get what they want.*

* This is actually *very very common. Log are great for to solve that way*.
*Now  we use a new algorithm the LOG LOSS and  it work to a better functions.
*We used the logarithm that is more  *Easy to get but now
It's all used to the negative

This is a very popular code because there is an zero and one
To get the P we need to negative function as will to a good plus the minus is more useful

What we want is the formula that is very powerful that is the LOG LOSS code!*


**(Take away):*
*The derivative code, what are they? How it work? And why it does that?*

*All formulas code the one that makes with calculus to have more results about the topics.*


## Log Loss in Machine Learning: Why Logarithms?

**Recap: The Coin Flip Game as Machine Learning**

*   You found the best coin (*model*) to win the coin flip game.
*   **Dataset:** 10 coin flips (7 heads, 3 tails).

*Objective:. Find with calculus the model that leads to a log loss.  The result is the P function which value is 07 for all functions. *

    * A reason the numbers are complicated then derivate  is hard with function values is not as good
2 Why it didn't work to find all the way without code as good as that one*

**Key Questions:**

*   Why did we use the logarithm in the log loss function?
*   What are the advantages of the log loss?

**Reasons for Using Logarithms:**

1.  **Simplifying Derivatives (Product Rule Avoidance):**

    *   Derivatives of products are *hard* to compute, especially with many terms.

    *If is simple you can use the product to but are always needed. To check three of more to use it the result gets very messy and the solution.
*   Derivatives of sums are *easier* to compute (sum rule).

      How does we find that model with min value? Using LOG code as good for those values with derivative products that more helpful that the rule product. Is all about try and not to have a lot number *

    *In other to code it more better. And a great  log loss to good function.*

2.  **Avoiding Tiny Numbers (Numerical Stability):**

    *   The product of many small probabilities (numbers between 0 and 1) can become *extremely tiny*.

   To make smaller the code is use the log instead of a hard a complicated code. Use Log make it good

    *The product formula can be something and use the 100 numbers and between zero with small
*   The logarithm of a very small number is a *large negative number*.

The small functions are the better because are a high big number to computer  that makes a very tiny and
A large computers cannot to help and handle
This  one can work or be help for function to handle and are better than one for zero
*   Computers can handle these large negative numbers more easily than extremely tiny probabilities.

""Any time and every time and all time when we use machine, thinking about it and using the Log ""

*    *Especially derivatives. *

In other words, any complicated derivative, it helps a lot as more simple the better*
You need to find it to create something better*""
**Summary**
The code in small way to is more useful to make and it helps to a complicated product *

*The logarithmical way, it does easy or and if to use* and can simplify to do that!*
""
 *The product does not means,  you will use*