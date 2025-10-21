# AI & ML Internship - Task 2 Submission

**Task:** Exploratory Data Analysis (EDA)
**Dataset:** Iris Dataset

---

## 1. Objective
The objective of this task was to perform Exploratory Data Analysis (EDA) on the Iris dataset. This involves analyzing the data to understand its main characteristics, find patterns, visualize relationships between features, and identify outliers.

## 2. Dataset
The **Iris dataset** was used, as suggested by the task sheet. It was loaded directly from the Seaborn library. This dataset contains 150 samples of 3 different species of Iris flowers (Setosa, Versicolor, and Virginica) and their four measured features:
* Sepal Length (cm)
* Sepal Width (cm)
* Petal Length (cm)
* Petal Width (cm)

## 3. Analysis Steps Performed
As per the task's mini-guide, the following EDA steps were performed:

1.  **Basic Information:** Checked the dataset for null values, data types (`.info()`), and statistical summaries (`.describe()`).
2.  **Categorical Analysis:** A **Count Plot** was generated to visualize the distribution of the three 'species' classes.
3.  **Univariate & Bivariate Analysis:** A **Pairplot** was created.
    * The diagonal shows histograms (univariate) to understand the distribution of each feature.
    * The off-diagonal shows scatter plots (bivariate) to visualize the relationships between pairs of features, colored by species.
4.  **Correlation Analysis:** A **Heatmap** was generated from a correlation matrix to quantify the linear relationship between the four numerical features.
5.  **Outlier & Distribution Analysis:** A series of **Boxplots** were created to compare the distributions of each numerical feature across the three different species and to visually identify any potential outliers.

## 4. Visualizations

Here are the 4 main plots generated during the analysis:

### Plot 1: Categorical Distribution (Count Plot)
This plot shows that the dataset is perfectly balanced, with exactly 50 samples for each of the three species.
![Species Count Plot](iris_species_countplot.png)

### Plot 2: Outlier & Distribution Comparison (Boxplots)
These plots show the distribution for each feature, broken down by species. 'Petal Length' and 'Petal Width' show a clear separation between species. Some outliers are visible in the 'Sepal Width' of the 'Virginica' species.
![Iris Boxplots](iris_boxplots.png)

### Plot 3: Feature Correlation (Heatmap)
This heatmap shows a very strong positive correlation between 'Petal Length' and 'Petal Width' (0.96). 'Sepal Length' also has a strong positive correlation with 'Petal Length' and 'Petal Width'. 'Sepal Width' is the outlier, having a weak negative correlation with other features.
![Correlation Heatmap](iris_correlation_heatmap.png)

### Plot 4: Univariate & Bivariate Analysis (Pairplot)
This plot gives a complete overview. The scatter plots (bivariate) show that the 'Setosa' species (blue) is linearly separable from the other two, especially using 'Petal Length' and 'Petal Width'. The other two species are more clustered together.
![Iris Pairplot](iris_pairplot.png)

## 5. Tools Used
* Python
* Pandas
* Seaborn
* Matplotlib
