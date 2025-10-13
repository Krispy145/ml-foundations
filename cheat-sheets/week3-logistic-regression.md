# Week 3 — Logistic Regression Cheat Sheet

### 🧩 Core Formula

The hypothesis (prediction) function for classification:
\[
f(x) = g(w \cdot x + b)
\]

Where the sigmoid function maps any real number to (0,1):
\[
g(z) = \frac{1}{1 + e^{-z}}
\]

In vector form (for multiple samples):
\[
\hat{y} = g(Xw + b)
\]

Where:

- **x** → input feature(s)
- **w** → weight(s) or slope(s)
- **b** → bias or intercept
- **f(x)** → predicted probability P(y=1|x)
- **g(z)** → sigmoid activation function

---

### ⚙️ Model Parameters — θ (Theta)

The model parameters θ represent everything the algorithm is trying to learn:
\[
θ = \begin{bmatrix} b \\ w \end{bmatrix}
\]

so the model can be rewritten compactly as:
\[
f(x) = g(θ^T x)
\]
_(assuming x includes a bias term 1 as its first column)_

---

### 🎯 Decision Boundary

The decision boundary separates the two classes:
\[
w \cdot x + b = 0
\]

**Decision rule:**

- Predict class 1 if \(f(x) \geq 0.5\) (i.e., \(w \cdot x + b \geq 0\))
- Predict class 0 if \(f(x) < 0.5\) (i.e., \(w \cdot x + b < 0\))

**Key insight:** The decision boundary is linear, but with polynomial features, it can become non-linear.

---

### 📉 Cost Function — Logistic Loss

Unlike linear regression, we use logistic loss for classification:

**Single-example loss:**
\[
L(f, y) = -y \log(f) - (1-y) \log(1-f)
\]

**Cost function (average loss):**
\[
J(w, b) = \frac{1}{m} \sum\_{i=1}^{m} L(f^{(i)}, y^{(i)})
\]

**Vectorized form:**
\[
J(θ) = -\frac{1}{m} [y^T \log(f) + (1-y)^T \log(1-f)]
\]

Where:

- **m** = number of training examples
- **f** = sigmoid(Xθ) = predicted probabilities
- **y** = true binary labels (0 or 1)

**Why logistic loss?** It's convex, making gradient descent reliable, and penalizes confident wrong predictions heavily.

---

### 🔁 Gradient Descent (Learning Algorithm)

Goal: iteratively update θ to minimize J(θ)

**Gradients:**
\[
\frac{\partial J}{\partial w} = \frac{1}{m} X^T (f - y)
\]
\[
\frac{\partial J}{\partial b} = \frac{1}{m} \sum\_{i=1}^{m} (f^{(i)} - y^{(i)})
\]

**Update rule:**
\[
w := w - α \frac{\partial J}{\partial w}
\]
\[
b := b - α \frac{\partial J}{\partial b}
\]

Where:

- **α (alpha)** = learning rate (controls step size)
- **f** = sigmoid(Xw + b) = current predictions

---

### 🛡️ Regularization — Fighting Overfitting

**The Problem:** Overfitting occurs when the model memorizes training data but fails on new data.

**L2 Regularization (Ridge):**
Adds penalty term to cost function:

\[
J(w, b) = -\frac{1}{m} [y^T \log(f) + (1-y)^T \log(1-f)] + \frac{λ}{2m} ||w||^2
\]

**Regularized gradients:**
\[
\frac{\partial J}{\partial w} = \frac{1}{m} X^T (f - y) + \frac{λ}{m} w
\]
\[
\frac{\partial J}{\partial b} = \frac{1}{m} \sum\_{i=1}^{m} (f^{(i)} - y^{(i)}) \quad \text{(no regularization on bias)}
\]

Where:

- **λ (lambda)** = regularization parameter (controls overfitting)
- **||w||²** = sum of squared weights
- **Key:** Don't regularize the bias term b

---

### 📏 Feature Scaling

**Why scale features?**
When features have different ranges, gradient descent becomes inefficient and may zig-zag.

**Z-score normalization:**
\[
x' = \frac{x - μ}{σ}
\]

**Target range:** Features should be roughly in [-3, 3] range.

**Critical for logistic regression:** Helps sigmoid function work effectively across all features.

---

### 🎯 Best Practices

**Training workflow:**

1. Scale features using training set statistics
2. Apply same scaling to new data
3. Monitor convergence with learning curves
4. Validate on separate test set
5. Tune regularization parameter λ

**Overfitting solutions:**

- **More data:** Collect additional training examples
- **Feature selection:** Remove irrelevant features
- **Regularization:** Increase λ to penalize large weights
- **Cross-validation:** Use k-fold CV to select best λ

**Feature scaling storage:**

- Save μ and σ from training set
- Apply identical scaling to all future predictions

---

### 💡 Quick Reference

- **Model:** \(f(x) = g(w \cdot x + b)\)
- **Sigmoid:** \(g(z) = \frac{1}{1 + e^{-z}}\)
- **Decision boundary:** \(w \cdot x + b = 0\)
- **Loss:** \(L = -y \log(f) - (1-y) \log(1-f)\)
- **Cost:** \(J = \frac{1}{m} \sum L + \frac{λ}{2m} ||w||^2\)
- **Gradients:** \(\frac{\partial J}{\partial w} = \frac{1}{m} X^T (f - y) + \frac{λ}{m} w\)
- **Scaling:** \(x' = \frac{x - μ}{σ}\)

---

### 🧠 Reflection

This week revealed why logistic regression is perfect for classification problems. The sigmoid function elegantly maps any real number to a probability, while the logistic loss function provides a convex optimization landscape. Regularization became my go-to tool for preventing overfitting, and I learned that feature scaling is crucial for both convergence and model performance. The decision boundary concept was the key insight that connected linear models to classification.

---

### 💬 Note

I used AI to help me structure and format this cheat sheet while keeping the explanations in my own words for clarity and quick reference.
