# Data Cleaning

On this day we are going to explore the data cleaning methods.


### Missings

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



### Outliers

Detecting Outliers (very rare values) are also important. (by plotting a box diagram, clipping the variable by some percentil, etc). The outliers must be removed from the data so that they do not spoil the models. There are also [advanced methods of outlier detection](https://scikit-learn.org/stable/modules/outlier_detection.html) that can be taught.


### find similar words

[fuzzywuzzy](https://github.com/seatgeek/fuzzywuzzy) is a package to find similar strings that usually are typos and errors when the data was written.

---

### Exercises

- Missings
  1. What is the missing datatype used in pandas?
  2. How to replace all occurences of the value 9999 to missing in pandas?
  3. How to get the absolute number of missings for each variable in pandas?
  4. How to get the percentage of missings for each variable in pandas?
  5. How to drop rows with missing values?
  6. How to drop variables with missing values?
  7. What is the univariate imputation method in sklearn?
  8. What is the multivariate imputation method in sklearn?
  9. What is the best univariate imputation method to categorical variables? (Explain why)
  10. What is the best univariate imputation method to numerical variables? (Explain why)


### Solutions

- Missings
  1. np.NaN
  2. df.replace(9999, np.NaN)
  3. df.isnull().sum() or df.isna().sum()
  4. df.isnull().sum() / len(df) or df.isna().sum() / len(df)
  5. df.dropna(axis=0) or df.dropna(axis="index")
  6. df.dropna(axis=1) or df.dropna(axis="columns")
  7. SimpleImputer()
  8. IterativeImputer and KNNImputer
  9. Probably SimpleImputer(strategy="constant", fill_value="missing") because its creates a new category for missings.
  10. Probably SimpleImputer with strategy="mean" or "median" but with add_indicator=True because its creates a new column indicating the missing