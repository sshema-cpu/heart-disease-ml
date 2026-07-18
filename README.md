# 🫀 Can a Computer Predict Heart Disease?

**A hands-on comparison of Logistic Regression, Decision Trees, and Neural Networks — tested on 1,025 real patient records.**

*Machine Learning Final Project · Sam Shema · Texas Christian University*

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.x-orange.svg)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 📌 The Question

Heart disease is one of the leading causes of death globally. Early detection saves lives — so can machine learning help doctors flag high-risk patients faster?

This project builds a **binary classifier** that predicts heart disease from 13 medical attributes, and asks a deeper question along the way:

> **Does a more complex model actually earn its complexity?**

## 🏆 Key Results

| Model | Test Accuracy | CV Average (5-fold) | CV Std Dev | ROC-AUC |
|---|---|---|---|---|
| Logistic Regression | 81.0% | 84.4% | ±2.40% | 🥇 **Highest** |
| Decision Tree (depth=4) | 83.9% | **85.5%** | ✅ **±1.90%** | High |
| Neural Network (64→32) | **84.4%** | 85.4% | ±2.78% | High |

**The headline finding:** the Neural Network beat Logistic Regression by only ~3.4 points of accuracy — while Logistic Regression achieved the **best ROC-AUC**, meaning it ranks patients by risk most reliably. In a clinical setting, where doctors must explain predictions to patients, the simple interpretable model may be the most valuable one.

## 💡 Three Lessons Learned

1. **Complexity ≠ better.** On small structured datasets (~1K rows), simple models are highly competitive with deep learning.
2. **Perfect training accuracy is a red flag.** The Neural Network initially scored 100% on training data — classic overfitting. Early stopping + L2 regularization (`alpha=0.01`) brought it back to honest, generalizable performance.
3. **Most features barely matter.** Chest pain type alone drove **43%** of the Decision Tree's decisions; four features contributed almost nothing — suggesting a leaner 7–8 feature model could match this accuracy at lower cost.

## 📊 Dataset

- **Source:** [Kaggle — Heart Disease Dataset (UCI)](https://www.kaggle.com/datasets/johnsmith88/heart-disease-dataset)
- **Size:** 1,025 patient records × 14 columns · zero missing values
- **Balance:** 526 positive / 499 negative (51.3% / 48.7%)
- **Features:** age, sex, chest pain type, resting blood pressure, cholesterol, fasting blood sugar, resting ECG, max heart rate, exercise-induced angina, ST depression, ST slope, major vessels (ca), thalassemia (thal)

## 🔬 Methodology

```
Load CSV → EDA (class balance, correlation heatmap) → X/y split
→ 80/20 stratified train-test split → StandardScaler
→ Train 3 models → Evaluate (accuracy, precision, recall, F1, ROC-AUC)
→ 5-fold cross-validation → Confusion matrices, ROC curves, feature importance
```

**Models compared:**
- `LogisticRegression()` — the interpretable baseline
- `DecisionTreeClassifier(max_depth=4)` — non-linear patterns, visual rules
- `MLPClassifier(hidden_layer_sizes=(64, 32), early_stopping=True, alpha=0.01)` — deep learning contender

## 📁 Repository Structure

```
heart-disease-ml/
├── data/
│   └── heart.csv                      # Kaggle UCI heart disease dataset
├── notebooks/
│   └── heart_disease_prediction.ipynb # Full analysis: EDA → models → evaluation
├── report/
│   └── Sam_Shema_ML_Final_Report.pdf  # Written project report
├── docs/
│   └── index.html                     # Interactive portfolio page (GitHub Pages)
├── requirements.txt
└── README.md
```

## 🚀 Run It Yourself

```bash
# Clone the repo
git clone https://github.com/YOUR-USERNAME/heart-disease-ml.git
cd heart-disease-ml

# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook notebooks/heart_disease_prediction.ipynb
```

> The notebook was originally built in Google Colab — you can also upload it to [Colab](https://colab.research.google.com/) and add `data/heart.csv` to the session.

## 🔮 Future Work

- Trim low-importance features and test a leaner 7–8 feature model
- Try ensemble methods (Random Forest, XGBoost) — typically the winners on structured data
- Validate on an independent, demographically diverse patient population
- Note: this Kaggle version expands the classic ~300-row UCI Cleveland data, so records may repeat — external validation is the true test

## ⚠️ Disclaimer

This is an educational project. Predictions are **not medical diagnoses** — always consult a licensed healthcare professional.

---

**Sam Shema** · B.S. Data Science, Texas Christian University
📫 s.shema@tcu.edu · [LinkedIn](https://www.linkedin.com/in/YOUR-HANDLE) · [Portfolio](https://YOUR-USERNAME.github.io/heart-disease-ml/)
