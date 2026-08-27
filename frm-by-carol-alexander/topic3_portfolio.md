# Study Notes on **Financial Risk Management** by Professor Carol Alexander 

Original resource: [youtube](https://www.youtube.com/watch?v=mXC5yJ5MKwM&list=PL_V1gySvrP_ums2nxs_YuKY5Ufdmhyoh7&index=6)

# Topic 3: Portfolios Returns and their Distributions

## 3.1 Profit and Loss (P&L) and Returns



**Definition of Market Risk**

- Market risk is the uncertainty in the future value of a portfolio arising from movements in an interest rate or the price of a financial asset.

- Such portfolios are priced by marking-to-market in the trading book — or, if trading liquidity is insufficient to mark-to-market (MtM), they are valued by marking-to-model.

- The portfolio price (or value) feeds into the measurement of market risk through the distribution of the future profit & loss (P&L) or returns for the portfolio from now until the risk horizon, denoted $h$.



**Profit and Loss (P&L)**

- Typically, market risk is based on daily price data – converted into daily profit and loss (P&L) and/or daily returns

- Let $P_t$ denote the price of an asset or portfolio on day $t$

- The (backward-looking) $h$-day P&L between time $t - h$ and time $t$ is $P_t - P_{t-h}$. This is **observed** at time $t$

- The (forward-looking) $h$-day P&L between time $t$ and time $t + h$ is $P_{t+h} - P_t$. This is **forecast** at time $t$

- When market risk is based on P&L it is expressed in the same units as the price, such as USD ($)



**Two Kinds of Returns**

Returns only make sense when prices are positive

- A log return is a difference in log price, e.g. if prices are daily, the $h$ backward-looking return is  
  $$\ln P_t - \ln P_{t-h}$$

- Log returns are not realized but they are easy to work with mathematically – for instance, the $h$-day log return is the sum of $h$ consecutive 1-day log returns.

- The realised return is the percentage change in price:  
  $$\frac{P_t - P_{t-h}}{P_{t-h}} \quad \text{or} \quad \frac{P_{t+h} - P_t}{P_t}$$

- When market risk is based on returns – rather than P&L – it is expressed as a % of the asset or portfolio price

---


**Reminder 1**

The number  
$$e = 2.71828182845904523536028747135266249 \dots$$

is between 2 and 3, so the graph of the exponential function $e^x$ lies between $2^x$ and $3^x$

The exponential function $e^x$ is also denoted $\exp(x)$

---

**Reminder 2**

The natural log function $\ln x$ is the inverse function of $e^x$, meaning:

$$\ln(e^x) = x \quad \text{and} \quad e^{\ln x} = x$$

and the graph of $\ln x$ is the reflection of $y = e^x$ in the line $y = x$


---

**Reminder 3**

- Rules for $e^x$ are the same as the rules for any indices – like  
  2³ × 2⁴ = 2⁷, or 3⁰ = 1  

- So $e^0 = 1$ and exponentials turn sums into products:  
  $$e^{x+y} = e^x e^y, \quad e^{x-y} = e^x e^{-y} = e^x / e^y$$

- Rules for $\ln x$ are inverse of rules for $\exp(x)$ – e.g. $\ln 1 = 0$ and logs turn products into sums:  
  $$\ln(xy) = \ln x + \ln y, \quad \ln(x/y) = \ln x - \ln y$$

---

**Something New: The Log Approximation**

- When $-1 < x \leq 1$ it can be shown that:

$$\ln(1 + x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \frac{x^4}{4} + \dots$$

- Now, when $x$ is small – as it normally is for a daily return – we know that $x$ is much greater than $x^2$, and $x^2$ is much greater than $x^3$ etc….

- And if $x$ is close to zero, $x^2$ is very small and $x^3$ is tiny … so, from the above expansion, we have:

$$\ln(1 + x) \approx x$$



**Approximation of Realised Return by Log Return**

- Consider the case where $x$ in the previous slide is a daily, forward-looking realised return:

$$R_t = \frac{P_{t+1} - P_t}{P_t}$$

and rewrite this as

$$1 + R_t = \frac{P_{t+1}}{P_t}$$

- Taking logs yields

$$\ln(1 + R_t) = \ln P_{t+1} - \ln P_t$$

and so if the realised return $R_t$ is small then it is approximately equal to the log return, by the log approximation, i.e.:

$$\ln(1 + R_t) \approx R_t$$

- Also, the log return is always less than the realised return.


## 3.2. Normal Distributions

### **Forward-Looking Returns and P&L are Random Variables**

- Two side-by-side graphs showing normal distributions:
  - **Left Graph:** Return (%) vs Density — peak near 0%, spread from –6% to +6%
  - **Right Graph:** P&L ($m) vs Density — peak near 0, spread from –1.5 to +1.5 million dollars
- Both curves are bell-shaped and symmetric.
- Caption: “We often assume that portfolio returns are normally distributed”

---

### **Reminder of Normal Distributions**

- Graph titled “Reminder of Normal Distributions”
- Shows standard normal bell curve with mean = 0, standard deviation = 1.
- Percentages within standard deviations:
  - 68.2% of values lie between –1 SD and +1 SD
  - 95.4% of values lie between –2 SD and +2 SD
  - 99.7% of values lie between –3 SD and +3 SD
- Labeled regions:
  - Mean Value at center (0)
  - ±1 SD, ±2 SD, ±3 SD marked on x-axis
  - Tail probabilities: 2.1% beyond ±3 SD, 13.6% between ±2 and ±3 SD, etc.
- Source: Investopedia


---

### **Parameters of Normal Distributions**

- When a random variable $X$ has a **normal** or **Gaussian** distribution we write  
  $X \sim N(\mu, \sigma^2)$
- The distribution is specified by two only parameters, the **mean**, $\mu$ and the **variance**, $\sigma^2$:  
  $\mu = \mathbb{E}(X), \quad \sigma^2 = \mathbb{V}(X)$
- The normal density function is:  
  $f(x) = \frac{1}{\sigma\sqrt{2\pi}} \exp\left(-\frac{1}{2}\left(\frac{x - \mu}{\sigma}\right)^2\right)$

---

### **Standard Normal Distribution**

- $Z \sim N(0,1)$ is the standard normal variable

**Left Graph: Density Function (PDF)**  
- Title: $\phi =$ density function (pdf)  
- Bell-shaped curve centered at 0.
- Vertical line at $z_\alpha$; shaded area under curve to the left labeled “Area = 0.841345”
- Formula: $\phi(z) = \frac{1}{\sqrt{2\pi}} \exp(-0.5z^2)$

**Right Graph: Distribution Function (CDF)**  
- Title: $\Phi =$ distribution function (cdf)  
- S-shaped curve from 0 to 1.
- Vertical line at $z_\alpha$; horizontal line to y-axis indicates cumulative probability.
- Note: Values of $\Phi(z)$ are given in statistical tables.

---

### **Standard Normal Commands in Excel**

- `= NORMSDIST(x)` gives the value $\Phi(x)$
- `= NORMSINV(α)` gives a quantile $z_\alpha$ such that $P(Z < z_\alpha) = \alpha$
- e.g. `NORMSDIST(0.15)=0.56` and `NORMSINV(0.56)=0.15`

**Graph:**  
Title: $\Phi$ distribution function  
- Shows the cumulative distribution function (CDF) curve of the standard normal distribution.
- Horizontal line at $y=0.56$ intersects the curve; vertical drop to x-axis shows corresponding quantile (~0.15).

---

### **Quantiles of the Standard Normal Distribution**

- $\Phi(z) \in (0,1)$ is the distribution function for $Z \sim N(0,1)$
- The inverse function $\Phi^{-1}(\alpha)$ for $\alpha \in (0,1)$ is the $\alpha$-quantile $z_\alpha$
- When $\alpha$ is near 0 or 1 we call the quantile a **critical value**
- We often use the following critical values of $N(0,1)$:
  - $\Phi^{-1}(0.99) = 2.326$, $\Phi^{-1}(0.975) = 1.960$, $\Phi^{-1}(0.95) = 1.645$
  - $\Phi^{-1}(0.01) = -2.326$, $\Phi^{-1}(0.025) = -1.960$, $\Phi^{-1}(0.05) = -1.645$
- Because normal distributions are symmetric we have  
  $\Phi^{-1}(1 - \alpha) = -\Phi^{-1}(\alpha)$

## 3.3. Matrix Algebra



### **Definition of a Vector**

- Vectors are columns or rows of data usually denoted by lower-case bold type letters, $ \mathbf{x}, \mathbf{y}, \mathbf{a}, \mathbf{b} $ etc.
- A column vector has $ n $ rows and 1 column, i.e. its **dimension** is $ n \times 1 $. A row vector has $ n $ columns and 1 row, i.e. its dimension is $ 1 \times n $
- An example of a $ 4 \times 1 $ column vector is: $ \mathbf{x} = \begin{pmatrix} 1 \\ 2 \\ 0 \\ -1 \end{pmatrix} $
- A $ 1 \times 1 $ vector is called a **scalar** and it is not written in bold. For our purposes a scalar is just a number

---

### **Definition of a Matrix**

- A matrix is a rectangular array of numbers. It is denoted by a bold capital letter, such as $ \mathbf{X}, \mathbf{Y}, \mathbf{A} $ or $ \mathbf{B} $
- Its **dimension** is the number of rows and the number of columns. This is written as $ r \times c $.
- For example, $ \begin{pmatrix} 2 & 5 & 1 \\ 0 & 6 & 4 \end{pmatrix} $ is a $ 2 \times 3 $ matrix
- The individual cells (or **elements**) in a matrix are identified by their position in the row and column
- In general notation, the element at the junction of the $ i^{th} $ row and $ j^{th} $ column of matrix $ \mathbf{X} $ is written $ x_{ij} $
- So if $ \mathbf{X} = \begin{pmatrix} 1 & 5 & -1 & 3 \\ 2 & 1 & 4 & 6 \end{pmatrix} $ then $ x_{12} = 5 $, for example.


---

### **Transpose of a Matrix**

- The **transpose** of a matrix is produced by **swapping the rows and columns**
- Transpose is denoted by the $ T $ superscript or a ‘prime’ symbol $ ' $
- **Example**

$$
\begin{pmatrix} 3 & 12 & 9 & 29 \\ 2 & 18 & 4 & 61 \end{pmatrix}'
=
\begin{pmatrix} 3 & 2 \\ 12 & 18 \\ 9 & 4 \\ 29 & 61 \end{pmatrix}
$$

- The transpose of a column vector is a row vector:

$$
\begin{pmatrix} 2 \\ 8 \\ 1 \end{pmatrix}'
=
(2 \quad 8 \quad 1)
$$

---

### **Matrix Addition**

- Matrices can **only** be added and subtracted if each matrix has the **same dimension**
- So if $ \mathbf{X} = (x_{ij}) $ and $ \mathbf{Y} = (y_{ij}) $ are both $ r \times c $ matrices then

$$
\mathbf{X} + \mathbf{Y} = (x_{ij} + y_{ij}) \quad \text{and} \quad \mathbf{X} - \mathbf{Y} = (x_{ij} - y_{ij})
$$

**Example:**

$$
\begin{pmatrix} 3 & 4 & 2 \\ 0 & 6 & 5 \end{pmatrix}
+
\begin{pmatrix} 2 & -2 & 3 \\ 5 & 5 & 1 \end{pmatrix}
=
\begin{pmatrix} (3+2) & (4-2) & (2+3) \\ (0+5) & (6+5) & (5+1) \end{pmatrix}
=
\begin{pmatrix} 5 & 2 & 5 \\ 5 & 11 & 6 \end{pmatrix}
$$


---

### **Scalar Multiplication**

- Let $ \mathbf{X} = (x_{ij}) $ and $ c $ be any number (i.e. a scalar). Then

$$
c\mathbf{X} = (cx_{ij})
$$

**Example:**

$$
\mathbf{X} = \begin{pmatrix} 8 & 6 \\ 3 & 2 \end{pmatrix}
\Rightarrow
2\mathbf{X} = 2 \begin{pmatrix} 8 & 6 \\ 3 & 2 \end{pmatrix}
=
\begin{pmatrix} 16 & 12 \\ 6 & 4 \end{pmatrix}
$$


---

### **Vector Multiplication: Excel SUMPRODUCT**

- The **dot product** $ \mathbf{x} \cdot \mathbf{y} $ only exists for two row or column vectors $ \mathbf{x} $ and $ \mathbf{y} $ of the **same dimension**
- It works by multiplying elements in the same position then adding. For instance:

$$
\begin{pmatrix} 1 \\ 2 \\ 0 \\ -1 \end{pmatrix} \cdot
\begin{pmatrix} 2 \\ 3 \\ 7 \\ 5 \end{pmatrix}
= 2 + 6 + 0 - 5 = 3
$$

- Next we do matrix multiplication, which shows that $ \mathbf{x} \cdot \mathbf{y} = \mathbf{x}'\mathbf{y} $ for two column vectors and $ \mathbf{x} \cdot \mathbf{y} = \mathbf{x}\mathbf{y}' $ for two row vectors


---

### **Matrix Multiplication: Excel MMULT**

- Matrices can be multiplied, but **only** if their dimensions are **compatible**, namely that the number of columns in the first equals the number of rows in the second
- If $ \mathbf{X} $ has order $ r \times c $ and $ \mathbf{Y} $ has order $ m \times n $ then $ \mathbf{XY} $ only exists if $ c = m $; then $ \mathbf{XY} $ has order $ r \times n $
- The $ ij^{th} $ element of the product $ \mathbf{XY} $ is the **dot product** of the $ i^{th} $ row of $ \mathbf{X} $ and the $ j^{th} $ column of $ \mathbf{Y} $



---

### **Example of Matrix Multiplication**

$$
\begin{pmatrix} 6 & 2 & 1 \\ 8 & 9 & 4 \end{pmatrix}
\begin{pmatrix} 2 & 8 & 4 & 0 \\ 3 & 4 & 2 & 3 \\ 1 & 6 & 3 & 0 \end{pmatrix}
=
\begin{pmatrix} 19 & 62 & 31 & 6 \\ 47 & 124 & 62 & 27 \end{pmatrix}
$$

- For instance: $ 124 = 8 \times 8 + 9 \times 4 + 4 \times 6 $
- Note that $ \mathbf{XY} \neq \mathbf{YX} $ except for some special matrices



---

### **Definition of Quadratic Form**

- Let $ \mathbf{A} $ be a square matrix of dimension $ n \times n $ and let $ \mathbf{x} $ be any $ n \times 1 $ vector
- Then $ \mathbf{x}'\mathbf{A}\mathbf{x} $ is called a **quadratic form**
- For instance, if $ \mathbf{A} = \begin{pmatrix} 1 & 2 \\ 3 & -1 \end{pmatrix} $ and $ \mathbf{x} = (x, y)' $ then

```math
\mathbf{x}'\mathbf{A}\mathbf{x} = x^2 + 5xy - y^2
```

- So if, for instance, $ x = 1 $ and $ y = 2 $ then the value of the quadratic form is $ 1 + 10 - 4 = 7 $
- A matrix $ \mathbf{A} $ is **positive definite** if (and only if) all quadratic forms are positive, for any (non-zero) value of $ \mathbf{x} $.


## 3.4. Statistical Operators


### **Sample Mean**

*   The mean `x̄` of a sample `{x₁, ..., xₙ}` on a random variable *X* is the arithmetic average:
    `x̄ = 1/n * Σᵢ₌₁ⁿ xᵢ`
*   For instance, if the sample has five observations, {1, 2, 3, 4, 5}, then `x̄ = 3`
*   The mean sets the **location** of the sample, i.e. it lies in the middle of the observations
*   But how closely clustered the observations are, depends on the **sample variance**

---

### **Sample Standard Deviation: Excel STDEV**

*   The **variance** of a sample `{x₁, ..., xₙ}` on a random variable *X* is:
    `s² = 1/(n-1) * Σᵢ₌₁ⁿ (xᵢ - x̄)²`
*   For instance, if the sample is {1, 2, 3, 4, 5} then
    `s² = ((-2)² + (-1)² + 0² + 1² + 2²) / 4 = (4 + 1 + 0 + 1 + 4) / 4 = 2.5`
*   The greater the sample variance, the more **dispersed** is distribution
*   The standard deviation `s` is the **square root** of the variance. We use `s` because (like the mean) it is in the **same units** of measurement as the observations

---

### **Sample Covariance: Excel COVAR**

*   Consider two random variables *X* and *Y*. The covariance `sₓᵧ` between two same-size samples, `{x₁, ..., xₙ}` and `{y₁, ..., yₙ}` is:
    `sₓᵧ = 1/(n-1) * Σᵢ₌₁ⁿ (xᵢ - x̄)(yᵢ - ȳ)`
*   Example: Given {1, 2, 3, 4, 5} for *X* and {3, 2, 0, −2, −3} for *Y*, then `x̄ = 3` and `ȳ = 0` so:
    `sₓᵧ = ([-2×3] + [(-1)×2] + [1×-2] + [2×-3]) / 4 = (-6 - 2 - 2 - 6) / 4 = -4`
*   Covariance can be positive or negative and its sign should be apparent from a **scatter plot**

---

### **Scatter Plot: Observations from a Bivariate Distribution**

*   Sample from standard normal variables, correlation = 0.8
*   [Image shows a scatter plot with points trending upwards from left to right, indicating a positive correlation.]


---

### **Sample Correlation: Excel CORREL**

*   The sample covariance is a measure of association between two samples but it is measured in **weird units**
*   For instance, if *X* is height (measured in metres) and *Y* is weight (measured in kilos) the covariance is measured in metres × kilos
*   The sample correlation `rₓᵧ` is a **unit-less measure of association** obtained dividing the covariance by the product of the two standard deviations:
    `rₓᵧ = sₓᵧ / (sₓsᵧ)`
*   We always have `-1 ≤ rₓᵧ ≤ 1`



---

### **Example**

*   Consider samples {1, 2, 3, 4, 5} on *X* and {3, 2, 0, −2, −3} on *Y*
*   We have, after some calculations:
    `x̄ = 3, sₓ = 1.58, ȳ = 0, sᵧ = 2.55, sₓᵧ = -4`
*   Hence
    `rₓᵧ = -4 / (1.58 × 2.55) = -0.99`
*   If you calculate a sample correlation that is not between −1 and +1 you have made an error

---

### **Expectation in Operator and Parameter Notation**

*   The expected value of a random variable *X* is denoted `ℰ[X]` in **operator notation**, or `μ` in **parameter notation**. This may be assumed or forecasted **ex ante**
*   Sample statistics can only be derived from **ex post**, or historical observations (also called **realisations** of the random variable)
*   In finance, when *X* denotes a return over the next few days or weeks, we usually assume `ℰ[X]` is the risk-free (discount) rate
*   The expectation sets the **location** of the distribution of *X* meaning that most of the realisations of *X* should be located about `μ`
*   How close the realisations are to `μ` depends on the variance of *X*


---

### **Variance and Standard Deviation of a Random Variable**

*   The variance of a random variable *X* is denoted `∇[X]` in operator notation, or `σ²` in parameter notation
*   This is an assumed or forecast value for the variance of *X*, as distinct from the sample variance `s²`, which is a number that can be calculated
*   The greater the variance, the greater the **range** or **dispersion** of realisations of *X*
*   It may be written in terms of the expectation operator:
    `∇[X] = ℰ[(X - ℰ[X])²]`
*   The standard deviation of *X* is the square root of the variance, denoted `√∇[X]`, or `σ`

---

### **Covariance Between X and Y**

*   The covariance refers to two random variables *X* and *Y*, and it **tells us how they move together**
*   It is denoted `Cov[X, Y]` in parameter notation, or `σₓᵧ` in parameter notation and it is defined as:
    `Cov[X, Y] = ℰ[(X - ℰ[X])(Y - ℰ[Y])]`
*   When `Cov[X, Y]` is positive, positive values for *X* tend to be accompanied by positive values in *Y*; when it is negative, positive values for *X* tend to be accompanied by negative values in *Y*
*   If *X* and *Y* are independent then `Cov[X, Y] = 0`


---

### **Correlation Between X and Y**

*   The correlation `ℭorr[X, Y]` is a **standardized form** of `Cov[X, Y]`:
    `ℭorr[X, Y] = Cov[X, Y] / √(∇[X]∇[Y])`
*   Or, in parameter notation:
    `ρₓᵧ = σₓᵧ / (σₓσᵧ)`
*   It is **unit-less** and we always have `-1 ≤ ρₓᵧ ≤ 1`
*   If *X* and *Y* are independent then `ℭorr[X, Y] = 0`


---
### **Rules for Statistical Operators**

For random variables *X* and *Y* and constants *a* and *b*:
1.  `ℰ[aX + bY] = aℰ[X] + bℰ[Y]`
2.  `ℰ[XY] = ℰ[X]ℰ[Y] + Cov[X, Y]`
3.  `∇[aX + bY] = a²∇[X] + b²∇[Y] + 2ab Cov[X, Y]`
4.  `Cov[aX, bY] = ab Cov[X, Y]`
5.  `ℭorr[aX, bY] = sign(ab) ℭorr[X, Y]`

## 3.5. Portfolio Holdings and Weights

---

### Portfolio Holdings and Weights

- The **holding** of an asset in a portfolio is the **number of units**, e.g., the number of shares of a stock.
- The **weight** of an asset in a portfolio is the **proportion of portfolio value** that is invested in that asset.
- In practice, portfolio holdings can easily be kept constant over time but portfolio weights change every time the price of any asset changes.


---

### Example

- Suppose you have holdings of 100 shares of Amazon (AMZN) and 200 shares of Tesla (TSLA) in a portfolio.
- Suppose the price of AMZN is `$20` and the price of TSLA is `$25`.
- Then the portfolio value is
  $\$(100 \times 20 + 200 \times 25) = \$(2000 + 5000) = \$7000$
- So the weights are $2/7 = 28.6\%$ on AMZN and $5/7 = 71.4\%$ on TSLA.
- If the price of **either** stock changes, then so does the portfolio value and so **both weights change**.

---

### Calculating Constant-Weight Returns

- Market risk calculations are based on historical returns.
- Assuming the portfolio is not **rebalanced** during the historical period, the **actual returns** are based on constant holdings.
- However, when calculating the market risk of a portfolio, we assume that the **current portfolio weights** are **constant** over the historical period and hence **reconstruct artificial returns** based on this assumption.
- This assumption could only be true of the portfolio is rebalanced every day but it allows market risk to be calculated using a simple formula.


---

### Vector of Portfolio Weights

- Consider a **linear portfolio** containing **long** positions in $n$ assets with returns $r_i$ for $i = 1, \ldots, n$.
- Set $w_i$ to be the weight on asset $i$, i.e., the proportion of the total amount invested that is invested in asset $i$. Then $\mathbf{w} = (w_1, w_2, \ldots, w_n)'$ is called the vector of **portfolio weights**.
- Note that, for a fully-funded long-only portfolio,
  $w_1 + w_2 + \ldots + w_n = 1$
- For instance, if I have `$5m` and I invest `$1.5m` in asset 1 and `$3.5m` in asset 2, the portfolio weights are $(0.3, 0.7)'$

---

### Constant Weight Returns on a Stock Portfolio

- Any domestic stock portfolio $p$ is called a **linear portfolio** because its return may be written:
  $r_p = \mathbf{w}'\mathbf{r} = \sum_{i=1}^{n} w_i r_i$
  where $\mathbf{w} = (w_1, \ldots, w_n)'$ is the vector of portfolio weights and $\mathbf{r} = (r_1, \ldots, r_n)'$ is the vector of ordinary (not log) returns that are observed on the $n$ stocks.

- This is not only true for observed returns. A similar relationship holds for expected returns:
  $\mathbb{E}[r_p] = \mathbf{w}'\mathbb{E}[\mathbf{r}] = \sum_{i=1}^{n} w_i \mathbb{E}[r_i]$


---

### Example

- Consider a portfolio $P$ with $1m invested in asset 1 and $4m invested in asset 2. If asset 1 returns 10% and asset 2 returns 5%, what is the return $r_p$ on the portfolio?
- Solution:
  $\mathbf{w} = (w_1, w_2)' = (0.2, 0.8)' \text{ and } \mathbf{r} = (r_1, r_2)' = (0.1, 0.05)'$
  so
  $r_p = (0.2, 0.8)(0.1, 0.05)' = 0.2 \times 0.1 + 0.8 \times 0.05 = 0.02 + 0.04 = 0.06$
- Hence, the portfolio return is **6%**

## 3.6. Portfolio Volatility

---

### **What is Volatility?**

- Volatility is a very approximate measure of by how much a price could change one year from now
- For instance, 25% volatility means (very roughly) that, this time next year, there’s about 68% chance that the price could be 25% higher or 25% lower than now
- Mathematically, volatility of a linear portfolio is the **annualized** **standard deviation** of its returns or P&L
- To find standard deviation, we must first compute the variance.....


---

### **Variance of a Portfolio with Constant Weights**

- Our formula for the variance $\sigma_p^2$ of a portfolio $p$ uses the portfolio weights $w_i$ on the assets in the portfolio and the standard deviations $\sigma_i$ and correlations $\rho_{ij}$ (or covariances, $\sigma_{ij}$) of the asset’s returns
- If there are $n$ assets in the portfolio then:

$$\sigma_p^2 = \sum_{i=1}^n w_i^2 \sigma_i^2 + 2 \sum_{i=1}^n \sum_{j > i} w_i w_j \sigma_{ij}$$

- But $\sigma_{ij} = \rho_{ij} \sigma_i \sigma_j$ so we also have:

$$\sigma_p^2 = \sum_{i=1}^n w_i^2 \sigma_i^2 + 2 \sum_{i=1}^n \sum_{j > i} w_i w_j \rho_{ij} \sigma_i \sigma_j$$



---

### **Example**

- Asset 1 has volatility 20% and asset 2 has volatility 25% and their returns have correlation 0.4
- Find the volatility of a portfolio with $2m invested in asset 1 and $3m invested in asset 2
- **Solution:** The weights are $w_1 = \frac{2}{2+3} = 0.4$ and $w_2 = \frac{3}{2+3} = 0.6$ so

  $$\sigma_p^2 = 0.4^2 \times 0.2^2 + 0.6^2 \times 0.25^2 + 2 \times 0.4 \times 0.6 \times 0.4 \times 0.2 \times 0.25$$

  That is, $\sigma_p^2 = 0.0064 + 0.0225 + 0.0096 = 0.0385$.

- Hence the volatility is $\sqrt{0.0385} = 0.1962 = 19.62\%$



---

### **Definition of Covariance Matrix**

- Again consider $n$ assets with returns $r_i$ for $i = 1, \dots, n$
- Now set $v_{ij}$ to be the covariance between $r_i$ and $r_j$, for $i, j = 1, \dots, n$ – this is properly defined in the next section
- Then the matrix $\mathbf{V} = (v_{ij})$ is called the $n \times n$ **covariance matrix** of the returns on these $n$ assets
- Note that the $i^{th}$ **diagonal** element $v_{ii}$ is the variance of $r_i$
- Every covariance matrix is **symmetric** because $v_{ij} = v_{ji} \quad \forall i, j$
- And every covariance matrix is always **positive definite** – because the variance of a portfolio can be written as a quadratic form......


---

### **Writing Portfolio Variance as a Quadratic Form**

- Let $V$ be the covariance matrix of the returns on $n$ assets and let $\mathbf{w}$ be the $n \times 1$ vector of portfolio weights
- Then $\mathbf{w}'\mathbf{V}\mathbf{w}$ is the variance of the portfolio return. Being a variance, it must always be positive, for **any** weights – even if some are negative
- For instance, if $\mathbf{V} = \begin{pmatrix} 0.1 & 0.2 \\ 0.2 & 0.15 \end{pmatrix}$ and $\mathbf{w} = (w_1, w_2)'$ then

  $$\mathbf{w}'\mathbf{V}\mathbf{w} = 0.1w_1^2 + 0.4w_1w_2 + 0.15w_2^2$$

- So if $w_1 = 0.3$ and $w_2 = 0.7$ then

  $$\mathbf{w}'\mathbf{V}\mathbf{w} = 0.1 \times 0.3^2 + 0.4 \times 0.3 \times 0.7 + 0.15 \times 0.7^2 = 0.1665$$



---

### **General Formula**

We already have notation for the portfolio weights $\mathbf{w} = (w_1, \dots, w_n)'$ and asset returns $\mathbf{r} = (r_1, \dots, r_n)'$. Now we need another notation to summarize the variances $\sigma_i^2$ and covariances $\sigma_{ij}$ which is called the **covariance matrix** of the asset returns:

$$\mathbf{V} = \begin{pmatrix} \sigma_1^2 & \sigma_{12} & \dots & \sigma_{1n} \\ \sigma_{21} & \sigma_2^2 & \dots & \sigma_{2n} \\ \dots & \dots & \dots & \dots \\ \sigma_{n1} & \sigma_{n2} & \dots & \sigma_n^2 \end{pmatrix}$$

Now, using matrix multiplication it can be shown that

$$\sigma_p^2 = \sum_{i=1}^n w_i^2 \sigma_i^2 + 2 \sum_{i=1}^n \sum_{j > i} w_i w_j \sigma_{ij} = \mathbf{w}'\mathbf{V}\mathbf{w}$$


---

### **Example**

- Asset 1 has volatility 20% and asset 2 has volatility 25% and their returns have correlation 0.4. Find the volatility of a portfolio with `$2m` invested in asset 1 and `$3m` invested in asset 2

$$\mathbf{V} = \begin{pmatrix} 0.2^2 & 0.4 \times 0.2 \times 0.25 \\ 0.4 \times 0.2 \times 0.25 & 0.25^2 \end{pmatrix} = \begin{pmatrix} 0.04 & 0.02 \\ 0.02 & 0.0625 \end{pmatrix}$$

The weights are $\mathbf{w} = (0.4, 0.6)'$ so

$$\sigma_p^2 = \mathbf{w}'\mathbf{V}\mathbf{w} = (0.4, 0.6) \begin{pmatrix} 0.04 & 0.02 \\ 0.02 & 0.0625 \end{pmatrix} \begin{pmatrix} 0.4 \\ 0.6 \end{pmatrix}$$

This gives, $\sigma_p^2 = 0.0385$ so the volatility is

$$\sqrt{0.0385} = 0.1962 = 19.62\%$$


---

### **What Does i.i.d. Mean?**

- A stochastic process – such as a time series of daily log returns or P&L – is **independent and identically distributed (i.i.d.)** if the distribution is same at every point and time and there is no dependence between returns at different times – so returns cannot be autocorrelated
- Using the log return approximation for realised returns, the $h$-day log return is the sum of $h$ one-day returns:

  $$r_{ht} = \sum_{i=0}^{h-1} r_{t,t+i}$$

- If we assume log returns are i.i.d. then the mean of the $h$-day log return is just $h$ times the mean of the 1-day log return, and the same for the variance. Hence the standard deviation of an $h$-day log return is $\sqrt{h} \times$ the standard deviation of a 1-day log return


---

### **Annualisation**

- Recall that the volatility of a linear portfolio is the **annualised** standard deviation of the portfolio returns
- To annualise a standard deviation, we assume 250 trading days per year (or 365 for crypto markets) and use the **square-root-of-time** rule introduced on the previous slide
  If the log returns are i.i.d. their mean and variance both scale with the holding period, so the standard deviation scales with the **square root** of the holding period
- So, if $\mu_1$ and $\sigma_1$ denote the mean and standard deviation of daily log returns, then

  $$\mu_h = h\mu_1 \quad \text{and} \quad \sigma_h = \sqrt{h}\sigma_1$$




---

### **Examples**

1. **Find the volatility of an asset whose daily returns have a standard deviation of $\sigma_1 = 0.02$**
   - Volatility $= \sigma_{250} = 0.02 \times \sqrt{250} = 31.62\%$

2. **Find the volatility of an asset with monthly returns having a standard deviation of 8%**
   - Volatility $= \sigma_{250} = 0.08 \times \sqrt{12} = 27.71\%$

3. **Find the standard deviation of daily returns for an asset with volatility 20%**
   - $\sigma_1 = 0.2 \div \sqrt{250} = 1.265\%$

4. **Find the standard deviation of 10-day returns for an asset with volatility 20%**
   - $\sigma_{10} = 0.2 \div \sqrt{25} = 4\%$


---

### **Calculating Mean and Variance with Constant Weights**

**Mean and variance can be measured in two equivalent ways:**

1. Take data on each asset return $r_{it}$ for $i = \dots, n$ and $t = 1, \dots, T$ then multiply the **current** portfolio weights $w_i$ by each $r_{it}$ and use the formula $r_{pt} = \mathbf{w}'\mathbf{r}$ to obtain a time series of **reconstructed** (not actual) historical portfolio returns, then calculate the mean $\bar{r}_p$ and variance $s_p^2$ of the time series $r_{pt}$
2. Apply the formulae $\bar{r}_p = \mathbf{w}'\bar{\mathbf{r}}$ and $s_p^2 = \mathbf{w}'\mathbf{V}\mathbf{w}$

See **Portfolio Calculations** in the Excel workbook for Topic 3

---

### **Using Historical Data for Portfolio Volatility (1)**

- **Method (1):** Apply the current portfolio weights to the asset returns on each day in time series:

  $$r_{pt} = \mathbf{w}'\mathbf{r}_t = \sum_{i=1}^n w_i r_{it}, \quad t = 1, \dots, T$$

- This gives a time series of $T$ observations on the portfolio return
- Then we calculate the standard deviation of the portfolio returns and annualise it to obtain the portfolio volatility


---

### **Using Time Series Data for Portfolio Volatility (2)**

- **Method (2):** Take the variance of a time series of observations on asset returns (Excel Command `=VAR`)
- Take pair-wise covariances between all pairs of assets in the portfolio (Excel Command `=COVAR`)
- This way, construct the asset covariance matrix $V$
- Apply the formula $\mathbf{w}'\mathbf{V}\mathbf{w}$
- Take the square root to get the portfolio standard deviation and annualize into a volatility using the square root of time rule
