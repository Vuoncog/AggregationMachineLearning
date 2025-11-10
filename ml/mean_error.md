# Mean squared error (MSE)

$$ MSE = \frac{1}{n} \sum^n_{i=1} \\\ (y - \hat{y})^2$$
$n$ : Number of data points\
$y$ : True output\
$\hat{y}$ : Predicted output

|                          Advantages                          |      Disadvantages      |
|:------------------------------------------------------------:|:-----------------------:|
| Have only one **local minima**<br/>and one **global minima** | Not robust to outliners |
|                       Fast Convergence                       |    Not the same unit    |

Not the same **_Unit_**: If one independent value describe about the distance with unit $cm$. Use MAE, the unit will
be $cm^2$.

---

# Mean absolute error (MAE)

$$ MAE = \frac{1}{n} \sum^n_{i=1} \\\ \vert{\\\ y - \hat{y} \\\ \vert}  $$

|     Advantages      |        Disadvantages        |
|:-------------------:|:---------------------------:|
| Robust to outliners | Convergence takes more time |
|    The same unit    |                             |

---

# Root mean squared error (RMAE)

$$ RMSE = \sqrt{MAE} = \sqrt{\frac{1}{n} \sum^n_{i=1} \\\ (y - \hat{y})^2}$$


|    Advantages    |      Disadvantages      |
|:----------------:|:-----------------------:|
| Fast convergence | Not robust to outliners |
|  The same unit   |                         |