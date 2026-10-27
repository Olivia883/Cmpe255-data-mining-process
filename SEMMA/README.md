# SEMMA Project: Iris Classification

## Objective

Apply the SEMMA data mining methodology to the Iris dataset to explore flower measurements, prepare the data, build classification models, and evaluate their ability to predict iris species.

The project compares **K-Nearest Neighbors (KNN)** and a **Decision Tree** classifier using four flower measurements: sepal length, sepal width, petal length, and petal width.

## Dataset

- **Dataset:** Iris dataset
- **Kaggle reference:** https://www.kaggle.com/datasets/uciml/iris
- **Data loading method:** The dataset was loaded using `load_iris(as_frame=True)` from scikit-learn. The Kaggle page is provided as a dataset reference; the Kaggle CSV was not directly downloaded for this experiment.
- **Number of records:** 150
- **Number of columns:** 5
- **Target variable:** Iris species
- **Classes:** Setosa, Versicolor, and Virginica

## Methodology: SEMMA

### 1. Sample

Loaded the Iris dataset and examined its structure. The dataset contains 150 observations, with 50 samples for each of the three iris species.

The data was divided into training and testing sets using an 80/20 split, with stratification to preserve the class proportions.

- Training records: 120
- Testing records: 30
- Random state: 42

### 2. Explore

Examined the dataset's column names, data types, descriptive statistics, class distribution, and average measurements by species.

No missing values were found. Visual exploration using a pairplot showed that Setosa is relatively easy to distinguish using petal measurements, while Versicolor and Virginica have some overlapping measurements.

### 3. Modify

Selected the four numerical flower measurements as model features and the species as the target.

For KNN, a pipeline applied `StandardScaler` before classification because KNN is sensitive to differences in feature scales. The Decision Tree model was trained using the same selected features and training/testing split.

### 4. Model

Built and evaluated two classification models:

- **K-Nearest Neighbors (KNN):** `KNeighborsClassifier(n_neighbors=5)` with feature standardization.
- **Decision Tree:** `DecisionTreeClassifier(random_state=42)`.

Both models used the same training/testing split to support a fair comparison.

### 5. Assess

Both models achieved **93.33% test accuracy**, correctly classifying 28 of the 30 test observations.

| Evaluation measure | KNN | Decision Tree |
|---|---:|---:|
| Test accuracy | 93.33% | 93.33% |
| Correct predictions | 28/30 | 28/30 |
| Incorrect predictions | 2/30 | 2/30 |

The KNN model correctly classified all Setosa and Versicolor test samples but misclassified two Virginica samples as Versicolor. The Decision Tree correctly classified all Setosa samples and misclassified one Versicolor sample as Virginica and one Virginica sample as Versicolor.

The results show that both models performed well on this test split. However, the small dataset and single train/test split limit how broadly these results can be generalized.

## Project Files

- **Google Colab notebook:** [`SEMMA_Iris_Classification.ipynb`](SEMMA_Iris_Classification.ipynb)
- **Project report:** [`report.md`](report.md)
- **Article draft PDF:** See the SEMMA folder for the PDF version of the Medium article draft.
- **Dataset reference:** https://www.kaggle.com/datasets/uciml/iris

## AI Critique and Revision

The assignment requires AI-assisted critique and multiple revisions for each methodology section. Critiques and revisions must be performed and documented before this requirement can be marked complete.

The review record should include:

- The section reviewed and its initial version.
- The prompt used to request an expert critique of SEMMA.
- The feedback received.
- The changes made in response.
- Any feedback that was not adopted and the reason.

**Status:** Add links to the completed critique-and-revision records after the review rounds have been conducted and documented.

## Publication Deliverables

- **Medium article:** Draft prepared; publication link to be added after the article is published.
- **YouTube walkthrough:** Record and publish a detailed walkthrough of the notebook, SEMMA stages, model training, evaluation results, and limitations. Add the video link after publication.

## Limitations

- The evaluation uses a single stratified 80/20 train/test split.
- The test set contains only 30 observations, so individual predictions can noticeably affect the accuracy.
- The Kaggle dataset page is used as a reference; the experiment loads the Iris data from scikit-learn.
- The results demonstrate performance on this experiment's test set and do not guarantee the same performance on other datasets.

## Conclusion

This project applies all five SEMMA stages to an Iris classification task. KNN and Decision Tree each achieved 93.33% test accuracy, providing a useful comparison of two classification approaches. The notebook and report document the workflow, results, and limitations. The remaining publication and AI critique deliverables should be linked here once completed.
