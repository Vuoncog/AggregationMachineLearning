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

###### Cost function (Mean Squared Error)

$$
J(\theta_0,\theta_1) = \frac{1}{2m} \sum_{i=1}^{m} \big(h_\theta(x^{(i)}) - y^{(i)}\big)^2
$$

- $h_\theta(x^{(i)})$ : Dependent variable / Predicted variables
- $y^{(i)}$ : Original output value

###### Convergence algorithm

$$
\theta_j := \theta_j - \alpha \cdot \frac{\partial}{\partial\theta_j}J(\theta_0,\theta_1)
$$

- $\alpha$ : Learning rate
- $\frac{\partial}{\partial\theta_j}J(\theta_0,\theta_1)$ : Derivative of <i>Cost function</i> $J(\theta_0,\theta_1)$

To optimize the $\theta_0$ and $\theta_1$ to have minimal value of "Cost function", <b>convergence algorithm</b> will
repeat itself until
$\theta_0$ and $\theta_1$ reach the global minima in graph.

![Global minima](/assets/linear/global_minima.png)
<div style="text-align: center;">Global minima and Local minima</div>

![Global minima](/assets/linear/gradient_descent.jpeg)
<div style="text-align: center;">Gradient descent</div>

###### Formula after derivation

$$
\theta_0 := \frac{1}{m} \sum_{i=1}^{m} (\theta_0 - \alpha \cdot(\theta_0 + \theta_1(x^{(i)}) - (y^{(i)})))
$$

$$
\theta_1 := \frac{1}{m} \sum_{i=1}^{m}( \theta_1 - \alpha \cdot(\theta_0 + \theta_1(x^{(i)}) - (y^{(i)})) \cdot x^{(i)})
$$

###### Graph:

![Linear Regression Example](/assets/linear/simple_linear_regression.png)

---

# Multiple Linear Regression
###### Formula:

$$
h(x) = \theta_0 + \theta_1 x_1 + \theta_2 x_2 + ... + \theta_n x_n
$$
<div style="text-align: center;"><i>or</i></div>

$$
\hat{y} = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + ... + \beta_n x_n 
$$

- $h(x)$, $\hat{y}$ : Dependent variable / Predicted variables
- $x$ : Independent variable
- $\theta$, $\beta$ : Slope or coefficients
- $\theta_0$, $\beta_0$ : Intercept

###### Vector Gradient
$$
\nabla_\theta J(\theta) = \frac{1}{m} X^\top (X\theta - y)
$$

###### Vector Gradient after derivation
$$\theta := \theta - \alpha \nabla J$$
- $\alpha$: Learning rate

###### Normal Equation
$$
\nabla_\theta J(\theta) = \frac{1}{m} X^\top (X\theta - y) (Vector Gradient)
$$
Set $\nabla_\theta J(\theta) = 0$ to find $\theta$ formula
$$
\frac{1}{m} X^\top (X\theta - y) = 0
$$
$$X^T (X \theta - y) = 0$$
$$X^T X \theta - X^T y = 0$$
$$X^T X \theta = X^T y$$
$$\theta = (X^T X)^{-1} X^T y$$

###### Graph
![Linear Regression Example](/assets/linear/multiple_linear_regression.png)


