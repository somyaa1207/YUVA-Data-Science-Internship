# Week 3 – Unsupervised Learning and Clustering Analysis

## Objective

The objective of Week 3 was to apply unsupervised learning techniques to the cleaned Gurugram real-estate dataset and identify meaningful property segments using clustering.

## Work Completed

- Selected appropriate numerical and categorical features for clustering
- Encoded RERA approval and property status
- Applied log transformation to skewed numerical variables
- Standardized the clustering features using StandardScaler
- Evaluated different values of K using the Elbow Method and Silhouette Score
- Applied K-Means clustering
- Applied Agglomerative Hierarchical Clustering
- Compared both clustering methods using Silhouette Score, Davies-Bouldin Index, and Calinski-Harabasz Score
- Selected K-Means with 4 clusters as the final model
- Visualized clusters using PCA
- Analyzed cluster characteristics using price, area, rate per square foot, BHK count, RERA approval, status, and flat type
- Generated a final clustered dataset and cluster profile

## Final Model

**Algorithm:** K-Means Clustering  
**Number of Clusters:** 4  
**Silhouette Score:** 0.5009  
**Davies-Bouldin Index:** 0.6154  
**Calinski-Harabasz Score:** 6769.66

## Dataset

The cleaned dataset contains 14,223 property records. The final clustering model used 8 features after preprocessing.

## Outputs

- Jupyter Notebook containing the complete analysis
- Final clustered real-estate dataset
- Cluster profile
- Week 3 internship report
