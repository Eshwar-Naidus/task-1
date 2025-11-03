# AI & ML Internship - Task 7 Submission

**Task:** Support Vector Machines (SVM)
**Dataset:** `make_moons` from Scikit-learn

---

## 1. Objective
The objective of this task was to explore the use of Support Vector Machines (SVMs) for both linear and non-linear binary classification. This involved training SVMs with different kernels, visualizing their decision boundaries, and systematically tuning hyperparameters using cross-validation.

## 2. Dataset Preparation
1.  **Load Data:** The `make_moons` dataset was used, as it provides a simple, 2D dataset that is **not linearly separable**.
2.  **Scale Data:** SVMs are highly sensitive to the scale of features. The data was scaled using `StandardScaler` to ensure all features have a mean of 0 and a standard deviation of 1.
3.  **Split Data:** The scaled data was split into training (70%) and testing (30%) sets.

## 3. Steps Performed

### Step 1 & 2: Train Linear vs. RBF Kernel
* An `SVC(kernel='linear')` was trained.
* An `SVC(kernel='rbf')` (Radial Basis Function) was trained.

### Step 3: Visualize Decision Boundaries
The decision boundaries for both models were plotted on the training data.
* The **Linear kernel** tried to find the best *straight line* to separate the "moons," but performed poorly as expected.
* The **RBF kernel** successfully created a *non-linear, curved boundary* that accurately separated the two classes.

| Linear Kernel | RBF Kernel (Default) |
| :---: | :---: |
| ![Linear SVM](svm_with_linear_kernel.png) | ![RBF SVM](svm_with_rbf_kernel_(defaults).png) |

### Step 4: Tune Hyperparameters
To understand the effect of `C` (regularization) and `gamma` (kernel reach), two more models were trained and visualized:
* **Low C, Low gamma (Underfit):** The model created a very smooth, almost linear boundary, failing to capture the moon shape.
* **High C, High gamma (Overfit):** The model created a complex, wiggly boundary, "memorizing" the training data by creating "islands" around individual points.

| Underfit Model (`C=0.1`, `gamma=0.1`) | Overfit Model (`C=100`, `gamma=10`) |
| :---: | :---: |
| ![Underfit SVM](rbf_svm_low_c,_low_gamma_(underfit).png) | ![Overfit SVM](rbf_svm_high_c,_high_gamma_(overfit).png) |

### Step 5: Evaluate using Cross-Validation (GridSearchCV)
* **`GridSearchCV`** was used to systematically test a grid of `C` and `gamma` values.
* It used **5-fold cross-validation** to find the combination with the best average accuracy.
* **Best Parameters Found:** `{'C': 10, 'gamma': 1, 'kernel': 'rbf'}`
* **Best Cross-Validation Score:** `0.9450` (94.5%)
* The final, optimized model was visualized, showing a well-balanced and accurate decision boundary.

![Final Optimized SVM](final_optimized_rbf_svm.png)

## 4. Key Learnings
* SVMs require **scaled data**.
* The `kernel` parameter is key. `linear` is for linear problems, while `rbf` can solve complex, non-linear problems.
* Hyperparameters `C` and `gamma` must be tuned to prevent **overfitting** or **underfitting**.
* **`GridSearchCV`** is the standard, robust method for finding the best hyperparameters.

## 5. Tools Used
* Python
* Scikit-learn (`SVC`, `GridSearchCV`, `StandardScaler`, `make_moons`)
* NumPy
* Matplotlib
