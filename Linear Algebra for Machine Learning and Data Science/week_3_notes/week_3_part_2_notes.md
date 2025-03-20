## Linear Transformations: Matrices as Transformations of Space

**1. Matrices as Linear Transformations**

*   A powerful way to visualize matrices.
*   Linear transformation: Sends each point in a plane (or higher dimension) to another point in a structured way.
*   Example: 2x2 Matrix

**2. Illustration in 2D**

*   Consider a 2x2 matrix (e.g., `| 3 1 |` `| 1 2 |`).
*   Two planes:
    *   Left: Original space (a, b axes).
    *   Right: Transformed space.
*   Transformation process:
    1.  A point in the left plane has coordinates (a, b), forming a column vector.
    2.  Multiply the matrix by the column vector.
    3.  The resulting vector is the point in the transformed (right) plane.

**3. Examples**

*   **Origin (0, 0):** Always maps to the origin (0, 0) in a linear transformation.
*   **(1, 0):**  Matrix * `| 1 |` = `| 3 |`, so (1, 0) goes to (3, 1).
               `| 0 |`    `| 1 |`
*   **(0, 1):**  Matrix * `| 0 |` = `| 1 |`, so (0, 1) goes to (1, 2).
               `| 1 |`    `| 2 |`
*   **(1, 1):** Matrix * `| 1 |` = `| 4 |`, so (1, 1) goes to (4, 3).
               `| 1 |`    `| 3 |`

**4. Basis and Tessellation**

*   The square formed by (0,0), (1,0), (0,1), (1,1) in the original space is called a *basis*.
*   The parallelogram formed by their transformed points in the transformed space is also a *basis*.
*   A basis "covers" (tessellates) the entire plane.

**5. Linear Transformation as a Change of Coordinates**

*   Example: Find where (-2, 3) goes.
*   Starting at the origin, walk 2 blocks to the left and 3 blocks up in the original coordinates.
*   To find the transformed point, do the same in the *new* coordinates defined by the linear transformation.
*   Result: (-2, 3) maps to (-3, 4).
*   Calculation: Matrix * `| -2 |` = `| -3 |`
                       `|  3 |`   `|  4 |`

**6. Apple/Banana Example (Intuition)**

*   Imagine you go to the store:
    *   Day 1: Buy 3 apples and 1 banana.
    *   Day 2: Buy 1 apple and 2 bananas.
*   Let the price of apples be *a* and bananas be *b*.
*   Total price each day:
    *   Day 1: 3a + 1b
    *   Day 2: 1a + 2b
*   Matrix * `| a |` =  `| 3a + b |`  =  `| Price on Day 1 |`
         `| b |`      `| a + 2b |`       `| Price on Day 2 |`

*   Linear Transformation: Maps from (price of apple, price of banana) to (price on day 1, price on day 2).
*   **Example:** Apples are $1 and bananas are $1.
    *   Matrix * `| 1 |` = `| 4 |`
             `| 1 |`     `| 3 |`
    *   The point (1,1) which is price of apple and bananas maps to (4,3) which is price of day 1 and 2.
*   "Change of Coordinates": Price of apples/bananas to price paid on each day.


# Finding the Matrix of a Linear Transformation

This note summarizes how to find the matrix representation of a linear transformation, given how it transforms the standard basis vectors.

**Key Idea:** A linear transformation is fully determined by where it sends the basis vectors. In 2D space, these are typically the vectors (1, 0) and (0, 1).

**Process:**

1. **Identify the Images of the Basis Vectors:** Determine where the linear transformation sends the vectors (1, 0) and (0, 1).

2. **Construct the Matrix:** The images of the basis vectors form the columns of the matrix.

**Explanation:**

The video explains that matrix multiplication effectively transforms a vector by considering it as a linear combination of the column vectors of the matrix. Since (1,0) and (0,1) form the basis, where they are mapped to defines the entire transformation. This is how matrix multiplication works.

**Important Note:** This method relies on the fact that the transformation is *linear*. If the transformation is not linear, this method will not work.

# Matrix Multiplication as Composition of Linear Transformations

This note explains matrix multiplication, emphasizing its interpretation as the composition of linear transformations.

**Key Idea:** Multiplying matrices corresponds to applying linear transformations one after the other. This results in a new linear transformation that is equivalent to the combined effect of the original transformations.

**1. Linear Transformation Review:**

* A matrix represents a linear transformation that maps vectors from one space to another.
* For example, the matrix `| 3 1 |` transforms the basis vector (1,0) to (3,1) and (0,1) to (1,2).  This creates a new basis from the standard basis.
`| 1 2 |`

**2. Combining Linear Transformations:**

* If we have two linear transformations, represented by matrices A and B, applying B first and then A is equivalent to a single linear transformation.
* This combined transformation is represented by the matrix product A*B.
* **Important:** The order matters! If B is applied first, it is written on the right in the matrix product A*B.  This is because matrix-vector multiplication is written as Mv, where the matrix M acts on the vector v from the left.
* For example, transformation A represented by matrix `| 3 1 |` followed by Transformation B represtned by  `| 1 2 |`

**3. Calculating the Matrix Product:**

* To find the matrix product A*B, take the dot product of each row of A with each column of B.  The result of the dot product of row i of A and column j of B becomes the element in row i, column j of the resulting matrix.

* The calculation is as follow
 `| 3 1 |` * `| 2 -1 |` = `| (3*2 + 1*0) (3*-1 + 1*2) |` = `| 6 -1 |`
`| 1 2 |`   `| 0 2 |`   `| (1*2 + 2*0) (1*-1 + 2*2) |`   `| 2 3 |`

**4. General Matrix Multiplication:**

* Matrix multiplication is defined for non-square matrices as well, but there are size restrictions:
    * If A is an *m x n* matrix and B is a *p x q* matrix, then A*B is defined only if *n = p*.
    * The resulting matrix A*B will be an *m x q* matrix.
* To calculate A*B, take the dot product of the rows of A with the columns of B.
* This is as follow if we have A * B=
  `| a b |` * `| e f |` = `| a*e + b*g a*f + b*h |`
  `| c d |`   `| g h |`   `| c*e + d*g c*f + d*h |`

**5. Summary:**

* Matrix multiplication is a powerful tool that can be interpreted in two ways:
    * **Algebraically:** Multiplying the corresponding rows and columns using dot products.
    * **Geometrically:** Combining linear transformations.

Understanding both perspectives allows for a deeper understanding of linear algebra.

# The Identity Matrix

This note explains the concept of the identity matrix and its role in matrix multiplication and linear transformations.

**Key Idea:** The identity matrix acts like the number '1' in matrix multiplication. Multiplying any matrix by the identity matrix results in the original matrix. Geometrically, the identity matrix represents the linear transformation that leaves the space unchanged.

**1. Definition:**

* The identity matrix, denoted by **I**, is a square matrix with ones on the main diagonal (from top left to bottom right) and zeros everywhere else.
* Examples:
    * 2x2 Identity Matrix: `| 1 0 |`
                            `| 0 1 |`
    * 3x3 Identity Matrix: `| 1 0 0 |`
                            `| 0 1 0 |`
                            `| 0 0 1 |`

**2. Property:**

* For any matrix **A**, the following holds:
    * **A * I = A**  (Right Multiplication)
    * **I * A = A**  (Left Multiplication)

**3. Linear Transformation Interpretation:**

* The linear transformation corresponding to the identity matrix is the *identity transformation*.
* It maps every vector to itself:  v -> v.
* It leaves the space unchanged; there's no scaling, rotation, or shearing.
* The standard basis vectors (1, 0), (0, 1) are all mapped to themself by the transformation.

**4. Why it Works (Example):**

Consider the 2x2 identity matrix and a vector (a, b):

`| 1 0 | * | a | = | (1*a + 0*b) | = | a |`
`| 0 1 |   | b |   | (0*a + 1*b) |   | b |`

This demonstrates that multiplying the identity matrix by a vector leaves the vector unchanged.  The same principle applies to matrix-matrix multiplication.

**In Summary:** The identity matrix is a fundamental concept in linear algebra. It serves as the neutral element for matrix multiplication and represents the "do nothing" transformation.

# Inverse Matrices

This note explains the concept of an inverse matrix and how it relates to undoing a linear transformation.

**Key Idea:** The inverse of a matrix *undoes* the transformation performed by the original matrix.  When a matrix is multiplied by its inverse, the result is the identity matrix.

**1. Analogy to Numerical Inverses:**

* Just like a number has an inverse (e.g., the inverse of 2 is 1/2, because 2 * (1/2) = 1), a matrix can have an inverse.
* The inverse of a matrix **A**, denoted as **A⁻¹**, satisfies the property:
    * **A * A⁻¹ = I**
    * **A⁻¹ * A = I**
    * Where **I** is the identity matrix.

**2. Linear Transformation Interpretation:**

* If a matrix **A** represents a linear transformation that maps a vector space to a new space, then **A⁻¹** represents the linear transformation that maps the new space *back* to the original space.
* In other words, **A⁻¹** undoes the scaling, rotation, and shearing performed by **A**.
* If you apply transformation `A` than you apply `A^-1` you return in the origin space.

**3. Finding the Inverse (2x2 Example):**

* Let's say we have a matrix **A** = `| 3 1 |`.  We want to find its inverse, **A⁻¹** = `| a b |`.
`| 1 2 |`                                                                `| c d |`
* Then **A * A⁻¹ = I** which means
  `| 3 1 |` * `| a b |` = `| 1 0 |`
  `| 1 2 |`   `| c d |`   `| 0 1 |`

* Multiplying the matrices on the left, we get the following system of linear equations:

    * 3a + c = 1
    * 3b + d = 0
    * a + 2c = 0
    * b + 2d = 1

* Solve this system of equations for a, b, c, and d. The solution will give you the entries of the inverse matrix **A⁻¹**. In this case, A^-1 =  `| 2/5 -1/5 |`
                                                                                                             `| -1/5 3/5 |`

**4. When Does an Inverse Exist?**

* Not all matrices have inverses. If a matrix does not have an inverse, it is called *singular* or *non-invertible*.

* The example from the video give use the following equations a + c = 1, 2b + 2d = 0, 2a + 2c = 0 and b + d = 1.

* a + c = 1 and 2a + 2c = 0 is a contradiction since the first equation says a + c = 1 and the third equation says 2a + 2c = 0, but if a + c = 1, then 2a + 2c has to be 2. It cannot be 0.

**5. Summary:**

* The inverse matrix is a matrix that "undoes" the transformation of the original matrix.
* Finding the inverse involves solving a system of linear equations.
* Not every matrix has an inverse.