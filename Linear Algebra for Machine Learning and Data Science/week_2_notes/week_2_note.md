# Solving Systems of Linear Equations: A Step-by-Step Guide

This note summarizes a method for solving systems of linear equations, including identifying singular systems. The goal is to transform the original system into a "solved system" where each equation directly gives the value of a variable (if a unique solution exists).

## The Approach: Manipulation & Transformation

The key idea is to manipulate the equations in a way that preserves the solution while simplifying the system. Allowed manipulations include:

1.  **Multiplying an equation by a constant:** This doesn't change the information the equation carries (e.g., if `a + b = 10`, then `7a + 7b = 70` is equivalent).

2.  **Adding two equations:** The resulting equation is also true if the original equations are true.

## Example: Solving 5a + b = 17 and 4a - 3b = 6

Here's a walkthrough of solving a 2x2 system:

1.  **Normalize 'a' coefficients (Optional, but helpful):** Divide each equation by the coefficient of 'a' to make it 1.
    *   `5a + b = 17` becomes `a + 0.2b = 3.4`
    *   `4a - 3b = 6` becomes `a - 0.75b = 1.5`

2.  **Eliminate 'a' from the second equation:** Subtract the first equation from the second equation (component-wise):
    *   `(a - 0.75b) - (a + 0.2b) = 1.5 - 3.4`
    *   This simplifies to `-0.95b = -1.9`

3.  **Solve for 'b':** Divide both sides by -0.95 to get `b = 2`.

4.  **Substitute 'b' into the first equation:** Plug `b = 2` back into `a + 0.2b = 3.4`.
    *   `a + 0.2(2) = 3.4`
    *   `a + 0.4 = 3.4`
    *   `a = 3`

5.  **Solution:** The solved system is `a = 3` and `b = 2`.

## Dealing with Singular Systems (or Easy Cases)

Sometimes, the initial steps reveal a variable's value directly:

*   **Example:** Consider `5a + b = 17` and `3b = 6`. You want to eliminate 'a' from the second equation. However, the second equation *already* doesn't have 'a'! It directly implies `b = 2`.
*   **What to do:** Directly solve for that variable (in this case, `b`). Then, substitute that value into the *other* equation to solve for the remaining variable.


# Solving Singular Systems of Linear Equations

This note expands on the method for solving linear systems, focusing on how it handles singular cases: those with either infinitely many solutions (redundant) or no solutions (contradictory).

## Redundant Systems: Infinite Solutions

**Example:** Consider `a + b = 10` and `2a + 2b = 20`.  The second equation is just a multiple of the first, making it redundant.

1.  **Normalize 'a' coefficients (Optional):** Dividing each equation by the 'a' coefficient gives us `a + b = 10` and `a + b = 10`. They are identical!

2.  **Eliminate 'a' from the second equation:** Subtracting the first equation from the second gives `0 = 0`.

3.  **Interpretation:** `0 = 0` is trivially true but provides *no* information about the values of `a` or `b`. The system is now described by a *single* equation: `a + b = 10`.

4.  **Solution Parameterization:** Because one equation has been effectively eliminated we have freedom, we can define a paramater, say x. Let a = x.  Then, since `a + b = 10`, it follows that `b = 10 - x`. The general solution is thus: `(a, b) = (x, 10 - x)`, where 'x' can be any value. This system has infinitely many solutions forming a line.

## Contradictory Systems: No Solutions

**Example:** Consider `a + b = 10` and `2a + 2b = 24`.

1.  **Normalize 'a' coefficients (Optional):** Dividing each equation by the 'a' coefficient yields `a + b = 10` and `a + b = 12`.

2.  **Eliminate 'a' from the second equation:** Subtracting the first equation from the second gives `0 = 2`.

3.  **Interpretation:** `0 = 2` is a *contradiction*. This indicates that the system has *no* solution.  The equations are inconsistent.

## Key Takeaway

The process of trying to solve a system of linear equations can also reveal if the system is singular:

*   **Redundant System:** If you end up with `0 = 0`, the system is redundant and has infinitely many solutions. Parameterize one variable and express the others in terms of it.

*   **Contradictory System:** If you end up with `0 = C` (where `C` is a non-zero constant), the system is contradictory and has no solutions.


# Solving Systems of Three Equations with Three Variables

This note outlines how to solve systems of three linear equations with three unknowns (e.g., a, b, c). The process is similar to solving 2x2 systems, aiming to isolate each variable in a specific equation.

## The Strategy: Step-by-Step Elimination

1.  **Isolate 'a' in the first equation:** The goal is to have 'a' appear *only* in the first equation and with a coefficient of 1.
    *   **Normalize the first column:** Divide each *equation* by the coefficient of 'a' in that equation. This ensures that 'a' has a coefficient of 1 in all the equations.
    *   **Eliminate 'a' from the second and third equations:** Subtract the (modified) first equation from the second and third equations.  This will leave only 'b' and 'c' in those equations.

2.  **Solve the resulting 2x2 system (for 'b' and 'c'):** After step 1, you're left with two equations with two unknowns ('b' and 'c'). Use the methods you learned previously (multiplying by constants, adding/subtracting equations) to solve for 'b' and 'c'.
    *   **Normalize for 'b':** Divide equation two and three by their b coefficients so 'b' is 1.
    *   **Eliminate b:** Subtract equation two from equation three so equation three only has c. Isolate the value of c.

3.  **Back-Substitution:** Once you've found 'b' and 'c', substitute those values back into the equations to find 'a'. This is done in a reverse order
    *   Substitute b into equation two so b is gone and solve for c.
    *   Replace the values ​​of b and c into equation one so that the only one is a, and isolate a.

## Example

The video has a more detailed example, but here's a conceptual outline of the example mentioned.

**Solve:**

*   Equation 1:  (some expression with a, b, and c) = (some constant)
*   Equation 2:  (some expression with a, b, and c) = (some constant)
*   Equation 3:  (some expression with a, b, and c) = (some constant)

**Steps:**

1. Normalize a column 1:  a has a value of 1.
2. Remove a from 2 and 3.
3. Normalize b column 2
4. Isolate equation 3 to have variable b.

**Final Solution**

1. Use what you have and solve the equations!

This method systematically reduces the problem until each variable can be determined. Remember to carefully track your manipulations and substitutions to avoid errors.


# Matrix Row Reduction (Gaussian Elimination)

This note explains matrix row reduction, also known as Gaussian elimination, as a systematic way to simplify a matrix and extract useful information. It's directly related to solving systems of linear equations through manipulation.

## Connection to Solving Linear Equations

When solving a system of linear equations, you manipulate the equations to isolate variables. Matrix row reduction applies those *same* manipulations to the rows of the coefficient matrix.

**Example:**

Consider the system:

*   `5a + b = 17`
*   `4a - 3b = 6`

The original approach would eliminate `a` from the second equation, then substitute back to solve. This results in a "solved system":

*   `a = 3`
*   `b = 2`

In matrix form, this translates to:

1.  **Original System (Coefficient Matrix):** `[[5, 1], [4, -3]]`
2.  **Intermediate System (Row Echelon Form):** `[[1, ...], [0, 1]]` ... some manipulations... The key is having 1s on the diagonal and 0s below. This corresponds to one of the original equations, solved for a variable.
3.  **Solved System (Reduced Row Echelon Form):** `[[1, 0], [0, 1]]` This is the identity matrix, directly telling us the solution (3, 2) if we tack on the result vector as the last column to the matrix.

## Row Echelon Form (REF)

A matrix in row echelon form has the following characteristics:

*   All non-zero rows are above any rows of all zeros.
*   The leading coefficient (the first non-zero number) of a non-zero row is always strictly to the right of the leading coefficient of the row above it.
*   All entries in a column below a leading coefficient are zero.
*   In some definitions, the leading coefficient must be one.

## Reduced Row Echelon Form (RREF)

In the reduced row echelon form:

*    All zero rows are at the bottom of the matrix.
*   The leading entry in each non-zero row is 1 (called a leading 1).
*   Each leading 1 is the only non-zero entry in its column.
*   The leading 1 in any row is to the right of the leading 1 in the row above.

## REF and Singular Systems

Even in singular systems, REF provides information:

*   **Example (Redundant):** The system transforms into equations of 0 = 0
*   **REF Result:** A row of zeros in the REF indicates that you had dependent equations (redundancy).

## General REF Structure

A matrix in REF generally looks like this:

*   **Diagonal:** A sequence of 1s, possibly followed by a sequence of 0s.
*   **Below Diagonal:** All entries are 0.
*   **Right of 1s:** Any numbers are allowed (represent coefficients).
*   **Right of 0s:** All entries must be 0.

## Possible 2x2 REF Matrices

Based on these rules, for 2x2 matrices in REF, only three possibilities exist:

1.  `[[1, ...], [0, 1]]`  (Two 1s on the diagonal)
2.  `[[1, ...], [0, 0]]`  (One 1 on the diagonal)
3.  `[[0, 0], [0, 0]]` (Zero 1s on the diagonal)