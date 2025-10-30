# Linear Regression

###### Formula:

$$ h(x) = \theta_0 + \theta_1 x $$
<div style="text-align: center;"><i>or</i></div>

$$
\hat{y} = \beta_0 + \beta_1 x
$$

- $h(x)$, $\hat{y}$ : Dependent variable / Predicted variables
- $x$ : Independent variable
- $\theta_1$, $\beta_1$ : Slope or coefficients
- $\theta_0$, $\beta_0$ : Intercept

---

###### Cost function (Mean Squared Error)

$$
J(\theta_0,\theta_1) = \frac{1}{2m} \sum_{i=1}^{m} \big(h_\theta(x^{(i)}) - y^{(i)}\big)^2
$$

- $h_\theta(x^{(i)})$ : Dependent variable / Predicted variables
- $y^{(i)}$ : Original output value

---

###### Convergence algorithm

$$
\theta_j := \theta_j - \alpha \cdot \frac{\partial}{\partial\theta_j}J(\theta_0,\theta_1)
$$

- $\alpha$ : Learning rate
- $\frac{\partial}{\partial\theta_j}J(\theta_0,\theta_1)$ : Derivative of <i>Cost function</i> $J(\theta_0,\theta_1)$

To optimize the $\theta_0$ and $\theta_1$ to have minimal value of "Cost function", <b>convergence algorithm</b> will
repeat itself until
$\theta_0$ and $\theta_1$ reach the global minima in graph.
![Global minima](https://www.i2tutorials.com/wp-content/media/2019/09/Neural-network-32-i2tutorials.png)
<div style="text-align: center;">Global minima and Local minima</div>

![Global minima](https://miro.medium.com/v2/resize:fit:1200/1*lYpF8xJ3TiDoq461I0AcOQ.jpeg)
<div style="text-align: center;">Gradient descent</div>

###### Formula after derivation

$$
\theta_0 := \frac{1}{m} \sum_{i=1}^{m} (\theta_0 - \alpha \cdot(\theta_0 + \theta_1(x^{(i)}) - (y^{(i)})))
$$

$$
\theta_1 := \frac{1}{m} \sum_{i=1}^{m}( \theta_1 - \alpha \cdot(\theta_0 + \theta_1(x^{(i)}) - (y^{(i)})) \cdot x^{(i)})
$$

---

###### Graph:

![Linear Regression Example](https://www.researchgate.net/publication/381857634/figure/fig1/AS:11431281257626828@1719839742106/Linear-regression-model.png)
