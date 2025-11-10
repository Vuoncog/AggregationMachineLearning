# Coefficient of Determination (R-squared)

R-squared is a probability which determines the relation between dependent values ($y^{i}$) and independent
values ($x^{i}$).

###### Formula

$$R^2 = 1 - \frac{SS_{res}}{SS_{tot}}$$
$SS_{res}$ : Sum of Squares of Residuals \
$SS_{tot}$ : Total Sum of Squares

$$SS_{res} = \sum_{i} (y_i - \hat{y}_i)^2$$
$y_i$ : True output \
$\hat{y}_i$ : Dependent values / Predicted values

$$SS_{tot} = \sum_{i} (y_i - \bar{y})^2$$
$y_i$ : True output \
$\bar{y}_i$ : Means of true output

$$\bar{y} = \frac{1}{m} \sum_{i=1}^{m} y_i$$
$y_i$ : True output \
$m$ : Number of true output

---

### Example Dataset: Study time vs. Score

| $x_1$ :Study time (hour) | $y_i$ :Score |
|:------------------------:|:------------:|
|            1             |      12      |
|            2             |      18      |
|            3             |      31      |
|            4             |      39      |

For example with linear regression model: $\hat{y} = 2.5 + 9x_i$

$$\bar{y} = (12+18+31+39) / 4 = 100 / 4 = 25$$

| $x_i$ :Study time (hour) | $\hat{y} = 2.5 + 9x_1$ | $(y - \hat{y})$ | $SS_{res}$ |
|:------------------------:|:----------------------:|:---------------:|:----------:|
|            12            |          11.5          |       0.5       |    0.25    |
|            18            |          20.5          |      -2.5       |    6.25    |
|            31            |          29.5          |       1.5       |    2.25    |
|            39            |          38.5          |       0.5       |    0.25    |

$SS_{res} = 9.0$\
$SS_{tot}$ = $(12-25)^2 + (18-25)^2 + (31-25)^2 + (39-25)^2= 450 $\
$R^2 = 1 - \frac{SS_{res}}{SS_{tot}} = 1 - \frac{9.0}{450} = 1 - 0.02 = \mathbf{0.980}$

### Add dummy independent values

| $x_1$ :Study time (hour) | $x_2$ : Free time (hour) | $y_i$ :Score |
|:------------------------:|:------------------------:|:------------:|
|            1             |            1             |      12      |
|            2             |            3             |      18      |
|            3             |            2             |      31      |
|            4             |            4             |      39      |

Re-calculate linear regression model with dummy independent: $\hat{y} = 3.6 + 10.2x_1 - 1.6x_2$

| $x_1, x_2$ | $\hat{y} = 3.6 + 10.2x_1 - 1.6x_2$ | $(y - \hat{y})$ | $SS_{res}$ |
|:----------:|:----------------------------------:|:---------------:|:----------:|
|    1, 1    |  $3.6 + 10.2(1) - 1.6(1) = 12.2$   |      -0.2       |    0.04    |
|    2,3     |  $3.6 + 10.2(2) - 1.6(3) = 19.2$   |      -1.2       |    1.44    |
|    3,2     |  $3.6 + 10.2(3) - 1.6(2) = 31.0$   |       0.0       |    0.00    |
|    4,4     |  $3.6 + 10.2(4) - 1.6(4) = 38.0$   |       1.0       |    1.00    |

$SS_{res} = 2.48$\
$R^2 = 1 - \frac{SS_{res}}{SS_{tot}} = 1 - \frac{2.48}{450} \approx 1 - 0.0055 = \mathbf{0.9945}$
###### Conclusion:
R-squared increases when adding any new independent values. In mathetic, model is finding the way
to use new independent values for better fitting, so $SS_{res}$ reduces from 9.0 to 2.48. R-squared is
thinking that this way is making the model better, but it makes model more complex and will be got overfitting.
So <span style="color:green;"><b>Adjusted R-squared</b></span> formula punished independent values that do not
relate to model.
---
# <span style="color:green;"><b>Adjusted R-squared</b></span>
$$R^2_{adjusted} = 1 - \left[ \frac{(1 - R^2)(n - 1)}{n - p - 1} \right]$$
$n$ : Number of rows in dataset \
$p$: Number of independent values / features.
---
### Example Dataset: Study time vs. Score
| $x_1$ :Study time (hour) | $y_i$ :Score |
|:------------------------:|:------------:|
|            1             |      12      |
|            2             |      18      |
|            3             |      31      |
|            4             |      39      |
- n = 4, p = 1 (1 independent value: Study time)
- $R^2 = \mathbf{0.980}$
- $R^2_{adj} = 1 - \left[ \frac{(1 - 0.980)(4 - 1)}{4 - 1 - 1} \right]= 0.970$

### Add dummy independent values
| $x_1$ :Study time (hour) | $x_2$ : Free time (hour) | $y_i$ :Score |
|:------------------------:|:------------------------:|:------------:|
|            1             |            1             |      12      |
|            2             |            3             |      18      |
|            3             |            2             |      31      |
|            4             |            4             |      39      |
- n = 4, p = 2 (2 independent value: Study time, Free time)
- $R^2 = \mathbf{0.9945}$
- $R^2_{adj} = 1 - \left[ \frac{(1 - 0.9945)(4 - 1)}{4 - 2 - 1} \right] = 0.9835$