<h1 align="center">Day 2: Data Cleaning</h1>

On this day we are going to explore the data cleaning methods.


## ❓ Missing values

Missings can appear in different ways. Detect them is very important:
- Null (np.NaN)
- Constant (-1, 0, 99, 999, etc)

Once they have been detected an EDA will be done with libraries as [missingno](https://github.com/ResidentMario/missingno).

And knowing how to deal with missings is very important, the available options are the following:

- Drop them. (Not very recommended for important projects)
  - Drop the rows (samples) where they appear
  - Drop the columns (variables) where they appear
- Imputation
  - Work with SimpleImputer of sklearn (allows imputate by the mean, median, most_frequent & constant)
  - Work with MissingIndicator of sklearn (adds a boolean variable indicating the imputation of another variable)
  - Work with IterativeImputer & KNNImputer (allows stronger methods of imputation based on multivariate models)

Develop an intuition. You should not auomatically drop or impute missings without thinking about them. You need to be couriuos and ask yourself  **Is this value missing because it wasn't recorded or because it doesn't exist?** If a value is missing becuase it doesn't exist (like the height of the oldest child of someone who doesn't have any children) then it doesn't make sense to try and guess what it might be. These values you probably do want to keep as NaN. On the other hand, if a value is missing because it wasn't recorded, then you can try to guess what it might have been based on the other values in that column and row. This is called imputation.



## 🔎 Outliers

Detecting Outliers (very rare values) are also important. The outliers must be removed from the data so that they do not spoil the models.


- **Anomaly detection**: Detecting unusual observations:
  - **Outlier detection**: The training data contains outliers which we are interested in detecting them.
  - **Novelty detection**: The training data does not contains outliers and we are interested in detecting whether a **new** observation is an outlier.

Common **Outliers Detection techniques** are:

- Manual methods of Outlier detection:
  1. Plot the distribution (boxplot, stripplot)
  2. Then clip by:
    - A min value and a max value.
    - Standard Deviation.
    - Percentiles
- [Advanced methods](https://scikit-learn.org/stable/modules/outlier_detection.html) of Outlier detection:
  - Isolation Forest: sklearn.ensemble.IsolationForest
  - Local Outlier Factor: sklearn.neighbors.LocalOutlierFactor
  - Robust covariance: sklearn.covariance.EllipticEnvelope


Once they have been detected, we have to handling them. Common **Handling Outliers methods** are:
- Remove them. Usually the best option.
- Assign a value
  - The max limit
  - The mean
  - Etc.


## 🖋 Typos

At data entry is common to introduce errors. This errors are caled typos. Detect them and correct them is very important.

[fuzzywuzzy](https://github.com/seatgeek/fuzzywuzzy) is a package to find similar strings that usually are typos and errors when the data was written.