## Sampling Distribution of the Mean

### 1. What is a Sampling Distribution?
A sampling distribution is the probability distribution of a statistic (such as the mean or variance) derived from numerous samples taken from the same population[cite: 2]. To visualize this, imagine taking many random samples of size 'n' from a population, calculating the mean of each sample, and then plotting all these means. This plot represents the sampling distribution of the sample mean[cite: 3, 4].

### 2. Basic Terminologies of Sampling Distribution

* **Population**: The complete set of individuals or items under study[cite: 6].
* **Sample**: A subset of the population chosen for analysis[cite: 7].
* **Statistic**: A numerical value calculated from a sample (e.g., sample mean $\overline{X}$, sample variance $S^2$)[cite: 8].
* **Parameter**: A numerical value describing a characteristic of the population (e.g., population mean $\mu$, population variance $\sigma^2$)[cite: 9].
* **Sampling Distribution**: The probability distribution of a given statistic based on a random sample[cite: 10].
* **Standard Error (SE)**: The standard deviation of a sampling distribution, which measures the variability of a statistic[cite: 11].
* **Bias**: The difference between the expected value of a statistic and the true value of the parameter[cite: 12].
* **Law of Large Numbers**: As the sample size increases, the sample mean approaches the population mean[cite: 13].

### 3. Example: Sampling Distribution of the Mean

Consider a population: {4, 6, 8} and a sample size of 2 (with replacement)[cite: 15].

**Step 1: All possible samples** [cite: 15]
(4, 4), (4, 6), (4, 8)
(6, 4), (6, 6), (6, 8)
(8, 4), (8, 6), (8, 8)

**Step 2: Calculate Sample Means** [cite: 16]
| Sample | Sample Mean |
| :----- | :---------- |
| (4,4)  | 4           |
| (4,6)  | 5           |
| (4,8)  | 6           |
| (6,4)  | 5           |
| (6,6)  | 6           |
| (6,8)  | 7           |
| (8,4)  | 6           |
| (8,6)  | 7           |
| (8,8)  | 8           |

**Step 3: Frequency Distribution of Sample Means** [cite: 19]
| Sample Mean | Frequency | Probability |
| :---------- | :-------- | :---------- |
| 4           | 1         | $\frac{1}{9}$   |
| 5           | 2         | $\frac{2}{9}$   |
| 6           | 3         | $\frac{3}{9}$   |
| 7           | 2         | $\frac{2}{9}$   |
| 8           | 1         | $\frac{1}{9}$   |

**Step 4: Mean and Variance of Sampling Distribution** [cite: 22]
* **Mean**:
    $\mu_{\overline{x}}=4(\frac{1}{9})+5(\frac{2}{9})+6(\frac{3}{9})+7(\frac{2}{9})+8(\frac{1}{9})=6$ [cite: 22]
* **Variance**:
    $E(\overline{x}^{2})=\frac{336}{9}=37.333$ [cite: 22]
    $\sigma_{\overline{X}}^{2}=Var(\overline{X})=37.333-(6)^{2}=1.333$ [cite: 22]

### 4. Sampling Distribution of Difference of Means

Consider two populations: Population A: {2, 4} and Population B: {5, 7}, with a sample size of 2 for each[cite: 23].

* **Possible sample means**:
    * From A: 2, 3, 3, 4 [cite: 23]
    * From B: 5, 6, 6, 7 [cite: 23]

**Rectangular Table of Differences** [cite: 24]
| $X_A$ | 5   | 6   | 6   | 7   |
| :---- | :-- | :-- | :-- | :-- |
| **2** | -3  | -4  | -4  | -5  |
| **3** | -2  | -3  | -3  | -4  |
| **3** | -2  | -3  | -3  | -4  |
| **4** | -1  | -2  | -2  | -3  |

**Summary of Differences** [cite: 27]
* **Possible differences**: -5, -4, -3, -2, -1 [cite: 27]
* **Frequency table with probabilities**: [cite: 28]
| Difference | Frequency | Probability |
| :--------- | :-------- | :---------- |
| -5         | 1         | $\frac{1}{16}$  |
| -4         | 4         | $\frac{4}{16}=\frac{1}{4}$  |
| -3         | 6         | $\frac{6}{16}=\frac{3}{8}$  |
| -2         | 4         | $\frac{4}{16}=\frac{1}{4}$  |
| -1         | 1         | $\frac{1}{16}$  |
* **Most common difference**: -3 [cite: 29]

**Mean and Variance of Sampling Distribution of Differences** [cite: 30]

* **Mean (Expected Value)**:
    $E(\overline{X}_A - \overline{X}_B) = (-5)(\frac{1}{16}) + (-4)(\frac{4}{16}) + (-3)(\frac{6}{16}) + (-2)(\frac{4}{16}) + (-1)(\frac{1}{16}) = \frac{-5 - 16 - 18 - 8 - 1}{16} = \frac{-48}{16} = -3$ [cite: 30]

* **Variance**:
    First, calculate $E[(\overline{X}_A - \overline{X}_B)^2]$: [cite: 30]
    $E[(\overline{X}_A - \overline{X}_B)^2] = (-5)^2(\frac{1}{16}) + (-4)^2(\frac{4}{16}) + (-3)^2(\frac{6}{16}) + (-2)^2(\frac{4}{16}) + (-1)^2(\frac{1}{16}) = \frac{25 + 64 + 54 + 16 + 1}{16} = \frac{160}{16} = 10$ [cite: 30]
    Then, calculate the variance: [cite: 31]
    $\sigma^2_{\overline{X}_A-\overline{X}_B} = Var(\overline{X}_A - \overline{X}_B) = E[(\overline{X}_A - \overline{X}_B)^2] - (E(\overline{X}_A - \overline{X}_B))^2 = 10 - (-3)^2 = 10 - 9 = 1$ [cite: 31]

### 5. Properties of Sampling Distribution of Mean

* **Mean**: The mean of the sampling distribution of the mean is equal to the population mean, $\mu_{\overline{X}} = \mu$[cite: 32].
    * **Proof**:
        $E(\overline{X}) = E(\frac{1}{n}\sum_{i=1}^{n}X_i)$ [cite: 43]
        $= \frac{1}{n}\sum_{i=1}^{n}E(X_i) = \frac{1}{n} \cdot n \cdot \mu = \mu$ [cite: 44]

* **Variance**: The variance of the sampling distribution is $Var(\overline{X}) = \frac{\sigma^2}{n}$, where $\sigma$ is the population standard deviation[cite: 33].
    * **Proof**:
        $Var(\overline{X}) = Var(\frac{1}{n}\sum_{i=1}^{n}X_i)$ [cite: 45]
        $= \frac{1}{n^2}\sum_{i=1}^{n}Var(X_i) = \frac{1}{n^2} \cdot n \cdot \sigma^2 = \frac{\sigma^2}{n}$ [cite: 46]

* **Standard Error**: The standard error (SE) is $SE = \frac{\sigma}{\sqrt{n}}$[cite: 34].

* **Shape**:
    * If the population is normally distributed, $\overline{X}$ is normal for any sample size 'n'[cite: 47].
    * If the population is not normally distributed, for large 'n' (typically $\ge 30$), $\overline{X}$ is approximately normal[cite: 48].

* **Central Limit Theorem**: The Central Limit Theorem (CLT) holds for all sample sizes when the population is normal, or for large 'n'[cite: 35].

### 6. Properties of Sampling Distribution of Difference of Means

* **Mean**: The mean of the sampling distribution of the difference of means is the difference of population means, $\mu_{\overline{X}_A - \overline{X}_B} = \mu_A - \mu_B$[cite: 37].
* **Variance**: The variance of the sampling distribution of the difference of means is $Var(\overline{X}_A - \overline{X}_B) = \frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}$[cite: 38].
* **Standard Error**: The standard error is $SE(\overline{X}_A - \overline{X}_B) = \sqrt{\frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}}$[cite: 39].
* **Shape**: The sampling distribution of the difference of means approximates a normal distribution as 'n' increases[cite: 40].
* **Central Limit Theorem**: The Central Limit Theorem holds for all sample sizes when the populations are normal, or for large 'n'[cite: 41].

### 7. Central Limit Theorem (CLT)

**Statement**: Let $X_1, X_2, ..., X_n$ be independent and identically distributed (i.i.d.) random variables with mean $\mu$ and variance $\sigma^2$[cite: 51].
Then, the standardized sample mean, $Z = \frac{\overline{X} - \mu}{\sigma/\sqrt{n}}$, approaches a standard normal distribution ($N(0, 1)$) as $n \rightarrow \infty$[cite: 52].

**Proof Sketch (MGF)**:
Define $Y_i = \frac{X_i - \mu}{\sigma}$ and $Z_n = \frac{1}{\sqrt{n}}\sum_{i=1}^{n}Y_i$[cite: 53].
We have $E(Y_i) = 0$ and $Var(Y_i) = 1$[cite: 53].
As $n \rightarrow \infty$, the Moment Generating Function (MGF) of $Z_n$ approaches $e^{t^2/2}$ (the MGF of a $N(0, 1)$ distribution)[cite: 53]. Therefore, $Z_n \rightarrow N(0, 1)$ in distribution[cite: 53].

**Conclusion**:
* The sample mean $\overline{X}$ has an expected value equal to the population mean $\mu$[cite: 55].
* The standard error decreases as the sample size 'n' increases[cite: 55].
* The CLT allows us to assume normality for large 'n' even if the population is not normal[cite: 55].

### 8. Central Limit Theorem Examples

#### 8.1. CLT: One Population – Problem

**Given**: Time to complete a quiz is normally distributed with: [cite: 57]
* Mean $\mu = 30$ minutes [cite: 57]
* Standard deviation $\sigma = 8$ minutes [cite: 57]
* Sample size $n = 36$ [cite: 57]

**Tasks**:
1.  Find $P(\overline{X} < 28)$ [cite: 57]
2.  Find $P(29 < \overline{X} < 31)$ [cite: 57]

**Solution**:
**Step 1: Sampling distribution** [cite: 58]
Standard error of the mean: $\sigma_{\overline{X}} = \frac{\sigma}{\sqrt{n}} = \frac{8}{\sqrt{36}} = \frac{8}{6} \approx 1.33$ [cite: 58]

**Part (i): Find $P(\overline{X} < 28)$**
$Z = \frac{28 - 30}{1.33} \approx -1.50$ [cite: 58]
$P(Z < -1.50) \approx 0.0668$ [cite: 58]

**Part (ii): Find $P(29 < \overline{X} < 31)$**
For $\overline{X} = 29$: $Z_1 = \frac{29 - 30}{1.33} \approx -0.75$ [cite: 58]
For $\overline{X} = 31$: $Z_2 = \frac{31 - 30}{1.33} \approx 0.75$ [cite: 58]
$P(-0.75 < Z < 0.75) = P(Z < 0.75) - P(Z < -0.75) = 0.7734 - 0.2266 = 0.5468$ [cite: 58]

#### 8.2. CLT: Two Populations – Problem

**Given**:
* **School A**: $\mu_A = 75$, $\sigma_A = 10$, $n_A = 40$ [cite: 59]
* **School B**: $\mu_B = 70$, $\sigma_B = 12$, $n_B = 40$ [cite: 59]

**Tasks**:
1.  Find $P(\overline{X}_A - \overline{X}_B > 8)$ [cite: 59]
2.  Find $P(2 < \overline{X}_A - \overline{X}_B < 5)$ [cite: 59]

**Solution**:
Mean of the difference: $\mu_D = \mu_A - \mu_B = 75 - 70 = 5$ [cite: 60]
Standard deviation of the difference: $\sigma_D = \sqrt{\frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}} = \sqrt{\frac{10^2}{40} + \frac{12^2}{40}} = \sqrt{\frac{100}{40} + \frac{144}{40}} = \sqrt{2.5 + 3.6} = \sqrt{6.1} \approx 2.47$ [cite: 60]

**Part (i): Find $P(\overline{X}_A - \overline{X}_B > 8)$**
$Z = \frac{8 - 5}{2.47} \approx 1.215$ [cite: 60]
$P(Z > 1.215) \approx 0.1114$ [cite: 60]

**Part (ii): Find $P(2 < \overline{X}_A - \overline{X}_B < 5)$**
For $(\overline{X}_A - \overline{X}_B) = 2$: $Z_1 = \frac{2 - 5}{2.47} \approx -1.215$ [cite: 60]
For $(\overline{X}_A - \overline{X}_B) = 5$: $Z_2 = \frac{5 - 5}{2.47} = 0$ [cite: 60]
$P(-1.215 < Z < 0) = P(Z < 0) - P(Z < -1.215) = 0.5 - 0.1114 = 0.3886$ [cite: 60]