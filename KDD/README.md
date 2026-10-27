# KDD Project — Mall Customer Segmentation

## Project Overview

This project applies the Knowledge Discovery in Databases (KDD) methodology to the Mall Customer Segmentation dataset. K-means clustering is used to identify customer groups based on annual income and spending score.

The project follows all five KDD stages, from selecting and preparing the data to building clusters, interpreting the results, and documenting the findings.

## Research Question

Can customers be grouped into meaningful segments based on annual income and spending score?

## Dataset

**Dataset:** Mall Customer Segmentation Data

**Source:** [Kaggle — Mall Customer Segmentation Data](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)

The dataset contains 200 customer records and five columns:
- CustomerID
- Gender
- Age
- Annual Income (k$)
- Spending Score (1–100)

Annual income and spending score were selected as the clustering features. CustomerID was excluded because it is an identifier, while age and gender were retained in the original dataset but not used to fit the clustering model.

## KDD Methodology

1. **Selection:** Selected the dataset and chose annual income and spending score as the clustering features.
2. **Preprocessing:** Checked missing values, duplicate rows, duplicate customer IDs, and data types.
3. **Transformation:** Standardized the two selected features using scikit-learn's `StandardScaler`.
4. **Data Mining:** Tested K-means models with cluster counts from 2 through 10, comparing inertia and silhouette scores.
5. **Interpretation and Evaluation:** Selected a five-cluster model, examined cluster profiles, visualized the groups, and evaluated the result using the silhouette score.

## Results

The preprocessing checks found:
- 200 customer records.
- No missing values.
- No duplicate rows.
- No duplicate customer IDs.

The final K-means model used five clusters, with `random_state=42` and `n_init=10`.

**Final Silhouette Score:** 0.555.

This was the highest silhouette score among the tested values of 2 through 10 clusters. The elbow plot also supported five clusters as a reasonable choice.

### Customer Segments

| Cluster | Customers | Average annual income (k$) | Average spending score |
|---|---:|---:|---:|
| 0 | 81 | 55.30 | 49.52 |
| 1 | 39 | 86.54 | 82.13 |
| 2 | 22 | 25.73 | 79.36 |
| 3 | 35 | 88.20 | 17.11 |
| 4 | 23 | 26.30 | 20.91 |

The resulting groups represent different combinations of income and spending behavior. These segment descriptions are interpretations of the cluster averages, not labels provided by the original dataset.

The silhouette score indicates reasonably separated groups for the selected features, but it does not prove that five clusters are the only valid solution.

## Project Files

- `KDD_Mall_Customer_Segmentation.ipynb` — Google Colab notebook with the analysis and model outputs.
- [`report.md`](./report.md) — Detailed report covering the KDD stages and results.
- `KDD Medium Article.pdf` — Written article draft.
- [`kdd_mall_customer_clusters.csv`](./kdd_mall_customer_clusters.csv) — Customer records with assigned cluster numbers.

Make sure the filenames match the actual files in this folder.

## AI Critique and Revision

The assignment requires multiple rounds of AI critique and revision. The project should document the feedback received, changes made, and manual verification performed.

- Critique log: link to `ai_critique_log.md` once the review records are complete.
- Document each methodology section reviewed, the critique findings, the revisions made, and any remaining limitations.

## Limitations

- Only annual income and spending score were used for clustering.
- Age and gender were not used as model inputs.
- The model identifies patterns but does not explain why customers spend as they do.
- Results depend on the selected features, scaling, initialization, and cluster count.
- The customer segments have not been validated using real marketing campaigns or business outcomes.

The results should be treated as exploratory findings rather than proof that a particular marketing strategy will work.

## Publication Deliverables

- **Medium article:** Pending publication.
- **YouTube walkthrough:** Pending recording and upload.

Add the public URLs here after publication.

## Conclusion

The KDD process provided a structured approach to selecting, preprocessing, transforming, clustering, and evaluating the Mall Customer Segmentation dataset. The final five-cluster model achieved a silhouette score of 0.555 and identified customer groups with different income and spending patterns.

The results demonstrate how clustering can support exploratory customer segmentation. Further validation with additional behavioral data and real campaign outcomes would be necessary before applying these segments to actual marketing decisions.
