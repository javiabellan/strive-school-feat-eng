




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


```python
encoders = {
  "Min-max scaling":    MinMaxScaler(),
  "Max-abs scaling":    MaxAbsScaler(),
  "Standard scaling":   StandardScaler(),
  "Robust scaling":     RobustScaler(quantile_range=(25, 75)),
  "Box-Cox":            PowerTransformer(method="box-cox"),     # Can only be used for positive values
  "Yeo-Johnson":        PowerTransformer(method="yeo-johnson"), # Similar to Box-cox but can be used for negative values.
  "Quantile (normal)":  QuantileTransformer(n_quantiles=100, output_distribution="normal", random_state=0),
  "Quantile (uniform)": QuantileTransformer(n_quantiles=100, output_distribution="uniform", random_state=0)
}
```

### Feature Generation

- Variable combination (division, multiplication, etc)
  - For example if we have the variable "square meters" and "house price" we can get the variable "price per square meter" for free.
- Variable transformation (root, log, square, BoxCox transformation, ...)


### Exercises

- Apply log and BoxCox to skewed data