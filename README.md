# Event-Themed Research: Russia-Ukraine War Case Study
This document provides an overview of the methodology and results for clustering analysis performed on a dataset of websites. The analysis includes the selection of the optimal number of clusters, feature reduction, and local explanations for cluster assignments. Below is a summary of the key sections and findings.

# A. Details on Selecting Number of Clusters (k)
To determine the optimal number of clusters (k), first we utilized our baseline evaluation method from **Silhouette Score** and then for further justification for K-Means, K-Medoids, and Gaussian Mixture Model (GMM) clustering, we employed several evaluation techniques:

**Calinski-Harabasz Score**:

Used for K-Means and K-Medoids clustering.

The elbow graph ([A.1](#calinski-harabasz-elbow-graph)) suggests that k=3 is optimal, as the score decreases significantly beyond this point.

![A.1](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/caliski_elbow.png)

**Hierarchical Clustering (Dendrogram):**

The dendrogram ([A.2](#dendrogram-graph)) indicates that a Ward linkage distance of 47.5 splits the data into three clusters (k=3).
![A.2](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/Dendrogram.png)

**AIC and BIC Scores for GMM:**

The elbow graph ([A.3](#aic-bic-graph)) suggests two possible candidates for k: 3 and 5.
![A.3](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/AIC_BIC.png)

# B. Feature Reduction Based on Pair-Wise Pearson Correlation Coefficient
A feature correlation heatmap ([B.1](#pearson-corr-heatmap)) was used to identify highly correlated features.
Features with a Pearson correlation coefficient greater than 0.6 were discarded to reduce redundancy and improve model performance.
![B.1](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/feature_correlation.png)

# C. Local SHAP Explanation to Disclose Why Any Individual Website Resides in a Particular Cluster
Local explanations for cluster assignments were generated using SHAP (SHapley Additive exPlanations).
Figure ([Local_Exp](#local-exp)) provides a waterfall plot for a random instance from cluster C_2, showing the contribution of
individual features to the cluster assignment. This visualization helps explain why a specific website was assigned to a particular cluster.
![Confusion Matrix](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/supervised_model_cm.png)
![Global Absolute Mean Bar](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/majority_bar.png)
![Global Mean Bar](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/majority_raw_mean_bar.png)
![Local Exp](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/local_shap.png)

# D. Clusters of Domain Names Based on String Match
We also cluster the websites based on the string matching domain name similarity (95% similarity thresholds) which reveals several websites uses same domain name while registering the websites which indicates an attempt from one campaign individual/group just tweaking the top-level domain and keeping the same domain name in all the other websites. Figure ([Domain Name Cluster Only](#domain-name-cluster)) shows some of the same domain names with frequency that were used in different websites. This finding reveals that some triggered words like **help**, **support**, **help**, **aid** were frequently used.
![Domain Name Cluster Only](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/domain_string_cluster.png)

# E. Analysis of Top Level Domain(TLD)
Here, we also provide the TLD level analysis which discloses some patterns. 
![All TLD](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/all_TLD.png)
![Country Level Domai](https://github.com/MarazMia/Theme-Threat-Research-101/blob/main/Russia-Ukraine-War-Theme/ASIA_CCS_Diagrams/cc_TLD.png)

