# MSCS 634 – Lab 5
## Clustering Techniques Using DBSCAN and Hierarchical Clustering

### Purpose
This lab compares Agglomerative Hierarchical Clustering and DBSCAN
using the Wine dataset from scikit-learn.

### Data Preparation
The dataset contains 178 samples and 13 numerical features.
Features were standardized using StandardScaler. Known class labels
were used only for evaluation.

PCA was used for visualization, while clustering used all
13 standardized features.

### Experiments
- Ward Hierarchical Clustering with 2–6 clusters.
- DBSCAN with nine eps values and three min_samples values.
- Evaluation using silhouette, homogeneity, and completeness.
- Visualization using PCA scatter plots and a dendrogram.

### Key Insights
Hierarchical Clustering with three clusters produced the highest
silhouette score among the tested hierarchical settings:
approximately 0.2774.

DBSCAN with eps=2.25 and min_samples=5 identified two clusters
and 46 noise points. Its non-noise silhouette score was approximately
0.3371, with coverage of about 74.2%.

Small DBSCAN neighborhoods produced excessive noise, while larger
neighborhoods often merged groups. Increasing min_samples imposed
a stricter density requirement.

### Challenges and Decisions
Standardization was necessary because the features had different
scales. DBSCAN required experimentation with density parameters.

DBSCAN silhouette calculations excluded noise. Undefined silhouette
scores were recorded as NaN. Homogeneity and completeness included
all observations, treating noise as one predicted group.

Coverage was reported because a higher silhouette score on fewer
samples does not necessarily indicate better overall clustering.

The two PCA components explained approximately 55.4% of the variance,
so the plots provide a partial view of the clustering structure.

A notebook NameError was resolved by rerunning the imports before
executing the remaining cells in order.

### Files
- MSCS_634_Lab_5.ipynb: Executed notebook with results and analysis.
- README.md: Lab overview, findings, and implementation decisions.

### How to Run
Install the required packages:

    pip install jupyter numpy pandas matplotlib scipy scikit-learn

Open MSCS_634_Lab_5.ipynb in Jupyter and run all cells from top to bottom.
