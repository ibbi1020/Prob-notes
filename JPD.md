## Joint Probability Distribution: Notes

A joint probability distribution describes the probabilities of two or more random variables occurring simultaneously. It can be defined for both discrete and continuous random variables.

### 1. Joint Probability Distribution

* **Definition:** A joint probability distribution captures the likelihood of multiple random variables taking on specific values at the same time.
* **Discrete Case (Joint Probability Mass Function - PMF):** For two discrete random variables, X and Y, the joint PMF is denoted as `p(x, y) = P(X = x, Y = y)`.
* **Continuous Case (Joint Probability Density Function - PDF):** For two continuous random variables, X and Y, the joint PDF is denoted as `f(x, y)`. The probability that (X, Y) falls within a certain region `A` is given by integrating `f(x, y)` over that region: `P((X, Y) ∈ A) = ∬_A f(x, y) dx dy`.

### 2. Laws and Properties

#### For Discrete Joint PMF `p(x, y)`:
* **Non-negativity:** `0 ≤ p(x, y) ≤ 1` for all possible values of x and y.
* **Summation to One:** The sum of all probabilities over the entire range of X and Y must equal 1: `∑_x ∑_y p(x, y) = 1`.
* **Marginal PMF:**
    * `p_X(x) = ∑_y p(x, y)` (marginal PMF of X)
    * `p_Y(y) = ∑_x p(x, y)` (marginal PMF of Y)
* **Independence:** X and Y are independent if and only if `p(x, y) = p_X(x) * p_Y(y)` for all x and y.

#### For Continuous Joint PDF `f(x, y)`:
* **Non-negativity:** `f(x, y) ≥ 0` for all x and y.
* **Integration to One:** The double integral of `f(x, y)` over the entire range of X and Y must equal 1: `∫_(-∞)^∞ ∫_(-∞)^∞ f(x, y) dy dx = 1`.
* **Marginal PDF:**
    * `f_X(x) = ∫_(-∞)^∞ f(x, y) dy` (marginal PDF of X)
    * `f_Y(y) = ∫_(-∞)^∞ f(x, y) dx` (marginal PDF of Y)
* **Independence:** X and Y are independent if and only if `f(x, y) = f_X(x) * f_Y(y)` for all x and y.

### 3. Mean (Expected Value) Formulas

* **Expected Value of a Function `g(X, Y)`:**
    * **Discrete:** `E[g(X, Y)] = ∑_x ∑_y g(x, y) p(x, y)`
    * **Continuous:** `E[g(X, Y)] = ∫_(-∞)^∞ ∫_(-∞)^∞ g(x, y) f(x, y) dy dx`
* **Marginal Means:**
    * `μ_X = E[X] = ∑_x x * p_X(x)` (discrete) or `∫_(-∞)^∞ x * f_X(x) dx` (continuous)
    * `μ_Y = E[Y] = ∑_y y * p_Y(y)` (discrete) or `∫_(-∞)^∞ y * f_Y(y) dx` (continuous)
* **Linearity of Expectation:** `E[aX + bY + c] = aE[X] + bE[Y] + c`

### 4. Variance Formulas

* **Marginal Variances:**
    * `Var(X) = E[(X - μ_X)²] = E[X²] - (E[X])²`
    * `Var(Y) = E[(Y - μ_Y)²] = E[Y²] - (E[Y])²`
    * For discrete variables, `E[X²] = ∑_x x² * p_X(x)`
    * For continuous variables, `E[X²] = ∫_(-∞)^∞ x² * f_X(x) dx`
* **Covariance:** A measure of how two random variables change together.
    * `Cov(X, Y) = E[(X - μ_X)(Y - μ_Y)] = E[XY] - E[X]E[Y]`
    * For discrete variables, `E[XY] = ∑_x ∑_y xy * p(x, y)`
    * For continuous variables, `E[XY] = ∫_(-∞)^∞ ∫_(-∞)^∞ xy * f(x, y) dy dx`
* **Variance of a Sum/Difference of Two Variables:**
    * `Var(aX + bY) = a²Var(X) + b²Var(Y) + 2abCov(X, Y)`
    * If X and Y are independent, `Cov(X, Y) = 0`, so `Var(aX + bY) = a²Var(X) + b²Var(Y)`.
