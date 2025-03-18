## Week 3: Vectors, Matrices, and Linear Transformations in Machine Learning

**Table of Contents**

*   [Main Topics](#main-topics)
*   [1. Vectors and Matrices as Numbers (Analogy)](#1-vectors-and-matrices-as-numbers-analogy)
*   [2. Linear Regression: A System of Linear Equations](#2-linear-regression-a-system-of-linear-equations)
*   [3. Neural Networks: Collections of Linear Models](#3-neural-networks-collections-of-linear-models)
*   [4. Linear Algebra's Role in Neural Networks](#4-linear-algebras-role-in-neural-networks)
*   [Vectors: Magnitude and Direction](#vectors-magnitude-and-direction)
*   [1. Magnitude (Size): Norms](#1-magnitude-size-norms)
*   [2. Direction](#2-direction)
*   [Vector Notations](#vector-notations)
*   [Generalized Norm Definitions (n components)](#generalized-norm-definitions-n-components)
*   [Vector Addition, Subtraction, and Scalar Multiplication](#vector-addition-subtraction-and-scalar-multiplication)
*   [1. Vector Addition](#1-vector-addition)
*   [2. Vector Subtraction](#2-vector-subtraction)
*   [3. Distance Between Vectors](#3-distance-between-vectors)
*   [4. Scalar Multiplication](#4-scalar-multiplication)
*   [Dot Product](#dot-product)
*   [1. Dot Product: A Compact Way to Express Systems of Linear Equations](#1-dot-product-a-compact-way-to-express-systems-of-linear-equations)
*   [2. Dot Product and Norm](#2-dot-product-and-norm)
*   [3. Transpose](#3-transpose)
*   [4. Formal Definition of the Dot Product](#4-formal-definition-of-the-dot-product)
*   [Angle Between Vectors and the Dot Product](#angle-between-vectors-and-the-dot-product)
*   [1. Orthogonal (Perpendicular) Vectors](#1-orthogonal-perpendicular-vectors)
*   [2. Dot Product and Angle](#2-dot-product-and-angle)
*   [3. Sign of the Dot Product and Vector Orientation](#3-sign-of-the-dot-product-and-vector-orientation)
*   [Matrix-Vector Multiplication](#matrix-vector-multiplication)
*   [1. Matrix-Vector Multiplication: Representing Systems of Linear Equations](#1-matrix-vector-multiplication-representing-systems-of-linear-equations)
*   [2. System of Equations as Matrix-Vector Product](#2-system-of-equations-as-matrix-vector-product)
*   [3. Dimensions and Compatibility](#3-dimensions-and-compatibility)

---

**Main Topics:**

*   Vectors and matrices
*   Properties: size, direction
*   Vector/Matrix Operations (addition, multiplication, etc.)
*   Matrix Inverses
*   Linear Transformations

**Key Takeaway:** Vectors and matrices are essential for representing datasets and building machine learning models.

---

**1. Vectors and Matrices as Numbers (Analogy)**

*   Just like numbers can be added, multiplied, etc., similar operations can be applied to vectors and matrices.
*   Example: Sum of vectors, product of vectors, product of matrices, product of vector & matrix.
*   Matrix inverse (analogous to the multiplicative inverse of a number).

---

**2. Linear Regression: A System of Linear Equations**

*   Recall linear regression from Week 1:
    *   Dataset with features `x_1, x_2, ..., x_n`
    *   Multiple examples (rows) in feature matrix `X`
    *   Target vector `y`
*   Goal: Find weights `w_1, w_2, ..., w_n` (vector `W`) and bias `b`
*   Linear equation: `W * X + b = y_hat` (where `y_hat` is the vector of predicted target values)
*   Machine Learning: Solve this system iteratively to make predictions for new `x` values.

---

**3. Neural Networks: Collections of Linear Models**

*   Real-world data is often nonlinear, requiring more complex models.
*   Neural networks approximate nonlinear systems using many smaller linear models chained together.

**Neural Network Architecture (Simplified):**

*   **Input Layer:** Represents features `x_1, x_2, ..., x_n`
*   **Hidden Layers:**
    *   Each neuron in a layer contains a linear model: `W * X + b`
    *   An *activation function* is applied to this linear output.
    *   Layers contain multiple Neurons that have different weights, bias and outputs
    *   Output from this layer becomes the input for the next layer.
*   **Output Layer:** Final prediction.

**Layer-by-Layer Processing:**

1.  **Layer 1:** `W[1] * X + b[1] = a[1]`
    *   `X` is the matrix of input features
    *   `W[1]` is a matrix of weights in layer 1
    *   `b[1]` is a vector of biases in layer 1
    *   `a[1]` is the matrix of the activated values of the first layer.
2.  **Layer 2:** `W[2] * a[1] + b[2] = a[2]`
    *   `a[1]` becomes the input of layer 2.
    *   Linear model from previous layer with different set of weights and a bias value in each case.
3.  Repeat for each layer, using the output of the previous layer as input.

**Key Idea:**

*   Neural networks are complex due to their scale, but fundamentally they're built from many small, interconnected linear models.
*   Use vectors, matrices, and *tensors* to efficiently represent inputs, outputs, and operations within each layer.

---

**4. Linear Algebra's Role in Neural Networks**

*   Rather than writing separate linear equations for each neuron in the network
*   Linear algebra is applied to vectors, matrices, and tensors to compute machine learning results

---


## Vectors: Magnitude and Direction

**Vectors as Arrows:**

*   Vectors can be visualized as arrows in a plane (2D) or higher-dimensional space.
*   Defined by a tuple of numbers (coordinates).
*   Number of coordinates = Dimension of the space (e.g., (4, 3) lives in 2D).
*   The coordinates of a vector are the point where the vector ends with respect to the origin of the x, y (and z etc) axis.
*   **Two Important Properties:** Magnitude (size) and Direction.

---

**1. Magnitude (Size): Norms**

*   Norms provide ways to measure the "size" or "length" of a vector.
*   Different norms exist, emulating real-life distance measurements.

    *   **Taxicab Distance (L1-Norm):**
        *   Distance traveling along horizontal and vertical streets (blocks).
        *   `L1-Norm of (a, b) = |a| + |b|` (sum of absolute values).
    *   **Helicopter Distance (L2-Norm):**
        *   Direct flight distance (straight line).
        *   `L2-Norm of (a, b) = sqrt(a^2 + b^2)` (Pythagorean theorem).

**Default Norm:** L2-Norm (length of the arrow).

---

**2. Direction**

*   Direction can be deduced from the vector's coordinates.
*   Example: Vector (4, 3)
    *   Angle (theta) with the horizontal axis: `tan(theta) = 3/4`
    *   `theta = arctan(3/4) = 0.64 radians = 36.87 degrees`
*   Vectors can have the same direction but different magnitudes (norms). Example vector(2, 1.5) points in the same direction as vector (4, 3).

---

**Vector Notations:**

Vectors denoted with the variable x can be represented in several ways:

*   **Row vector:** `(x_1, x_2, ..., x_n)`
*   **Column vector:**
    ```
    [ x_1 ]
    [ x_2 ]
    [ ... ]
    [ x_n ]
    ```
*   **Arrow above the vector name:** `\vec{x}` (less common in this course)
*   **Bold font:** **x** (less common in this course)
*   **Square Brackets:** `[x_1, x_2, ..., x_n]` used interchangeably with parentheses

---

**Generalized Norm Definitions (n components):**

*   **L1-Norm:** Sum of the absolute values of all components.
    `||x||_1 = |x_1| + |x_2| + ... + |x_n|`
*   **L2-Norm:** Square root of the sum of the squares of all components.
    `||x||_2 = sqrt(x_1^2 + x_2^2 + ... + x_n^2)`


## Vector Addition, Subtraction, and Scalar Multiplication

**1. Vector Addition**

*   Adding two vectors results in another vector.
*   Done component-wise.
*   **Example:**
    *   u = (4, 1)
    *   v = (1, 3)
    *   u + v = (4+1, 1+3) = (5, 4)
*   **Geometric Interpretation:** Sum vector is the diagonal of the parallelogram formed by u and v.

**2. Vector Subtraction**

*   Subtracting two vectors results in another vector.
*   Done component-wise.
*   **Example:**
    *   v = (1, 3)
    *   u = (4, 1)
    *   v - u = (1-4, 3-1) = (-3, 2)
*   **Geometric Interpretation:** The difference can be viewed as a vector that, when translated, matches the vector joining the points.

**General Definitions:**

*   **Sum (x + y):** `(x_1 + y_1, x_2 + y_2, ..., x_n + y_n)`
*   **Difference (x - y):** `(x_1 - y_1, x_2 - y_2, ..., x_n - y_n)`
*   **Requirement:** x and y must have the same number of components.

---

**3. Distance Between Vectors**

*   The difference between two vectors tells how far apart they are.
*   Distance can be measured using norms of the difference vector.
    *   **L1 Distance:**  L1-Norm of (x - y) = Sum of absolute values of components of (x-y).
    *   **L2 Distance:**  L2-Norm of (x - y) = Square root of the sum of the squares of the components of (x-y).
*   Knowing distances between vectors is important for calculating similarities between data points in machine learning.

---

**4. Scalar Multiplication**

*   Multiplying a vector by a scalar (a number).
*   Multiply each component of the vector by the scalar.
*   **Example:**
    *   x = (1, 2)
    *   Lambda (scalar) = 3
    *   Lambda * x = (3*1, 3*2) = (3, 6)
*   **Geometric Interpretation:** Stretches the vector by the scalar factor.

**Negative Scalar:**

*   If the scalar is negative, the vector is stretched and reflected about the origin.
*   **Example:**
    *   x = (1, 2)
    *   Lambda = -2
    *   Lambda * x = (-2*1, -2*2) = (-2, -4)

**General Definition:**

*   Let x be an n-dimensional vector and Lambda be a scalar.
*   Lambda * x = (Lambda * x_1, Lambda * x_2, ..., Lambda * x_n)


## Dot Product

**1. Dot Product: A Compact Way to Express Systems of Linear Equations**

*   A very important operation in linear algebra.
*   Essentially, multiplying corresponding entries of vectors and summing the results.

**Example: Fruit Purchase**

*   **Number of Fruits (vector):** [2, 4, 1] (apples, bananas, cherries)
*   **Price per Fruit (vector):** [3, 5, 2] (dollars per apple, banana, cherry)
*   **Cost of Apples:** 2 * 3 = $6
*   **Cost of Bananas:** 4 * 5 = $20
*   **Cost of Cherries:** 1 * 2 = $2
*   **Total Cost:** 6 + 20 + 2 = $28

**Dot Product Calculation:**

*   [2, 4, 1] · [3, 5, 2] = (2 * 3) + (4 * 5) + (1 * 2) = 6 + 20 + 2 = 28

**Common Notation:** Row vector dotted with a column vector.

---

**2. Dot Product and Norm**

*   The L2-norm (magnitude) of a vector is related to the dot product of the vector with itself.
*   For a vector **v**, the L2-norm is: `||v||_2 = sqrt(v · v)`

**Example:**

*   v = (4, 3)
*   L2-Norm (||v||_2) = 5
*   v · v = (4 * 4) + (3 * 3) = 16 + 9 = 25
*   sqrt(v · v) = sqrt(25) = 5

---

**3. Transpose**

*   An operation that transforms columns into rows (and vice versa).
*   Denoted by a superscript "T".
*   **Column Vector to Row Vector:**
    *   v = [ x_1, x_2, ..., x_n]
    *   v^T = (x_1, x_2, ..., x_n)
*   **Row Vector to Column Vector:**
    *   v = (x_1, x_2, ..., x_n)
    *   v^T = [ x_1, x_2, ..., x_n]
*   **Matrix Transpose:** Transpose each column to get the rows of the transposed matrix.
    *   The dimensions of the matrix swap (e.g., a 3x2 matrix becomes a 2x3 matrix).

---

**4. Formal Definition of the Dot Product**

*   Given two vectors **x** and **y** with *n* components:
*   x = (x_1, x_2, ..., x_n)
*   y = (y_1, y_2, ..., y_n)
*   **Dot Product (x · y):** `x_1*y_1 + x_2*y_2 + ... + x_n*y_n`
*   Another notation for Dot Product: <x, y>
*   Important: In some contexts, the first vector should be a row vector and the second a column vector. Use the transpose when necessary.


## Angle Between Vectors and the Dot Product

**1. Orthogonal (Perpendicular) Vectors**

*   Two vectors are orthogonal if their dot product is zero.
*   **Example:**
    *   u = (-1, 3)
    *   v = (6, 2)
    *   u · v = (-1 * 6) + (3 * 2) = -6 + 6 = 0

**Recap:**

*   **v · v = ||v||^2** (Dot product of a vector with itself is the norm squared).
*   **If u and v are orthogonal, then u · v = 0.**

---

**2. Dot Product and Angle**

*   The dot product is related to the angle between two vectors.
*   **If u and v point in the same direction:**  u · v = ||u|| * ||v||
*   **If u and v have an angle (theta) between them:**

    *   Imagine you project u onto v.
    *   Let u' be that projection
    *   `u · v = ||u'|| * ||v||`   (Product of magnitudes of projection of u and v)
*   **It doesn't matter if you project u onto v or v onto u; the dot product is the same.**
*   **General Formula:**  `u · v = ||u|| * ||v|| * cos(theta)`  (where theta is the angle between u and v)

---

**3. Sign of the Dot Product and Vector Orientation**

*   The sign of the dot product tells us the orientation of one vector relative to the other.
*   Consider vector **w** = (6, 2).

    *   **Orthogonal Vectors:**  Vectors perpendicular to **w** (e.g., (-1, 3)) have a dot product of zero with **w**.
    *   **Vectors to the "Right":** Vectors to the right of **w** (e.g., (2, 4)) have a *positive* dot product with **w**. These vectors have a positive projection on w.
    *   **Vectors to the "Left":** Vectors to the left of **w** (e.g., (-4, 1)) have a *negative* dot product with **w**. These vectors have a negative projection on w (the projection is in the opposite direction of **w**).

**General Rule:**

*   If **u** is a vector,

    *   **Vectors with a dot product of 0 with u** are all perpendicular vectors to u.
    *   **Vectors with a positive dot product with u** are all the vectors in the region "to one side" of the perpendicular vectors.
    *   **Vectors with a negative dot product with u** are all the vectors in the other region "to one side" of the perpendicular vectors.

## Matrix-Vector Multiplication

**1. Matrix-Vector Multiplication: Representing Systems of Linear Equations**

*   A compact way to represent systems of linear equations using matrices and vectors.

**Recall: Dot Product**

*   The dot product is the sum of products of corresponding entries of vectors.

**Single Equation as a Dot Product:**

*   Example: 2a + 4b + c = 28
*   Can be written as:  [2, 4, 1] · [a, b, c] = 28  (row vector * column vector)

**2. System of Equations as Matrix-Vector Product**

*   Multiple equations can be represented more efficiently.

**Example: System of Three Equations**

1.  a + b + c = 10
2.  a + 2b + c = 15
3.  a + b + 2c = 12

**Dot Product Representation:**

1.  [1, 1, 1] · [a, b, c] = 10
2.  [1, 2, 1] · [a, b, c] = 15
3.  [1, 1, 2] · [a, b, c] = 12

*   A matrix-vector product is simply multiple dot products "stacked" together.

**3. Dimensions and Compatibility**

*   **Crucial:** The number of *columns* in the matrix must equal the length of the vector.  (Inner dimensions must match).
*   If they don't match, the dot product is undefined.

**Example:**

*   Matrix A (m x n) * Vector x (n x 1)
    *   The result is a vector of size (m x 1).

**4. General Case**

*   The matrix can be rectangular (m x n) as long as the number of columns (n) matches the length of the vector.
*   Resultant Vector: Size will be equal to the number of rows (m) in the matrix.
