<h1 align="center">Day 1: Robust ML Pipeline</h1>

Training ML models is easy, but sometimes is a total mess. Following a good methodology help us a lot.


### Encodings

Exits different ways to encode variables:

- Categorical Variables: Ordinal Encoding, OneHot Encoding, Embedding, ...
- Numerical Variables: MinMaxScaler, StandardScaler (normalization), ...
- Text Variables: BoW, TFIDF

Knowing each one of these encodings is fundamental before creating any model. In addition it is necessary to know which ARE THE BEST CODINGS FOR EACH TYPE OF MODEL for example, for Categorical variables it is better Ordinal enc. for the trees (Random Forest, Boosting), and OneHot for the linear models and neural networks.


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




