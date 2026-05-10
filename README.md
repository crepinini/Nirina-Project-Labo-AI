# Nirina-Project-Labo-AI

This repository contains the code and outputs for the **Smart School project**.  
The project is divided into two main parts:

1. **Failure Prediction**: predicting students’ exam scores and identifying students at risk of failing.
2. **Automatic Correction / OCR**: recognising handwritten characters using Optical Character Recognition.

The complete report is based on the experiments, figures and tables generated from the notebooks in this repository.

## Table of Contents

- [Repository Structure](#repository-structure)
- [Part 1 — Failure Prediction](#part-1--failure-prediction)
- [Part 2 — Automatic Correction / OCR](#part-2--automatic-correction--ocr)
- [Dataset Requirement](#dataset-requirement)
- [How to Run the Project](#how-to-run-the-project)
- [Outputs](#outputs)
- [Reproducibility](#reproducibility)
- [Author](#author)

## Repository Structure

```text
Nirina-Project-Labo-AI/
│
├── code/
│   ├── part1-failure.ipynb      # Failure prediction notebook
│   ├── part2-OCR.ipynb          # OCR notebook
│   └── outputs/                 # Generated figures, tables and model outputs
│
├── README.md
├── .gitignore
└── .gitattributes
```

## Part 1 — Failure Prediction

The first part of the project focuses on predicting students’ exam scores using tabular data.
The task is treated as a supervised regression problem, with an additional risk interpretation based on the failure threshold of 50.

The notebook includes:

* Exploratory Data Analysis (EDA)
* Missing-value analysis
* Correlation and Mutual Information analysis
* Feature selection and feature engineering
* Data preprocessing with pipelines
* Model comparison
* Hyperparameter tuning
* Overfitting analysis
* Final model selection

The models tested include:

* Dummy mean baseline
* Linear Regression
* Ridge Regression
* Decision Tree
* Random Forest
* Histogram Gradient Boosting
* MLP Neural Network

The final selected model is a tuned **Histogram Gradient Boosting Regressor**, chosen based on validation MAE, R², at-risk recall and overfitting behaviour.


## Part 2 — Automatic Correction / OCR

The second part of the project focuses on handwritten character recognition.
The OCR task is treated as a supervised image-classification problem.

The notebook includes:

* Loading IDX image and label files
* Preparing the OCR dataset
* Correcting image orientation
* Balancing the training set
* Training a CNN model
* Evaluating validation and test performance
* Analysing confusion matrices
* Studying confidence thresholds
* Identifying the most difficult characters

The OCR model is a **Convolutional Neural Network (CNN)** trained to classify:

* digits from `0` to `9`
* uppercase letters from `A` to `Z`
* lowercase letters from `a` to `z`

The evaluation includes accuracy, balanced accuracy, macro F1-score, weighted F1-score, top-3 accuracy and confusion analysis.


## Dataset Requirement

Before running the notebooks, the datasets must be placed inside the `code/` folder.

For the failure prediction part, make sure the student dataset is available in the following location:

```text
code/student_dataset.csv
```

If the notebook expects another exact filename, keep the same name as used in the notebook or update the path at the beginning of the notebook.

For the OCR part, the image and label files must also be placed in the `code/` folder or in the path expected by the notebook.

Typical OCR files may include:

```text
code/train-images-idx3-ubyte
code/train-labels-idx1-ubyte
code/test-images-idx3-ubyte
code/test-labels-idx1-ubyte
```

The notebooks assume that the required datasets are available locally before execution.


## How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/crepinini/Nirina-Project-Labo-AI.git
cd Nirina-Project-Labo-AI
```

### 2. Open the code folder

```bash
cd code
```

### 3. Add the datasets

Place the required datasets in the `code/` folder before running the notebooks in the folder `student_dataset/`.


### 4. Install the required Python libraries

The notebooks use common data science and machine learning libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn tensorflow keras
```

Depending on the local environment, additional packages may be required.

### 5. Launch Jupyter Notebook

```bash
jupyter notebook
```

Then run the notebooks in this order:

```text
part1-failure.ipynb
part2-OCR.ipynb
```


## Outputs

The notebooks generate outputs such as:

* figures
* tables
* model comparison results
* confusion matrices
* OCR evaluation results

These outputs are saved in the `code/outputs/` folder and are used to support the report and annexes.


## Reproducibility

Random seeds are used where possible to improve reproducibility.
However, some results may slightly vary depending on the Python version, library versions, hardware and TensorFlow execution environment.


## Author

**Nirina Crépin - 25363**

Academic year 2025–2026

