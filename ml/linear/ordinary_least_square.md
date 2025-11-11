# Ordinary Least Square (OLS)

##### Linear regression: $ \hat{y} = \beta_0 + \beta_1x $
##### OLS formula:
$$ S(\beta_0,\beta_1) \\\ = \\\ \frac{1}{n} \sum^n_{i=1} (y_i - \hat{y}_i)^2 $$
$S(\beta_0,\beta_1)$ : OLS\
$y_i$ : True output\
$\hat{y}_i$ : Predicted output
---
Derivation of OLS and assigning that derivation with zero
($\frac{\partial{S(\beta_0,\beta_1)}}{\partial{\beta_0}} = 0 \\\ and \\\ \frac{\partial{S(\beta_0,\beta_1)}}{\partial{\beta_1}} = 0$) to reach purpose of OLS:
- Calculate intercept $\beta_0$
- Calculate intercept $\beta_1$

### Implementation:

$$ S(\beta_0,\beta_1) \\\ = \\\ \frac{1}{n} \sum^n_{i=1} (y_i - \hat{y}_i)^2 $$
$$ replace \\\ \hat{y} = \beta_0 + \beta_1x $$
$$ S(\beta_0,\beta_1) \\\ = \\\ \frac{1}{n} \sum^n_{i=1} (y_i - \beta_0 - \beta_1 x_i)^2 $$

### Derivation of OLS for $\beta_0$:

$$ \frac{\partial{S(\beta_0,\beta_1)}}{\partial{\beta_0}} = 0 $$
$$ \frac{1}{n} \sum^n_{i=1}[2 \cdot(y_i - \beta_0 - \beta_1 x_i)] = 0 $$
$$ \frac{1}{n} (\sum^n_{i=1}y_i - \sum^n_{i=1}\beta_0 - \sum^n_{i=1}\beta_1 x_i) = 0 $$
$$  \frac{1}{n}\sum^n_{i=1}\beta_0  = \frac{1}{n}\sum^n_{i=1}y_i - \frac{1}{n}\sum^n_{i=1}\beta_1 x_i $$
$$  \beta_0  = \bar{y} - \beta_1\bar{x_i} \\\ (*) $$

### Derivation of OLS for $\beta_1$:

$$ \frac{\partial{S(\beta_0,\beta_1)}}{\partial{\beta_1}} = 0 $$
$$ \frac{1}{n} \sum^n_{i=1}[2 \cdot(y_i - \beta_0 - \beta_1 x_i) \\\ x_i] = 0 $$
$$ \frac{1}{n} \sum^n_{i=1}(y_i x_i - \beta_0 x_i - \beta_1 x_i^2) = 0 $$
$$ replace \\\ \beta_0  = \bar{y} - \beta_1\bar{x_i} \\\ (*) $$
$$ \frac{1}{n} \sum^n_{i=1}(y_i x_i - (\bar{y} - \beta_1\bar{x_i}) x_i - \beta_1 x_i^2) = 0 $$
$$ \frac{1}{n} \sum^n_{i=1}(y_i x_i - \bar{y}x_i + \beta_1\bar{x_i}x_i  - \beta_1 x_i^2) = 0 $$
$$ \frac{x_i}{n} \sum^n_{i=1}(y_i - \bar{y}) + \frac{x_i}{n}\beta_1 \sum^n_{i=1}(\bar{x_i} - x_i) = 0 $$
$$ \frac{x_i}{n}\beta_1 \sum^n_{i=1}(\bar{x_i} - x_i) = -\frac{x_i}{n} \sum^n_{i=1}(y_i - \bar{y}) $$
$$ \beta_1 \sum^n_{i=1}(\bar{x_i} - x_i) = -\sum^n_{i=1}(y_i - \bar{y}) $$
$$ \beta_1  = \frac{-\sum^n_{i=1}(y_i - \bar{y})}{\sum^n_{i=1}(\bar{x_i} - x_i)} $$
$$ \beta_1  = \sum^n_{i=1}\frac{(\bar{y} - y_i)}{(\bar{x_i} - x_i)} = \sum^n_{i=1}(\bar{y} - y_i)(\bar{x_i} - x_i)^{-1} $$