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
![Global minima](https://upload.wikimedia.org/wikipedia/commons/6/68/Extrema_example_original.svg)
<div style="text-align: center;">Global minima and Local minima</div>

![Global minima](https://i.sstatic.net/e4wjp.png)
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

![Linear Regression Example](https://upload.wikimedia.org/wikipedia/commons/3/3a/Linear_regression.svg)
