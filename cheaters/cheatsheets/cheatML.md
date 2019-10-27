## Linear regression with one variable

Hypothesis: $h_\theta(x) = \theta_0 + \theta_1x$

Parameters: $\theta_0, \theta_1$

Cost function: $J(\theta_0, \theta_1) = \frac{1}{2m} \sum_{i=1}^m (h_\theta(x^{(i)}) - y^{(i)})^2$

Goal: minimize $J(\theta_0, \theta_1)$

Gradient descent: repeat until convergence
$$\theta_0 := \theta_0 - \alpha \frac 1m \sum_{i=1}^m (h_\theta(x^{(i)}) - y^{(i)})$$

$$\theta_1 := \theta_1 - \alpha \frac 1m \sum_{i=1}^m (h_\theta(x^{(i)}) - y^{(i)}) x^{(i)}$$

update $\theta_0$ and $\theta_1$ simultaneously, term after $\alpha$ is $\frac \delta{\delta \theta}$ of $J(\theta)$

