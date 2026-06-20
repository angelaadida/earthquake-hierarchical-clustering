# 🌍 Earthquake Clustering — Hierarchical (Agglomerative) Algorithm

Unsupervised machine learning project applying **Hierarchical Clustering** on 782 earthquake records to discover natural groupings in global seismic data using dendrograms and agglomerative clustering.

---

## 🎯 Problem Statement

Group 782 earthquakes (2001–2023) into natural clusters based on seismic features — without predefined labels — using a bottom-up **Agglomerative Clustering** approach.

- **Dataset**: 782 earthquakes (2001–2023), 19 features
- **Algorithm**: Agglomerative Hierarchical Clustering
- **Linkage methods tested**: Ward, Single

---

## 🔄 ML Pipeline

### Step 1: EDA
- Missing value analysis
- Correlation heatmap
- Feature distributions, skewness & kurtosis
- IQR outlier detection

### Step 2: Drop Irrelevant Features
Removed: `title`, `location`, `net`, `date_time`, `country`

### Step 3: Data Preprocessing
- Median imputation for numerical features
- IQR outlier capping
- RobustScaler normalization
- Mode imputation + OneHotEncoding for categorical features (`alert`, `magType`, `continent`)

### Step 4: Dimensionality Reduction
- **PCA** reduced to 2 components for visualization

### Step 5: Dendrogram Analysis
- Generated linkage matrix using **Ward** method
- Identified optimal number of clusters = **2** from dendrogram cut

### Step 6: Agglomerative Clustering & Evaluation

| Linkage | Clusters | Silhouette Score |
|---------|----------|-----------------|
| Ward | 2 | 0.172 |
| **Single** | **2** | **0.228** |

### Step 7: Visualization
- Scatter plot: Magnitude vs Depth colored by cluster
- Centroid markers overlay

---

## 📊 Results

**Best model**: Agglomerative Clustering with `linkage='single'`
- **Silhouette Score: 0.228**
- 2 clusters reveal distinct earthquake groupings by depth and magnitude patterns

---

## 🛠️ Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python |
| Data Analysis | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn, Missingno |
| Preprocessing | Scikit-learn (SimpleImputer, RobustScaler, OneHotEncoder) |
| Dimensionality Reduction | PCA (Scikit-learn) |
| Clustering | AgglomerativeClustering (Scikit-learn) |
| Dendrogram | SciPy (linkage, dendrogram) |
| Evaluation | Silhouette Score |

---

## 🚀 How to Run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy missingno ydata-profiling
```

Open `Hier_Clustering_earthquake_week7_sub.ipynb` in Jupyter Notebook and run all cells.

---

## 📁 Project Structure

```
earthquake-hierarchical-clustering/
│
├── Hier_Clustering_earthquake_week7_sub.ipynb   # Main notebook
├── earthquake_data.csv                           # Dataset
└── README.md
```

---

## 🔗 Related Projects

- [Earthquake Magnitude Regression](https://github.com/angelaadida/earthquake-magnitude-regression)
- [Earthquake KMeans Clustering](https://github.com/angelaadida/earthquake-kmeans-clustering)

---

## 👩‍💻 Author

**Angela** — Data Scientist | AI • ML • GenAI • RAG  
📍 Kuala Lumpur, Malaysia  
🔗 [GitHub](https://github.com/angelaadida)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
