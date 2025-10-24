# AI & ML Internship - Task 4 Submission

**Task:** K-Means Clustering
**Dataset:** Mall Customer Segmentation Data

---

## 1. Objective
The objective of this task was to implement the **K-Means clustering** algorithm, a form of **unsupervised learning**, to identify distinct segments of mall customers.

## 2. Dataset & Feature Selection
The **Mall Customer Segmentation Data** was used. This dataset contains basic info about customers, including their age, gender, annual income, and spending score.

For this clustering task, two key features were selected:
1.  **`Annual Income (k$)`**
2.  **`Spending Score (1-100)`**

The goal was to group customers based on *how much they earn* vs. *how much they spend*.

## 3. Finding the Optimal K (Elbow Method)
To find the best number of clusters (K), the **Elbow Method** was used.
1.  A K-Means model was trained for each K value from 1 to 10.
2.  The **WCSS** (Within-Cluster Sum of Squares, or `inertia_`) was calculated for each K. WCSS measures how compact the clusters are.
3.  The WCSS values were plotted against K.

The "elbow" of the plot—the point where the drop in WCSS slows down dramatically—is the optimal K. As seen in the plot, this point is **K=5**.

![Elbow Method Plot](mall_elbow_plot.png)

## 4. Model Training & Visualization
A final K-Means model was trained using `K=5`. The algorithm successfully grouped the data into 5 distinct customer segments, which are visualized below.

The **red 'X' markers** represent the final centroids (centers) for each cluster.

![K-Means Clusters](mall_clusters.png)

### Interpreting the Clusters
* **Cluster 0 (e.g., Purple):** High Income, Low Spending (Careful)
* **Cluster 1 (e.g., Orange):** Average Income, Average Spending (Standard)
* **Cluster 2 (e.g., Blue):** Low Income, Low Spending (Frugal)
* **Cluster 3 (e.g., Red):** Low Income, High Spending (Targets?)
* **Cluster 4 (e.g., Green):** High Income, High Spending (Prime Targets)

## 5. Tools Used
* Python
* Pandas
* Scikit-learn (for `KMeans`)
* Matplotlib & Seaborn (for visualization)
