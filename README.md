<div align="center">

#  Advertising Sales Prediction

### Comparing TV, Radio, and Newspaper spend as predictors of sales with Simple Linear Regression

![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=flat-square&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Linear%20Regression-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-150458?style=flat-square&logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-2ea44f?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square)

*Three single-feature regression models, built and compared to answer one question: which advertising channel actually drives sales?*

[About](#-about-the-project) • [Objective](#-objective) • [Dataset](#-dataset) • [Workflow](#-project-workflow) • [Results](#-results--summary) • [Installation](#-installation)

</div>

---

##  About the Project

This project is part of an ongoing Machine Learning learning journey. Three separate **Simple Linear Regression** models were built with Python and Scikit-learn, each predicting product sales from a single advertising channel.

The goal wasn't just to produce a prediction — it was to work through the **complete ML workflow** end to end: data preparation, model training, visualization, evaluation, and comparison, using a problem simple enough to isolate and understand each step clearly.

---

##  Objective

Rather than building one model with multiple inputs, this project deliberately trains **three independent single-feature models** — one per advertising channel:

| Model | Input Feature | Question It Answers |
|---|---|---|
| Model 1 | TV Advertising | How well does TV spend alone predict sales? |
| Model 2 | Radio Advertising | How well does radio spend alone predict sales? |
| Model 3 | Newspaper Advertising | How well does newspaper spend alone predict sales? |

Comparing the three in isolation — rather than jumping straight to a multi-feature model — makes it possible to directly rank **which channel has the strongest standalone relationship with sales**, which is the central question this project answers.

---

##  Dataset

**Dataset:** Advertising Dataset

| Role | Feature |
|---|---|
| Input (used one at a time) | TV Advertising |
| Input (used one at a time) | Radio Advertising |
| Input (used one at a time) | Newspaper Advertising |
| **Target** | **Sales** |

---

##  Tools and Libraries

| Category | Tools |
|---|---|
| Language | Python |
| Data Handling | Pandas, NumPy |
| Visualization | Matplotlib |
| Machine Learning | Scikit-learn |

---

##  Project Workflow

```mermaid
flowchart LR
    A[Load Dataset] --> B[Select Single Feature]
    B --> C[Train/Test Split]
    C --> D[Train Linear Regression]
    D --> E[Predict on Test Set]
    E --> F[Visualize Regression Line]
    F --> G[Evaluate: MSE, RMSE, R²]
    G --> H[Compare All 3 Models]
```

1. **Load the dataset** using Pandas.
2. **Select the input feature** for single-feature regression (TV, Radio, or Newspaper).
3. **Split the dataset** into training and testing sets (`train_test_split`).
4. **Train a Simple Linear Regression model** (`LinearRegression`).
5. **Predict** the test set results.
6. **Visualize the regression line** against the actual data points using Matplotlib.
7. **Evaluate performance** using:
   - **Mean Squared Error (MSE)**
   - **Root Mean Squared Error (RMSE)**
   - **R² Score**
8. **Compare all three models** side by side with comparison tables and bar charts.

This same seven-step process was repeated independently for each advertising channel, keeping the methodology identical across all three so the final comparison is a fair, apples-to-apples ranking rather than an artifact of inconsistent preprocessing.

---

##  Results & Summary

After evaluating all three models on the held-out test set:

| Channel | R² Score | MSE / RMSE | Relative Performance |
|---|:---:|:---:|---|
|  **TV Advertising** | **Highest** | **Lowest** |  Strongest predictor |
|  **Radio Advertising** | Moderate | Moderate |  Middle performer |
|  **Newspaper Advertising** | Lowest | Highest |  Weakest predictor |

> Exact metric values for each model are available in the notebook — the table above summarizes the relative ranking established by the evaluation.

### Why This Ranking Makes Sense

A higher R² paired with lower MSE/RMSE on the **TV** model indicates sales variance is best explained by a straight-line relationship with TV spend specifically — the other two channels show a weaker, noisier linear relationship with sales, which is exactly what the comparison was designed to surface.

---

##  Conclusion

Based on the evaluation metrics, **TV advertising is the strongest single feature for predicting sales** when modeled with Simple Linear Regression — it produced both the highest R² Score and the lowest error (MSE/RMSE) of the three channels tested. **Newspaper advertising** was the weakest standalone predictor among the three.

This points toward a natural next step: since no single channel captures the full picture, a **multiple linear regression** model combining all three channels would likely outperform any one of these single-feature models individually.

---

##  Project Structure

```
Advertising-Sales-Prediction/
│
├── data/
│   └── advertising.csv
├── notebooks/
│   └── advertising_sales_prediction.ipynb
├── README.md
└── requirements.txt
```

---

##  Installation

```bash
# 1. Clone the repository
git clone https://github.com/khaled-amireh/Advertising-Sales-Prediction.git
cd Advertising-Sales-Prediction

# 2. Create and activate a virtual environment (recommended)
python -m venv venv
source venv/bin/activate      # On Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch the notebook
jupyter notebook notebooks/advertising_sales_prediction.ipynb
```

---

## 🚀 Future Improvements

- [ ] Build a **Multiple Linear Regression** model combining all three channels
- [ ] Test for multicollinearity between advertising channels before combining them
- [ ] Add polynomial or interaction terms to capture non-linear advertising effects
- [ ] Cross-validate each model for a more robust performance estimate
- [ ] Explore regularized regression (Ridge/Lasso) once multiple features are combined

---

## 👤 Author

**Khaled Amireh**
[GitHub](https://github.com/khaled-amireh)

---

<div align="center">

*If you found this project useful, consider giving it a ⭐ on GitHub.*

</div>
