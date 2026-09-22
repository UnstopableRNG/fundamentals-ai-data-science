# Fundamentals of AI & Data Science — Network Traffic Classification

A machine learning project analysing network traffic data and classifying network activity using supervised machine learning techniques.

This project was completed as part of **COMP H2706 – Fundamentals of AI & Data Science** at TU Dublin.

## Overview

The project uses a network traffic dataset to investigate the classification of different types of network activity.

Two machine learning approaches were implemented and compared:

* Complement Naïve Bayes
* Decision Tree

The project covers data preprocessing, exploratory analysis, model training, hyperparameter tuning and model evaluation.

## Dataset

The dataset contains network traffic records with a mixture of numerical and categorical features.

Examples of features used in the analysis include:

* Bytes sent
* Bytes received
* Average packet size
* Protocol
* Device type
* Privilege level

The dataset is included in the `dataset/` directory.

## Data Preprocessing

The dataset was loaded using Pandas and missing values were removed before modelling.

Categorical features were identified and converted into numerical values using `OrdinalEncoder`.

The feature values were then adjusted so that the minimum value of each feature was zero, allowing the data to be used with the Complement Naïve Bayes model.

The data was split into:

* 70% training data
* 30% testing data

A fixed random state of `42` was used for the train-test split.

## Exploratory Data Analysis

The project includes exploratory analysis of the network traffic dataset.

Visualisations include:

* Histograms of the feature distributions
* A correlation heatmap

These visualisations were used to examine feature distributions and relationships within the dataset.

## Machine Learning Models

### Complement Naïve Bayes

The project uses `ComplementNB` as the Naïve Bayes classifier.

A baseline model was first trained and evaluated.

Hyperparameter tuning was then performed using `GridSearchCV` with `StratifiedKFold` cross-validation.

The parameters explored were:

* `alpha`
* `norm`

The tuned model was evaluated using test-set accuracy, a confusion matrix, classification report and five-fold cross-validation.

### Decision Tree

A `DecisionTreeClassifier` was used as the second classification model.

A baseline Decision Tree was first trained and evaluated.

A tuned version was then created using `GridSearchCV`.

The following parameters were explored:

* `criterion`
* `max_depth`
* `min_samples_split`
* `min_samples_leaf`
* `min_impurity_decrease`

The tuned Decision Tree was evaluated using test-set accuracy, a confusion matrix and classification report.

## Model Evaluation

The project evaluates model performance using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion matrices
* Cross-validation

The final notebook compares the test-set accuracy of the tuned Complement Naïve Bayes and Decision Tree models.

## Results and Analysis

The analysis demonstrates differences in performance between the two classification approaches.

The project also considers the importance of evaluating cybersecurity classification models using metrics beyond accuracy, particularly when malicious traffic may be incorrectly classified as benign.

The accompanying analysis identified class imbalance and possible overfitting as important considerations when interpreting the model results.

## Technologies Used

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Complement Naïve Bayes
* Decision Tree
* GridSearchCV
* StratifiedKFold

## Repository Structure

```text
fundamentals-ai-data-science/
├── README.md
├── Project.ipynb
└── dataset/
    └── Dataset2_odd_students.csv
```

## Learning Outcomes

This project provided practical experience with:

* Data loading and preparation
* Exploratory data analysis
* Handling missing values
* Categorical feature encoding
* Supervised machine learning
* Complement Naïve Bayes
* Decision Tree classification
* Hyperparameter tuning
* Cross-validation
* Classification reports
* Confusion matrices
* Applying machine learning to cybersecurity data
* Interpreting model performance

## Project Status

Completed as part of the **COMP H2706 – Fundamentals of AI & Data Science** module at TU Dublin.
