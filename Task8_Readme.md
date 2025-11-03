# AI & ML Internship - K-Means Task (Advanced)

**Task:** K-Means Clustering with PCA and Silhouette Score
**Dataset:** Mall Customer Segmentation

---

## 1. Objective
The objective was to perform customer segmentation using K-Means clustering. This task followed a specific guide to include **PCA** for visualization, the **Elbow Method** for finding K, and the **Silhouette Score** for evaluation.

## 2. Dataset & Preprocessing
1.  **Load Data:** The Mall Customer dataset was loaded.
2.  **Feature Selection:** The `Annual Income (k$)` and `Spending Score (1-100)` features were selected.
3.  **Scaling:** Features were scaled using `StandardScaler`, as K-Means is a distance-based algorithm and requires features to be on a uniform scale.

## 3. Steps Performed

### Step 1: Find Optimal K (Elbow Method)
The Elbow Method was used to find the optimal number of clusters. `Inertia_` (WCSS) was calculated for K=1 through K=10. The plot clearly showed an "elbow" at **K=5**, which was chosen as the optimal K.

![Elbow Method Plot](mall_elbow_method.png)

### Step 2: Fit K-Means Model
A K-Means model was trained on the scaled data with `n_clusters=5`. The resulting cluster labels (0-4) were assigned to each customer.

### Step 3: Evaluate (Silhouette Score)
The model was evaluated using the **Silhouette Score**. This score measures how well-separated the clusters are.
* **Result:** The model achieved a **Silhouette Score of 0.5547**. A score closer to +1 is better, and 0.55 is a strong, a high score, indicating that the clusters are dense and well-separated.

### Step 4: Visualize (PCA)
To visualize the 2D clusters, **Principal Component Analysis (PCA)** was used to transform the scaled data into two "Principal Components." These components were then plotted on a scatter plot, with each point colored by its assigned cluster label. This plot clearly shows the five distinct customer segments.

![PCA Cluster Visualization](mall_clusters_pca.png)

## 4. Key Learnings
* The **Elbow Method** (using Inertia) is effective for finding the optimal K.
* The **Silhouette Score** is a powerful metric for evaluating *unsupervised* clustering, as it provides a single number to quantify how good the cluster separation is.
* **PCA** is a useful technique for visualizing high-dimensional data (or, in this case, 2D data) in a way that captures the most variance, making cluster visualization clean.

## 5. Tools Used
* Python
* Pandas
* Scikit-learn (`KMeans`, `StandardScaler`, `PCA`, `silhouette_score`)
* Matplotlib & Seaborn (for visualization)
