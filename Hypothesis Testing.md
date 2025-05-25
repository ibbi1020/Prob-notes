## Hypothesis Testing

### 1. Basics of Hypothesis Testing Concepts

* **Null Hypothesis ($H_0$)**: Represents the status quo, no effect, or no difference. In machine learning contexts, it often means the baseline model is not better or there's no improvement (e.g., "new model is not better").
* **Alternative Hypothesis ($H_1$ or $H_A$)**: States there is an effect or a difference. This is the claim that a new model or feature improves performance.
* **Test Statistic**: A numerical value (e.g., z-score, t-score) used to test hypotheses. It quantifies the difference in performance metrics (e.g., accuracy gap).
* **P-value**: The probability of observing data as extreme as (or more extreme than) the sample data, assuming the null hypothesis ($H_0$) is true. It indicates how surprising the result is if there's no real difference.
* **Significance Level ($\alpha$)**: A pre-determined threshold for rejecting the null hypothesis (commonly 0.05 or 0.01). It represents the confidence required to claim an improvement is real. If p-value $\le \alpha$, reject $H_0$.

### 2. Types of Errors and Power

* **Type I Error ($\alpha$)**: Rejecting the null hypothesis ($H_0$) when it is actually true (a "false positive"). This means believing a model is better when it's not.
* **Type II Error ($\beta$)**: Failing to reject the null hypothesis ($H_0$) when the alternative hypothesis ($H_1$) is actually true (a "false negative"). This means missing a real improvement.
* **Power of a Test ($1-\beta$)**: The probability of correctly rejecting a false null hypothesis. It measures the sensitivity of the test—its ability to detect a real improvement.

### 3. One-tailed vs. Two-tailed Tests

* **One-tailed Test**: Tests for an effect in one specific direction (e.g., Is the new model better? Is the mean less than a certain value?).
    * Example: $H_0: \mu = \mu_0$ vs. $H_1: \mu < \mu_0$ (left-tailed) or $H_1: \mu > \mu_0$ (right-tailed).
* **Two-tailed Test**: Tests for an effect in either direction (e.g., Is the new model *different*?).
    * Example: $H_0: \mu = \mu_0$ vs. $H_1: \mu \ne \mu_0$.

### 4. Hypothesis Testing for One Population Mean ($\mu$)

#### 4.1. When Population Standard Deviation ($\sigma$) is Known (Z-Test)

* **Test Statistic**:
    $Z = \frac{\overline{X} - \mu_0}{\sigma / \sqrt{n}}$
    Where:
    * $\overline{X}$ = sample mean
    * $\mu_0$ = hypothesized population mean
    * $\sigma$ = population standard deviation
    * $n$ = sample size

* **Example Problem (Type-I Error Calculation)**:
    * **Given**: $H_0: \mu = 15$ vs. $H_1: \mu < 15$, $\sigma = 0.5$, $n = 50$. Critical region: $\overline{X} < 14.9$.
    * **Standard Error (SE)**: $SE = \frac{\sigma}{\sqrt{n}} = \frac{0.5}{\sqrt{50}} \approx 0.0707$
    * **Z-score**: $Z = \frac{14.9 - 15}{0.0707} \approx -1.414$
    * **Type I Error ($\alpha$)**: $P(Z < -1.414) \approx 0.0788$.

* **Example Problem (Type-II Error Calculation)**:
    * **For alternative $\mu = 14.8$**:
        * Critical value $\overline{X}^* = 14.9$.
        * For $\mu = 14.8$, $Z_{14.8} = \frac{14.9 - 14.8}{0.0707} \approx 1.414$
        * **Type II Error ($\beta$)**: $P(Z > 1.414) \approx 0.0788$.
    * **For alternative $\mu = 14.9$**:
        * Critical value $\overline{X}^* = 14.9$.
        * For $\mu = 14.9$, $Z_{14.9} = \frac{14.9 - 14.9}{0.0707} = 0$
        * **Type II Error ($\beta$)**: $P(Z > 0) = 0.5$.

#### 4.2. When Population Standard Deviation ($\sigma$) is Unknown (t-Test)

* **Test Statistic**:
    $t = \frac{\overline{X} - \mu_0}{S / \sqrt{n}}$
    Where:
    * $S$ = sample standard deviation
    * Degrees of freedom ($df$) = $n-1$.

### 5. Hypothesis Testing for One Population Proportion ($p$)

* **Conditions**: $n \cdot p_0 \ge 5$ and $n \cdot (1-p_0) \ge 5$.
* **Test Statistic**:
    $Z = \frac{\hat{p} - p_0}{\sqrt{\frac{p_0(1-p_0)}{n}}}$
    Where:
    * $\hat{p}$ = sample proportion
    * $p_0$ = hypothesized population proportion

### 6. Hypothesis Testing for Two Population Means ($\mu_1 - \mu_2$)

#### 6.1. When Population Standard Deviations ($\sigma_1, \sigma_2$) are Known (Z-Test)

* **Test Statistic**:
    $Z = \frac{(\overline{X}_1 - \overline{X}_2) - (\mu_1 - \mu_2)_0}{\sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}}}$
    (Often, $(\mu_1 - \mu_2)_0 = 0$ for testing equality of means).

* **Example Problem**:
    * **Given**:
        * Model A: $\overline{X}_1 = 84\%$, $\sigma_1 = 4\%$, $n_1 = 40$
        * Model B: $\overline{X}_2 = 86\%$, $\sigma_2 = 3\%$, $n_2 = 40$
        * $H_0: \mu_1 = \mu_2$ ($H_0: \mu_1 - \mu_2 = 0$) vs. $H_1: \mu_1 < \mu_2$ (Model B has higher accuracy than A), $\alpha = 0.01$.
    * **Test Statistic**:
        $Z = \frac{(84 - 86) - 0}{\sqrt{\frac{4^2}{40} + \frac{3^2}{40}}} = \frac{-2}{\sqrt{\frac{16}{40} + \frac{9}{40}}} = \frac{-2}{\sqrt{\frac{25}{40}}} = \frac{-2}{\sqrt{0.625}} \approx \frac{-2}{0.7906} \approx -2.53$
    * **Critical Value**: For a left-tailed test at $\alpha = 0.01$, $Z_{0.01} = -2.33$.
    * **Conclusion**: Since $-2.53 < -2.33$, reject $H_0$.
    * **P-value**: $P(Z < -2.53) \approx 0.0057$. Since $0.0057 < 0.01$, reject $H_0$.
    * *Interpretation*: Removing the feature (Model B) improves the model significantly.

#### 6.2. When Population Standard Deviations ($\sigma_1, \sigma_2$) are Unknown (t-Test)

* **Test Statistic (Unequal Variances - Welch's t-test)**:
    $t = \frac{(\overline{X}_1 - \overline{X}_2) - (\mu_1 - \mu_2)_0}{\sqrt{\frac{S_1^2}{n_1} + \frac{S_2^2}{n_2}}}$
    Degrees of freedom calculated using Satterthwaite approximation.

* **Example Problem**:
    * **Given**:
        * Domain A: $\overline{X}_1 = 90\%$, $S_1 = 3.5\%$, $n_1 = 60$
        * Domain B: $\overline{X}_2 = 88\%$, $S_2 = 4.0\%$, $n_2 = 50$
        * $H_0: \mu_1 = \mu_2$ vs. $H_1: \mu_1 \ne \mu_2$, $\alpha = 0.05$.
    * **Test Statistic**:
        $Z = \frac{(90 - 88) - 0}{\sqrt{\frac{3.5^2}{60} + \frac{4.0^2}{50}}} = \frac{2}{\sqrt{\frac{12.25}{60} + \frac{16}{50}}} = \frac{2}{\sqrt{0.2041 + 0.32}} = \frac{2}{\sqrt{0.5241}} \approx \frac{2}{0.7239} \approx 2.76$
    * **Critical Values**: For a two-tailed test at $\alpha = 0.05$, $Z_{\alpha/2} = Z_{0.025} = \pm 1.96$.
    * **Conclusion**: Since $2.76 > 1.96$, reject $H_0$.
    * **P-value**: $P(|Z| > 2.76) = 2 \cdot P(Z > 2.76) \approx 2 \cdot 0.0029 = 0.0058$. Since $0.0058 < 0.05$, reject $H_0$.
    * *Interpretation*: There is a significant difference in model accuracy between the two domains.

### 7. Hypothesis Testing for Two Population Proportions ($p_1 - p_2$)

* **Conditions**: All $n_1p_1, n_1(1-p_1), n_2p_2, n_2(1-p_2)$ are $\ge 5$.
* **Test Statistic (Pooled Proportion)**:
    $Z = \frac{(\hat{p}_1 - \hat{p}_2) - (p_1 - p_2)_0}{\sqrt{\hat{p}_{pooled}(1-\hat{p}_{pooled})\left(\frac{1}{n_1} + \frac{1}{n_2}\right)}}$
    Where $\hat{p}_{pooled} = \frac{X_1 + X_2}{n_1 + n_2} = \frac{n_1\hat{p}_1 + n_2\hat{p}_2}{n_1 + n_2}$.

## Hypothesis Testing of Linear Regression Parameters

### 1. Simple Linear Regression Model

* **Model**: $Y_i = \beta_0 + \beta_1 X_i + \epsilon_i$
    Where:
    * $Y_i$: Dependent variable for observation $i$.
    * $X_i$: Independent variable for observation $i$.
    * $\beta_0$: Y-intercept (population parameter).
    * $\beta_1$: Slope (population parameter), representing the change in $Y$ for a one-unit change in $X$.
    * $\epsilon_i$: Random error term, assumed to be normally distributed with mean 0 and constant variance $\sigma^2$ ($E[\epsilon_i]=0$, $Var(\epsilon_i)=\sigma^2$).

* **Estimated Regression Line**: $\hat{Y}_i = \hat{\beta}_0 + \hat{\beta}_1 X_i$
    Where $\hat{\beta}_0$ and $\hat{\beta}_1$ are the estimated coefficients from the sample data.

* **Ordinary Least Squares (OLS) Estimators**:
    * $\hat{\beta}_1 = \frac{\sum (X_i - \overline{X})(Y_i - \overline{Y})}{\sum (X_i - \overline{X})^2} = \frac{n\sum X_i Y_i - (\sum X_i)(\sum Y_i)}{n\sum X_i^2 - (\sum X_i)^2}$
    * $\hat{\beta}_0 = \overline{Y} - \hat{\beta}_1 \overline{X}$

* **Residuals**: $e_i = Y_i - \hat{Y}_i$ (the difference between observed and predicted values).

* **Sum of Squares**:
    * **Total Sum of Squares (SST)**: $\sum (Y_i - \overline{Y})^2$
    * **Regression Sum of Squares (SSR)**: $\sum (\hat{Y}_i - \overline{Y})^2$ (explained variation)
    * **Error Sum of Squares (SSE)** or **Residual Sum of Squares (RSS)**: $\sum (Y_i - \hat{Y}_i)^2 = \sum e_i^2$ (unexplained variation)
    * **Relationship**: $SST = SSR + SSE$

* **Mean Square Error (MSE)**: An estimate of the error variance $\sigma^2$.
    $MSE = S_e^2 = \frac{SSE}{n-2}$

### 2. Hypothesis Testing for Regression Coefficients

The most common hypothesis test in linear regression is to test whether the independent variable ($X$) has a significant linear relationship with the dependent variable ($Y$). This is done by testing the slope coefficient $\beta_1$.

* **Hypotheses for $\beta_1$**:
    * **Null Hypothesis ($H_0$)**: $\beta_1 = 0$ (There is no linear relationship between X and Y).
    * **Alternative Hypothesis ($H_1$)**: $\beta_1 \ne 0$ (There is a linear relationship between X and Y). (Can also be one-sided: $\beta_1 > 0$ or $\beta_1 < 0$).

* **Test Statistic**:
    * **t-statistic**:
        $t = \frac{\hat{\beta}_1 - \beta_{1,0}}{S_{\hat{\beta}_1}}$
        Where:
        * $\hat{\beta}_1$: Estimated slope coefficient.
        * $\beta_{1,0}$: Hypothesized value of the slope under $H_0$ (usually 0).
        * $S_{\hat{\beta}_1}$: Standard error of the estimated slope.
    * **Degrees of Freedom (df)**: $n-2$ (for simple linear regression).

* **Standard Error of the Slope ($S_{\hat{\beta}_1}$)**:
    $S_{\hat{\beta}_1} = \frac{S_e}{\sqrt{\sum (X_i - \overline{X})^2}}$
    Where $S_e = \sqrt{MSE} = \sqrt{\frac{SSE}{n-2}}$ is the standard error of the estimate.

* **Example Problem**:
    * **Given**: $n=5$, $\hat{\beta}_1 = 0.5$, $S_{\hat{\beta}_1} = 0.1$, $\alpha = 0.05$.
    * **Hypotheses**: $H_0: \beta_1 = 0$ vs. $H_1: \beta_1 \ne 0$.
    * **Degrees of Freedom**: $df = n-2 = 5-2 = 3$.
    * **Test Statistic**: $t = \frac{0.5 - 0}{0.1} = 5$.
    * **Critical Value**: For $df=3$ and $\alpha=0.05$ (two-tailed), $t_{0.025, 3} = 3.182$.
    * **Conclusion**: Since $|5| > 3.182$, reject $H_0$.
    * *Interpretation*: There is a significant linear relationship between X and Y.

### 3. Hypothesis Testing for the Intercept ($\beta_0$)

* **Hypotheses**:
    * **Null Hypothesis ($H_0$)**: $\beta_0 = 0$
    * **Alternative Hypothesis ($H_1$)**: $\beta_0 \ne 0$

* **Test Statistic**:
    $t = \frac{\hat{\beta}_0 - \beta_{0,0}}{S_{\hat{\beta}_0}}$
    Where $S_{\hat{\beta}_0}$ is the standard error of the estimated intercept.

* **Standard Error of the Intercept ($S_{\hat{\beta}_0}$)**:
    $S_{\hat{\beta}_0} = S_e \sqrt{\frac{1}{n} + \frac{\overline{X}^2}{\sum (X_i - \overline{X})^2}}$

### 4. Multiple Linear Regression

* **Model**: $Y_i = \beta_0 + \beta_1 X_{i1} + \beta_2 X_{i2} + \dots + \beta_p X_{ip} + \epsilon_i$
    Where $p$ is the number of predictor variables.

* **Degrees of Freedom**: $n - (p+1)$ (or $n-k-1$, where $k$ is the number of predictors).

* **Estimate of Variance ($\hat{\sigma}^2$)**:
    $\hat{\sigma}^2 = MSE = \frac{SSE}{n - (p+1)}$
    (Sometimes denoted as $n-p$ if $p$ is the number of parameters including intercept).

* **Standard Error of Coefficients in Multiple Regression ($SE(\hat{\beta}_j)$)**:
    $SE(\hat{\beta}_j) = \sqrt{\hat{\sigma}^2 \cdot [(X^T X)^{-1}]_{jj}}$
    Where $[(X^T X)^{-1}]_{jj}$ is the $j$-th diagonal element of the inverse of the $X^T X$ matrix.

* **Example Problem (Multiple Regression Standard Error)**:
    * **Given**: $n=4$, $p=3$ (meaning 3 parameters: $\beta_0, \beta_1, \beta_2$), $SSE=16$.
    * **Estimate of Variance**: $\hat{\sigma}^2 = \frac{SSE}{n-p} = \frac{16}{4-3} = 16$.
    * **If $[(X^T X)^{-1}]_{11} = 3$ (for $\beta_1$)**:
        * $SE(\hat{\beta}_1) = \sqrt{16 \cdot 3} = \sqrt{48} \approx 6.93$.

### 5. Logistic Regression

* **Purpose**: Used for binary classification (predicting a categorical outcome with two classes, e.g., 0 or 1).
* **Logistic Function (Sigmoid)**:
    $f(z) = \frac{1}{1 + e^{-z}}$
    Where $z = \beta_0 + \beta_1 X_1 + \dots + \beta_p X_p$.
* **Key Properties of Logistic Function**:
    * S-shaped (sigmoid) curve.
    * Output always between 0 and 1 (represents probability).
    * $f(z) \rightarrow 1$ as $z \rightarrow +\infty$, and $f(z) \rightarrow 0$ as $z \rightarrow -\infty$.
    * Symmetric around $z=0: f(0)=0.5$.
* **In Logistic Regression**:
    $P(Y = 1 | X) = \frac{1}{1 + e^{-(\beta_0 + \beta_1 X_1 + \dots + \beta_p X_p)}}$
    This models the probability of the dependent variable being 1 given the independent variables.
* **Transformation (Log-odds or Logit)**:
    $\ln\left(\frac{P(Y=1|X)}{1-P(Y=1|X)}\right) = \beta_0 + \beta_1 X_1 + \dots + \beta_p X_p$
    The left side is the log-odds of $Y=1$, which is a linear function of the independent variables.
* **Interpretation of Coefficients**:
    * $\beta_j$ represents the change in the log-odds of the dependent variable for a one-unit increase in $X_j$, holding other variables constant.
    * For a positive $\beta_j$, as $X_j$ increases, the probability of $Y=1$ increases.
    * For a negative $\beta_j$, as $X_j$ increases, the probability of $Y=1$ decreases.
* **Hypothesis Testing**: Individual coefficients ($\beta_j$) in logistic regression are typically tested using Wald tests, which are z-tests for large samples, or likelihood ratio tests.
    * $H_0: \beta_j = 0$ (variable $X_j$ has no effect on the log-odds of Y).
    * $H_1: \beta_j \ne 0$ (variable $X_j$ has an effect).

The p-values for these tests indicate the statistical significance of each predictor.