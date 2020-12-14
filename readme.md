# Feature Engineering Module

Content for 2 weeks of class (10 days).

<table>
  <!----------------------------------- Week 1 ----------------------------------->
  <tr>
    <th width="200" rowspan="5"><h3>Week 1:<br>Pure Feature Engineering</h3></th>
      <td><a href="#">1. Basic encodings (MinMaxScaler, StandardScaler, Ordinal Encoding, OneHot Encoding, ColumnTransformer)</a></td></tr>
  <tr><td><a href="#">2. Missings & Outliers (Drop vars, impute vars)</a></td></tr>
  <tr><td><a href="#">3. FE for Several tables (manually merge & join, featuretools)</a></td></tr>
  <tr><td><a href="#">4. FE for Time Series (lag features, tsfresh)</a></td></tr>
  <tr><td><a href="#">5. FE for NLP (BoW, TFIDF, N-Grams)</a></td></tr>
  
  <!----------------------------------- Week 2 ----------------------------------->
  <tr>
    <th width="200" rowspan="5"><h3>Week 2:<br>FE applied to ML models</h3></th>
      <td><a href="#">6. Validation strategies (simple split, CrossValidation, Stratification)</a></td></tr>
  <tr><td><a href="#">7. FE for Tree models (Random Forest, Gradient Boosting,...)</a></td></tr>
  <tr><td><a href="#">8. FE for Multiplicative models (linear models, SVM, Neural Networks)</a></td></tr>
  <tr><td><a href="#">9. Advanced encodings (Mean Encoding, BoxCox, QuantileTransformer)</a></td></tr>
  <tr><td><a href="#">10. Kaggle challenge</a></td></tr>
  
</table>




### Day 1: How to encode variables

Exits different ways to encode variables:

- Categorical Variables: Ordinal Encoding, OneHot Encoding, Embedding, ...
- Numerical Variables: MinMaxScaler, StandardScaler (normalization), ...
- Text Variables: BoW, TFIDF

Knowing each one of these encodings is fundamental before creating any model. In addition it is necessary to know which ARE THE BEST CODINGS FOR EACH TYPE OF MODEL for example, for Categorical variables it is better Ordinal enc. for the trees (Random Forest, Boosting), and OneHot for the linear models and neural networks.


### Day 2: Deal with Missings & Outliers

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


Detecting Outliers (very rare values) are also important. (by plotting a box diagram, clipping the variable by some percentil, etc). The outliers must be removed from the data so that they do not spoil the models. There are also [advanced methods of outlier detection](https://scikit-learn.org/stable/modules/outlier_detection.html) that can be taught.



### Day 3: FE for Several tables

Many times we find the data in different tables where they are related to each other by primary and foreign keys (typical storage of relational systems like SQL databases). Knowing how to combine all these data in a single table is a necessary skill to a data scientist.

For practice we will do:
- Manually combine the tables (using the pandas merge or join)
- Use libraries like featuretools



### Day 4: FE for Time Series 

Extracting temporary information when we have a timestamp (a date or date + time) is very important. In this session we work with some temporal dataset to get LAG FEATURES or LAGS.

On this day we also talk about the data leakage because it is very easy to make mistakes and insert data leaks when we extract lags vars.

For practice we will do:
- Manually extract lag features (using the pandas groupby)
- Use libraries like tsfresh



### Day 5: Advanced FE

On this day we explore less known encoding techniques, mainly this day we talk about the Mean encoding (also known as Target encoding).

We also talk about other examples of Feature Engineering like:

- Variable combination (division, multiplication, etc)
  - For example if we have the variable "square meters" and "house price" we can get the variable "price per square meter" for free.
- Variable transformation (root, log, square, BoxCox transformation, ...)
- Work with geo data:
  - For example, if we have cities or locations, extracting coordinates (latitude & longitude) helps a lot.


For practice we will do:
- Do Mean encoding by hand
- Explore [category_encoders](http://contrib.scikit-learn.org/category_encoders/) library
- Apply log and BoxCox to skewed data
