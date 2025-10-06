# Week 1 — Linear Regression Cheat Sheet

### 🧩 Core Formula

The hypothesis (prediction) function:
\[
f(x) = w \cdot x + b
\]

In vector form (for multiple samples):
\[
\hat{y} = Xw + b
\]

Where:

- **x** → input feature(s)
- **w** → weight(s) or slope(s)
- **b** → bias or intercept
- **f(x)** → predicted value for input x

---

### ⚙️ Model Parameters — θ (Theta)

The model parameters θ represent everything the algorithm is trying to learn:
\[
θ = \begin{bmatrix} b \\ w \end{bmatrix}
\]
so the model can be rewritten compactly as:
\[
f(x) = θ^T x
\]
_(assuming x includes a bias term 1 as its first column)_

---

### 📉 Cost Function — Mean Squared Error (MSE)

The cost function measures _how far off_ the predictions are from the true values.

There are a few common ways to write it:

1️⃣ **Expanded (scalar) form:**
\[
J(w, b) = \frac{1}{2m} \sum*{i=1}^{m} (f*{w,b}(x^{(i)}) - y^{(i)})^2
\]

2️⃣ **Vectorized form:**
\[
J(θ) = \frac{1}{2m} (Xθ - y)^T (Xθ - y)
\]

Where:

- **m** = number of training examples
- **X** = input matrix (each row = one training example)
- **y** = true output values
- **Xθ - y** = prediction errors

---

### 🔁 Gradient Descent (Learning Algorithm)

Goal: iteratively update θ to minimize J(θ)

**Update rule:**
\[
θ := θ - α \cdot \frac{1}{m} X^T (Xθ - y)
\]

Where:

- **α (alpha)** = learning rate (controls step size)
- We repeat until cost stops decreasing

**Intuition:**  
Each iteration, θ moves a little “downhill” on the cost function surface.  
Too large α → overshoots.  
Too small α → takes forever to converge.

---

### 💡 Quick Insights

- **Gaussian noise:** Adds small random variation to make the dataset more realistic (mimics measurement errors).
- **Normal Equation:**  
  Direct, closed-form solution for θ without iterations:
  \[
  θ = (X^T X)^{-1} X^T y
  \]
  Useful for smaller datasets but not scalable for huge feature sets.
- **Gradient Descent:**  
  Works for any number of features and scales to large data; foundation for neural networks later.

---

### 🧠 Reflection

This week I learned how a model “fits” a line to data by finding θ values that minimize the cost function.  
It’s the first real taste of how machines _learn from data_ — by adjusting parameters to reduce error.  
Both gradient descent and the normal equation reach the same solution, just in different ways.

---

### 💬 Note

I used AI to help me structure and format this cheat sheet while keeping the explanations in my own words for clarity and quick reference.
