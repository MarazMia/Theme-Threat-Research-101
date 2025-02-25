This document provides an overview of the methodology and results for clustering analysis performed on a dataset of websites. The analysis includes the selection of the optimal number of clusters, feature reduction, and local explanations for cluster assignments. Below is a summary of the key sections and findings.

Appendix
A. Details on Selecting Number of Clusters (
k
k)
To determine the optimal number of clusters (
k
k) for K-Means, K-Medoids, and Gaussian Mixture Model (GMM) clustering, we employed several evaluation techniques:

Calinski-Harabasz Score:

Used for K-Means and K-Medoids clustering.

The elbow graph (Figure \ref{fig:CalinskiElbow }) suggests that 
k
=
3
k=3 is optimal, as the score decreases significantly beyond this point.

Hierarchical Clustering (Dendrogram):

The dendrogram (Figure \ref{fig:dendrogram }) indicates that a Ward linkage distance of 47.5 splits the data into three clusters (
k
=
3
k=3).

AIC and BIC Scores for GMM:

The elbow graph (Figure \ref{fig:AIC_BIC_elbow }) suggests two possible candidates for 
k
k: 3 and 5.

B. Feature Reduction Based on Pair-Wise Pearson Correlation Coefficient
A feature correlation heatmap (Figure \ref{fig:final_feature_correlation }) was used to identify highly correlated features.

Features with a Pearson correlation coefficient greater than 0.6 were discarded to reduce redundancy and improve model performance.

C. Local SHAP Explanation to Disclose Why Any Individual Website Resides in a Particular Cluster
Local explanations for cluster assignments were generated using SHAP (SHapley Additive exPlanations).

Figure \ref{fig:local_shap_example } provides a waterfall plot for a random instance from cluster 
C
2
C 
2
​
 , showing the contribution of individual features to the cluster assignment.

This visualization helps explain why a specific website was assigned to a particular cluster.

D. Distribution of the VirusTotal (VT) Queried Flags' Count for All Three Clusters
Table \ref{tab:vt_flag_cnt } summarizes the count of four different VT API results for websites in each cluster.

Most websites were not previously observed or reported by vendors, as indicated by the high count of the "Not Found" status.

Due to this limitation, IPQS was used as an alternative lookup method for website analysis.

Figures
Calinski-Harabasz Elbow Graph:

Recommended 
k
=
3
k=3 for K-Means and K-Medoids clustering (Figure \ref{fig:CalinskiElbow }).

Dendrogram for Hierarchical Clustering:

Cutoff point for 
k
=
3
k=3 (Figure \ref{fig:dendrogram }).

AIC and BIC Elbow Graph for GMM:

Recommended 
k
=
3
k=3 or 
5
5 (Figure \ref{fig:AIC_BIC_elbow }).

Feature Correlation Heatmap:

Pairwise Pearson correlation values for feature reduction (Figure \ref{fig:final_feature_correlation }).

Local SHAP Explanation (Waterfall Plot):

Example for a random instance from cluster C_2
​
  (Figure \ref{fig:local_shap_example }).

Key Takeaways
The optimal number of clusters for most methods is 
k
=
3
k=3.

Feature reduction was performed using a Pearson correlation threshold of 0.6.

Local SHAP explanations provide interpretability for cluster assignments.

VirusTotal API results indicated limited prior reporting, prompting the use of IPQS for additional analysis.
