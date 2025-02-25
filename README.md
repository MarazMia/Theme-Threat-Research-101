# Event-Themed Research: Russia-Ukraine War Case Study
This document provides an overview of the methodology and results for clustering analysis performed on a dataset of websites. The analysis includes the selection of the optimal number of clusters, feature reduction, and local explanations for cluster assignments. Below is a summary of the key sections and findings.

# A. Details on Selecting Number of Clusters (k)
To determine the optimal number of clusters (k), first we utilized our baseline evaluation method from **Silhouette Score** and then for further justification for K-Means, K-Medoids, and Gaussian Mixture Model (GMM) clustering, we employed several evaluation techniques:

**Calinski-Harabasz Score**:

Used for K-Means and K-Medoids clustering.

The elbow graph ([Calinski-Harabasz Elbow Graph](#calinski-harabasz-elbow-graph)) suggests that k=3 is optimal, as the score decreases significantly beyond this point.

![Calinski-Harabasz Elbow Graph](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/caliski_elbow.png)

**Hierarchical Clustering (Dendrogram):**

The dendrogram ([Dendrogram Graph](#dendrogram-graph)) indicates that a Ward linkage distance of 47.5 splits the data into three clusters (k=3).
![Dendrogram Graph](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/Dendrogram.png)

**AIC and BIC Scores for GMM:**

The elbow graph ([AIC-BIC Graph](#aic-bic-graph)) suggests two possible candidates for k: 3 and 5.
![AIC-BIC Graph](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/AIC_BIC.png)

# B. Feature Reduction Based on Pair-Wise Pearson Correlation Coefficient
A feature correlation heatmap ([Pearson's-Corr-Heatmap](#pearson-corr-heatmap)) was used to identify highly correlated features.
Features with a Pearson correlation coefficient greater than 0.6 were discarded to reduce redundancy and improve model performance.
![Pearson's-Corr-Heatmap](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/feature_correlation.png)

# C. Local SHAP Explanation to Disclose Why Any Individual Website Resides in a Particular Cluster
Local explanations for cluster assignments were generated using SHAP (SHapley Additive exPlanations).
Figure ([Local_Exp](#local-exp)) provides a waterfall plot for a random instance from cluster C_2, showing the contribution of
individual features to the cluster assignment. This visualization helps explain why a specific website was assigned to a particular cluster.
![Local Exp](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/local_shap.png)

