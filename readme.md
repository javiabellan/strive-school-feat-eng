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



### Remember ML: Tree models

Models that are based on decisions (if,esle):

- Tree models
  - Decission trees
  - Random Forest
  - Gradient Boosting
- Preprecessing needed:
  - Numerical Variables: Do nothing
  - Categorical Variables: Ordinal Encoding,


### Remember ML: Multiplicative models

- Multiplicative models
  - Linear models
  - SVM
  - Neural Networks
- Preprecessing needed:
  - Numerical Variables: Scaling or Normalization
  - Categorical Variables: OneHot Encoding


### Data Cleaning: Missings

And knowing how to deal with missings is very important, the available options are the following:

- Drop them
  - Drop the rows (samples) where they appear
  - Drop the columns (variables) where they appear
- Imputation
  - Work with SimpleImputer of sklearn (allows imputate by the mean, median, most_frequent & constant)
  - Work with MissingIndicator of sklearn (adds a boolean variable indicating the imputation of another variable)
  - Work with IterativeImputer & KNNImputer (allows stronger methods of imputation based on multivariate models)

### Data Cleaning: Outliers

Detecting Outliers (very rare values) are also important. (by plotting a box diagram, clipping the variable by some percentil, etc). The outliers must be removed from the data so that they do not spoil the models. There are also [advanced methods of outlier detection](https://scikit-learn.org/stable/modules/outlier_detection.html) that can be taught.


### Numerical Encoding

- Scaling
  - MinMaxScaler
  - StandardScaler
- Normalization
  - Log
  - Sqrt
  - BoxCox
  - Jea Jonson
  - Quantile

### Categorical Encoding

- Ordinal Encoding
- OneHot Encoding
- Embedding
- Count Encoding (aka Frequency Encoding)
- Target Encoding (aka Mean Encoding)
- CatBoost Encoding


### Text Encoding

- BoW
- TFIDF
- Ngrams


### Time Series

### Dimensionality Reduction

### Feature selection

### Feature combination




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
