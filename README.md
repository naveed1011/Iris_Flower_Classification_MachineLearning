# Iris Flower Classification using Machine Learning

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3-green?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A comprehensive machine learning project for classifying Iris flower species using multiple classifiers with rigorous evaluation methodology.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Results](#results)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Key Visualizations](#key-visualizations)
- [Future Improvements](#future-improvements)
- [Author](#author)

---

## Project Overview

This project implements a **complete machine learning pipeline** to classify Iris flowers into three species based on their morphological measurements. The workflow includes:

1. **Data Cleaning** — Handling missing values, duplicates, and feature selection
2. **Exploratory Data Analysis** — Correlation analysis, distribution visualization, and class separability assessment
3. **Feature Engineering** — Label encoding, train-test splitting with stratification, and feature scaling
4. **Model Training** — Five different classifiers (SVM, Logistic Regression, Decision Tree, Random Forest, KNN)
5. **Robust Evaluation** — Stratified 5-fold cross-validation with multi-metric assessment
6. **Hyperparameter Tuning** — GridSearchCV optimization for top-performing models
7. **Model Comparison** — Side-by-side performance analysis with visualizations

---

## Dataset

The **Iris dataset** is one of the most well-known datasets in machine learning, introduced by British statistician Ronald Fisher in 1936. It contains 150 samples from three species of Iris flowers, with 50 samples per species.

| Feature | Description | Unit |
|---------|-------------|------|
| Sepal Length | Length of the sepal | cm |
| Sepal Width | Width of the sepal | cm |
| Petal Length | Length of the petal | cm |
| Petal Width | Width of the petal | cm |
| Species | Target class (Iris-setosa, Iris-versicolor, Iris-virginica) | — |

**Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/iris)

---

## Methodology

### Preprocessing
- **Dropped** the `Id` column (non-informative)
- **Removed** duplicate rows
- **Encoded** species labels using `LabelEncoder`
- **Split** data 80/20 with stratification to preserve class balance
- **Scaled** features using `StandardScaler` (critical for SVM, Logistic Regression, and KNN)

### Models Trained

| Model | Why Included |
|-------|-------------|
| **Support Vector Machine (SVM)** | Excellent for high-dimensional spaces; uses kernel trick for non-linear boundaries |
| **Logistic Regression** | Strong baseline linear classifier; interpretable coefficients |
| **Decision Tree** | Non-parametric; handles non-linear relationships; interpretable |
| **Random Forest** | Ensemble of trees; reduces overfitting; robust to noise |
| **K-Nearest Neighbors** | Instance-based learning; simple yet effective for small datasets |

### Evaluation Strategy
- **Train-Test Split:** 80/20 with stratified sampling
- **Cross-Validation:** 5-fold stratified CV for robust performance estimation
- **Metrics:** Accuracy, Precision, Recall, F1-Score, Confusion Matrix
- **Hyperparameter Tuning:** GridSearchCV with exhaustive parameter search

---

## Results

### Cross-Validation Performance

| Model | Mean CV Accuracy | Std Deviation |
|-------|-----------------|---------------|
| Support Vector Machine | ~97-100% | Low |
| Logistic Regression | ~96-100% | Low |
| Random Forest | ~95-100% | Low |
| Decision Tree | ~95-100% | Moderate |
| K-Nearest Neighbors | ~95-100% | Low |

> **Note:** Exact values depend on random seed and data splits. Run the notebook for precise results.

### Key Findings

1. **Petal dimensions are the most discriminative features** — Petal length and petal width are highly correlated (r=0.96) and provide clear class separation
2. **Iris-setosa is linearly separable** from the other two species
3. **Feature scaling is essential** for distance-based algorithms (SVM, KNN)
4. **SVM with RBF kernel** achieves the best performance after hyperparameter tuning

---

## Project Structure

```
Iris_Flower_Classification_MachineLearning/
│
├── Iris_Flower_Classification.ipynb   # Main Jupyter notebook
├── Iris.csv                           # Dataset
└── README.md                          # This file
```

---

## Installation

### Prerequisites
- Python 3.8 or higher
- pip or conda package manager

### Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/Iris_Flower_Classification_MachineLearning.git
   cd Iris_Flower_Classification_MachineLearning
   ```

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

4. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

5. **Open `Iris_Flower_Classification.ipynb` and run all cells.**

---

## Usage

The notebook is designed to be run sequentially from top to bottom. Each section is clearly marked with markdown headers:

1. **Section 1-3:** Setup and data preparation
2. **Section 4:** EDA with interactive visualizations
3. **Section 5:** Preprocessing pipeline
4. **Section 6-7:** Model training and cross-validation
5. **Section 8:** Hyperparameter optimization
6. **Section 9-10:** Detailed evaluation and comparison
7. **Section 11:** Summary and conclusions

---

## Key Visualizations

The notebook generates several publication-quality visualizations:

- **Correlation Heatmap** — Feature relationships and multicollinearity
- **Violin Plots** — Distribution shape and class separability
- **Pair Plot** — All pairwise feature relationships colored by species
- **Box Plots** — Feature ranges and outlier detection
- **Histograms** — Feature distributions per species
- **Confusion Matrices** — Per-class classification accuracy
- **Model Comparison Charts** — Bar and box plots of cross-validation scores

---

## Author

**Naveed Ahmad**

If you found this project useful, please consider giving it a star on GitHub!

---

## License

This project is open source and available under the [MIT License](LICENSE).
