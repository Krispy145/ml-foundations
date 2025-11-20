# Ml Foundations

Hands-on notebooks implementing core ML algorithms with evaluations and plots.

---

## 📈 Status

- **Status:** active (Active)
- **Focus:** Hands-on notebooks implementing core ML algorithms with evaluations and plots.
- **Last updated:** 20/11/2025
- **Target completion:** 24/11/2025

---

## 🔑 Highlights

- **Hands-on Learning** → Interactive Jupyter notebooks
- **Core Algorithms** → Linear regression, logistic regression
- **Data Visualization** → Matplotlib and Seaborn plots
- **Real Datasets** → Practical examples with real data
- **Cheat Sheets** → Quick reference guides
- **Progressive Learning** → Step-by-step complexity

---

## 🏗 Architecture Overview

```
notebooks/
├── course-one/     # Course 1: Supervised Machine Learning
│   ├── 01-linear-regression.ipynb
│   ├── 02-multiple-linear-regression.ipynb
│   ├── 03-logistic-regression.ipynb
│   └── 03b-logistic-regression-scikit.ipynb
cheat-sheets/
├── course-one/     # Course 1: Supervised Machine Learning
│   ├── week1-linear-regression.md
│   ├── week2-multiple-linear-regression.md
│   └── week3-logistic-regression.md
data/              # Local datasets (gitignored)
```

**Patterns used:**

- **Course Organization** → Structured by Machine Learning Specialization courses
- **Jupyter notebooks** → interactive data science workflow
- **NumPy/Pandas** → data manipulation and analysis
- **Scikit-learn** → machine learning algorithms
- **Matplotlib** → data visualization

---

## 📱 What It Demonstrates

- Machine learning fundamentals and algorithms
- Data science workflow and best practices
- Interactive learning with Jupyter notebooks
- Practical application of ML concepts

---

## 🚀 Getting Started

```bash
git clone https://github.com/Krispy145/ml-foundations.git
cd ml-foundations
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install -r requirements.txt
jupyter notebook
```

---

## 🧪 Testing

```bash
# Run notebook tests
jupyter nbconvert --execute --to notebook notebooks/*.ipynb
```

- Notebook execution → verify all cells run successfully
- Data validation → check data loading and processing
- Visualization → ensure plots render correctly

---

## 🔒 Security & Next Steps

- Follow security best practices for the technology stack
- Implement proper authentication and authorization
- Add comprehensive error handling and validation
- Set up monitoring and logging

---

## 🗓 Roadmap

| Milestone                    | Category              | Target Date | Status     |
| ---------------------------- | --------------------- | ----------- | ---------- |
| Complete Linear Regression | Machine Learning Specialization | 06/10/2025 | ✅ Done |
| Complete Multiple Linear Regression | Machine Learning Specialization | 07/10/2025 | ✅ Done |
| Complete Logistic Regression | Machine Learning Specialization | 26/10/2025 | ✅ Done |
| Complete Course 1: Supervised Machine Learning | Machine Learning Specialization | 26/10/2025 | ✅ Done |
| Complete Course 2: Advanced Learning Algorithms | Machine Learning Specialization | 05/12/2025 | ⏳ In Progress |
| Complete Course 3: Unsupervised Learning, Recommenders, RL | Machine Learning Specialization | 16/01/2026 | ⏳ Planned |
| Complete Machine Learning Specialization (Andrew Ng) | Machine Learning Specialization | 22/12/2025 | ⏳ Planned |


---

## 📄 License

MIT © Krispy145