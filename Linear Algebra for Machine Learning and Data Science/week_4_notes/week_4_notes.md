# Week 4: Linear Transformations, Determinants, Eigenvalues, and Principal Component Analysis (PCA)

This week focuses on key concepts in linear algebra and their applications, particularly within the context of linear transformations. We'll cover determinants, singularity, eigenvalues, eigenvectors, basis, span, and culminate in understanding Principal Component Analysis (PCA).

## Overview

The goal is to characterize linear transformations and explore their real-world applications, especially in dimensionality reduction techniques like PCA.

PCA is a dimensionality reduction algorithm. Imagine that your data points in space tend to lie close to a line. PCA helps simplify the data set by projecting all the points to the line, so that you go from a two dimensional data set to a one dimensional data set that carried almost the same amount of information. So, in summary, principal component analysis is a technique that is used in data science applications to reduce the dimensions of a dataset while losing as little data as possible. You can imagine a data set with many columns of data, which can sometimes be cumbersome to use or difficult to visualize. The goal of PCA is to intelligently reduce the number of columns, providing the benefits of a more compact data set without losing all the useful information the original data set contained.

## Lesson 1: Characterizing Linear Transformations with Determinants

### Singularity

*   We'll examine the concept of singularity in linear transformations.
*   A non-singular transformation preserves the dimensionality of the space (e.g., a plane remains a plane).
*   A singular transformation reduces the dimensionality (e.g., a plane collapses to a line).
*   The singularity of a transformation is directly related to the singularity of the corresponding matrix.

### Geometric Interpretation of the Determinant

*   The determinant quantifies how a linear transformation stretches or shrinks space.
*   A positive determinant indicates expansion; a negative determinant indicates expansion with a reflection.
*   The absolute value of the determinant represents the scaling factor of areas (in 2D) or volumes (in 3D).

### Properties of Determinants

*   **Determinant of a Product:**  det(AB) = det(A) * det(B)
*   **Determinant of an Inverse:** det(A<sup>-1</sup>) = 1 / det(A)
*   These properties are useful for analyzing inverse transformations and cascades of transformations.

## Lesson 2: Basis, Span, Eigenvalues, and PCA

### Basis

*   A basis is a set of vectors that can define a space.
*   Any point in a space can be reached through linear combinations of the vectors in a basis.
*   Example:  Any two non-collinear vectors form a basis for a plane.

### Span

*   The span of a set of vectors is the set of all points that can be reached through linear combinations of those vectors.
*   A single vector spans a line.
*   Two non-collinear vectors span a plane.

### Eigenvalues and Eigenvectors

*   Eigenvectors are directions that remain unchanged (up to scaling) when a linear transformation is applied.
*   Applying a linear transformation to a point along an eigenvector only scales the point along that same vector.
*   Eigenvalues are the scaling factors associated with the corresponding eigenvectors.
*   Eigenvectors help characterize linear transformations and are used in many machine learning applications.

### Principal Component Analysis (PCA)

*   PCA is a dimensionality reduction technique.
*   It finds the principal components (directions of maximum variance) in a dataset.
*   It projects the data onto a lower-dimensional subspace defined by these principal components, preserving as much variance as possible.
*   PCA is used to reduce the number of columns, providing the benefits of a more compact data set without losing all the useful information the original data set contained.


# Understanding Singular and Non-Singular Linear Transformations

This section explores the connection between singular and non-singular matrices and their corresponding linear transformations. We will see how the properties of a matrix affect the behavior of the transformation it represents, particularly regarding the transformation's image (the set of all output points).

## Matrices and Linear Transformations: A Recap

Recall that a matrix can represent a linear transformation. The matrix transforms a basis of vectors (e.g., the standard basis in the plane) into a new set of vectors. This can be visualized as transforming a grid from one shape to another.

## Non-Singular Transformations

*   **Image Covers the Entire Space:** A non-singular transformation, represented by a non-singular matrix, maps the input space (e.g., the entire plane) onto the entire output space (e.g., the entire plane).
*   **Change of Basis:** It effectively changes the basis from one set of vectors to another, where the new basis can still "reach" every point in the space.  The blue grid is transformed into an orange grid that covers every single point on the plane.
*   **Example:** A matrix with entries 3, 1, 1, and 2 represents a non-singular transformation. The blue grid is transformed into an orange grid that covers every single point on the plane.

## Singular Transformations

*   **Image is Restricted:** A singular transformation, represented by a singular matrix, maps the input space onto only a *portion* of the output space. It does *not* cover the entire output space.
*   **Degenerate Transformation:** The transformation can be considered "degenerate" because it reduces the dimensionality of the space.
*   **Example 1: Transformation to a Line:** A matrix with entries 1, 1, 2, 2 transforms the entire plane onto a single line. The blue square basis doesn't go to a parallelogram. It does, but it's a degenerate parallelogram. It's actually a line segment. There's a problem because the grid on the left doesn't get sent to the entire plane. It gets sent to this line because when we had a parallelogram, no matter how thin, it was able to cover the entire plane on the right. But if a parallelogram is flat and it's only one line segment, then that can only cover the orange line on the right. It cannot cover the entire plane.
*   **Example 2: Transformation to a Point:** A matrix with entries 0, 0, 0, 0 transforms the entire plane to a single point (the origin).  The entire plane gets sent to that orange point in the origin. That matrix is definitely very singular because the image is not even a plane, is not even a line, it's actually a point.

## Rank and the Image of a Transformation

*   **Rank Defined:** The *rank* of a linear transformation (or its corresponding matrix) is the dimension of its image.

*   **Examples:**
    *   **Non-Singular (Full Rank):** If the transformation maps the plane onto the plane (the image is the plane), the rank is 2.  The dimension of the image of the first one is two, and that's precisely the rank of this matrix.
    *   **Singular (Rank 1):** If the transformation maps the plane onto a line (the image is the line), the rank is 1.  The dimension of the image here is one because it's a line, and that's the rank of this matrix.
    *   **Singular (Rank 0):** If the transformation maps the plane onto a point (the image is the point), the rank is 0.  The dimension here of the point is zero, which is the rank of the third matrix. That's another way to calculate rank; the dimension of the image of the linear transformation.


# The Determinant as Area/Volume Scaling Factor in Linear Transformations

This section explores the geometric interpretation of the determinant, revealing it as a measure of how linear transformations scale areas (in 2D) or volumes (in 3D). We'll see how this interpretation relates to the singularity or non-singularity of a matrix.

## Determinant: A Recap

Recall that the determinant is a scalar value calculated from the entries of a square matrix. It plays a crucial role in determining the invertibility and properties of the matrix.

## Determinant and Area/Volume Scaling

*   **Non-Singular Matrix:** For a non-singular 2x2 matrix, the determinant represents the scaling factor of the area under the linear transformation. It determines how much the unit square is transformed and what its area will be.
*   The determinant of the matrix is the area of the image of the fundamental basis formed by the unit square.
*   **Example:** The matrix with entries 3, 1, 1, and 2 has a determinant of 5. This matrix transforms the unit square into a parallelogram with an area of 5.

## Determinant and Singular Transformations

*   **Singular Matrix:** A singular matrix has a determinant of 0. This means the linear transformation collapses the area (in 2D) or volume (in 3D) to zero.
*   **Transformation to a Line:** In the case of transformation to a line segment the determinant of the matrix is precisely the area of the image of the fundamental square, which is a line segment and so its 0.
*   **Transformation to a Point:** In the case of transformation to a point,  the determinant of the matrix is the area of the image of the fundamental square, this time is a point, is also 0.
*In summary, we got a non singular matrix with determinant 5, just precisely the area of the image of the fundamental square, then another singular matrix with determinant 0, which is the area of the image of the fundamental square, which is a line segment and another singular matrix again with determinant 0, since the area of the image of the fundamental square, this time is a point, is also 0.

## Negative Determinants and Orientation

*   **Orientation:** The sign of the determinant indicates whether the transformation preserves or reverses the orientation of the space.
*   **Positive Determinant:** Preserves orientation (clockwise order remains clockwise).
*   **Negative Determinant:** Reverses orientation (clockwise order becomes counter-clockwise, or vice versa). The area is consider negative due to the order of vectors in counterclockwise order, consider it positive if the vectors are in clockwise order.
*   **Singularity and Sign:** A determinant being positive or negative doesn't actually affect the singularity of the matrix and so all that matters for the matrix to be non singular, is that the determinant is different than 0.
*   **Example:** Swapping the columns of a matrix changes the sign of its determinant, indicating a reflection.

## Implications

*   **Singularity:** A matrix is non-singular if and only if its determinant is non-zero. This means the transformation doesn't collapse the space to a lower dimension.

# Determinant of a Product of Matrices: A Geometric Interpretation

This section explores the property that the determinant of a product of matrices is equal to the product of their individual determinants: det(AB) = det(A) * det(B). We'll understand this property through the lens of linear transformations and area scaling.

## The Rule: det(AB) = det(A) * det(B)

The determinant of a product of matrix follows a really nice rule that  the determinant of AB is equal to the determinant of A times the determinant of B.

## Geometric Explanation using Linear Transformations

1.  **Transformation A:**  Matrix A represents a linear transformation that scales areas by a factor equal to its determinant, det(A). The first matrix, 3,1,1,2, we've seen it already, and is the matrix that sends this fundamental basis to this basis over here. The five is the area of the parallelogram. That means that this transformation actually blows up the areas by five.

2.  **Transformation B:** Matrix B represents another linear transformation that scales areas by a factor equal to its determinant, det(B). The second matrix has a determinant of three. If you work it out, is the one that sends this fundamental basis here into this parallelogram here that has area three. The three correspond to the determinant. That means that this transformation blows up the areas by three.

3.  **Combined Transformation AB:**  The product AB represents the combined effect of applying transformation B first, then transformation A.

4.  **Area Scaling:** When we apply transformation B, the area is scaled by det(B). Then, when we apply transformation A, the area is further scaled by det(A). The total scaling factor is therefore det(A) * det(B). This parallelogram here goes to this parallelogram over here with area 15. Because what the transformation does is, no matter what area you have, it blows it up by a factor of the determinant.

5.  **Determinant of AB:** Since the determinant of AB represents the overall area scaling factor of the combined transformation, it must be equal to the product of the individual scaling factors: det(AB) = det(A) * det(B).

## Implications and Singularity

*   **Product with a Singular Matrix:** The product of a singular matrix and any other matrix (in either order) is always singular.
    *   This is because the determinant of a singular matrix is 0. The determinant of AB is the determinant of A times the determinant of B but determinant of B is zero because B is singular. The determinant of AB has to be zero, because it is the determinant of A*0. Therefore, AB is singular.
    *   Multiplying by 0 always results in 0, regardless of the other number involved. Similarly, if one matrix is singular, then that matrix multiplied with any other matrix in the world is also singular.

*   **Geometric Intuition:** A singular matrix collapses the space onto a lower-dimensional subspace (e.g., a line or a point). Applying any subsequent transformation cannot "recover" the lost dimension, so the combined transformation will also be singular. If you multiply two matrix, for example this one over here, which is non singular, with this one over here, which is singular, well, the second matrix being singular means it sends everything into a part of a line. That means that when you combine them, then it sends a fundamental basis into some segment. It has determinant zero because this segment has area 0.
In other words, whatever area you have left, it gets blown up by zero.


# Determinant of an Inverse Matrix: det(A⁻¹) = 1/det(A)

This section explores the relationship between the determinant of a matrix and the determinant of its inverse. We'll discover the rule: det(A⁻¹) = 1/det(A).

## Observations and Examples

*   **Matrix and its Inverse:** A matrix with determinant 5 has an inverse with determinant 0.2 (1/5). A matrix with determinant 8 has an inverse with determinant 0.125 (1/8).
*   **Singular Matrix:** A singular matrix (determinant 0) does not have an inverse.  0 has no multiplication inverse.

## The Rule: det(A⁻¹) = 1/det(A)

If matrix A is invertible, then the determinant of its inverse (A⁻¹) is equal to one divided by the determinant of A.

## Proof

1.  **Product Formula:** We know that det(AB) = det(A) * det(B).

2.  **Substitute A⁻¹:** Let B = A⁻¹. Then, det(A * A⁻¹) = det(A) * det(A⁻¹).

3.  **Identity Matrix:**  A * A⁻¹ = I (the identity matrix). So, det(I) = det(A) * det(A⁻¹).

4.  **Determinant of the Identity Matrix:** The determinant of the identity matrix is always 1. Why? Well, let's actually calculate it. Notice that for a two by two matrix is 1 times 1 minus 0 times 0, which is 1.

5.  **Solve for det(A⁻¹):**  Therefore, 1 = det(A) * det(A⁻¹). Dividing both sides by det(A) (since A is invertible, det(A) ≠ 0), we get det(A⁻¹) = 1/det(A).


# Understanding the Concept of a Basis in Linear Algebra

This section introduces the concept of a basis in linear algebra. A basis is a fundamental concept, which allows us to describe and navigate vector spaces effectively.

## What is a Basis?

*   A basis is a set of vectors that define a space. In the previous week, you learn that a matrix can be seen as a linear transformation from the plane to the plane, which sends this fundamental square into this parallelogram and both were called basis.
*   In reality, all that matters here is not the four points of the square of the parallelogram, but the two vectors that define it. Those are the ones that are referred from now on as a basis.
*   The primary characteristic of a basis is that every point in the space can be expressed as a linear combination of the vectors in the basis.

## Linear Combination Explained
*   What do I mean by that? Well, let's say we have these two vectors and I'm telling you that those two are a basis, why? Well, pick any point in space, say this one.
*   We can reach any point in the space by combining the basis vectors.
*   This means we can scale the vectors (multiply them by a scalar) and add them together to reach any point in the space.
*   We can walk forwards or backward along the direction of a basis vector to get to any point.

## Examples of Bases for the Plane

There are lots and lots.
*   Any two non-parallel vectors in the plane form a basis. I could get to any point, for example, this point using those two directions. Here's one way, I walk in this way, and then in this one. Remember that I can walk backwards if I want to. So those two vectors also form a basis.
*   We can always reach any point in the plane using these vectors. I can walk like this and then like this to get to the point. So as a matter of fact, pretty much any two vectors form a basis.
*   It's almost hard to think of what's not a basis, what would be a non-basis.

## What is NOT a Basis (Linear Dependence)

*   Two vectors pointing in the same direction (or opposite directions) do **not** form a basis for the plane. So here's an example, let's take the two vectors over here. These two vectors, I can arrive for example, to this point over here, but I could not arrive to this point over here by walking in those two directions because I only have one direction.
*   With only one direction, you can only reach points along a single line; you cannot cover the entire plane.
*   Such vectors are called linearly dependent.
*   So, anything that comprises two vectors that go in the same direction and they could be opposites or they could go in the same direction, but as long as they belong to the same line, the two vectors do not form a basis.

## Key Takeaway

*   A basis provides a "coordinate system" for a vector space, allowing us to express any point in the space as a combination of the basis vectors.
*   For the plane (2D space), any two non-parallel vectors form a basis.

# Span, Linear Independence, and the Formal Definition of a Basis

This section dives deeper into the concept of a basis by introducing the concepts of span and linear independence. We'll explore what it means for a set of vectors to span a space and be linearly independent, and then combine these ideas into a formal definition of a basis.

## Span: The Reach of Vectors

*   **Definition:** The span of a set of vectors is the set of all points that can be reached by taking linear combinations of those vectors (walking in the directions of these vectors in any combination).
*   **Examples:**
    *   Two non-parallel vectors in the plane span the entire plane.
    *   Two vectors pointing in the same direction span a line.
    *   A single vector spans a line through the origin.
    *   Two vectors 180 degrees apart span a line through the origin.

## Minimal Spanning Set and Basis

*   A basis needs to be a minimal spanning set.
*   A basis is a minimal spanning set, so each one of them separately is a basis of that line. But the two of them are not a basis. They're a spanning set, but they're not a basis.
*   Any vector that starts at the origin and goes in that same direction is also a basis for that line.

## Basis Length and Dimension

*   The length of the basis of a space is the dimension of that space. On the left the line has a basis of length 1, and it has a dimension of 1, because line has dimension 1. On the right the plane has a basis of length 2, formed by two vectors, and the plane has a dimension of 2.
*   Any basis of a given space has the same number of elements.
*   Number of vectors in a basis = dimension of the space.

## Linear Independence

*To do that we'll need to introduce the concept of linearly independent and linearly dependent vectors. A group of vectors is said to be linearly independent if none of the vectors in the group can be obtained as a linear combination of the others. If you consider just one vector in the plane, it is always going to be linearly independent.
*   Two vectors are linearly independent if you can't reach one by scaling the other.
*   Adding a third vector that can be created by combining the existing two doesn't change their span, making the vectors linearly *dependent*.

## Checking for Linear Dependence

Let's see how we can check if a set is linearly dependent or not.
*   To see that the set of vector is linearly dependent you need to find constants Alpha and Beta that satisfy that Alpha times v_1 plus Beta times v_2 equals v_3.
*   Express one vector as a linear combination of the others.
*   Solve the resulting system of equations.
    *   If a solution exists, the vectors are linearly dependent.
    *   If no solution exists, the vectors are linearly independent.
*   If you were to find that the system has no solution, then that means the set is linearly independent.

## Formal Definition of a Basis

*   A basis is a set of vectors that satisfies **two conditions**:
    1.  **Spanning:** The set must span the vector space (you can reach any point in the space).
    2.  **Linear Independence:** The vectors in the set must be linearly independent (no vector can be written as a linear combination of the others).

* These first two span a line or a one-dimensional space, and a plane or a two-dimensional space, and they are linearly independent, so they form a basis. The last two are linearly dependent, and they do not form a basis. As we see in these two examples, we need to be careful to remember that not all sets of n vectors will form a basis for an n-dimensional space.

## Example

*   The set formed by 1, 0 and 0,1 spans a line or a one-dimensional space, and a plane or a two-dimensional space, and they are linearly independent, so they form a basis.
*The set formed by 1,0 and 2,0 are linearly dependent, and they do not form a basis. As we see in these two examples, we need to be careful to remember that not all sets of n vectors will form a basis for an n-dimensional space.


# Eigenbasis: A Special Basis for Simplifying Linear Transformations

This section introduces the concept of an eigenbasis, a particular type of basis that simplifies the representation and understanding of linear transformations.

## Motivation

*   Some bases are more useful than others.
*   One particularly useful basis is the eigenbasis.
*   Eigenbasis are especially valuable in machine learning applications like Principal Component Analysis (PCA).

## Illustration

*   Consider the linear transformation corresponding to the matrix with entries 2, 1, 0, and 3.
* The matrix acting on the vector 1, 0 gets vector 2,0
* The matrix acting on the vector 0,1 gets vector 1,3
*   The square (fundamental basis) gets transformed into a parallelogram.
*   This transformation represents a change of coordinates (or a change of basis).

## Changing to a Different Basis

*   Choosing a different basis can reveal more about the transformation.
*   Let's again use 1,0 and 1,1 as a second element of that basis.
* Let's say that matrix acting on the vector 1, 0 gets vector 2,0.
* Let's say that matrix acting on the vector 1, 1 gets vector 3,3.
* What is special here? Notice that the sides of the two parallelograms are parallel to the corresponding one in the other basis.
* What we're doing to the plane is we're stretching by two in this direction, the horizontal direction, and stretching by three in this diagonal direction.

## Eigenbasis: Consisting of Stretchings

*   An eigenbasis consists only of stretchings.
*   It's a very special way of looking at a linear transformation with respect to a basis that sends a parallelogram to another parallelogram with sides parallel to the original one.

## Benefits of Using Eigenbasis

*   **Simplified Calculations:** Finding the image of a point becomes much easier, just stretchings.
*   **Simplified Linear Transformation:** Let's say that you want to find the image of the point 3, 2. You can multiply it by the matrix and get 8, 6, which is over here.
*   You can also express that point as a combination of elements in the basis.
*   This really simplifies the linear transformation. It just consists of two stretchings.

## Terminology: Eigenvectors and Eigenvalues

*   The vectors in the eigenbasis are called **eigenvectors**. The two vectors in the basis are gonna be called the eigenvectors
*   The stretching factors are called **eigenvalues**. and the stretching factor, the two and the three, are going to be called eigenvalues.
*   Eigenvalues and eigenvectors are tremendously important in linear algebra because they really simplify our calculations.

## Key Takeaway

*   An eigenbasis is a special basis that simplifies the representation of linear transformations by expressing them as stretches along specific directions.
*   Eigenvectors and eigenvalues are fundamental tools for understanding and manipulating linear transformations.


# The Power of Eigenvalues and Eigenvectors: Simplifying Matrix Transformations

This section delves into why eigenvalues and eigenvectors are so special. We'll see how they allow us to replace matrix multiplication with scalar multiplication along specific directions, and how this can be used to simplify calculations.

## Revisiting Eigenvalues and Eigenvectors
* Let's look a bit more closely why eigenvalues and eigenvectors are so special.
* It's better to have a clear understanding of Eigenvalues and Eigenvectors.
* Eigenvalues and Eigenvectors comes in pairs
* Remember that eigenvectors and eigenvalues come in pairs. So, v1 and lambda 1 form a pair, and v2 and lambda 2 form a second pair.

## Eigenvectors: Directions of Simple Scaling

*   The transformation corresponding to eigenvectors tell the direction.
*   Eigenvectors are the directions in which the matrix A acts by simple scaling (stretching).
*   If *v* is an eigenvector of *A*, then *A*v = λ*v*, where λ is the eigenvalue.
*   This equation says that for this special vector v1 A times v1 is the same as multiplying v1 by the scalar lambda 1.
*   In the direction of an eigenvector, matrix multiplication is equivalent to scalar multiplication.

## The Eigenvalue Equation: Av = λv

Let me formalize what these two equations are saying. I'll call our matrix here A and I'll call the first eigenvector here v1. Then this equation says that for this special vector v1 A times v1 is the same as multiplying v1 by the scalar lambda 1.
*In the second equation, A multiplied by v2 is equal to the scalar lambda 2 multiplied by v2.

## Computational Efficiency

*   Matrix multiplication is computationally expensive (more operations).
*   Scalar multiplication is much cheaper (fewer operations).
* What this equation is saying then is that, at least along a matrix eigenvectors, you can turn a large computation into a smaller one.
*   The eigenvalue equation transforms a large computation (matrix multiplication) into a small one (scalar multiplication) *along the eigenvectors*.

## Expanding to the Whole Space Using the Eigenbasis

*   If the eigenvectors form a basis (the eigenbasis), then *any* vector can be expressed as a linear combination of eigenvectors.
*  Since the vectors 1, 0 and 1, 1 form a basis, then you know that you can write the vector -1, 2 as a linear combination of those basis vectors.
*    In this case it's -3 times 1, 0 + 2 times 1,1. So you can simply replace, -1, 2 by- 3 times 1, 0 + 2 times 1,1.
*   Expressing any vector as a linear combination of eigenvectors and then applying the transformation allows you to replace the matrix multiplication with scalar multiplications.
*   This enables you to transform vectors without performing full matrix multiplication.
*   It allows you to decide *when* you want to do the more intensive calculations.

## Formalization

*Let's show you the formula.
* You have already calculated these matrix multiplications and you can just substitute the scalar multiplications like this. Now your equation, is just scalar multiplications.
* You have -3 times 2 times the vector 1, 0, + 2 times 3 times the vector 1, 1.
* You can quickly multiply through these scalars, and finally solve this equation to get the vector 0, 6, which if you remember, is the vector you solved for before.

## Key Takeaways

*As you just saw, this means that along that vector a matrix multiplication just becomes a scalar multiplication. Visually you can think of eigenvectors as telling you the direction in which a linear transformation is just a stretch, and the eigenvalues tell you how much it is stretched.
*   **Av = λv:** The fundamental equation characterizing eigenvectors and eigenvalues.
*   **Geometric Interpretation:** Eigenvectors indicate directions of stretching, and eigenvalues indicate the amount of stretch.
*As you'll see, eigenvectors can save work and help characterize a linear transformation in powerful ways.
*   **Eigenbasis:** A basis formed by eigenvectors.
*From the perspective of this eigenbasis the linear transformation A is just a collection of stretches.
*   **Computational Advantages:** Eigenvectors and eigenvalues can significantly reduce computational complexity.


# Finding Eigenvalues and Eigenvectors: A Step-by-Step Guide

This section provides a step-by-step guide on how to find eigenvalues and eigenvectors of a matrix.

## Motivation
Now that you know what an icon basis is, you may be wondering how to find it. The process is actually not too difficult.
The process entails solving an equation with a determinant.
First, take a look at the matrix with entries 2,1, 0,1,3 and take a look at how it acts on these points around the square. This should make the entire transformation clear. As you've seen before, the two horizontal vectors get stretched by two and the diagonals get stretched by three.
Now for the other points this happens.

## Eigenvalues and Infinitely Many Points

*   To explain, we need to see two matrices. As an example we will look at the one that stretches the plane by 2 and one that streches to a diagnal.
Now compare this to another matrix, one that simply stretches the entire plane by a factor of three in any direction. This matrix has entries 3,0,0 and 3 and it's really three times the identity matrix.
Notice one thing these two transformations are not the same transformation, but they do coincide in many points. In other words, they act the exact same way for infinitely many points. All the points in this line. To be more specific, in this diagonal, the two transformations do the exact same thing.
What's happening? Well, let's look at the difference. If these two transformations match at infinitely many points, that means the difference is zero at infinitely many points.
In other words, this matrix times vectors x, y for infinity metric vectors is 0,0.

## Singular Transformations

* Recall that non singular transformation has a unique solution to the equation matrix times vector equal 0,0 and that's the vector 0,0.
* Recall what singularity means.
* We can do the same procedure, take the difference and that matrix times a vector equal 0,0 for infinitely many vectors. That means that the matrix 0,1, 0,1, or the difference between our matrix and two times the identity, is a singular matrix.

## Finding Eigenvalues: The Characteristic Polynomial

*Therefore, this matrix, 2-Lambda, 1,0,3 minus Lambda has to be a singular matrix so our determinant is zero
* If Lambda was an eigenvalue, then the transformation given by a matrix and the transformation given by scaling the plane entirely by a factor of Lambda are equal for infinitely many vectors xy.
* The place where the characteristic polynomial is zero are the eigenvalues.
* This means their difference (A - λI) has a non-trivial (infinite) set of solutions (a singular matrix)
The general idea is the following:
1. Form the matrix (A - λI)
2. Calculate its determinant (this gives the characteristic polynomial)
3. Find the roots of the characteristic polynomial (these are the eigenvalues λ)

## How to Find Eigenvectors

*Recall that the eigenvector is the vector that satisfies the equation matrix times vector equals eigenvalue times vector.
*If we expand this, we get these equations over here and the solution for these are x=1, y=0, or any multiple vector. Here is one of the eigenvalue vector, the one corresponding to the Eigenvalue 2.
** The equations would be:
(2-Lambda)*x + 1*y = 0
 0x + (3-Lambda)*y = 0
Then you can do:
* 1st Eigenvalue (x =1, y =0)
* 2nd Eigenvalue (x=1, y=1)
This gives Eigen Vector direction. You choose one specific.
 *   For each eigenvalue (λ), solve the equation (A - λI)v = 0, where v is the eigenvector.
This process is how:
*   Find the eigenvector corresponding to each eigenvalue
* Finding matrix, factoring with 3d vectors,
*The process of finding in vectors for a three by three matrix is very similar. Consider A equals 2,1,-1, 1,0,-3, -1,-3,0.

## Finding Eigenvectors For each eigenvalue.
Find the equations. If there is a parameter then there are infinite solutions.
Then that means you need to solve this equation, where x_1, x_2, and x_3 are the three components of the eigenvector.
Multiplying the form by the vector gives the new vector 4x_1, 4x_2, 4x_3. Completing this dot product on the left gives you this new vector. Now all you need to do is set these three vectors equal to one another and solve for x_1, x_2, and x_3.

## Finding Eigenvalues
Take the matrix. Create new matrix by doing A-Lambda times vector equal to 0. 
(Eigen value Equation). This gets you the eigenvectors!

## General Methodology for Eigenspaces.
1.Get Lambda from determinent. 2. Use Lambda to find a system of equations.
2. Find parametric of solutions
**
For matrices with any shape then you can not compute eigenvalues and eigenvectors:
*If you notice the two examples you worked on were for two by two and three by three matrices, all of which are square matrices. Could you compute the eigenvalues and eigenvectors for any matrix of any shape? Remember to get the eigenvalues you need to solve for a determinant.
*As you learned in previous lessons, the determinant is only defined for square matrices. For any square matrix, you can find eigenvalues and eigenvectors. However, the matrix is not squared like the one right here, then it doesn't have any eigenvectors or eigenvalues.


# Not All Matrices Have a Full Set of Eigenvectors

This section explores cases where a matrix may not have a complete set of linearly independent eigenvectors, even when the matrix is of size *n x n*. This can happen when eigenvalues are repeated.

## The Question

Could it be that all three by three matrices always have three eigenvectors? Well, it turns out that that's not always the case.

## Example 1: Three Eigenvalues, Three Eigenvectors

* You get A = Matrix with all different Eigenvalues, 
   1st EigenValue = 4, 1st Eigen vector = 0,1,0
   2nd EigenValue = 2, 2nd Eigen vector = 2,1,0
   3rd EigenValue = 2, 3rd Eigen vector = 1,1,2

In order to work with eigenvalues do:
1. 0 =0,
2. -X_1 +2X_2-0.5X_3 = 0
3.  4x_1 =4x_2
4.  get to the solutions and see that you can get 3 EigenVectors

## Example 2: Three Eigenvalues, But Only Two Eigenvectors

Now what happens when one value on the A= matrix changes?

* The new result turns out to be different with an *One* Less EigenVector
* For the number to be an eigenvalue, you need the value to be a root in all equations.
*EigenValue of Four is the same calculation we did before.
* Again you need three set equations in order to know solutions.
4(EigenValue of Four) 0,1,0
2 (the same happens), and you get that 3 Eigen Value cannot be found.
2(same happens). You still have to choose another solution because cannot satisfy
a valid matrix for the 2 or three values if only using 0, k ,4k!

## Summary: Eigenvalues and Eigenvectors for 2x2 and 3x3 Matrices

The Matrix depends on two eigenvalues Lambda1 and Lambda2.

1. IF the two EigenValues are distinct, then you get 2 eigenvectors.
2. IF the 2 EigenValues are equal, you can choose either 1 or 2 to use.

 The Matrix depends on three eigenvalues Lambda1, Lambda2 and Lambda3

1. IF the three EigenValues are distinct, then you get 3 eigenvectors.
2. IF the three EigenValues have a number (twice/double), then you chose 2 or three vectors to user.

## Principal Component Analysis (PCA)

**Goal:** Reduce the dimensionality (number of columns/features) of a dataset while preserving as much information as possible.

**Concept:** Transform a dataset with many features into a dataset with fewer features.  Same number of observations (rows), fewer features (columns).  It makes the dataset "skinnier".

**Why Reduce Dimensions?**

1.  **Data Size:** To work with a more manageable dataset when the original is very large (hundreds/thousands of features).
2.  **Visualization:**  Facilitates exploratory data analysis by allowing easier visualization of data with fewer dimensions. Scatter plots and bar charts are easier to understand.

**Naive Approach (Deleting Columns):**

*   Simple, but loses information.

**PCA Approach (Projections):**

*   Reduces dimensions by projecting data points onto a vector space with fewer dimensions.

**Example: Projecting points onto a line (y = x)**

1.  **Original Data:** 4 observations with x and y coordinates.
2.  **Projection Line:**  y = x
3.  **Projection Process:** Each point is moved perpendicularly onto the line.
4.  **New Coordinates:**  Instead of x,y coordinates, the position is defined by the distance along the line from the origin.

**Mathematical Explanation:**

*   **Vector Representation:**  The line y = x is the span of the vector (1, 1).
*   **Dot Product:** Take the dot product of each data point's coordinates with the vector (1, 1). This provides the "location" of the projection along the direction vector.
*   **Scaling:** Dividing by the *norm* (L2 Norm, magnitude) of the vector ensures that no stretching is introduced and the vector ends up with a length of 1.
* Formula to get the coordinates after projecting each point onto the line:
   * coordinate on the x=y line = ((x_coordinate of the original point + y_coordinate of the original point) / sqrt(2))
   * where sqrt(2) is the norm of the (1,1) vector defining x=y line.

**Generalization of Projection**

* To project any matrix A onto the direction given by a vector v:
   * first, multiply the matrix A by vector v
   * next, scale vector v so that it has a norm of 1 (i.e. divide v by its own l2 norm)

**Projection Equation**

*   **Single Vector Projection:** `Ap = A(v / ||v||)`  where `Ap` is the projected matrix, `A` is the original data matrix, `v` is the direction vector, and `||v||` is the norm of v.
*   If A has r rows and c columns, vector v must have length c, or be a c x 1 matrix.
*   The projection `Ap` will have dimensions of r rows and 1 column.

**Multiple Vector Projections**

*   Projecting onto two vectors is the same as projecting onto the plane those vectors span.
*   Create a matrix `V` of size `c x k`, where each column is one of the `k` vectors you want to project onto, each normalized to have a norm of 1.
*   **Projection Equation:** `Ap = AV` where A is r x c, V is c x k, so Ap is r x k.

**Next Question:**  How to choose the vectors to project onto (i.e., how to construct the V matrix).

## PCA: Choosing the Best Projection for Dimensionality Reduction

**Goal:** Find the projection that preserves the maximum possible spread (variance) in the data, even as you reduce the dimensionality.

**Review of Projections:**

*   **Original Data:** 2D data (points in a plane), each point defined by two features/coordinates (x, y).
*   **Dimensionality Reduction:** Moving to 1D data (points on a line).  Replacing the x,y coordinates with a single coordinate.
*   **Centering the Data:** Data should ideally be centered around (0, 0) *before* projection.

**Examples of Projections:**

*   **Projecting onto the x-axis:** The points move perpendicularly onto the x-axis.
*   **Projecting onto the y-axis:** The points move perpendicularly onto the y-axis.
*   **Projecting onto y + x = 0 line (vector 1, -1):** Another possible projection.
*   **Projecting onto 2x - y = 0 line (vector 1, 2):** Yet another possible projection.

**Key Concept: Spread and Information**

*   **Data Spread (Variance):** After each projection, the projected points may be more or less spread out along the line.
*   **Information Preservation:**
    *   *More spread* means *more information* from the original dataset is preserved.
    *   *Less spread* means *less information* is preserved.

**PCA's Objective:**

*   Find the projection that maximizes the spread (variance) of the data along the lower-dimensional space.

**Benefits of Dimensionality Reduction (and PCA):**

1.  **Easier Data Management:** Smaller datasets are easier to work with.
2.  **Information Loss Minimization (PCA Specific):** PCA reduces dimensions while minimizing how much information is lost.
3.  **Improved Analysis and Visualization:** Makes complex datasets easier to analyze and visualize. You can spot patterns/insights that might be hidden in the full dataset.

**Next Steps:**

*   The video emphasizes that this was a quick introduction. Future videos will explain *how* PCA actually works to find the optimal projection.

## Statistical Concepts for PCA: Mean, Variance, and Covariance

**I. Mean**

*   **Definition:** The average value of all observations in a dataset.
*   **Calculation (for each feature):**
    *   Sum all values of the feature (x_i, y_i, etc.).
    *   Divide by the number of observations (n).
*   **Multi-dimensional Data:** For data with multiple features (e.g., x and y), the mean is a point with coordinates (mean of x, mean of y). `(μx, μy)`.

**II. Variance**

*   **Definition:** A measure of how spread out the data is.  A dataset with no spread has a variance of zero.
*   **Intuition:** Higher variance means data points are further away from the mean (on average).
*   **Calculation:**

    *  var = sum((x_i - mu)^2) / (n-1)
    Where sum is all of the x_i data points. mu is the mean, and n is the number of total data points.
*   **Formal Notation:** `var(x)`
*   **Interpretation:** Variance is the average squared distance from the mean.

**III. Covariance**

*   **Definition:** Measures how two features of a dataset vary with respect to one another. Quantifies the *relationship* between two variables.
*   **Intuition:**
    *   **Positive Covariance:**  As x increases, y tends to increase (positive trend).
    *   **Negative Covariance:** As x increases, y tends to decrease (negative trend).
    *   **Near-Zero Covariance:** No clear relationship between x and y (flat trend or no trend).
*   **Calculation:**

    *  cov(x,y) = sum( (x_i - mu_x) * (y_i - mu_y)) / (n-1)
    Where sum is all of the x_i and y_i data points. mu_x is the mean for x, mu_y is the mean for y, and n is the number of total data points.
*   **Quadrants:** Subtracting the means (mu_x, mu_y) effectively recenters the data, splitting the plane into four quadrants.
    *   Quadrant 1: x > mu_x, y > mu_y.  Contribution to covariance is positive.
    *   Quadrant 2: x < mu_x, y > mu_y.  Contribution to covariance is negative.
    *   Quadrant 3: x < mu_x, y < mu_y.  Contribution to covariance is positive.
    *   Quadrant 4: x > mu_x, y < mu_y.  Contribution to covariance is negative.
*   **Covariance as a "Direction" Indicator:** On average, are there more points in the quadrants that contribute positively or negatively to the overall relationship between the two variables?
    *   Most points in positive quadrants -> positive covariance.
    *   Equal spread in positive and negative quadrants -> covariance close to zero.
    *   Most points in negative quadrants -> negative covariance.

**Key Takeaways:**

*   **Mean:**  The "center" of the data.
*   **Variance:**  How spread out the data is for a *single* variable.
*   **Covariance:** How two variables *relate* to each other (trend direction).

## The Covariance Matrix

**What it is:**

*   A structured way of storing all the relationships (variances and covariances) between pairs of variables in your dataset.
*   A square matrix.

**Construction:**

1.  **Calculate Variances:** Find the variance of each variable (feature) in the dataset.
2.  **Calculate Covariances:** Find the covariance between *every* pair of variables in the dataset.
3.  **Build the Matrix:**
    *   Rows and Columns: The matrix `C` has a row and a column for each variable.
    *   Diagonal Elements: The diagonal elements `C[i, i]` are the variances of each variable `i`.
    *   Off-Diagonal Elements: The off-diagonal elements `C[i, j]` are the covariances between variable `i` and variable `j`.
    *   **Symmetry:**  `cov(x, y) = cov(y, x)`, so the matrix is symmetrical across the diagonal.

**Formal Representation**
*   The covariance matrix captures variances of variables in the diagonal and the covariance of those variables everywhere else.

**Matrix Notation for Efficient Calculation:**

1.  **Data Matrix (A):** Store all data points in a matrix `A`.
    *   Rows: Each row is an *observation* (data point).
    *   Columns: Each column contains all the observations for a *single variable*.
2.  **Mean Matrix (Mu):** A matrix of the *same shape* as `A`.  Each column contains the *mean value* for that variable.
3.  **Covariance Matrix Formula:**
    *   `C = (1 / (n - 1)) * (A - Mu).T * (A - Mu)`
    *   Where:
        *   `C` is the covariance matrix.
        *   `n` is the number of observations.
        *   `(A - Mu)` is a matrix where each element is the original data point minus the mean value of the feature.
        *   `.T` denotes the transpose of the matrix.

**Explanation of the Formula:**

*   **(A - Mu):** This subtracts the mean of each feature from each data point. It centers the data.
*   **(A - Mu).T * (A - Mu):** This performs a matrix multiplication that effectively calculates the sums of squared differences and cross-products needed for variance and covariance calculations.
*   **(1 / (n - 1)):** This normalizes the result to provide an unbiased estimate of the covariance.

**Example with Data Points:**

The video shows how to apply the matrix notation formula to a dataset with 8 observations and two features (x, y). It demonstrates:

*   Calculating Mu_x and Mu_y (the means of each feature).
*   Creating the (A - Mu) matrix.
*   Transposing (A - Mu).
*   Performing the matrix multiplication.
*   Obtaining the covariance matrix C.

**Generalization to More Features:**

The process extends to datasets with more than two features (e.g., adding a 'z' column). The steps remain the same:

1.  Arrange the data with a feature in each column.
2.  Calculate the column averages (Mu).
3.  Subtract the average from each column (A - Mu).
4.  Multiply (A - Mu).T by (A - Mu).
5.  Divide by (n - 1) to get the covariance matrix C.

**Key Takeaway:**

The covariance matrix is a fundamental tool for understanding the relationships between variables in a dataset. The matrix notation provides a concise and efficient way to compute this important structure.

## Eigenvectors & Eigenvalues of the Covariance Matrix: Intuition

**Key Idea:**  Eigenvectors and eigenvalues of the covariance matrix are crucial for understanding the principal directions of variance in your data.

**In short:** Eigenvectors of the covariance matrix represent the directions of greatest variance in your data, and their corresponding eigenvalues tell you how much variance is in each of those directions.

**Expanded Explanation:**

Eigenvectors of the covariance matrix represent the directions in the data space that are preserved after the transformation represented by the covariance matrix. Since the covariance matrix describes how the data points spread out, its eigenvectors point along the directions of maximum variance. The corresponding eigenvalues quantify how much variance exists along each eigenvector.

In PCA, we choose the eigenvectors with the largest eigenvalues because they best preserve the *original covariance structure* of the data when projecting to a lower-dimensional space. Other eigenvectors, with smaller eigenvalues, would represent directions where the variance is lower, meaning projecting along those directions would discard more of the original data's structure.

**Key Implications:**

*   **Direction Preservation:** Eigenvectors maintain the direction of the transformation (covariance).
*   **Covariance Direction:** The aim is to preserve the covariance structure of the data.
*   **Maximum Variance:** Largest eigenvalues correspond to the directions of maximum variance.
*   **Information Loss:** Choosing smaller eigenvalues for projection results in greater information loss during dimensionality reduction.

## PCA: Intuition Behind Why It Works (Geometric Interpretation)

**Recap:** PCA works by finding eigenvectors and eigenvalues of the covariance matrix, sorting them, and projecting data onto the top eigenvectors to reduce dimensionality.

**Intuition: The Covariance Matrix as a Transformation**

1.  **Data:** You have your centered data (X and Y).

2.  **Covariance Matrix (C):** Think of `C` not just as a table of numbers, but as a *linear transformation* that changes the shape of space.  It distorts and stretches space.

3.  **Transformation of Basis Vectors:**

    *   The vector (1, 0) is transformed to (9, 4) by C.
    *   The vector (0, 1) is transformed to (4, 3) by C.

4.  **Transformation of a Circle:**

    *   Imagine drawing a circle of radius 1. Apply the transformation C to every point on that circle.
    *   The transformed points will form an *ellipse*.  The circle is stretched and distorted into an ellipse.

5.  **Ellipse and Variance:**

    *   The major axis (longest direction) of the ellipse represents the direction of the *greatest stretching* or *greatest variance* in the data.
    *   Any other direction through the ellipse will be shorter than the major axis.

6.  **Eigenvectors and Stretching:**

    *   The eigenvectors of C (in the example: (2, 1) with eigenvalue 11, and (-1, 2) with eigenvalue 1) define a special *eigenbasis*.
    *   From the perspective of this eigenbasis, the transformation C *only stretches* space. There is no rotation or shearing.

7.  **Maximum Stretch Along the Eigenvector with the Largest Eigenvalue:**

    *   A point along the eigenvector (2, 1) will be stretched by a factor of *11* (its eigenvalue).
    *   A point along the eigenvector (-1, 2) will be stretched by a factor of *1* (its eigenvalue).
    *   Any other vector will be stretched by a factor between 1 and 11.

8.  **Examples of Stretching:**

    *   The vector (0, 1) with norm 1 gets sent to the vector (4, 3) with norm 5 (stretch of 5).
    *   The vector (1, 0) with norm 1 gets sent to the vector (9, 4) with norm ~9.85 (stretch of ~9.85).

9.  **Why This Justifies PCA:**

    *   **Covariance Matrix Characterizes Spread:** `C` describes how the data is spread out.
    *   **Eigenvectors are Stretching Directions:** Eigenvectors of `C` define the directions where the transformation is a pure stretching.
    *   **Largest Eigenvalue = Greatest Stretch:** The largest eigenvalue corresponds to the direction of greatest stretching.
    *   **PCA Maximizes Variance:** Choosing eigenvectors with the largest eigenvalues gives you the directions with the biggest stretch (the most variance), which is what PCA aims to preserve.

**Key Takeaway:**

PCA works because the covariance matrix can be viewed as a stretching transformation. The eigenvectors define the directions of those stretches, and the largest eigenvalue identifies the direction of the greatest stretch (maximum variance). By projecting onto these directions, PCA preserves the most important aspects of the data's spread while reducing dimensionality.


## PCA: Formalized Steps (Final Algorithm)

**Goal:** Reduce dimensionality of a dataset from *m* features (e.g., 5) to *k* principal components (e.g., 2).

**Steps:**

1.  **Data Matrix (X):**
    *   Start with a dataset of *n* observations and *m* variables (x1, x2, ..., xm).
    *   Construct a matrix `X` where:
        *   Rows: Each row represents an observation.
        *   Columns: Each column represents a variable/feature.
2.  **Center the Data:**
    *   Calculate the column averages (means) for each variable. Let this vector of means be denoted by `mu`.
    *   Subtract the column averages from each column of the data matrix: `X_centered = X - mu`
3.  **Calculate the Covariance Matrix (C):**
    *   Compute the covariance matrix `C` using the centered data:
        *   `C = (1 / (n - 1)) * (X_centered.T * X_centered)`
        *   `C` will be an *m x m* matrix.
4.  **Find Eigenvalues and Eigenvectors of C:**
    *   Calculate the eigenvalues and eigenvectors of the covariance matrix `C`.
5.  **Sort Eigenvector/Eigenvalue Pairs:**
    *   Sort the eigenvector/eigenvalue pairs in descending order of eigenvalue.
6.  **Select Principal Components:**
    *   Choose the top *k* eigenvectors corresponding to the *k* largest eigenvalues. These are your principal components.
7.  **Create Projection Matrix (V):**
    *   Create a matrix `V` where each column is one of the selected top *k* eigenvectors (principal components).
    * Each eigenvector should be normalized, so it has a norm of 1.
    *   `V` will be an *m x k* matrix.
8.  **Project the Data:**
    *   Multiply the *centered* data by the projection matrix `V`:
        *   `X_PCA = X_centered * V`
        *   Where:
            *   `X_PCA` is the reduced-dimensionality data (the principal components).
            *   `X_PCA` will have *n* rows (same as original data) and *k* columns (the chosen number of principal components).

**Result:**

*   `X_PCA` is your new dataset with *k* features, representing the projection of your original data onto the *k* principal components.  You have reduced the dimensionality of the data from *m* to *k* while preserving as much variance as possible.

## Discrete Dynamical Systems (and Markov Matrices)

**Context:** Application of eigenvectors (seen on the final assignment) to model how systems evolve over time.

**Example: Weather Prediction**

*   **States:** Sunny, Cloudy, Rainy
*   **Transition Probabilities:** Probabilities of transitioning between states (weather conditions).
    *   Example: If today is sunny, there's an 80% chance tomorrow will be sunny, 15% chance cloudy, 5% chance rainy.

**1. Markov Matrix**

*   A square matrix where:
    *   All values are non-negative (probabilities can be zero or positive).
    *   Each column adds up to one (the column probabilities should sum to 100%).
    *   Markov matrices are critical for modeling system evolution.

**2. State Vector (X_t)**

*   Represents the current state of the system at time *t*.
*   Example: If today is cloudy, the state vector is `X_0 = [0, 1, 0]` (0% sunny, 100% cloudy, 0% rainy).

**3. System Evolution**

*   To find the probabilities of the next state, multiply the transition matrix by the current state vector:
    *   `X_(t+1) = TransitionMatrix * X_t`
*   Repeat this process to predict the probabilities for future states (X_2, X_3, X_4, ...).

**4. Equilibrium Vector**

*   Over time (many iterations), the state vector tends to stabilize.
*   The limit as n approaches infinity of X_n gives the equilibrium vector.
*   Equilibrium Vector: This is the end of the state for the dynamical system.

**5. Equilibrium Vector as an Eigenvector**

*   The equilibrium vector is an eigenvector of the transition matrix with an eigenvalue of 1.  This is because multiplying the transition matrix by the equilibrium vector results in (essentially) the same vector.
*   Mathematically: `TransitionMatrix * EquilibriumVector = 1 * EquilibriumVector`

**6. Importance of the Equilibrium Vector**

*   The equilibrium vector gives the long-run probabilities of being in each state, regardless of the initial state.
*   In the weather example, it tells you the long-term probabilities that any given day will be sunny, cloudy, or rainy.

**Key Takeaways:**

*   Markov matrices and state vectors are used to model system evolution over time.
*   By repeatedly multiplying the transition matrix by the state vector, you can predict future states.
*   The equilibrium vector is a stable state that the system tends to approach, and it's an eigenvector of the transition matrix with eigenvalue 1.