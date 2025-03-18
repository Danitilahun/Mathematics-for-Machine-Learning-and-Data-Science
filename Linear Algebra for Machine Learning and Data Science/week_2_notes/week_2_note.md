# Table of Contents

1.  [Solving Systems of Linear Equations: A Step-by-Step Guide](#solving-systems-of-linear-equations-a-step-by-step-guide)
    *   [The Approach: Manipulation & Transformation](#the-approach-manipulation--transformation)
    *   [Example: Solving 5a + b = 17 and 4a - 3b = 6](#example-solving-5a--b--17-and-4a---3b--6)
    *   [Dealing with Singular Systems (or Easy Cases)](#dealing-with-singular-systems-or-easy-cases)

2.  [Solving Singular Systems of Linear Equations](#solving-singular-systems-of-linear-equations)
    *   [Redundant Systems: Infinite Solutions](#redundant-systems-infinite-solutions)
    *   [Contradictory Systems: No Solutions](#contradictory-systems-no-solutions)
    *   [Key Takeaway](#key-takeaway)

3.  [Solving Systems of Three Equations with Three Variables](#solving-systems-of-three-equations-with-three-variables)
    *   [The Strategy: Step-by-Step Elimination](#the-strategy-step-by-step-elimination)
    *   [Example](#example)

4.  [Matrix Row Reduction (Gaussian Elimination)](#matrix-row-reduction-gaussian-elimination)
    *   [Connection to Solving Linear Equations](#connection-to-solving-linear-equations)
    *   [Row Echelon Form (REF)](#row-echelon-form-ref)
    *   [Reduced Row Echelon Form (RREF)](#reduced-row-echelon-form-rref)
    *   [REF and Singular Systems](#ref-and-singular-systems)
    *   [General REF Structure](#general-ref-structure)
    *   [Possible 2x2 REF Matrices](#possible-2x2-ref-matrices)

5.  [Row Operations and Preserving Singularity](#row-operations-and-preserving-singularity)
    *   [Row Operations](#row-operations)
    *   [Why Singularity Preservation Matters](#why-singularity-preservation-matters)
    *   [Key Takeaway](#key-takeaway-1)

6.  [The Rank of a Matrix: Measuring Information](#the-rank-of-a-matrix-measuring-information)
    *   [Rank: A Measure of Information](#rank-a-measure-of-information)
    *   [Rank and Systems of Equations](#rank-and-systems-of-equations)
    *   [Rank and Solution Space](#rank-and-solution-space)
    *   [Rank and Singularity](#rank-and-singularity)

7.  [Rank of 3x3 Matrices: Geometric Interpretation](#rank-of-3x3-matrices-geometric-interpretation)
    *   [Rank and Independent Equations](#rank-and-independent-equations)
    *   [Geometric Interpretation](#geometric-interpretation)
    *   [Finding Rank: A Simpler Way?](#finding-rank-a-simpler-way)

8.  [Calculating Rank Using Row Echelon Form](#calculating-rank-using-row-echelon-form)
    *   [Row Reduction to REF: The Process](#row-reduction-to-ref-the-process)
    *   [Examples](#examples)
    *   [Rank and REF: The Connection](#rank-and-ref-the-connection)
    *   [Singularity and REF](#singularity-and-ref)
    *   [Key Takeaways](#key-takeaways-1)

9.  [Row Echelon Form for Larger Matrices (and Rank)](#row-echelon-form-for-larger-matrices-and-rank)
    *   [General Structure of REF](#general-structure-of-ref)
    *   [Example Matrix Visualization](#example-matrix-visualization)
    *   [Importance of Pivots](#importance-of-pivots)
    *   [Convention for this Course: Pivot Ones](#convention-for-this-course-pivot-ones)
    *   [Calculating Rank: Examples](#calculating-rank-examples)
    *   [Rank from REF](#rank-from-ref)
    *   [Key Takeaways](#key-takeaways-2)

10. [Elementary Row Operations](#elementary-row-operations)

11. [Row Echelon Form (REF) Properties](#row-echelon-form-ref-properties)

12. [Row Echelon Form (REF) vs. Reduced Row Echelon Form (RREF)](#row-echelon-form-ref-vs-reduced-row-echelon-form-rref)

13. [Elementary Row Operations](#elementary-row-operations-1)

14. [Reduced Row Echelon Form (RREF)](#reduced-row-echelon-form-rref-1)

15. [Gaussian Elimination: Solving Linear Systems](#gaussian-elimination-solving-linear-systems)
    *   [The Augmented Matrix](#the-augmented-matrix)
    *   [Gaussian Elimination Steps](#gaussian-elimination-steps)
    *   [Singularity: Infinite Solutions vs. No Solutions](#singularity-infinite-solutions-vs-no-solutions)
    *   [Recap: Gaussian Elimination](#recap-gaussian-elimination)


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


# Row Operations and Preserving Singularity

This note explains row operations in matrices and their critical property: they *preserve singularity*. This means applying row operations to a singular matrix results in a singular matrix, and applying them to a non-singular matrix results in a non-singular matrix.

## Row Operations

These are the allowed manipulations you can perform on a matrix's rows:

1.  **Switching Rows:** Swap the positions of two rows.

    *   **Effect on Determinant:** The determinant of the resulting matrix is the *negative* of the original determinant. If the determinant was 0, it remains 0. If it was non-zero, it remains non-zero (just with a different sign).
    *   **Singularity Preservation:** This operation preserves singularity and non-singularity.

2.  **Multiplying a Row by a Non-Zero Scalar:** Multiply all elements in a row by a constant (that is not zero).

    *   **Effect on Determinant:** The determinant of the resulting matrix is the scalar multiplied by the original determinant.
    *   **Singularity Preservation:** Since the scalar is non-zero, multiplying by it won't change a zero determinant to non-zero, or vice versa. Therefore, this preserves singularity and non-singularity.
    *   **Important Note:** The scalar *must* be non-zero. Multiplying a row by zero *will* change a non-singular matrix into a singular matrix (because it creates a row of all zeros).

3.  **Adding a Row to Another Row:** Add the elements of one row to the corresponding elements of another row.

    *   **Effect on Determinant:** The determinant of the resulting matrix is the *same* as the original determinant.
    *   **Singularity Preservation:** Since the determinant doesn't change, this operation also preserves singularity and non-singularity.

## Why Singularity Preservation Matters

This property is crucial because it means that you can use row operations to simplify a matrix without changing whether it's singular or non-singular. This is fundamental to Gaussian elimination and other matrix decomposition techniques. You can transform a matrix into a simpler form (like row echelon form) and still know if the original matrix had a unique solution (non-singular) or not (singular).

## Key Takeaway

Row operations are powerful tools for manipulating matrices, but it's essential to remember that they *must* be performed correctly to preserve the fundamental properties of the matrix, including its singularity.

# The Rank of a Matrix: Measuring Information

This note explains the concept of the rank of a matrix, which measures how much independent information the matrix (or its corresponding system of linear equations) contains.

## Rank: A Measure of Information

*   **Intuition:** Rank represents the number of *independent* pieces of information within a matrix or a system of equations. Redundant or contradictory information reduces the rank.
*   **Systems of Sentences Analogy:**
    *   "The dog is black" and "The cat is orange": Two pieces of information (rank = 2).
    *   "The dog is black" and "The dog is black": One piece of information (rank = 1). The sentences are the same.
    *   "The dog is" and "The dog is": Zero pieces of information about color (rank = 0). You can't determine any animal color with these messages.

## Rank and Systems of Equations

The rank of a matrix is defined as the rank of its corresponding system of equations.

*   **Example 1 (Full Rank):** System of equations where each equation adds *new* information (e.g., two lines that intersect at a point).  The rank is equal to number of non-redundant rows/equations.
*   **Example 2 (Rank Deficiency):** System of equations where one equation is a multiple of the other (redundant). The system carries only *one* piece of information.
*   **Example 3 (Zero Rank):** A matrix with all zero values has rank zero, it holds no data.

## Rank and Solution Space

There's a relationship between the rank of a matrix and the dimension of its solution space (the set of solutions when the constants on the right-hand side are zero):

`Rank + Dimension of Solution Space = Number of Rows`

*   **Example 1 (Full Rank):** The solution is only a=0, b=0 (a point). Dimension of solution space = 0. If rows = 2, Rank = 2 - 0 = 2
*   **Example 2 (Rank = 1):** The solutions form a line. Dimension of solution space = 1. The rank is calculated as Rank = 2 -1 =1
*   **Example 3 (Rank = 0):** Every a and b is a solution (the entire plane). Dimension of solution space = 2. Rank = 2 - 2 = 0

## Rank and Singularity

*   **Non-Singular Matrix:** Has *full rank* (rank equals the number of rows). This means the equations are independent, and there's a unique solution (or no solution in an overdetermined system).
*   **Singular Matrix:** Has a rank *less* than the number of rows. This indicates redundancy or contradiction, leading to either infinitely many solutions or no solutions.

# Rank of 3x3 Matrices: Geometric Interpretation

This note extends the concept of rank to 3x3 matrices, linking it to the geometric meaning of the corresponding system of equations.

## Rank and Independent Equations

For a 3x3 matrix, the rank reflects the number of *linearly independent* equations in the associated system. A linearly independent equation brings new information that cannot be derived from the other equations. "Not bringing any information" can be interpreted as and equation that is already a linear combination of the other equations in the system.

**Examples:**

*   **System 1 (Rank 3):** All three equations are linearly independent. No equation can be obtained from a combination of the other two. The system has 3 pieces of information. In geometry, this means the three planes intersect at a single point.
*   **System 2 (Rank 2):** One equation is a linear combination of the other two (e.g., the second equation is the average of the first and third). The system has only 2 independent pieces of information. In geometry, this means the three planes intersect along a line (infinite solutions). Two of the planes are needed to define that line.
*   **System 3 (Rank 1):** Two equations are multiples of the first equation. The system has only 1 independent piece of information.  In geometry, this means the three equations all represent variations of the same plane (infinite solutions).
*   **System 4 (Rank 0):** All equations are of the form 0 = 0. No equation provides any information about the variables.  The system has 0 pieces of information.

## Geometric Interpretation

Think of each equation as defining a plane in 3D space:

*   **Rank 3:** Three planes intersect at a single point (unique solution).
*   **Rank 2:** Three planes intersect along a line (infinitely many solutions).
*   **Rank 1:** Three equations describe the same plane (infinitely many solutions).
*   **Rank 0:** No planes or system does not make sense to even exist as the values hold nothing/ or the data in them are not usable at all.

## Finding Rank: A Simpler Way?

The next step will explore a simpler method for calculating the rank of a matrix, likely involving the row echelon form (REF). Transforming a matrix to its REF and using the number of nonzero rows as the rank simplifies computation.

# Calculating Rank Using Row Echelon Form

This note explains how to determine the rank of a matrix using its row echelon form (REF), providing a straightforward method for calculating rank after performing row reduction.

## Row Reduction to REF: The Process

To find the REF of a matrix:

1.  **Divide by Leading Coefficients:** Divide each row by its leftmost non-zero coefficient (the "leading coefficient"). This makes the leading coefficient equal to 1.

2.  **Eliminate Below Leading Coefficients:** Use row operations (subtracting multiples of one row from another) to make all entries below the leading coefficients in each column equal to zero.

3.  **Handle Zero Rows:** If you encounter a row with all zeros, leave it at the bottom of the matrix. You cannot divide by zero, so skip this

## Examples

1.  **Non-Singular Matrix:**
    * Matrix : [[5,1], [4,-3]]
    * First step: [[1,0.2], [1,0.75]]
    * Second step: [[1, 0.2], [0, -0.95]]
    * Matrix After Normalizing: [[1,0.2], [0,1]]

2.  **Singular Matrix:**
    * Matrix: [[5,1], [10,2]]
    * First step: [[1,0.2],[1,0.2]]
    * Next Step: [[1,0.2], [0,0]]
    Since the leftmost entries cannot be divided, stop and this is the row echelon form for this matrix.

3.  **Very Singular Matrix:**
    * Matrix: [[0,0], [0,0]]
    * In this case, there is nothing to do since all values are already zero. Just say this is the row echelon form

## Rank and REF: The Connection

The *rank* of a matrix is equal to the *number of non-zero rows* in its row echelon form or, if you force the diagonal to contain 1's then the rank of a matrix is equal to the *number of ones* on the diagonal in the row echelon form.

*   **Example 1 : Rank is 2 and both leading values are 1.**
*   **Example 2: Rank is 1 because there is one value on the leading diagonal.
*   **Example 3: Rank is 0 as the entries contain nothing to work with.**

## Singularity and REF

*   **Non-Singular Matrix:** Its REF will have leading 1s on the entire main diagonal (no zeros on the diagonal). The rank is equal to the number of rows and the number of columns.
*   **Singular Matrix:** Its REF will have at least one zero on the diagonal meaning it will be rank deficient, the rank will be less than the number of rows.

## Key Takeaways

*   Row reduction to REF provides a systematic way to calculate the rank of a matrix.
*   The rank, determined from the REF, reveals important information about the nature of the matrix and the corresponding system of linear equations (whether it has unique, infinite, or no solutions).
*   REF also provides an easier, more organized way to tell if a matrix is singular or non-singular.


# Row Echelon Form for Larger Matrices (and Rank)

This note extends the concept of row echelon form (REF) to larger matrices (beyond 2x2) and reinforces its connection to the rank of a matrix.

## General Structure of REF

A matrix in row echelon form (REF) follows these rules:

*   **Zero Rows at the Bottom:** Any rows consisting entirely of zeros are at the bottom of the matrix.
*   **Pivots:** Each non-zero row has a *pivot* (the leftmost non-zero entry).
*   **Pivot Placement:** Every pivot must be strictly to the right of the pivots of all the rows above it. In other words, if you imagine drawing a line that connects all the pivots, the only matrix that must follow is that the diagonal cannot have anything to the left of it.
*   **Entries Below Pivots:** All entries *below* a pivot must be zero. The pivot is the lowest left the matrix can be, there cannot be anything below its value.

## Example Matrix Visualization

REF might look something like these matrix (the * represents possible values):
1.  * * *
2.  0 1 *
3.  0 0 1

The number of non-zero entries is the matrix is also its rank

## Importance of Pivots

*   Pivots are key to determining the rank.
*   In REF, the number of pivots directly tells you the rank of the matrix. The pivot should only contain leading one entries, so all rows that have only leading entries means it is rank dependent. If pivot =0, then the rows are not rank dependent and we need other rows.

## Convention for this Course: Pivot Ones

*   This class will use a specific convention for REF: *the pivots must always be equal to 1*.
*   To achieve this, always divide each row by its leading non-zero entry after placing a pivot.
*   This is for consistency with solving systems of equations (where you'd divide by the coefficient of the leading variable).
*   *This does not affect the rank.* It's simply a cosmetic step to standardize the REF. There is also no zero on the diagonal, so it will be a full diagonal
*   This convention will be consistent by getting rid of the variables and dividing by leading entries or coefficients to isolate our variable and to create one. This leads to a easier way of figuring what the values are in our matrix.

## Calculating Rank: Examples

1. If the system can be simplified to the pivot ones then subtract any two rows where one another can create the 0 and 1 value for all of them.
2. A singular matrix has one pivot value and there can be no more actions done

## Rank from REF

*   The *rank* of a matrix is equal to the *number of pivot ones* in its row echelon form (using our convention). To do this use the steps of: subtracting entries, row operations to leading coefficients to get what they want in the matrix. Remember if a row consists of nothing other than a row that is 0 that is a pivot.

This is a straightforward way to determine the rank of a matrix after performing row reduction. This also brings the idea that for row echelon matrices there is no need to solve what they are. Because of the simple format and what they turn, it helps us simplify the math and isolate the value to be solved.

## Key Takeaways

*   The structure and conventions of REF provide an accessible way to calculate the rank of a matrix.
*   Understanding pivots is fundamental to understanding REF and rank.
*   In the videos, it highlights a specific way of visualizing it to simply the math, while being able to isolate it and solve it.

# Reduced Row Echelon Form (RREF)

This note explains reduced row echelon form (RREF), which is a further simplification of row echelon form (REF).

## Getting to RREF: The Process

The goal is to transform the matrix into an even simpler form that uniquely identifies solutions.

1.  **Start with Row Echelon Form (REF):** First, the matrix must already be in REF, so divide until it is 1 so the process is easier and more consistent to apply.

2.  **Zeroes Above Pivots:** Use each pivot to eliminate all non-zero entries *above* it in its column. You're making all entries in a column that has a leading 1 into zero. You want to use the numbers above to make the values for what each entry should be.

## Relationship to Solving Systems

Recall the reason why you are making all the numbers zero is because with doing this there should be only one value. All the variables involved will be equal to zero. With that you will come close

## General Form

A matrix in RREF has these characteristics:

*   It is in row echelon form.
*   Each pivot is a 1 (this is our course's convention for REF as well).
*   All entries *above* each pivot are 0.

## Methods of Simplifying Entries

When you simplify make sure you follow how the process was created:
1. Remember every row can get a value for how important it can be
2. This also gives an easier visualization for the matrix to what it should be.

## Properties:

Make each Pivot 1 to clear it and remember there can be two types 
* With values: You have the pivot value that you can change to work with the row.
* All zero: you have a zero row so there is really nothing you can do.
## Key Takeaways

RREF is a unique, highly simplified form of a matrix:

*   REF matrices can go through a further row operation. Remember to always follow what REF matrices are meant to and with making the pivots all zero. 


# Gaussian Elimination: Solving Linear Systems

This note outlines Gaussian elimination, a formalized algorithm for solving systems of linear equations using row operations and an augmented matrix.

## The Augmented Matrix

*   **Concept:** To solve a system, include the constant values from the right-hand side of the equations. To do this simply append it as another column to the coefficinet matrix.
*   **Augmented Matrix:** This combined matrix, with coefficients and constants, is called the augmented matrix. Add a line to remind yourself.

## Gaussian Elimination Steps

1.  **Create the Augmented Matrix:** Form the matrix from the coefficients in the system of equations. To do this take the last row of one of the equation and add it a a final row of the matrix
2.  **Pivot Selection:** Locate a pivot point along the diaganol. Make the first element a one so it is easier to continue the process.
3.  **Make Element one:** Get the pivot as 1 to move on.
4.  **Eliminate Below Pivot:** Use row operations to make all values below the pivot equal to 0. You want all the entires with the pivot to zero

5. *The rows with the pivots should be at least rank dependent with another value ( 1,3,1 )*
6.  **Make Next Pivot 1:** Once the element is zero you will move to another column and another pivot
7.  **Isolate system, look to Back Substitution.** Make values in the row equal to 1
8.  **Repeat the process in each diagonal**

*After this process the system can be solved through this equation*
*a is 0 b is minus one and c is 0*
## Singularity: Infinite Solutions vs. No Solutions

If, during Gaussian elimination, you encounter a row of all zeros *on the coefficient side* of the augmented matrix, the system is singular. *However, you must look at the corresponding value on the constant side to determine whether you have infinite or no solutions.*

*   **Infinite Solutions:**  If the entire row (including the constant) is zero, then that row represents the equation `0 = 0`. This is always true, and it means that the system has infinitely many solutions.
    *   Think of this as the original equations being dependent, so one equation is essentially redundant. The number of free variables equals the number of zero rows in the diagonal and solve system by a variable.

*   **No Solutions (Contradictory):** If the row on the coefficient side is all zeros, *but the constant on the right-hand side is non-zero*, then that row represents an equation like `0 = 4` (or any other non-zero number). This is a contradiction, meaning that the system has no solutions. The equations are inconsistent.

The presence of a row with only zero on coefficient means singularity, but with constant it will tell you if the situation is correct.

## Recap: Gaussian Elimination

1.  **Create Augmented Matrix** Create each row.
2.  **Reduce to REF** Put into row echelon form
  - Check to see if row consists of nothing:
     1: If that number is 0, then INFINITE solutions!
     2: If the number is anything but 0, the NO solutions.
Make sure each are pivot equals = 1 and then make it back substuited

This helps provide a step for what to look for and find all the values needed. Make sure to learn this well and that you can utilize it and memorize well.