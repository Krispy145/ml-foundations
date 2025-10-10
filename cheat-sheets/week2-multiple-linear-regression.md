# Week 2 — Multiple Linear Regression Cheat Sheet

### 🧩 Multiple Features

Extending from single to multiple features:

**Model:**
\[
\hat{y} = w \cdot x + b
\]

Where:

- **w** → weight vector (one weight per feature)
- **x** → feature vector (multiple input features)
- **b** → bias term
- **\(\hat{y}\)** → predicted value

**Key insight:** Multiple linear regression uses one target variable with many input features.

---

### ⚡ Vectorization

**Why vectorize?**

- Leverages optimized BLAS/GPU operations
- Code becomes more readable and concise
- Significantly faster execution

**Implementation:**

- Use NumPy's `@` operator or `.dot()` for matrix operations
- Process entire datasets in single operations

---

### 📉 Cost Function & Gradients

**Cost Function (MSE):**
\[
J(w, b) = \frac{1}{2m} \sum\_{i=1}^{m} (\hat{y}^{(i)} - y^{(i)})^2
\]

**Gradients:**
\[
\frac{\partial J}{\partial w} = \frac{1}{m} X^T (Xw + b - y)
\]
\[
\frac{\partial J}{\partial b} = \frac{1}{m} \sum\_{i=1}^{m} (\hat{y}^{(i)} - y^{(i)})
\]

**Common issues:**

- Cost increasing → learning rate too large or sign error in gradient
- Slow convergence → check gradient calculations

---

### 📏 Feature Scaling

**Why scale features?**
When features have different ranges (e.g., square footage vs. number of bedrooms), gradient descent becomes inefficient and may zig-zag.

**Z-score normalization:**
\[
x' = \frac{x - \mu}{\sigma}
\]

**Mean normalization:**
\[
x' = \frac{x - \mu}{x*{max} - x*{min}}
\]

**Target range:** Features should be roughly in [-3, 3] range.

**Critical for polynomials:** When using \(x^2, x^3, \sqrt{x}\), scaling becomes essential as ranges explode.

---

### 🔄 Gradient Descent Updates

**Update rules:**
\[
w := w - \alpha \frac{\partial J}{\partial w}
\]
\[
b := b - \alpha \frac{\partial J}{\partial b}
\]

**Convergence monitoring:**

- Plot cost function vs. iterations
- Cost should decrease monotonically
- If cost increases, reduce learning rate

**Learning rate selection:**

- Try values spaced ~3x apart: 1e-3, 3e-3, 1e-2, 3e-2, etc.
- Choose largest rate that shows smooth decrease
- Optional: stop when \(|J\_{t-1} - J_t| < \epsilon\)

---

### 🔧 Feature Engineering

**Polynomial features:**
Create non-linear relationships using polynomial terms:
\[
X = [x, x^2, x^3, \sqrt{x}, ...]
\]

**Interaction terms:**
Combine features for multiplicative effects:
\[
x\_{interaction} = x_1 \times x_2
\]
Example: area = width × depth

**Key benefit:** Linear models can capture non-linear patterns through feature engineering while keeping the same gradient descent machinery.

---

### 🎯 Best Practices

**Training workflow:**

1. Scale features using training set statistics
2. Apply same scaling to new data
3. Monitor convergence with learning curves
4. Validate on separate test set

**Feature scaling storage:**

- Save \(\mu\) and \(\sigma\) from training set
- Apply identical scaling to all future predictions

---

### 💡 Quick Reference

- **Model:** \(\hat{y} = w \cdot x + b\)
- **Cost:** \(J = \frac{1}{2m} \sum (\hat{y} - y)^2\)
- **Gradients:** \(\frac{\partial J}{\partial w} = \frac{1}{m} X^T (Xw + b - y)\)
- **Scaling:** \(x' = \frac{x - \mu}{\sigma}\)
- **Convergence:** Plot J vs iterations, ensure monotonic decrease

---

### 🧠 Reflection

This week demonstrated how multiple linear regression extends naturally from single-feature regression. The key insights were the importance of feature scaling for efficient gradient descent and how feature engineering allows linear models to capture non-linear patterns. Vectorization proved essential for both performance and code clarity.

---

### 💬 Note

I used AI to help me structure and format this cheat sheet while keeping the explanations in my own words for clarity and quick reference.
