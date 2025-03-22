**Topic:** Newton's Method (1D) - Root Finding & Optimization

*   **Newton's Method (Root Finding):**
    *   Goal: Find the zeros (roots) of a function f(x).
    *   Iterative Procedure:
        1.  Start with an initial guess x_0.
        2.  Find the tangent line to f(x) at x_0.
        3.  Find where the tangent line intersects the x-axis (this is x_1).
        4.  Repeat steps 2-3 until the root is found to sufficient accuracy.
    *   Formula: x_(k+1) = x_k - f(x_k) / f'(x_k)

*   **Newton's Method (Optimization):**
    *   Goal: Minimize a function g(x).
    *   Key Idea: Minimizing g(x) is equivalent to finding the zeros of its derivative g'(x).
    *   Algorithm:
        1.  Start with an initial guess x_0.
        2.  Update: x_(k+1) = x_k - g'(x_k) / g''(x_k)   (where g'' is the second derivative).
        3.  Repeat until convergence.

**Topic:** Newton's Method in Action - Minimizing f(x) = e^x - ln(x)

*   **Goal:** Minimize f(x) = e^x - ln(x) using Newton's method for optimization.

*   **Background:**
    *   Minimum is at the omega constant (approximately 0.5671).
    *   Derivative of f(x): f'(x) = e^x - 1/x (this is what we'll find the zero of)
    *   Second derivative of f(x): f''(x) = e^x + 1/x^2

*   **Newton's Method Iterations:**
    *   Starting point: x_0 = 0.05
    *   Iterative formula: x_(k+1) = x_k - f'(x_k) / f''(x_k)
    *   The video demonstrates how quickly Newton's Method gets to the omega constant


**Topic:** The Second Derivative - Properties and Use in Optimization

*   **Definition:** The second derivative is the derivative of the derivative. It can be seen as acceleration. (dv/dt).
*   **Notation:**
    *   Leibniz: d²f/dx² or d/dx (df(x)/dx)
    *   Lagrange: f''(x)

*   **Real-World Analogy: Car Motion**
    *   Distance (x) -> Velocity (v = dx/dt) -> Acceleration (a = dv/dt = d²x/dt²)
    *   Acceleration represents the rate of change of velocity.

*   **Curvature:**
    *   The second derivative measures how much a curve deviates from being a straight line (curvature).

*   **Concavity:**
    *   Positive second derivative: Concave up (convex), looks like a happy face.
    *   Negative second derivative: Concave down, looks like a sad face.

*   **Optimization Use:**
    *   Points where the first derivative is zero are candidates for local maxima or minima.
    *   **Second Derivative Test:**
        *   If f'(x) = 0 and f''(x) > 0: Local minimum.
        *   If f'(x) = 0 and f''(x) < 0: Local maximum.
        *   If f'(x) = 0 and f''(x) = 0: Inconclusive.


**Topic:** The Hessian Matrix - Second Derivatives in Multiple Variables

*   **Extending Second Derivatives:** Explains how the concept of the second derivative extends to functions of multiple variables.

*   **Hessian Matrix:** The Hessian is a matrix that contains all the second-order partial derivatives of a multi-variable function.

*   **Example:** f(x, y) = 2x² + 3y² - xy
    *   f_x = 4x - y
    *   f_y = 6y - x
    *   f_xx = 4
    *   f_xy = -1
    *   f_yx = -1
    *   f_yy = 6
    *   Hessian = [[f_xx, f_xy], [f_yx, f_yy]] = [[4, -1], [-1, 6]]

*   **Symmetry of the Hessian:**
    *   In most cases, f_xy = f_yx (when both partial derivatives are differentiable).

*   **General Form of the Hessian:**
    *   For a function f(x, y):
        *   Hessian = [[∂²f/∂x², ∂²f/∂x∂y], [∂²f/∂y∂x, ∂²f/∂y²]]

*   **Importance:** The Hessian is very useful in optimization (e.g., Newton's method for multi-variable functions).



**Topic:** The Hessian and Optimization - Multiple Variables

*   **Extending Concepts:** Relates second derivative properties (concavity) to optimization in multiple variables.

*   **Local Minimum:**
    *   One variable: f''(x) > 0 (concave up).
    *   Two variables: Hessian's eigenvalues are all positive (positive definite).

*   **Local Maximum:**
    *   One variable: f''(x) < 0 (concave down).
    *   Two variables: Hessian's eigenvalues are all negative (negative definite).

*   **Saddle Point:**
    *   Occurs when the function is not concave up or down.
    *   Hessian has both positive and negative eigenvalues.

*   **Using Eigenvalues:** The video discusses how finding the eigenvalues determines if function is positive/negative definite. Finding Eigen values is finding determinant(H-lambda I) and solving for the roots.

*   **Summary:**
    *   If all eigenvalues of the Hessian are strictly positive: local minimum.
    *   If all eigenvalues of the Hessian are strictly negative: local maximum.
    *   If eigenvalues have mixed signs or are zero: inconclusive, may be a saddle point.


**Topic:** Newton's Method for Optimization - Multiple Variables

*   **Extending Newton's Method:** Explains how to use Newton's method to optimize functions of several variables.
*   **Update Step Formula:**
        This section describes a high value formula for optimizing across various inputs. It may be more useful to refer to gradient decent where derivatives with respect to every element in the set is iterated to reach the optimal local values
    *   x_(k+1) = x_k - [∇²f(x_k)]^(-1) * ∇f(x_k)
        *   x_k is the current coordinate vector
        *   ∇f(x_k) is the gradient of f at x_k.
        *   [∇²f(x_k)]^(-1) is the inverse of the Hessian matrix at x_k.
*   **Considerations:** Multiplying the gradient by the Hessian inverse to the right is needed.
*   **Example and Results:** The eighth value is very close to the local minimum and can be used for the output.