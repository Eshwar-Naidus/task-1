# AI & ML Internship - Task 3 Submission

**Task:** Model Training & Evaluation
**Dataset:** Red Wine Quality Dataset

---

## 1. Objective
The goal of this task was to train a simple machine learning model, evaluate its performance using standard classification metrics, and visualize the results.

## 2. Dataset Preparation
The **Red Wine Quality Dataset** (from the UCI repository) was used.
* **Target Variable:** The original 'quality' column (a score from 3 to 8) was converted into a binary classification target called `quality_label`.
    * **0 (Bad):** Quality score <= 5
    * **1 (Good):** Quality score > 5
* **Features:** All other 11 physicochemical columns (e.g., 'alcohol', 'density', 'pH') were used as features (X).
* **Data Split:** The data was split into an 80% training set and a 20% testing set using `train_test_split`.

## 3. Model Training
A **Decision Tree Classifier** (`DecisionTreeClassifier` from scikit-learn) was chosen for this task. The model was trained (`.fit()`) on the 80% training data.

## 4. Model Evaluation
The trained model was used to make predictions on the 20% unseen test data. Its performance was measured using the following metrics:

* **Accuracy:** The percentage of total correct predictions.
* **Precision:** The percentage of *positive* (Good Wine) predictions that were actually correct.
* **Recall:** The percentage of *actual positive* (Good Wine) cases that the model successfully identified.
* **F1-Score:** The harmonic mean of Precision and Recall, providing a single balanced score.

## 5. Visualization: Confusion Matrix
A **Confusion Matrix** was plotted and saved to visualize the model's performance in detail. It shows the counts of:
* **True Positives (TP):** Correctly predicted "Good Wine"
* **True Negatives (TN):** Correctly predicted "Bad Wine"
* **False Positives (FP):** Incorrectly predicted "Good Wine" (Type I Error)
* **False Negatives (FN):** Incorrectly predicted "Bad Wine" (Type II Error)

![Confusion Matrix](wine_confusion_matrix.png)

## 6. Tools Used
* Python
* Pandas
* Scikit-learn (sklearn)
* Matplotlib
