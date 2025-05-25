## Estimation by Confidence Interval

### 1. Interval Estimation

* **Definition**: An interval estimate provides a range of values that is likely to contain the unknown population parameter.
* **Dependence**: The interval depends on the sample data and its sampling distribution.
* **Precision**: Increasing the sample size reduces variability, leading to a shorter, more precise interval.
* **Information Value**: Interval estimates often provide more meaningful information than single-value (point) estimates.

### 2. Confidence Interval (CI)

* **Definition**: A confidence interval estimate of an unknown population parameter $\theta$ is an interval, computed from sample data, that is likely to contain the true value of $\theta$ with a specified level of confidence ($1-\alpha$).
* **Interpretation**: For a 95% CI: "We are 95% confident that this interval contains the true population mean $\mu$."
    * It does *not* mean there's a 95% probability that $\mu$ is in the interval (since $\mu$ is a fixed, unknown value).
    * It means that if we were to take many samples and construct a confidence interval for each, approximately 95% of those computed intervals would contain the true $\mu$.

### 3. General Form of a Confidence Interval

An interval estimate of a population parameter $\theta$ is of the form:
$\hat{\theta}_L < \theta < \hat{\theta}_U$
Where $\hat{\theta}_L$ (lower bound) and $\hat{\theta}_U$ (upper bound) depend on the value of the sample and the sampling distribution of $\hat{\theta}$.

The general formula for a confidence interval is:
**Estimate $\pm$ Margin of Error**

The **Margin of Error (ME)** is calculated as:
$ME = (\text{Critical Value}) \times (\text{Standard Error of the Estimate})$

The **Critical Value** is determined by the desired confidence level (e.g., $Z_{\alpha/2}$ for normal distribution, $t_{\alpha/2}$ for t-distribution).

### 4. Factors Affecting Confidence Interval Width

* **Sample Size ($n$)**: Larger sample sizes lead to smaller standard errors, resulting in narrower (more precise) confidence intervals.
* **Population Standard Deviation ($\sigma$)**: Smaller population standard deviation leads to narrower intervals.
* **Confidence Level ($1-\alpha$)**: Higher confidence levels (e.g., 99% vs. 95%) require a larger critical value, resulting in wider intervals.

### 5. Confidence Interval for the Population Mean ($\mu$)

#### 5.1. When Population Standard Deviation ($\sigma$) is Known

* **Conditions**:
    * Population is normally distributed, OR
    * Sample size $n \ge 30$ (due to Central Limit Theorem).
* **Formula**:
    $\overline{X} \pm Z_{\alpha/2} \cdot \frac{\sigma}{\sqrt{n}}$
    Where:
    * $\overline{X}$ = sample mean
    * $Z_{\alpha/2}$ = Z-score from the standard normal distribution corresponding to the desired confidence level.
    * $\sigma$ = population standard deviation
    * $n$ = sample size

* **Common Z-values**:
    * 90% CI: $Z_{0.05} = 1.645$
    * 95% CI: $Z_{0.025} = 1.96$
    * 99% CI: $Z_{0.005} = 2.575$

* **Example Problem**:
    * **Given**: $\overline{X} = 200$, $\sigma = 12$, $n = 25$, Confidence Level = 95%.
    * **Solution**:
        * $Z_{\alpha/2} = Z_{0.025} = 1.96$
        * CI = $200 \pm 1.96 \cdot \frac{12}{\sqrt{25}} = 200 \pm 1.96 \cdot 2.4 = 200 \pm 4.704$
        * Confidence Interval: $(195.296, 204.704)$
        * *Interpretation*: We are 95% confident that the true mean lifespan of all ball bearings lies between 195.3 and 204.7 hours.

#### 5.2. When Population Standard Deviation ($\sigma$) is Unknown

* **Conditions**:
    * Population is normally distributed, OR
    * Sample size $n \ge 30$.
* **Formula**:
    $\overline{X} \pm t_{\alpha/2, n-1} \cdot \frac{S}{\sqrt{n}}$
    Where:
    * $\overline{X}$ = sample mean
    * $t_{\alpha/2, n-1}$ = t-score from the t-distribution with $n-1$ degrees of freedom corresponding to the desired confidence level.
    * $S$ = sample standard deviation
    * $n$ = sample size

### 6. Confidence Interval for the Population Proportion ($p$)

* **Conditions**:
    * $n \cdot \hat{p} \ge 5$ AND $n \cdot (1-\hat{p}) \ge 5$.
* **Formula**:
    $\hat{p} \pm Z_{\alpha/2} \sqrt{\frac{\hat{p}(1-\hat{p})}{n}}$
    Where:
    * $\hat{p}$ = sample proportion
    * $Z_{\alpha/2}$ = Z-score from the standard normal distribution.
    * $n$ = sample size

### 7. Confidence Interval for the Difference in Two Population Means ($\mu_A - \mu_B$)

#### 7.1. When Population Standard Deviations ($\sigma_A, \sigma_B$) are Known

* **Conditions**:
    * Populations are normally distributed, OR
    * Both sample sizes $n_A \ge 30$ AND $n_B \ge 30$.
* **Formula**:
    $(\overline{X}_A - \overline{X}_B) \pm Z_{\alpha/2} \sqrt{\frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}}$

#### 7.2. When Population Standard Deviations ($\sigma_A, \sigma_B$) are Unknown

* **Formula (General Case)**:
    $(\overline{X}_A - \overline{X}_B) \pm t_{\alpha/2, df} \sqrt{\frac{S_A^2}{n_A} + \frac{S_B^2}{n_B}}$
    Where $df$ is the degrees of freedom, often calculated using the Satterthwaite approximation:
    $df = \frac{\left(\frac{S_A^2}{n_A} + \frac{S_B^2}{n_B}\right)^2}{\frac{(S_A^2/n_A)^2}{n_A-1} + \frac{(S_B^2/n_B)^2}{n_B-1}}$

* **Example Problem**:
    * **Given**:
        * Type A: $\overline{X}_A = 102.5$, $S_A = 4.8$, $n_A = 60$
        * Type B: $\overline{X}_B = 98.1$, $S_B = 5.2$, $n_B = 55$
        * Confidence Level = 99%
    * **Solution (Using Z-distribution approximation due to large sample sizes)**:
        * Mean Difference = $102.5 - 98.1 = 4.4$
        * Standard Error of Difference $\approx \sqrt{\frac{4.8^2}{60} + \frac{5.2^2}{55}} = \sqrt{\frac{23.04}{60} + \frac{27.04}{55}} = \sqrt{0.384 + 0.4916} = \sqrt{0.8756} \approx 0.9357$
        * For 99% CI, $Z_{\alpha/2} = Z_{0.005} = 2.575$
        * CI = $4.4 \pm 2.575 \cdot 0.9357 = 4.4 \pm 2.41$
        * Confidence Interval: $(1.99, 6.81)$
        * *Interpretation*: We are 99% confident that the true difference in mean breaking strengths between Type A and Type B wire is between 1.99 N and 6.81 N.

### 8. Confidence Interval for the Difference in Two Population Proportions ($p_A - p_B$)

* **Conditions**:
    * $n_A \hat{p}_A \ge 5$, $n_A(1-\hat{p}_A) \ge 5$ AND
    * $n_B \hat{p}_B \ge 5$, $n_B(1-\hat{p}_B) \ge 5$.
* **Formula**:
    $(\hat{p}_A - \hat{p}_B) \pm Z_{\alpha/2} \sqrt{\frac{\hat{p}_A(1-\hat{p}_A)}{n_A} + \frac{\hat{p}_B(1-\hat{p}_B)}{n_B}}$

### 9. Determining Sample Size

* **Formula for Sample Size (Mean, $\sigma$ known)**:
    $n = \left( \frac{Z_{\alpha/2} \cdot \sigma}{ME} \right)^2$
    Where $ME$ is the desired margin of error.

* **Formula for Sample Size (Proportion)**:
    $n = \frac{Z_{\alpha/2}^2 \cdot \hat{p}(1-\hat{p})}{ME^2}$
    If no prior estimate of $\hat{p}$ is available, use $\hat{p}=0.5$ for the most conservative (largest) sample size:
    $n = \frac{Z_{\alpha/2}^2 \cdot 0.25}{ME^2}$