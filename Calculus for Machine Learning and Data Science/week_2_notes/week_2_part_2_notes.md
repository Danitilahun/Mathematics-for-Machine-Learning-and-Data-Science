**Topic:** Introduction to Gradient Descent (1D)

*   **Problem:** Minimizing a function, f(x) = e^x - ln(x), where finding the exact minimum analytically (by solving f'(x) = 0) is difficult.

*   **Challenge:** The derivative f'(x) = e^x - 1/x. Solving e^x - 1/x = 0 analytically (e^x = 1/x) is hard

*   **Iterative Approach (Basic):**
    1.  **Start with a random x.**
    2.  **Move left and right by a small amount.**
    3.  **Evaluate f(x) at both new points.**
    4.  **Choose the point with the lower f(x) value.**
    5.  **Repeat steps 2-4 until a local minimum is found.**

*   **Limitation:** Basic Method. An improvement will be shown in the next video.

**Topic:** Gradient Descent (1D) - Smarter Approach

*   **Improvement over previous method:** Gradient descent uses the derivative (slope) of the function to intelligently move towards the minimum.

*   **Key Idea:**
    *   If the slope is negative, move *right* (increase x).
    *   If the slope is positive, move *left* (decrease x).

*   **Update Rule:**
    *   `x_(new) = x_(old) - α * f'(x_(old))`
        *   `x_(new)`:  The new x-coordinate.
        *   `x_(old)`:  The current x-coordinate.
        *   `α`:  The *learning rate* (a small positive number, e.g., 0.01) that controls the step size.
        *   `f'(x_(old))`:  The derivative of the function evaluated at `x_(old)`.

*   **Learning Rate (α):**
    *   A smaller learning rate leads to smaller, more cautious steps.
    *   A larger learning rate leads to larger steps, which can be faster but risk overshooting the minimum.

*   **Benefits:**
    *   **Automatic step size adjustment:** Steeper slopes result in larger steps; flatter slopes result in smaller steps.
    *   **Iterative:** Repeat the update rule until the change in `x` becomes negligible (i.e., you're close to the minimum).
    *   **Avoids directly solving f'(x) = 0:** Only requires evaluating the derivative at each step.

*   **Algorithm Summary:**
    1.  Choose a learning rate (α).
    2.  Choose a starting point (x_0).
    3.  Iterate:  `x_k = x_(k-1) - α * f'(x_(k-1))` until convergence.

*   **Example:** Minimizing `f(x) = e^x - ln(x)`
    *   `f'(x) = e^x - 1/x`
    *   Start: x_0 = 0.05, α = 0.005
    *   Iteration 1: x_1 = 0.05 - 0.005 * (e^(0.05) - 1/0.05) = 0.1447
    *   Iteration 2: x_2 = 0.1447 - 0.005 * (e^(0.1447) - 1/0.1447) = 0.1735