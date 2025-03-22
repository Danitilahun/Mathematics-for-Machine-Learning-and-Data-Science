**Topic:** The Perceptron - Fundamental Unit of Neural Networks

*   **Motivation:** Predicting house prices using features like size (x1) and number of rooms (x2).

*   **Perceptron:** A single-layer neural network that takes inputs and produces an output (ŷ). In This part it's shown how to express linear regression as a perceptron

*   **Structure:**
    *   **Inputs (x1, x2, ...):** Features used for prediction.
    *   **Weights (w1, w2, ...):** Represent the importance of each feature.
    *   **Bias (b):** A constant term added to the summation.
    *   **Summation:** Σ(w_i * x_i) + b.
    *   **Output (ŷ):** The predicted value.

*   **Equation:**
    *   ŷ = w1 * x1 + w2 * x2 + b

*   **Goal:** Find the optimal weights (w1, w2, ...) and bias (b) that minimize the error between predicted values and actual prices. To do this, use the Loss Function.

**Topic:** Loss Function - Evaluating Model Performance

*   **Goal:** Evaluate the performance of a model (e.g., linear regression line for house prices) and improve it.

*   **Error:** The difference between the predicted value (ŷ) and the actual value (y).

*   **Problem with Simple Error (y - ŷ):** Positive and negative errors can cancel each other out, giving a misleadingly low overall error.

*   **Loss Function (L):** A function that quantifies the error for each data point.  The goal is to minimize this function. The model is improved by minimizing this function.
    *   **Formula:** L(y, ŷ) = (1/2) * (y - ŷ)^2.
        *   (1/2) is added to simplify derivative calculations. It does not change the optimal m and b, but makes the math simpler.
        *   Squaring the error ensures that all errors are positive.

*   **Minimizing the Loss Function:** The goal is to find the weights (w1, w2, ...) and bias (b) that minimize the loss function.

*   **Gradient Descent:** Gradient descent will be used to minimize the loss function and find the optimal weights and bias.


**Topic:** Training the Perceptron with Gradient Descent

*   **Goal:** Find the optimal weights (w1, w2) and bias (b) that minimize the loss function L(y, ŷ).

*   **Method:** Use gradient descent to update the weights and bias iteratively.

*   **Gradient Descent Formulas:**
    *   `w1_(new) = w1_(old) - α * (∂L/∂w1)`
    *   `w2_(new) = w2_(old) - α * (∂L/∂w2)`
    *   `b_(new) = b_(old) - α * (∂L/∂b)`
    *   α is the learning rate

*   **Calculating Partial Derivatives:** Chain rule is used to calculate the partial derivatives required for gradient descent.
    *   ∂L/∂b = (∂L/∂ŷ) * (∂ŷ/∂b)
    *   ∂L/∂w1 = (∂L/∂ŷ) * (∂ŷ/∂w1)
    *   ∂L/∂w2 = (∂L/∂ŷ) * (∂ŷ/∂w2)

*   **Individual Derivative Calculations:**
    *   ∂L/∂ŷ = -(y - ŷ)
    *   ∂ŷ/∂b = 1
    *   ∂ŷ/∂w1 = x1
    *   ∂ŷ/∂w2 = x2

*   **Putting it Together:**
    *   ∂L/∂b = -(y - ŷ) * 1 = -(y - ŷ)
    *   ∂L/∂w1 = -(y - ŷ) * x1
    *   ∂L/∂w2 = -(y - ŷ) * x2

*   **Complete Gradient Descent Update Rules:**
    *   `w1_(new) = w1_(old) + α * x1 * (y - ŷ)`
    *   `w2_(new) = w2_(old) + α * x2 * (y - ŷ)`
    *   `b_(new) = b_(old) + α * (y - ŷ)`
* by incorporating this correction term it is assured that the derivates are negative as the slide shows earlier

*   **Iteration:** Repeat the update process for a large number of iterations to converge to the optimal weights and bias values.


**Topic:** Perceptron for Binary Classification

*   **Extending Perceptrons:** Building upon the regression example, This part demonstrates how to use perceptrons for binary classification problems (e.g., sentiment analysis).

*   **Example: Alien Sentiment Analysis:**
    *   Problem: Classifying alien sentences as happy or sad.
    *   Features: Number of "aack" (x1) and "beep" (x2) words.

*   **Key Modification: Activation Function**
    *   Difference from Regression: An activation function is added to the perceptron to constrain the output to a specific range (0 to 1 for binary classification).

*   **Activation Function: Sigmoid**
    *   Sigmoid Function (σ(z)): Squashes any real number z into the range (0, 1).
    *   Formula: σ(z) = 1 / (1 + e^(-z))
    *   Purpose:
        *   Converts the raw output of the summation node into a probability-like value (between 0 and 1).
        *   Can be interpreted as the model's confidence in the classification. (e.g. close to 0 means very sad)

*   **Perceptron Structure (Classification):**
    1.  **Inputs (x1, x2):** Features (e.g., word counts).
    2.  **Weights (w1, w2):** Feature importances.
    3.  **Bias (b):** Constant term.
    4.  **Summation:** z = w1 * x1 + w2 * x2 + b
    5.  **Sigmoid Activation:** ŷ = σ(z) = 1 / (1 + e^(-z))
    6.  **Output (ŷ):** Predicted probability of belonging to one class (e.g., being happy).

**Topic:** The Sigmoid Function - Details and Derivative

*   **Review of Sigmoid Function:**
    *   Formula: σ(z) = 1 / (1 + e^(-z))
    *   Property: Squashes any real number into the range (0, 1).
    *   Graph: Shows asymptotes at 0 and 1.

*   **Key Concept: Derivative of the Sigmoid Function**
    *   The sigmoid function has a particularly simple and useful derivative.
    *   Why is this important? Simpler derivatives greatly speed up model training by making calculations of the Gradient Descent easier.

*   **Derivative Calculation:**
    *   The video provides a step-by-step derivation of the derivative of the sigmoid function.
    *   Result:  d/dz σ(z) = σ(z) * (1 - σ(z))
    *   This simplifies the calculations when doing gradient descent for machine learning models that use the sigmoid function.

**Topic:** Training the Classification Perceptron - Log Loss

*   **Example:** Sentence: "Aack beep beep beep" (x1 = 1, x2 = 3); weights: w1 = 4.5, w2 = 1.5, b = 2; Actual label (y) = 0 (sad).

*   **Need for a New Loss Function:** Squared error or absolute error isn't optimal for classification.

*   **Log Loss (L(y, ŷ)):** The preferred loss function for classification.
    *   Formula: L(y, ŷ) = -[y * log(ŷ) + (1 - y) * log(1 - ŷ)]
        *   y: Actual label (0 or 1).
        *   ŷ: Predicted probability (between 0 and 1) from the sigmoid function.
    *   Properties:
        *   Probabilistic Interpretation: log loss is naturally related to probabilities. The problem discussed is fitting a coin to heads or tails given a data set. The data set is like the classification example with some sentences that are labeled "good" or "bad".
        *   Large error when y and ŷ are different, small error when y and ŷ are similar.

*   **Gradient Descent with Log Loss:** The goal is to find the optimal weights and bias that minimize the log loss.
    *   Update Rules:
        *   `w1_(new) = w1_(old) - α * (∂L/∂w1)`
        *   `w2_(new) = w2_(old) - α * (∂L/∂w2)`
        *   `b_(new) = b_(old) - α * (∂L/∂b)`
    *   Where α is the learning rate.


**Topic:** Gradient Descent for Classification Perceptron (Detailed)

*   **Goal:** Minimize Log Loss (L(y, ŷ)) to find optimal weights (w1, w2) and bias (b) for the classification perceptron.

*   **Strategy:** Apply gradient descent, requiring calculation of partial derivatives of the log loss with respect to w1, w2, and b.

*   **Chain Rule Application:** Partial derivatives are calculated using the chain rule. Example d/d w_1 L =  d/dŷ L * d/dw_1 ŷ

*   **Derivative Calculations:**
    *   ∂L/∂ŷ = (-y / ŷ) + ((1 - y) / (1 - ŷ)) = (ŷ - y) / (ŷ * (1 - ŷ))
    *   ∂ŷ/∂w1 = σ(z) * (1 - σ(z)) * x1 = ŷ * (1 - ŷ) * x1
    *   ∂ŷ/∂w2 = σ(z) * (1 - σ(z)) * x2 = ŷ * (1 - ŷ) * x2
    *   ∂ŷ/∂b = σ(z) * (1 - σ(z)) = ŷ * (1 - ŷ)

*   **Simplified Partial Derivatives (After Canceling):**
    *   ∂L/∂w1 = (ŷ - y) * x1
    *   ∂L/∂w2 = (ŷ - y) * x2
    *   ∂L/∂b = (ŷ - y)

*   **Gradient Descent Update Rules:**
    *   `w1_(new) = w1_(old) - α * (ŷ - y) * x1`
    *   `w2_(new) = w2_(old) - α * (ŷ - y) * x2`
    *   `b_(new) = b_(old) - α * (ŷ - y)`
    *   Where α is the learning rate.

*   **Summary:** Derives the gradient descent update rules for a classification perceptron using log loss and the sigmoid activation function.


**Topic:** Neural Networks - Introduction

*   **Neural Network Definition:** A neural network is a collection of interconnected perceptrons (nodes) organized in layers.
*   **Motivation:** Neural networks can model more complex relationships than a single perceptron. They can draw more complex boundaries than straight lines.
*   **Example: Two-Layer Neural Network**
    *   Consists of an input layer, a hidden layer (with two perceptrons), and an output layer.
        *    Red/Green Perceptron layer. Input x1,x2 is passed through this.
        *    Purple Perceptron. Results of Green/Red Preceptron passed through here.

*   **Variables:**
    *   x1, x2: Inputs (features)
    *   w_ij: Weights connecting input i to node j in the next layer.
    *   b_j: Bias of node j.
    *   z_j: Weighted sum of inputs plus bias for node j.
    *   a_j: Activation (sigmoid) of node j.
    *   ŷ: Output prediction of the neural network.

*   **Mathematical Representation:**
    *  The function representation of the neural network is provided in the summary. It shows how the input, weight and bias, the sum, the sigmoid function are all represented.

*   **Log Loss:** As with the prior slide, given the classification task, Log Loss is a good function to minimize. (L (y, ŷ))


**Topic:** Training a Neural Network - Gradient Descent in Detail

*   **Objective:** Minimize the log loss function (L(y, ŷ)) by adjusting weights and biases in the neural network.

*   **Method:** Apply gradient descent to each weight and bias, requiring calculation of numerous partial derivatives using the chain rule.
*   **Derivative Calculation:**
        This section shows the derivative for a single node. To find the derivative for other nodes the steps must be repeated

*   **Simplification to Key Expressions:**
        Derivative Expression for the following:
          Weight update
             *   `w11_(new) = w11_(old) + α * (y - ŷ) * w1 * x1`
          Bias update
              *   `b1_(new) = b1_(old) + α * (y - ŷ) * w1`
          
          For output node derivative:
             *   del/dw2 L = -1 (y-ŷ) a_2
             *   W2(new) = W2(Old) + Alpha * ( y - ŷ) * A_2 
             *   Similarly we find expression for derivative of weights in the following nodes. 
             
        

*   **Summary of the Gradient Descent Process:**
    * Iterate across all of the data sets and make small adjustments to the weights based on the equations above
    * repeat for many steps to find the optimal value

*   **Results of Training:** Updates the values in each of the nodes. By iterating through all data sets and performing the calculations in the function, the NN can be trained to make the best predictions.


**Topic:** Backpropagation - Training Deep Neural Networks

*   **Overview:** Explains how to train a multi-layer neural network using backpropagation, a method for calculating gradients.

*   **Network Structure:**
    *   The network has multiple layers (input, hidden layers, output).
    *   Notation: Superscripts are used to denote the layer to which a variable belongs (e.g., w^(l) is a weight in layer l).

*   **Process: Minimizing Log Loss Using Gradient Descent**
    * The Goal is to perform the process of Gradient Descent. Because of the chained nature of the weights, the procedure "Back Propogation" must be used.
    * At each data point, the derivatives must be calculated, and each weight adjusted.
    * Backpropagation relies heavily on chain rule.

*   **Chain Rule for Different Layers:**
    *   Starting from the output layer and going backward, partial derivatives are calculated layer by layer.
    * At each data point, the following steps should be performed:
          * Step 1: Calculate DL/DY
          * Step 2: Calculate DL over all Weights in the last Layer.
          * Step 3: Working backward from the last later to the first layer repeat the chain to update weights.
          * Step 4: Use a learning rate to adjust weights
        

*   **Key Points:**
    *   **Reuse of Calculations:** Store calculated derivatives to avoid redundant computations.
    *   **Easy-to-Compute Derivatives:** Neural network architecture ensures that the individual derivatives in the chain rule are relatively simple (sigmoid or linear functions).