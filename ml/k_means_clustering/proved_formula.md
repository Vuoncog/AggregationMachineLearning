$$J = \frac{1}{2}\sum_{i=1}^{k} \left( \frac{1}{n} \sum_{\mathbf{x}_i \in C_j} \sum_{\mathbf{x}_j \in C_j} {||\mathbf{x}_j - \mathbf{x}_j||}_2^2 \right)$$
-

#### With $ \bar{x} = \frac{1}{n} \sum_{i=1}^n \mathbf{x}_i $

$\implies J = \sum_{i=1}^{k} \frac{1}{2n} \sum_{i=1}^n \sum_{l=1}^n ||(\mathbf{x}_i - \bar{x}) - (\mathbf{x}_j - \bar{x})||_2^2$\
$\implies J = \sum_{i=1}^{k} \frac{1}{2n} \sum_{i=1}^n \sum_{l=1}^n \left( ||\mathbf{x}_i - \bar{x}||_2^2 - 2(\mathbf{x}_i - \bar{x})^T(\mathbf{x}_j - \bar{x}) + ||\mathbf{x}_j - \bar{x}||_2^2 \right)$\
$\implies J = \sum_{i=1}^{k} \frac{1}{2n} \left[{\sum_{i=1}^n \sum_{l=1}^n ||\mathbf{x}_i - \bar{x}||_2^2}_{}- {\sum_{i=1}^n \sum_{l=1}^n 2(\mathbf{x}_i - \bar{x})^T(\mathbf{x}_j - \bar{x})}_{}+ {\sum_{i=1}^n \sum_{l=1}^n ||\mathbf{x}_j - \bar{x}||_2^2}_{} \right] $\
$\implies J = \sum_{i=1}^{k} \frac{1}{2n} (n \sum_{i=1}^n ||\mathbf{x}_i - \bar{x}||_2^2 + n \sum_{i=1}^n ||\mathbf{x}_i - \bar{x}||_2^2) $\
$\implies J = \sum_{i=1}^{k} \frac{1}{2n} (n \sum_{i=1}^n ||\mathbf{x}_i - \bar{x}||_2^2 + n \sum_{i=1}^n ||\mathbf{x}_i - \bar{x}||_2^2) $\
$\implies J = \sum_{i=1}^{k} \sum_{i=1}^n ||\mathbf{x}_i - \bar{x}||_2^2$