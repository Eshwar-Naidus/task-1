# AI & ML Internship - Task 5 Submission

**Task:** Decision Trees and Random Forests
**Dataset:** Iris Dataset

---

## 1. Objective
The objective of this task was to explore **Decision Tree classifiers**, understand the concept of **overfitting**, use **Random Forests** to improve performance, interpret **feature importances**, and evaluate models robustly using **cross-validation**.

## 2. Dataset
The classic **Iris dataset** was used. It contains 150 samples of 3 species of Iris flowers, with 4 features each (sepal length/width, petal length/width).

## 3. Steps Performed

### Step 1: Train & Visualize a Full Decision Tree
* A standard `DecisionTreeClassifier` was trained on 80% of the data without any constraints on its depth.
* The resulting tree was visualized. It was quite deep (e.g., depth 6), indicating potential overfitting.

![Full Decision Tree](decision_tree_full.png)

### Step 2: Analyze Overfitting & Control Depth
* The full tree achieved **perfect accuracy (1.0)** on the training data but lower accuracy on the unseen test data, confirming **overfitting**.
* A second Decision Tree was trained with `max_depth=3` to limit its complexity (pruning).
* This "pruned" tree showed much closer training and test accuracy, indicating better **generalization**.

![Pruned Decision Tree](decision_tree_pruned.png)

### Step 3: Train Random Forest & Compare Accuracy
* A `RandomForestClassifier` (with 100 trees) was trained on the same data.
* The Random Forest achieved higher accuracy on the test set compared to the single pruned Decision Tree, demonstrating the power of ensemble methods.

### Step 4: Interpret Feature Importances
* The `feature_importances_` attribute was extracted from both the pruned Decision Tree and the Random Forest.
* A bar plot was generated to compare which features each model considered most important.
* Both models strongly agreed that **petal width** and **petal length** are the most decisive features for classifying Iris species.

![Feature Importances Plot](feature_importances.png)

### Step 5: Evaluate using Cross-Validation
* **5-Fold Cross-Validation** was performed on the *entire* dataset for both the pruned Decision Tree and the Random Forest.
* This provided a more reliable estimate of each model's performance on unseen data.
* The results confirmed that the Random Forest not only performs better on average but is also more stable (lower variance in scores across folds).
    * **Decision Tree Mean CV Accuracy:** ~95.33%
    * **Random Forest Mean CV Accuracy:** ~96.00%

## 4. Key Learnings
* Unconstrained Decision Trees can easily **overfit**.
* Limiting `max_depth` is a simple way to **prevent overfitting**.
* **Random Forests** typically outperform single Decision Trees.
* Tree-based models allow for easy interpretation of **feature importance**.
* **Cross-validation** provides a more robust measure of model performance than a single train/test split.

## 5. Tools Used
* Python
* Pandas & NumPy
* Scikit-learn (`DecisionTreeClassifier`, `RandomForestClassifier`, `train_test_split`, `cross_val_score`, `accuracy_score`)
* Matplotlib & Seaborn (for visualization)
