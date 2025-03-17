# Understanding Systems of Sentences (and Equations)

*   **Core Idea:** A system of sentences, much like a system of linear equations, aims to convey information.

*   **Types of Systems:**

    *   **Non-Singular (Complete):** The ideal! Each sentence provides a unique piece of information.

        *   *Key characteristic:* Contains as many independent pieces of information as sentences.

    *   **Singular:** Less informative than a non-singular system. Includes:

        *   **Redundant:** Some sentences repeat information already provided.
        *   **Contradictory:** Sentences create conflict or impossibility.

*   **Goal:** Use the system to derive new information. Non-singular systems are more effective for this.

*   **Future Concept: Rank:** Measures the level of redundancy within a system.

# Linear Equations and Systems: From Sentences to Solving

*   **Linear Equations as Numerical Sentences:** Equations express numerical relationships, similar to how sentences convey information.

*   **Simple Systems Scenarios:**
    *   Grocery store problems used to find prices of individual fruits based on combined purchases.
    *   Systematically finding prices through logical deduction.

*   **Types of Systems & Solutions:**
    *   **Unique Solution (Non-Singular):** Enough independent equations to pinpoint a single value for each variable.
    *   **Infinitely Many Solutions (Redundant):** Equations are dependent/duplicates, lacking unique constraints.
    *   **No Solution (Contradictory):** Equations conflict; information given is inconsistent.

*   **Key Terms:**
    *   **Linear Equation:** Variables multiplied by scalars and summed, plus a constant (no exponents on variables, no trig functions, etc.). a + b = 10, 2a + 3b = 15
    *   **System of Linear Equations:** A set of linear equations considered together.

*   **General Form of linear equations:**
    * We're only allowed to have numbers or scalars attached to variables a,b,c etc.
    *  An extra number all by itself is allowed to be in the equation.

*   **Non Linear Equations:**
    * They can have squares like a squared, b squared.
    * They can have things like sine, cosine, tangent, arctan, anything like that, powers like b to the five.
    *They can have powers like two to the a or three to the b.
    *Furthermore, you can actually multiply the a's and b's.
    * You can have ab squared, b divided by a, 3 divided by b.
    * Things like logarithms, anything along those lines.

*   **Linear Algebra:** The study of linear equations.

# Visualizing Linear Equations and Systems

*   **Visual Representation:**
    *   2-variable linear equation = line on a coordinate plane.
    *   3-variable linear equation = plane in 3D space.
    *   More variables = higher-dimensional objects.

*   **Example: a + b = 10 (Line)**
    *   Plot points that satisfy equation (e.g., (10,0), (0,10), (4,6)).
    *   These points form a line representing all solutions.
    *   Slope and y-intercept are visual features of the line.

*   **System of Equations = Arrangement of Lines/Planes:**
    *   **Unique Solution (Non-Singular):** Lines intersect at a single point. Planes intersect at a single point
    *   **Infinitely Many Solutions (Redundant):** Lines overlap (same line).Planes intersects to form a line
    *   **No Solution (Contradictory):** Lines are parallel (never intersect).

*   **Visualizing Redundancy:**
    *   Equations like `a + b = 10` and `2a + 2b = 20` represent the same line.

*   **Visualizing Contradiction:**
    *   Equations like `a + b = 10` and `2a + 2b = 24` represent parallel lines, never intersecting.

*   **3D Space (Planes):**
    *   Equation `a + b + c = 1` is a plane in 3D space.
    *   If constant term is zero (e.g., 3a - 5b + 2c = 0), the plane goes through the origin (0,0,0).

*   **Intersecting Planes:**
    *   Analogous to intersecting lines for 2D systems.
    *   Non-singular system: Planes intersect at a single point.
    *   Singular system: Planes intersect along a line or coincide (same plane).
*   **Interactive Tools:**  Use hands on exercises for a more clear idea
    *   Tools exist to manipulate 2x2 systems (lines) and 3D systems (planes) for visual understanding.

# Simplifying Singularity Visualization: Zero Constants

*   **Focus on Singularity:** The core concept going forward is distinguishing singular vs. non-singular systems.

*   **Ignoring Constants:** Constants in linear equations (the numbers not attached to variables, like the "10" in `a + b = 10`) *do not* affect whether a system is singular or non-singular.

*   **Zeroed-Out Systems:**
    *   Set all constants to zero in the system of equations (e.g., change `a + b = 10` to `a + b = 0`).
    *   This simplifies analysis *without* changing singularity/non-singularity.

*   **Geometric Interpretation of Simplified Systems:**
    *   All lines pass through the origin (0, 0).
    *   Singular systems remain singular, regardless of original constant values.
        *   Redundant systems remain redundant
        *   Contradictory systems become redundant when constants are set to zero.
    *   Non-singular systems remain non-singular

*   **Simplified View:** Allows for easier visualization and analysis of singularity/non-singularity.

# Introducing Matrices: Capturing Coefficients

*   **Matrices from Equation Systems:** Matrices arise naturally from the coefficients in a system of linear equations.

*   **Zeroed-Constant Systems:** Utilize the simplification of setting constants to zero (as it doesn't affect singularity).

*   **Matrix Creation:**
    *   Take the coefficients of the variables (a, b, etc.) in the simplified system.
    *   Arrange them in a rectangular array (the matrix).
    *   Each row corresponds to an equation.
    *   Each column corresponds to the coefficients of a specific variable.

*   **Example:**
    *   System: `a + b = 0`, `a + 2b = 0` becomes matrix `[[1, 1], [1, 2]]`

*   **Singularity & Matrices:**
    *   If the system is non-singular (unique solution), the corresponding matrix is non-singular.
    *   If the system is singular (infinite or no solutions), the corresponding matrix is singular.

*   **3x3 Systems & Matrices:** The same procedure can be applied to three equation and three variable system
    *   System: a+b+c =0;a+2b+c=0;a+b+2c=0 becomes matrix [[1,1,1],[1,2,1],[1,1,2]]

*   **Note:** This process can be extended to systems with any number of variables and equations.

# Linear Dependence: Identifying Singular Matrices

*   **Singularity & Dependence:** A system/matrix is singular if one equation/row carries redundant information. This is captured by the concept of linear dependence.

*   **Linear Dependence:** One equation/row can be obtained as a combination of the other equations/rows.
    *   Example: If Row3 = 2\*Row1 + Row2, then Row3 is linearly dependent on Row1 and Row2.

*   **Linear Independence:** No equation/row can be created as a combination of the others. Each equation/row brings unique information.

*   **2x2 Matrices:**
    *   A 2x2 matrix is singular if one row is a multiple of the other.
    *   A 2x2 matrix is non-singular if the rows are linearly independent.

*   **Larger Matrices (Example):** a=1, b=2, a+b=3
    *   The equation `a + b = 3` is redundant as it is the sum of the first two equations.
    *   Corresponding matrix `[[1, 0, 0], [0, 1, 0], [1, 1, 0]]` has linearly dependent rows because Row3 = Row1 + Row2.

*   **Identifying Linear Dependence:**
    *   Look for relationships between equations/rows.
    *   Can one be obtained as a sum, difference, or scaled multiple of the others? It could require more complex algebraic operations

*   **Singularity Implies Dependence:**
    *   A matrix with linearly dependent rows is singular.
    *   A matrix with linearly independent rows is non-singular.

# The Determinant: A Quick Test for Singularity

*   **Linear Dependence & Singularity:** Singular matrices have linearly dependent rows.
*   **The Determinant:** A formula that quickly indicates singularity.
    *   Determinant = 0: Matrix is singular.
    *   Determinant != 0: Matrix is non-singular.

*   **2x2 Determinant Formula:**
    *   For matrix `[[a, b], [c, d]]`, the determinant is `ad - bc`.  (Main diagonal product minus anti-diagonal product)

*   **Calculating Determinants:**
    *   Non-singular matrix (example) has a non-zero determinant.
    *   Singular matrix has a zero determinant.

*   **3x3 Determinant:** More complex, but follows a similar pattern:
     *  Consider the main diagonal with entries 1, 2, and 2. Its product is 1*2*2 = 4. Now consider the next one with entries 1, 1, 1, so the product of these entries is one. Now, the next one, again with product of entries one. Now we're going to subtract the diagonals that go in the other direction, so this one is 1*2*1 = 2, this one over here is 1*1*1 = 1, and this one over here is 1*1*2 = 2. We're adding 4+1+1-2-1-2

*   **Triangular Matrices:**
    *   If all elements *below* the main diagonal are zero (upper triangular matrix), the determinant is simply the product of the elements *on* the main diagonal.
    *   These *can* still be singular if one of the diagonal elements is zero.

*   **Singular System Summary:**
    *   **Not a Unique Solution:** Has either infinitely many solutions or no solution.
    *   **Determinant is Zero:** Calculating the determinant will result in zero.
    *   **Linearly Dependent:** Equations/rows are linearly dependent.
    *   **No Inverse:** The corresponding matrix does not have an inverse.