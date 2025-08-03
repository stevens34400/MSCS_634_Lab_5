# MSCS_634_Lab_5

## Clustering Lab: Wine Dataset

**Lab Assignment:** Lab 5 - Hierarchical and DBSCAN Clustering

### Overview
This lab explores clustering techniques—Hierarchical (Agglomerative) and DBSCAN—applied to the Wine dataset from `sklearn.datasets`. The objective is to evaluate clustering behavior under different parameter settings, visualize groupings, and compare algorithmic strengths and weaknesses.

### Dataset
- **Source:** Wine dataset from `sklearn.datasets`
- **Features:** 13 wine characteristics including alcohol content, malic acid, ash, magnesium, phenols, etc.
- **Samples:** 178 wine samples
- **Preprocessing:** StandardScaler applied for feature normalization

### Methodology

#### Hierarchical Clustering (Agglomerative)
- **Linkage Method:** Ward
- **Parameters Tested:** n_clusters = [2, 3, 4, 5]
- **Evaluation Metrics:** Silhouette score, homogeneity score, completeness score
- **Visualization:** Dendrogram and PCA-based scatter plots

#### DBSCAN Clustering
- **Parameters Tested:** 
  - eps = [0.3, 0.5, 0.7]
  - min_samples = [5, 10]
- **Evaluation Metrics:** Silhouette score, homogeneity score, completeness score
- **Visualization:** PCA-based scatter plots with noise points highlighted

### Key Findings

#### Optimal Configurations
- **Hierarchical Clustering:** n_clusters = 3 (matches true class count)
  - High homogeneity and completeness scores
  - Solid silhouette score indicating good separation
  - Avoids over-fragmentation

- **DBSCAN:** eps = 0.5, min_samples = 5
  - Best trade-off between cluster quality and noise detection
  - Meaningful density-based clusters
  - Preserves cluster purity while maintaining class cohesion

#### Algorithm Comparison

**Hierarchical Clustering:**
- ✅ Easy to interpret via dendrograms
- ✅ Requires pre-specifying cluster count
- ❌ Not robust to irregular-shaped clusters

**DBSCAN:**
- ✅ Finds arbitrarily shaped clusters
- ✅ Handles noise and outliers
- ✅ No need to specify number of clusters
- ❌ Struggles with varying densities
- ❌ eps parameter tuning is challenging

### Dependencies
- pandas
- numpy
- scikit-learn
- matplotlib
- scipy

### Files
- `Clustering_Lab_Wine.ipynb` - Main Jupyter notebook with analysis
- `README.md` - This documentation file
