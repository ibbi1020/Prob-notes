## Logistic Regression

Logistic Regression is a statistical model used for binary classification tasks, predicting the probability of a categorical outcome (typically 0 or 1).

### 1. Sigmoid Function and its Basic Properties

* **Definition**: The sigmoid (or logistic) function, denoted by $\sigma(z)$, transforms any real-valued number into a probability between 0 and 1.
    $\sigma(z) = \frac{1}{1 + e^{-z}}$

* **Key Properties**:
    * **Range**: The output of the sigmoid function is always between 0 and 1: $0 < \sigma(z) < 1$ for all real $z$.
    * **Symmetry**: It exhibits symmetry around the origin: $\sigma(-z) = 1 - \sigma(z)$.
        * *Proof*:
            $\sigma(-z) = \frac{1}{1 + e^{-(-z)}} = \frac{1}{1 + e^{z}}$
            $1 - \sigma(z) = 1 - \frac{1}{1 + e^{-z}} = \frac{(1 + e^{-z}) - 1}{1 + e^{-z}} = \frac{e^{-z}}{1 + e^{-z}} = \frac{1/e^z}{1 + 1/e^z} = \frac{1}{e^z + 1}$
            Thus, $\sigma(-z) = 1 - \sigma(z)$.
    * **Derivative**: The derivative of the sigmoid function is: $\frac{d}{dz}\sigma(z) = \sigma(z)(1-\sigma(z))$.
    * **Inverse (Logit Function)**: The inverse of the sigmoid function is the logit function, which transforms a probability $p$ back to a real number $z$:
        If $p = \sigma(z)$, then $z = \ln\left(\frac{p}{1-p}\right)$. This is known as the **log-odds**.

### 2. From Linear to Logistic Regression

* **Challenge with Linear Regression for Classification**: Using linear regression for a binary outcome (0 or 1) can lead to predictions outside the [0, 1] range, which are meaningless for probabilities. A threshold is then needed to classify, but the linear relationship doesn't naturally model probability.
* **The Link Function**: Logistic regression uses a non-linear transformation (the sigmoid function) to link the linear combination of predictors to the probability of the outcome.
    * The linear predictor: $z = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \dots + \beta_p X_p$
    * The probability: $P(Y=1|X) = \sigma(z) = \frac{1}{1 + e^{-(\beta_0 + \beta_1 X_1 + \dots + \beta_p X_p)}}$

### 3. Log-Odds Interpretation

* The core idea of logistic regression is to model the **log-odds** of the event occurring as a linear function of the predictors.
    $\ln\left(\frac{P(Y=1|X)}{1-P(Y=1|X)}\right) = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + \dots + \beta_p X_p$
    Where:
    * $\frac{P(Y=1|X)}{1-P(Y=1|X)}$ is the **odds** of $Y=1$.
    * The left side is the **log-odds** or **logit** of $Y=1$.

* **Interpretation of Coefficients ($\beta_j$)**:
    * $\beta_j$ represents the change in the **log-odds** of the dependent variable (Y=1) for a one-unit increase in the independent variable $X_j$, assuming all other variables are held constant.
    * If $\beta_j > 0$, an increase in $X_j$ leads to an increase in the probability of $Y=1$.
    * If $\beta_j < 0$, an increase in $X_j$ leads to a decrease in the probability of $Y=1$.
    * If $\beta_j = 0$, $X_j$ has no effect on the log-odds (and thus probability) of $Y=1$.
    * Exponentiating $\beta_j$ ($e^{\beta_j}$) gives the **odds ratio**, which is the factor by which the odds change for a one-unit increase in $X_j$.

### 4. Estimating Parameters: Maximum Likelihood Estimation (MLE)

* Unlike linear regression which uses Ordinary Least Squares (OLS), logistic regression parameters ($\beta$ coefficients) are estimated using Maximum Likelihood Estimation.
* **Likelihood Function**: For $n$ independent observations $(X_i, Y_i)$, where $Y_i \in \{0, 1\}$ and $P(Y_i=1|X_i) = p_i = \sigma(\beta_0 + \beta_1 X_i)$, the likelihood function is:
    $L(\beta_0, \beta_1, \dots, \beta_p) = \prod_{i=1}^{n} p_i^{Y_i} (1-p_i)^{1-Y_i}$

* **Log-Likelihood Function**: It's typically easier to maximize the natural logarithm of the likelihood function:
    $\ell(\beta_0, \dots, \beta_p) = \ln(L(\beta_0, \dots, \beta_p)) = \sum_{i=1}^{n} [Y_i \ln(p_i) + (1-Y_i) \ln(1-p_i)]$
    Substituting $p_i = \sigma(z_i)$ and $1-p_i = 1-\sigma(z_i) = \sigma(-z_i)$ where $z_i = \beta_0 + \beta_1 X_i$:
    $\ell(\beta_0, \dots, \beta_p) = \sum_{i=1}^{n} [Y_i \ln(\sigma(z_i)) + (1-Y_i) \ln(\sigma(-z_i))]$
    Using the property $\ln(\sigma(z)) = \ln(1/(1+e^{-z})) = -\ln(1+e^{-z})$ and $\ln(\sigma(-z)) = -\ln(1+e^{z})$
    A common form derived in the slides is:
    $\ell(\beta_0, \beta_1) = \sum_{i=1}^{n} [Y_i z_i - \ln(1 + e^{z_i})]$, where $z_i = \beta_0 + \beta_1 X_i$.

* **Maximization**: The maximum likelihood estimates ($\hat{\beta}$ values) are found by taking the partial derivatives of the log-likelihood function with respect to each $\beta$ coefficient, setting them to zero, and solving the resulting system of equations. These equations are non-linear and typically require iterative numerical optimization methods (e.g., gradient ascent, Newton-Raphson).

### 5. Evaluating Logistic Regression Models

* **Confusion Matrix**: A table used to evaluate the performance of a classification model, summarizing correct and incorrect predictions for each class.
    * True Positive (TP): Correctly predicted positive.
    * True Negative (TN): Correctly predicted negative.
    * False Positive (FP): Incorrectly predicted positive (Type I error).
    * False Negative (FN): Incorrectly predicted negative (Type II error).
* **Performance Metrics**:
    * **Accuracy**: $\frac{TP + TN}{TP + TN + FP + FN}$ (Overall correctness)
    * **Precision (Positive Predictive Value)**: $\frac{TP}{TP + FP}$ (Proportion of positive predictions that were actually correct)
    * **Recall (Sensitivity or True Positive Rate)**: $\frac{TP}{TP + FN}$ (Proportion of actual positives that were correctly identified)
    * **F1-Score**: The harmonic mean of Precision and Recall: $2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}$
    * **Specificity (True Negative Rate)**: $\frac{TN}{TN + FP}$ (Proportion of actual negatives that were correctly identified)
* **ROC Curve (Receiver Operating Characteristic)**: A plot showing the performance of a classification model at all classification thresholds. It plots the True Positive Rate (Recall) against the False Positive Rate (1-Specificity).
    * **Area Under the Curve (AUC)**: The area under the ROC curve. A higher AUC indicates a better model. An AUC of 0.5 suggests no better than random chance, while an AUC of 1.0 indicates a perfect model.

### 6. Example: Simple Logistic Regression Problem

* **Problem**: Model the probability of 'Success' (Y=1) based on 'Hours Studied' (X).
    * Given: $P(Y=1|X) = \frac{1}{1+e^{-(\beta_0 + \beta_1 X)}}$
    * Example parameters: $\beta_0 = -4$, $\beta_1 = 0.8$.
* **Calculations**:
    * For X = 3 hours:
        $z = -4 + 0.8 \times 3 = -4 + 2.4 = -1.6$
        $P(Y=1|X=3) = \frac{1}{1+e^{-(-1.6)}} = \frac{1}{1+e^{1.6}} \approx \frac{1}{1+4.953} \approx 0.168$
    * For X = 7 hours:
        $z = -4 + 0.8 \times 7 = -4 + 5.6 = 1.6$
        $P(Y=1|X=7) = \frac{1}{1+e^{-(1.6)}} \approx \frac{1}{1+0.202} \approx 0.832$
* **Interpretation**: As hours studied increase, the probability of success increases, following the sigmoid curve.

### 7. Overfitting and Regularization

* **Overfitting**: Occurs when a model learns the training data too well, including its noise and outliers, leading to poor generalization on new, unseen data. In logistic regression, this can happen with too many features or a very complex model.
* **Regularization**: Techniques used to prevent overfitting by adding a penalty term to the loss function, discouraging large coefficients.
    * **L1 Regularization (Lasso)**: Adds a penalty proportional to the *absolute value* of the coefficients ($\lambda \sum |\beta_j|$). Can lead to sparse models by shrinking some coefficients exactly to zero, effectively performing feature selection.
    * **L2 Regularization (Ridge)**: Adds a penalty proportional to the *square* of the coefficients ($\lambda \sum \beta_j^2$). Shrinks coefficients towards zero but rarely to exactly zero. It's good for preventing multicollinearity.
    * **Elastic Net**: A combination of L1 and L2 regularization.
* **Hyperparameter $\lambda$ (Regularization Strength)**: Controls the amount of regularization.
    * Large $\lambda$: Stronger regularization, simpler model, higher bias, lower variance.
    * Small $\lambda$: Weaker regularization, more complex model, lower bias, higher variance.
* **Choosing $\lambda$**: Typically done using cross-validation.