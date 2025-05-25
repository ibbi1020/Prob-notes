### Maximum Likelihood Estimation (MLE)

Maximum Likelihood Estimation (MLE) is a method for determining the best estimates for unknown parameters of a model[cite: 1, 2]. It operates on the principle of selecting the parameters that render the observed data most probable[cite: 1, 2].

**Key Concepts:**
* **Introduction**: MLE, introduced by Ronald Fisher in the 1920s, aims to maximize the likelihood of observing the given data[cite: 1].
* **Likelihood Function** ($L(\theta)$): This function represents the joint probability density function (PDF) or probability mass function (PMF) of the observed data, treated as a function of the parameter(s) $\theta$. For independent and identically distributed (i.i.d.) observations $x_1, x_2, ..., x_n$, the likelihood function is given by $L(\theta) = \prod_{i=1}^{n} f(x_i; \theta)$[cite: 1].
* **Interpretation of Likelihood**: The likelihood is not a probability; rather, it indicates the "plausibility" of different parameter values given the observed data. A higher likelihood suggests that the parameter better explains the observed data[cite: 1].

**Properties of MLEs:**
* **Consistent**: As the sample size increases, MLEs converge to the true parameter value[cite: 1].
* **Efficient**: For large sample sizes (asymptotically), MLEs achieve the lowest possible variance[cite: 1].
* **Sufficient**: MLEs often capture all relevant information about the parameter contained within the sample[cite: 1].
* **Not Necessarily Unbiased**: MLEs can be biased, particularly with small sample sizes. For example, the MLE for the variance ($\sigma^2$) of a normal distribution, $\hat{\sigma}^2 = \frac{1}{n}\sum_{i=1}^{n}(X_i-\overline{X})^2$, is biased because it underestimates the true variance (the unbiased estimator uses $n-1$ in the denominator instead of $n$)[cite: 1].

**Procedure for Finding an MLE:**
1.  **Write the likelihood function** $L(\theta)$[cite: 1].
2.  **Take the natural logarithm** to obtain the log-likelihood function $l(\theta)$[cite: 1].
3.  **Differentiate** $l(\theta)$ with respect to $\theta$[cite: 1].
4.  **Set the derivative to zero** ($\frac{dl}{d\theta}=0$) and solve for $\theta$ to find the estimator $\hat{\theta}$[cite: 1].
5.  **Verify maximization** using a second derivative test or other methods[cite: 1].

**Examples:**
* **Geometric Distribution**: For $n$ independent experiments following a geometric distribution with PMF $P(X=x)=(1-p)^{x-1}p$, the MLE of the probability of success, $p$, is $\hat{p} = \frac{n}{S} = \frac{1}{\overline{x}}$, where $S = \sum_{i=1}^{n}x_i$ is the sum of observed trial numbers and $\overline{x}$ is the sample mean[cite: 1].
* **Normal Distribution** ($X_i \sim \mathcal{N}(\mu, \sigma^2)$):
    * **MLE of $\mu$ when $\sigma^2$ is known**: The MLE for the mean ($\mu$) is the sample mean, $\hat{\mu} = \frac{1}{n}\sum_{i=1}^{n}X_i = \overline{X}$[cite: 1].
    * **MLE of $\sigma^2$ when $\mu$ is known**: The MLE for the variance ($\sigma^2$) is $\hat{\sigma}^2 = \frac{1}{n}\sum_{i=1}^{n}(X_i-\mu)^2$[cite: 1].
    * **Joint MLEs of $\mu$ and $\sigma^2$**: When both parameters are unknown, the joint MLEs are $\hat{\mu} = \overline{X}$ and $\hat{\sigma}^2 = \frac{1}{n}\sum_{i=1}^{n}(X_i-\hat{\mu})^2$ (note the divisor $n$, not $n-1$)[cite: 1].
* **Poisson Distribution**: For i.i.d. random variables $X_1, ..., X_n$ from a Poisson distribution with PMF $P(X=k) = \frac{e^{-\lambda}\lambda^k}{k!}$, the MLE of $\lambda$ is the sample mean, $\hat{\lambda} = \overline{x}$[cite: 1].
* **Exponential Distribution**: For i.i.d. random variables $X_1, ..., X_n$ from an exponential distribution with PDF $f(x) = \lambda e^{-\lambda x}$, the MLE of $\lambda$ is $\hat{\lambda} = \frac{1}{\overline{x}}$[cite: 1].