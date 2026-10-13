<div align="center">
<p align="center">
  <img
    src="maxresdefault.jpg"
    alt="BNA Platform logo"
  >
</p>
  
# Titanic Survival Prediction

### Comparing Decision Trees, Support Vector Machines, and K-Nearest Neighbors

An educational machine-learning notebook that prepares Titanic passenger data and compares three binary-classification approaches for survival prediction.

</div>

---

## Table of Contents

- [Project Overview](#project-overview)
- [Implemented Workflow](#implemented-workflow)
- [Dataset](#dataset)
- [Exploratory Analysis and Visualizations](#exploratory-analysis-and-visualizations)
- [Models and Methodology](#models-and-methodology)
- [Evaluation](#evaluation)
- [Technologies](#technologies)
- [Project Structure](#project-structure)
- [Installation and Setup](#installation-and-setup)
- [Running the Notebook](#running-the-notebook)
- [Reproducibility and Data Requirements](#reproducibility-and-data-requirements)
- [Limitations and Future Improvements](#limitations-and-future-improvements)
- [Author](#author)

## Project Overview

This project uses the well-known Titanic passenger prediction task to demonstrate a complete, compact classification workflow:

1. Load tabular passenger data from `train.csv`.
2. Handle selected missing values.
3. Encode categorical variables.
4. Train three classification models.
5. Generate predictions, accuracy scores, and confusion matrices.
6. Compare model accuracies visually.

The notebook is primarily a comparative modelling exercise. Its goal is to show how a Decision Tree, an RBF-kernel Support Vector Machine (SVM), and K-Nearest Neighbors (KNN) can be applied to the same survival-prediction problem.

## Implemented Workflow

The notebook contains the following implemented steps:

### Data loading and preprocessing

- Reads `train.csv` with `pandas.read_csv`.
- Replaces missing `Age` values with the median age.
- Replaces missing `Fare` values with the median fare.
- Replaces missing `Embarked` values with the most frequent port.
- Encodes `Sex` and `Embarked` using `LabelEncoder`.

The supplied notebook references `X_train`, `X_test`, `y_train`, `y_test`, `X_train_scaled`, and `X_test_scaled`
### Model training and prediction

Each model is fitted on the training data and used to predict the held-out test data. Accuracy is calculated with `accuracy_score`, and confusion matrices are generated with `confusion_matrix`.

### Model comparison

The notebook builds a results table containing the three model labels and their computed accuracies, sorts it in descending order, and plots the comparison as a bar chart.

## Dataset

The notebook expects a file named `train.csv` in the notebook's working directory. The file is not included in this repository snapshot, and the notebook does not document an external download URL.

The available code demonstrates that the dataset contains at least the following columns:

| Column | Evidence from notebook | Processing |
|---|---|---|
| `Age` | Referenced directly in preprocessing | Missing values filled with the median |
| `Fare` | Referenced directly in preprocessing | Missing values filled with the median |
| `Embarked` | Referenced directly in preprocessing | Missing values filled with the mode, then label encoded |
| `Sex` | Referenced directly in preprocessing | Label encoded |


## Exploratory Analysis and Visualizations

The notebook includes model-oriented visualizations rather than a separate descriptive EDA section:

- A rendered Decision Tree diagram with node colours.
- A Decision Tree confusion-matrix heatmap.
- An SVM confusion-matrix heatmap.
- A KNN confusion-matrix heatmap.
- A bar chart comparing the three computed accuracies.


## Models and Methodology

| Model | Configuration in notebook | Input preparation |
|---|---|---|
| Decision Tree | `DecisionTreeClassifier(max_depth=3, random_state=42)` | Uses `X_train` and `X_test` without an explicitly shown scaler |
| Support Vector Machine | `SVC(kernel="rbf", random_state=42)` | Uses `X_train_scaled` and `X_test_scaled` |
| K-Nearest Neighbors | `KNeighborsClassifier(n_neighbors=5)` | Uses `X_train_scaled` and `X_test_scaled` |


## Evaluation

The implemented evaluation metric is classification accuracy:

```python
accuracy_score(y_test, y_pred)
```

The notebook also computes and visualizes a confusion matrix for every model:

```python
confusion_matrix(y_test, y_pred)
```

### Results table

The notebook constructs the following comparison table at runtime:

| Model | Metric |
|---|---:|
| Decision Tree | Accuracy computed in notebook; numeric value not saved in output |
| SVM | Accuracy computed in notebook; numeric value not saved in output |
| KNN | Accuracy computed in notebook; numeric value not saved in output |

<p align="center">
  <img
    src="Screenshot 2026-10-13 005629.png"
    alt="BNA Platform logo"
  >
</p>

## Technologies

The notebook imports and uses:

- Python
- NumPy
- pandas
- Matplotlib
- Seaborn
- scikit-learn
- Jupyter Notebook or JupyterLab





## Project Structure

The supplied project directory currently contains:

```text
.
└── Titanic Survival Prediction.ipynb
```



## Installation and Setup

Create and activate a virtual environment, then install the libraries imported by the notebook:

### Windows PowerShell

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

### macOS or Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```



## Running the Notebook

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Alternatively, launch JupyterLab:

```bash
jupyter lab
```

Open `Titanic Survival Prediction.ipynb` and run the cells from top to bottom.


## Reproducibility and Data Requirements

- The Decision Tree uses `random_state=42`.
- The SVM is instantiated with `random_state=42`.
- The KNN model uses `n_neighbors=5`.
- The Decision Tree is constrained with `max_depth=3`.
- The SVM uses an RBF kernel.
- The notebook's train/test split configuration and complete feature pipeline are not available in the supplied file.

## Limitations and Future Improvements






- Report accuracy values and confusion-matrix counts in a reproducible results table.
- Add precision, recall, F1-score, and possibly ROC-AUC for a more complete evaluation.
- Use a preprocessing pipeline to fit transformations only on training data and reduce leakage risk.
- Add tests or a small executable script if the project is intended for repeated use.

## Author

Author information was not included in the supplied notebook or workspace.

- **Name:** `Achref Bejaoui`
- **GitHub:** `https://github.com/Achref-004`
- **LinkedIn:** `https://linkedin.com/in/achref-bejaoui00`

---

