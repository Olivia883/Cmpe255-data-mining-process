# SEMMA Project Report: Iris Flower Classification

## 1. Project Overview

### Objective
The goal of this project is to classify iris flowers into three species using four numerical measurements: sepal length, sepal width, petal length, and petal width.

### Research Question
How accurately can a machine learning model classify iris flower species using these four measurements?

### Dataset
The project uses the Iris dataset from scikit-learn, with the following Kaggle dataset page used as a source reference:

https://www.kaggle.com/datasets/uciml/iris

The dataset contains 150 observations, four numerical input features, and one species label.

## 2. SEMMA Methodology

### 2.1 Sample

The Iris dataset was loaded into a pandas DataFrame. Initial inspection showed 150 rows and five columns. The dataset contains three species: setosa, versicolor, and virginica, with 50 observations per species.

No missing values were found in the dataset.

### 2.2 Explore

Descriptive statistics and a pair plot were used to examine the flower measurements and relationships between features.

The average petal length was 1.46 cm for setosa, 4.26 cm for versicolor, and 5.55 cm for virginica. Average petal width was 0.25 cm, 1.33 cm, and 2.03 cm, respectively.

The pair plot showed that petal measurements separated setosa from the other species particularly well. Versicolor and virginica had some overlap.

### 2.3 Modify

The four numerical measurements were used as input features, and species was used as the target variable.

The data was divided into 120 training observations and 30 testing observations. The split used `random_state=42` and stratification by species. Each species contributed 40 training observations and 10 testing observations.

A StandardScaler was included in the K-Nearest Neighbors pipeline. The scaler was fitted through the training pipeline to avoid using test-set information during training.

### 2.4 Model

Two classification models were trained:

- **K-Nearest Neighbors (KNN):** Used five neighbors and standardized input features.
- **Decision Tree:** Used a decision tree classifier with `random_state=42`.

Both models used the same training and testing split.

### 2.5 Assess

Both models achieved 93.33% accuracy on the 30-observation test set, correctly classifying 28 flowers.

#### KNN results
- Accuracy: 93.33%
- Setosa: 10 of 10 correctly classified
- Versicolor: 10 of 10 correctly classified
- Virginica: 8 of 10 correctly classified

KNN misclassified two virginica flowers as versicolor.

#### Decision Tree results
- Accuracy: 93.33%
- Setosa: 10 of 10 correctly classified
- Versicolor: 9 of 10 correctly classified
- Virginica: 9 of 10 correctly classified

The Decision Tree misclassified one versicolor flower as virginica and one virginica flower as versicolor.

Both models achieved a macro-average F1-score of approximately 0.93. Neither model had higher overall accuracy on this test split.

## 3. Interpretation

The experiment demonstrates that both KNN and Decision Tree can classify the Iris dataset effectively on the selected test set. Setosa was classified correctly by both models for all ten test observations. The remaining errors involved confusion between versicolor and virginica.

The models made different classification errors despite achieving the same overall accuracy. Additional validation, such as cross-validation, would help determine how consistently the models perform on other data splits.

## 4. Limitations

The test set contains only 30 observations, so each prediction has a noticeable effect on the reported accuracy. The results reflect one stratified split and should not be interpreted as a guarantee of performance on all future data.

The project uses the standard Iris dataset loaded through scikit-learn. The notebook should be used to reproduce the actual experiment, while the Kaggle page is provided as a dataset reference.

## 5. Conclusion

This project followed the five SEMMA stages: Sample, Explore, Modify, Model, and Assess. The dataset was inspected, explored, prepared, and used to train two classification models.

KNN and Decision Tree both achieved 93.33% accuracy on the held-out test set. Their confusion matrices showed that setosa was easily distinguished in this experiment, while some confusion remained between versicolor and virginica.

The experiment provides a structured introduction to the SEMMA methodology. Further validation would be needed to assess how reliably the models generalize beyond this test set.

## 6. Project Artifacts

- `SEMMA_Iris_Classification.ipynb` — notebook containing the analysis and executed code
- `report.md` — project report
