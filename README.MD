# AI & ML Internship - Task 1 Submission

**Task:** Data Cleaning & Preprocessing
**Dataset:** Titanic Dataset

---

## Objective

The objective of this task was to clean and prepare the raw Titanic dataset for a machine learning model. This involved implementing a full data preprocessing pipeline as per the internship requirements.

## Preprocessing Steps Performed

As per the task instructions, the following steps were completed using a scikit-learn `Pipeline` and `ColumnTransformer`:

1.  **Import & Explore Data**:
    * Loaded the `Titanic-Dataset.csv` dataset using Pandas.
    * Explored the data using `.info()` and `.head()` to identify data types and missing (null) values.
    * Dropped non-relevant columns: `PassengerId`, `Name`, `Ticket`, and `Cabin` (which had over 75% missing values).

2.  **Handle Missing Values**:
    * A `SimpleImputer` was used for both data types.
    * **Numerical Features (Age, Fare):** Missing values were imputed using the `median`.
    * **Categorical Features (Embarked):** Missing values were imputed using the `most_frequent` (mode).

3.  **Convert Categorical Features (Encoding)**:
    * A `OneHotEncoder` was used to convert categorical columns (`Sex`, `Pclass`, `Embarked`) into numerical format. This is the correct method for nominal data as it avoids implying an ordinal relationship.

4.  **Normalize/Standardize Numerical Features**:
    * A `StandardScaler` was applied to all numerical features (`Age`, `Fare`, `SibSp`, `Parch`) to rescale them to have a mean of 0 and a standard deviation of 1. This is crucial for many ML algorithms.

5.  **Visualize Outliers**:
    * A boxplot for the `Fare` column was generated using Seaborn to visualize the presence of significant outliers. The resulting image (`fare_boxplot.png`) is included in this repository.

## Files in this Repository

* `task'1.pynb`: The Python script containing all the preprocessing code.
* `Titanic-Dataset.csv`: The raw dataset used for the task.
* `fare_boxplot.png`: The saved boxplot visualization for outlier detection.
* `README.md`: This summary file.

## Tools Used

* Python
* Pandas
* NumPy
* Matplotlib / Seaborn
* Scikit-learn
