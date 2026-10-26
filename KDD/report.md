# KDD Project Report: Mall Customer Segmentation

## 1. Project Overview

This project applies the Knowledge Discovery in Databases (KDD) process to identify customer segments using the Mall Customer Segmentation dataset. K-means clustering was used to group customers according to annual income and spending score.

**Research question:** Can customers be grouped into meaningful segments based on annual income and spending score?

**Dataset source:** [Kaggle — Mall Customer Segmentation Data](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)

**Dataset size:** 200 customer records and 5 columns.

## 2. Stage 1: Selection

The Mall Customer Segmentation dataset was selected because it includes customer demographics, annual income, and spending score.

The analysis focused on two features:
- Annual Income (k$)
- Spending Score (1–100)

CustomerID was excluded from clustering because it is an identifier rather than a behavioral feature. Age and Gender were retained in the original dataset but not used as clustering inputs.

## 3. Stage 2: Preprocessing

The dataset was inspected for missing values, duplicate rows, duplicate customer IDs, and data types.

Results:
- Missing values: 0 in every column.
- Duplicate rows: 0.
- Duplicate CustomerIDs: 0.
- The dataset contained 200 records.

No record removal or missing-value imputation was necessary based on these checks.

## 4. Stage 3: Transformation

Annual income and spending score were selected as the input features. The features were standardized using `StandardScaler` before applying K-means.

The transformed features had means approximately equal to zero and standard deviations equal to one. Standardization helped put the two features on a comparable scale for clustering.

## 5. Stage 4: Data Mining

K-means clustering was evaluated for values of k from 2 through 10. The elbow method and silhouette score were used to compare candidate cluster counts.

The highest silhouette score among the tested values occurred at **k = 5**, with a score of **0.555**. The elbow plot also showed that inertia decreased less sharply after approximately five clusters.

Based on these results, the final K-means model used five clusters with `random_state=42` and `n_init=10`.

### Cluster sizes and profiles

| Cluster | Customers | Average age | Average annual income (k$) | Average spending score |
|---|---:|---:|---:|---:|
| 0 | 81 | 42.72 | 55.30 | 49.52 |
| 1 | 39 | 32.69 | 86.54 | 82.13 |
| 2 | 22 | 25.27 | 25.73 | 79.36 |
| 3 | 35 | 41.11 | 88.20 | 17.11 |
| 4 | 23 | 45.22 | 26.30 | 20.91 |

### Visual analysis

The scatter plot of annual income versus spending score showed five recognizable groups. Cluster centers were plotted to indicate each group's average location.

The results distinguish customers with relatively high or low income and high or low spending scores, as well as a larger middle group.

## 6. Stage 5: Interpretation and Evaluation

The final model was evaluated using the silhouette score.

- Number of clusters: 5.
- Final silhouette score: 0.555.
- Customers evaluated: 200.

A silhouette score of 0.555 indicates reasonable cluster separation for this dataset. It does not prove that five clusters are the only possible solution, so the result should be interpreted alongside the elbow plot, cluster profiles, and visualization.

### Business interpretation

The clusters suggest several possible customer segments:

- **Cluster 0 — Average income, average spending:** This is the largest group and may benefit from general promotions.
- **Cluster 1 — High income, high spending:** This group could be considered for premium offers or loyalty programs.
- **Cluster 2 — Low income, high spending:** Affordable promotions or targeted discounts could be worth exploring.
- **Cluster 3 — High income, low spending:** Further analysis could investigate why these customers have relatively low spending scores.
- **Cluster 4 — Low income, low spending:** Budget-conscious promotions may be relevant to this group.

These are exploratory interpretations, not proven explanations of customer behavior. Actual marketing decisions would require additional validation.

### Limitations

This project uses only annual income and spending score for clustering. Age and Gender were not included in the model, and the analysis cannot explain why a customer has a particular spending score. K-means also depends on the selected features, scaling method, and number of clusters. Further analysis on additional data would help determine whether these segments remain useful in practice.

## 7. Reproducibility and Deliverables

The project notebook documents the dataset inspection, feature selection, standardization, model comparison, final clustering, and evaluation.

The exported `kdd_mall_customer_clusters.csv` contains the original customer records and their assigned cluster numbers.

Key settings:
- Algorithm: K-means.
- Features: Annual Income (k$) and Spending Score (1–100).
- Candidate cluster counts: 2–10.
- Selected cluster count: 5.
- Random state: 42.
- Initialization setting: `n_init=10`.

## 8. Conclusion

The KDD process was used to prepare and analyze the Mall Customer Segmentation dataset. The final five-cluster model achieved a silhouette score of 0.555 and identified groups with different income and spending patterns.

The findings demonstrate how clustering can support exploratory customer segmentation. The segments offer a starting point for further business analysis, but they should be validated before being used to make real-world marketing decisions.
