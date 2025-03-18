
# Row Echelon Form (REF) Properties

To be in row echelon form, a matrix must have the following properties:

1.  **Leading 1:** If a row does not consist entirely of zeros, then the first non-zero number in the row is a 1 (called the leading 1).

2.  **Zero Rows at Bottom:** All zero rows are at the bottom of the matrix.

3.  **Stair-Step Structure:** In any two successive rows that do not consist entirely of zeros, the leading 1 in the lower row occurs farther to the right than the leading 1 in the higher row.

**Example Matrix:**

[
[1, 0, 2],
[0, 1, 4],
[0, 0, 0]
]

**Explanation:**

*   This matrix *does not completely satisfy* the REF properties as not completely following all the specific parameters
*   The leading entries are 1. So the property is to make sure it follows all of them. If one doesnt it fails that format.
*   The one above only needs to fix the first part as the leading entry is not a value of 1 and only the leading variable. So only the first point failed.

# Row Echelon Form (REF) vs. Reduced Row Echelon Form (RREF)

**Key Difference:**

*   **Row Echelon Form (REF) is not unique:** You can perform a sequence of row operations and arrive at different valid REF matrices from the same original matrix.

**For Reduced Row Echelon Form (RREF):**

*   **RREF *is* unique:** For any given matrix, there is only one possible reduced row echelon form.
*   **Additional Property:** Each column containing a leading 1 has zeros in all its other entries.

In other words, RREF goes a step further than REF in simplifying the matrix, resulting in a standardized, unique form.

# Elementary Row Operations

The operations you perform in the row echelon form (REF) and reduced row echelon form (RREF) process are called **elementary row operations**. There are three types:

1.  **Row Switching (Interchange):** Swap the positions of two rows.

    *   **Notation:** `R_i <-> R_j` (Swap row *i* and row *j*)

2.  **Row Multiplication (Scaling):** Multiply all elements in a row by a non-zero scalar.

    *   **Notation:** `k * R_i -> R_i` (Multiply row *i* by scalar *k*)
    *   **Important:** *k* must be non-zero.

3.  **Row Addition (Replacement):** Add a multiple of one row to another row.

    *   **Notation:** `R_i + k * R_j -> R_i` (Add *k* times row *j* to row *i*, replacing row *i* with the result)

**Key Points:**

*   These are the *only* operations allowed in row reduction.
*   These operations *preserve the solution set* of the corresponding system of equations. That's why you can manipulate the matrix without changing the fundamental relationship between the variables.
*   They are applied systematically to achieve the row echelon form (or reduced row echelon form).
*   **Keep in mind:**
    *   You are using the row so everything in the row is involved.
    *   The *k* value will be the one you will use in the other row for adding or subtracting purposes. It will become your new k value of the other row.