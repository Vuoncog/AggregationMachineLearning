#### Sigmoid function
$$p = \frac{1}{1+e^{-z}}$$

##### With $z = \mathbf{w}^T \mathbf{x} + b$

---
#### Binary Cross Entropy function
$$L(y, p) = -[y \log(p) + (1-y) \log(1-p)]$$
-

---
#### Replace sigmoid to Binary Cross Entropy function

* #### Handle $\log(p)$
$\log(p) = \log(\frac{1}{1+e^{-z}})$\
$\implies \log(p) = \log(1) - \log(1+e^{-z})$\
$\implies \log(p) = - \log(1+e^{-z})$\

* #### Handle $\log(1-p)$
$1-p = 1-\frac{1}{1+e^{-z}}$\
$\implies 1-p = \frac{(1+e^{-z})-1}{1+e^{-z}}$\
$\implies 1-p = \frac{e^{-z}}{1+e^{-z}}$\
$\implies \log(1-p) = \log(\frac{e^{-z}}{1+e^{-z}})$\
$\implies \log(1-p) = \log(\frac{e^{-z}}{1+e^{-z}})$\
$\implies \log(1-p) = \log(e^{-z})-\log(1+e^{-z})$\
$\implies \log(1-p) = -z-\log(1+e^{-z})$\
$\implies \log(1-p) = -z-\log(1 + \frac{1}{e^z})$\
$\implies \log(1-p) = -z-\log(\frac{e^z+1}{e^z})$\
$\implies \log(1-p) = -z-(\log(e^z+1)-\log(e^z))$\
$\implies \log(1-p) = -z-(\log(e^z+1)-z)$\
$\implies \log(1-p) = \log(e^z+1)$

* ##### Proved:  $\log(1+e^{-z}) = \log(e^z+1)-z$

$L(y, z) = -[y \log(p) + (1-y) \log(1-p)]$\
$\implies L(y, z) = -[y(-\log(1+e^{-z})) + (1-y)(\log(e^z+1))]$\
$\implies L(y, z) = -[y(\log(e^z+1)-z) + (1-y)(\log(e^z+1))]$\
$\implies L(y, z) = -y(\log(e^z+1))-yz - \log(e^z+1) + y(\log(e^z+1))$\
$\implies L(y, z) = -yz - \log(e^z+1)$

* ##### First derivation
$L'(z) = \frac{d}{dz} (\log(1+e^z) - yz)$

Set $u = 1+e^z$\
$\implies \frac{d}{dz} \log(u) = \left( \frac{d}{du} \log(u) \right) \cdot \left( \frac{du}{dz} \right)$\
$\frac{d}{du} \log(u) = \frac{1}{u}$\
$\frac{du}{dz} = \frac{d}{dz} (1+e^z) = 0 + e^z = e^z$

$\implies L'(z) = \frac{e^z}{1+e^z}  - y = p - y$

* ##### Second derivation
$L''(z) = \frac{d}{dz}(\frac{e^z}{1+e^z} - y)$\
$\implies L''(z) = \frac{d}{dz}(\frac{e^z}{1+e^z})$\
$\implies L''(z) = \frac{(e^z)(1+e^z) - (e^z)(e^z)}{(1+e^z)^2}$\
$\implies L''(z) = \frac{e^z + e^{2z} - e^{2z}}{(1+e^z)^2}$\
$\implies L''(z) = \frac{e^z}{(1+e^z)^2}$

#### Because:
- $e^z > 0 \\\ \forall z$
- $(1+e^z)^2 \geq0$

#### $\implies$ Binary Cross Entropy is convex
