# Data Cleaning: Missings

This is the day to explore the most frequent data cleaning methods.

Missings can appear in different ways. Detect them is very important:
- Null (np.NaN)
- Constant (-1, 0, 99, 999, etc)

Once they have been detected an EDA will be done with libraries as [missingno](https://github.com/ResidentMario/missingno).

And knowing how to deal with missings is very important, the available options are the following:

- Drop them
  - Drop the rows (samples) where they appear
  - Drop the columns (variables) where they appear
- Imputation
  - Work with SimpleImputer of sklearn (allows imputate by the mean, median, most_frequent & constant)
  - Work with MissingIndicator of sklearn (adds a boolean variable indicating the imputation of another variable)
  - Work with IterativeImputer & KNNImputer (allows stronger methods of imputation based on multivariate models)
