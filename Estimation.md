## Statistical Inference: Estimation

### 1. Estimation vs. Hypothesis Testing

* **Estimation**: Involves estimating the value of a population parameter using sample data[cite: 150].
    * *Example*: Estimating the population mean ($\mu$) using a sample mean ($\overline{X}$)[cite: 151].
* **Hypothesis Testing**: Involves testing a claim about a population parameter using sample data[cite: 151].
    * *Example*: Testing if the population mean $\mu=50$ based on sample data[cite: 152].

### 2. Estimates and Estimators

* **Estimate**: A specific value derived from sample data that approximates a population parameter[cite: 153].
    * *Example*: The sample mean $\overline{X}=45$ is an estimate of the population mean $\mu$[cite: 159].
* **Estimator**: A rule or formula used to compute an estimate from sample data[cite: 155].
    * *Example*: The formula $\overline{X}$ is an estimator of $\mu$[cite: 156].

### 3. Symbols for Population Parameters and Sample Parameters

| Population Parameters | Sample Parameters |
| :-------------------- | :---------------- |
| $\mu$ - Population mean [cite: 157]  | $\overline{X}$ - Sample mean [cite: 157] |
| $\sigma^2$ - Population variance [cite: 157] | $s^2$ - Sample variance [cite: 157] |
| $\sigma$ - Population standard deviation [cite: 157] | $S$ - Sample standard deviation [cite: 157] |
| $N$ - Population size [cite: 157] | $n$ - Sample size [cite: 157] |

### 4. Point Estimate vs. Interval Estimate

* **Point Estimate**: A single value used to estimate the population parameter[cite: 158].
    * *Example*: The sample mean $\overline{X}=45$ is a point estimate of the population mean $\mu$[cite: 159].
* **Interval Estimate**: A range of values used to estimate the population parameter[cite: 160].
    * *Example*: A 95% confidence interval [40, 50] for the population mean $\mu$[cite: 161].

### 5. Criteria for a Good Estimate

A good estimator should possess the following four properties:

* **Unbiasedness**: An estimator $\hat{\theta}$ is unbiased if its expected value equals the true population parameter $\theta$[cite: 162].
    * $E(\hat{\theta})=\theta$ [cite: 163]
* **Consistency**: An estimator is consistent if, as the sample size 'n' increases, the estimator tends to the true population parameter[cite: 163].
    * $\hat{\theta}_{n}\longrightarrow\theta$ as $n\rightarrow\infty$ [cite: 164]
* **Efficiency**: An efficient estimator has the smallest possible variance among all unbiased estimators[cite: 165].
* **Sufficiency**: An estimator is sufficient if it uses all the information in the sample that is relevant to estimating the parameter[cite: 166].

### 6. Proof of Unbiasedness of Sample Mean and Sample Variance

#### 6.1. Unbiasedness of Sample Mean

Let $X_1, X_2, ..., X_n$ be a random sample drawn from a population with mean $\mu$ and variance $\sigma^2$[cite: 168]. The sample mean is defined as:
$\overline{X}=\frac{1}{n}\sum_{i=1}^{n}X_{i}$ [cite: 169]

To show $E[\overline{X}]=\mu$:
By the linearity of expectation:
$E[\overline{X}]=E[\frac{1}{n}\sum_{i=1}^{n}X_{i}]=\frac{1}{n}\sum_{i=1}^{n}E[X_{i}]$ [cite: 169]
Since $X_1, X_2, ..., X_n$ are i.i.d. with $E[X_i]=\mu$[cite: 170], we get:
$E[\overline{X}]=\frac{1}{n}\cdot n\mu=\mu$ [cite: 170]
Hence, the sample mean is an unbiased estimator of $\mu$[cite: 170].

#### 6.2. Unbiasedness of Sample Variance

Let $X_1, X_2, ..., X_n$ be a random sample drawn from a population with mean $\mu$ and variance $\sigma^2$[cite: 171]. The sample variance is defined as:
$s^{2}=\frac{1}{n-1}\sum_{i=1}^{n}(X_{i}-\overline{X})^{2}$ [cite: 172]

To show $E[s^{2}]=\sigma^{2}$:
First, expand the squared deviations:
$\sum_{i=1}^{n}(X_{i}-\overline{X})^{2}=\sum_{i=1}^{n}(X_{i}-\mu)^{2}-n(\overline{X}-\mu)^{2}$ [cite: 173]
Therefore, the sample variance becomes:
$s^{2}=\frac{1}{n-1}(\sum_{i=1}^{n}(X_{i}-\mu)^{2}-n(\overline{X}-\mu)^{2})$ [cite: 173]

Now, take the expectation of $s^2$:
$E[s^{2}]=\frac{1}{n-1}(E[\sum_{i=1}^{n}(X_{i}-\mu)^{2}]-nE[(\overline{X}-\mu)^{2}])$ [cite: 174]
The first term, $E[\sum_{i=1}^{n}(X_{i}-\mu)^{2}]$, is $n\sigma^{2}$, because $E[(X_{i}-\mu)^{2}]=\sigma^{2}$ for each 'i'[cite: 175].
$E[\sum_{i=1}^{n}(X_{i}-\mu)^{2}]=n\sigma^{2}$ [cite: 175]
The second term, $E[(\overline{X}-\mu)^{2}]$, is the variance of the sample mean, which is $\frac{\sigma^{2}}{n}$[cite: 175].
$E[(\overline{X}-\mu)^{2}]=\frac{\sigma^{2}}{n}$ [cite: 175]

Substituting these into the equation for $E[s^2]$:
$E[s^{2}] = \frac{1}{n-1} [n\sigma^{2} - n \cdot \frac{\sigma^{2}}{n}]$ [cite: 176]
Simplifying:
$E[s^{2}] = \frac{1}{n-1} \cdot (n - 1)\sigma^{2} = \sigma^{2}$ [cite: 176]
Therefore, the sample variance is an unbiased estimator of $\sigma^2$[cite: 176].

### 7. Consistency and Proof for Sample Mean $\overline{X}$

#### 7.1. Definition of Consistency

An estimator $\hat{\theta}_n$ is said to be consistent for a parameter $\theta$ if:
$\hat{\theta}_{n} \xrightarrow{P} \theta$ as $n \rightarrow \infty$ [cite: 179, 181]
This means, for any $\epsilon > 0$, $\lim_{n\rightarrow\infty} P(|\hat{\theta}_n - \theta| > \epsilon) = 0$[cite: 179, 181].
If $E[\hat{\theta}_n] \rightarrow \theta$ and $Var(\hat{\theta}_n) \rightarrow 0$ as $n \rightarrow \infty$, then $\hat{\theta}_n$ is consistent[cite: 179, 181].

#### 7.2. Proof that $\overline{X}$ is a Consistent Estimator of $\mu$

Let $X_1, X_2, ..., X_n$ be i.i.d. random variables with $E[X_i] = \mu$ and $Var(X_i) = \sigma^2$[cite: 183, 184]. The sample mean is $\overline{X} = \frac{1}{n}\sum_{i=1}^{n}X_i$[cite: 184].

**Step 1: Expectation of $\overline{X}$**
$E[\overline{X}] = E[\frac{1}{n}\sum_{i=1}^{n}X_i] = \frac{1}{n}\sum_{i=1}^{n}E[X_i] = \frac{n\mu}{n} = \mu$ [cite: 185]
Thus, $\overline{X}$ is an unbiased estimator of $\mu$[cite: 185].

**Step 2: Variance of $\overline{X}$**
$Var(\overline{X}) = Var(\frac{1}{n}\sum_{i=1}^{n}X_i) = \frac{1}{n^2}\sum_{i=1}^{n}Var(X_i) = \frac{n\sigma^2}{n^2} = \frac{\sigma^2}{n}$ [cite: 186]
As $n \rightarrow \infty$, $Var(\overline{X}) \rightarrow 0$[cite: 186].

**Conclusion**:
Since $E[\overline{X}] = \mu$ and $Var(\overline{X}) \rightarrow 0$ as $n \rightarrow \infty$, $\overline{X}$ is a consistent estimator of $\mu$[cite: 187, 188].

### 8. Efficiency of Estimators

#### 8.1. Definition of Efficiency

An estimator $\hat{\theta}_1$ is said to be more efficient than another estimator $\hat{\theta}_2$ if $Var(\hat{\theta}_1) < Var(\hat{\theta}_2)$[cite: 190, 192].

**Relative Efficiency**:
Relative Efficiency = $\frac{Var(\hat{\theta}_2)}{Var(\hat{\theta}_1)}$ [cite: 190, 192]
A higher relative efficiency implies better performance[cite: 191, 193].

#### 8.2. Example Problem

**Estimator 1**: $\hat{\theta}_1 = \overline{X}$ [cite: 194]
**Estimator 2**: $\hat{\theta}_2 = \frac{X_1 + 2X_2}{3}$ [cite: 194]
Assume $X_1, X_2, ..., X_n$ are i.i.d. with mean $\mu$ and variance $\sigma^2$[cite: 195].

**Solution - Variances**:
$Var(\overline{X}) = \frac{\sigma^2}{n}$ [cite: 196]
$Var(\frac{X_1 + 2X_2}{3}) = \frac{1}{9}(Var(X_1) + Var(2X_2)) = \frac{1}{9}(\sigma^2 + 4\sigma^2) = \frac{5\sigma^2}{9}$ [cite: 196]

**Solution - Efficiency Comparison**:
Since $Var(\overline{X}) = \frac{\sigma^2}{n}$ and $Var(\hat{\theta}_2) = \frac{5\sigma^2}{9}$[cite: 197], $\overline{X}$ has a smaller variance when $n > \frac{9}{5}$[cite: 197]. Thus, $\overline{X}$ is more efficient[cite: 197].

**Relative Efficiency Calculation**:
Relative Efficiency = $\frac{Var(\hat{\theta}_2)}{Var(\overline{X})} = \frac{5\sigma^2/9}{\sigma^2/n} = \frac{5n}{9}$ [cite: 199, 200]
For $n=3$: Relative Efficiency = $\frac{5 \times 3}{9} = \frac{15}{9} = \frac{5}{3} \approx 1.666$[cite: 199, 200].
This means $\overline{X}$ is 1.666 times more efficient than $\hat{\theta}_2$[cite: 199, 200].

### 9. Sufficiency of a Statistic

#### 9.1. Definition of Sufficiency

A statistic $T(X_1, X_2, ..., X_n)$ is called sufficient for a parameter $\theta$ if the conditional distribution of $(X_1, X_2, ..., X_n)$ given $T(X)$ does not depend on $\theta$[cite: 202, 204]. Intuitively, $T(X)$ summarizes all the information about $\theta$[cite: 203, 205].

#### 9.2. Example Problem

**Given**: $f(x; \theta) = \theta x^{\theta-1}$, for $0 < x < 1, \theta > 0$[cite: 206].
**Show that** $T(X) = \sum_{i=1}^{n} \ln X_i$ is a sufficient statistic for $\theta$[cite: 206].

**Solution - Joint PDF**:
Since $X_1, X_2, ..., X_n$ are i.i.d.:
$f(x_1, ..., x_n; \theta) = \prod_{i=1}^{n} \theta x_i^{\theta-1} = \theta^n (\prod_{i=1}^{n} x_i)^{\theta-1} = \theta^n \exp((\theta-1)\sum_{i=1}^{n} \ln x_i)$ [cite: 208]

**Solution - Factorization**:
The joint PDF depends on the sample only through $\sum \ln X_i$[cite: 210]. Thus, $T(X) = \sum \ln X_i$ is sufficient for $\theta$[cite: 211].

#### 9.3. Example: Normal Distribution

**Suppose**: $X_1, X_2, ..., X_n \sim N(\mu, \sigma^2)$, where $\sigma^2$ is known[cite: 212, 215].
**Show that** $\overline{X}$ is a sufficient statistic for $\mu$[cite: 213, 216].

**Solution - Joint PDF**:
The joint PDF is:
$f(x_1, ..., x_n; \mu) = \prod_{i=1}^{n} \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(x_i - \mu)^2}{2\sigma^2}\right)$ [cite: 218]
$= \left(\frac{1}{\sqrt{2\pi\sigma^2}}\right)^n \exp\left(-\frac{1}{2\sigma^2}\sum_{i=1}^{n}(x_i - \mu)^2\right)$ [cite: 218]

**Simplifying the Exponent**:
Expand $\sum(x_i - \mu)^2 = \sum x_i^2 - 2\mu \sum x_i + n\mu^2$[cite: 220].
Thus:
$f(x_1, ..., x_n; \mu) = g(x_1, ..., x_n) \times h(\sum x_i, \mu)$ [cite: 220]
By the Factorization Theorem, $\sum x_i$ (or $\overline{X}$) is sufficient for $\mu$[cite: 220].
**Conclusion**: $\overline{X}$ is sufficient for $\mu$ when $\sigma^2$ is known[cite: 224].

### 10. Bias-Variance Tradeoff and Mean Squared Error (MSE)

#### 10.1. Mean Squared Error (MSE)

The **Mean Squared Error (MSE)** of an estimator $\hat{\theta}$ is a measure of its quality, combining both variance and bias[cite: 226].
$MSE(\hat{\theta}) = E[(\hat{\theta} - \theta)^2]$ [cite: 227]
This can be decomposed as:
$MSE(\hat{\theta}) = Var(\hat{\theta}) + (Bias(\hat{\theta}))^2$ [cite: 230]

* The first term, $E[(\hat{\theta} - E[\hat{\theta}])^2]$, is the variance of the estimator: $Var(\hat{\theta})$[cite: 227].
* The second term, $(E[\hat{\theta}] - \theta)^2$, is the square of the bias of the estimator: $(Bias(\hat{\theta}))^2$[cite: 229].

**Key Points**:
* A good estimator should have both low bias and low variance[cite: 230].
* If the estimator is unbiased, then $MSE(\hat{\theta}) = Var(\hat{\theta})$[cite: 231].

#### 10.2. Bias-Variance Tradeoff

* **Bias**: Error from incorrect model assumptions (high bias = underfitting, low accuracy)[cite: 232]. Accuracy improves as bias decreases[cite: 232].
* **Variance**: Error from model sensitivity to data (high variance = overfitting, low precision)[cite: 232]. Precision improves as variance decreases[cite: 232].

**Model Behavior**:
* **Underfitting**: High bias, low variance $\rightarrow$ poor accuracy, high generalization error[cite: 232].
* **Overfitting**: Low bias, high variance $\rightarrow$ poor precision, unstable predictions[cite: 232].
* **Good Model**: Balanced bias and variance $\rightarrow$ high accuracy and precision[cite: 232].

#### 10.3. Simulation Study Example

**Simulation Results**:
| Estimator | Avg Estimate | True Mean | Variance |
| :-------- | :----------- | :-------- | :------- |
| A         | 10.5         | 10.0      | 1.2      |
| B         | 9.8          | 10.0      | 0.5      |

**Task**:
(a) Calculate Bias and MSE[cite: 233].
(b) Which estimator is preferable? [cite: 234]

**Solution**:
* **Estimator A**:
    * $Bias_A = 10.5 - 10.0 = 0.5$ [cite: 235]
    * $MSE_A = (0.5)^2 + 1.2 = 0.25 + 1.2 = 1.45$ [cite: 235]
* **Estimator B**:
    * $Bias_B = 9.8 - 10.0 = -0.2$ [cite: 235]
    * $MSE_B = (-0.2)^2 + 0.5 = 0.04 + 0.5 = 0.54$ [cite: 235]

**Conclusion**:
Estimator B is more accurate (lower MSE)[cite: 235]. Estimator B is also more precise[cite: 236].