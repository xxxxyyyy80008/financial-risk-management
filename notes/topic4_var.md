# Study Notes on **Financial Risk Management** by Professor Carol Alexander 

Original resource: [youtube](https://www.youtube.com/watch?v=mXC5yJ5MKwM&list=PL_V1gySvrP_ums2nxs_YuKY5Ufdmhyoh7&index=6)

# Topic 4: Volatility and Value-at-Risk

## 4.1 Defining Value-at-Risk (VaR)


**Definition of Value-at-Risk (VaR)**

VaR is a loss we are ‘confident’ will not be exceeded when the portfolio remains unchanged for some time period

*   ‘Remain unchanged’ could mean either (i) the holdings are constant – i.e. the portfolio is **not rebalanced**, or (ii) the weights are constant – which assumes the portfolio is rebalanced
*   In mathematics the above definition reads: “The $\alpha\%$, $h$-day VaR, written $\text{VaR}_{h,\alpha}$, is $-1 \times \alpha$-quantile of the discounted $h$-day P&L distribution”
*   Terminology for the two VaR parameters:
    *   $h$ is the **holding period** for the VaR model – this is also called the **risk horizon** – it is the time-period over which the portfolio is assumed to remain unchanged
    *   $\alpha\%$ is the **significance level** for the VaR estimate – alternatively we say $(1 - \alpha)\%$ is the **confidence level**



**Examples of VaR**

**5% daily VaR = $2 million** means that

*   ... we are 95% confident that we will not lose more than $2 million when the portfolio remains unchanged for one day
*   ... we anticipate that this portfolio loses $2 million, or more, about once every 20 days

**1% 10-day VaR = $15 million** means that

*   ... we are 99% confident that we will not lose more than $15 million when the portfolio remains unchanged over 10 days
*   ... we anticipate that this portfolio loses $15 million, or more, about one two-week period in every 100


**Parameters: Holding Period $h$ and Significance Level $\alpha$**

*   Banking regulation sets $h = 10$ for market risk capital requirements and $h = 1$ for **backtesting** the VaR model
*   Hedge funds, asset managers, corporate treasury and institutional investors may set $h > 10$, or more
*   Banking regulation sets $\alpha = 1\%$ (meaning a confidence level of 99%) and $\alpha = 2.5\%$ (meaning a confidence level of 97.5%) for **market risk capital requirements**
*   Other users may set a higher $\alpha$ (lower confidence level), e.g. $\alpha = 5\%$, meaning 95% confidence



**Is VaR measured in $ or %?**

*   VaR is a level of loss and so it relates to a quantile of the portfolio's **profit and loss** (P&L) distribution, measured in $
*   But when a portfolio value has been **trending** it is best to use a quantile of the portfolio **returns** distribution.
*   Then VaR is given in % terms: it is a loss expressed as a % of the current portfolio value. **VaR in $ = VaR in % × current portfolio value**
*   Recall that returns do not make sense if the portfolio value can be zero or negative. Then we must measure VaR directly from the P&L distribution

## 4.2 Introducing VaR Models


**Portfolio-Level vs Risk-Factor Modelling**

Two ways to model portfolio risk:

**1. Portfolio Level:**

*   Keep the weights (or holdings) constant
*   Model the portfolio returns (or P&L) as the weighted sum of **correlated** individual asset returns (or P&L)
*   **Advantages:** Full capture of all risks (**systematic** and **idiosyncratic**)
*   **Limitations:** High-dimensional, less interpretable, no insight into common drivers


**2. Risk-Factor Level:**

*   Map portfolio to **systematic risk factors** by computing the sensitivities to these risk factors
*   Model only the **systematic**, i.e. the **non-diversifiable** part of the portfolio risk using risk-factor returns (or P&Ls) while holding the sensitivities constant
*   **Advantages:** Reduces dimensionality, identifies main systematic sources of risk
*   **Limitations:** Ignores **idiosyncratic** risks – but these are typically regarded as **diversifiable**

Choice between portfolio or risk-factor level depends on regulatory requirements and portfolio structure


**Risk Factors Depend on Portfolio Type**

| Portfolio Type | Typical Risk Factors |
| :--- | :--- |
| Domestic Equities | Sector indices (e.g. Pharma, Banking, Utilities) |
| Fixed Income | Interest rates at different maturities |
| Options | Underlying + implied volatilities |
| Commodities | Futures at different maturities |
| International | As above + exchange rates |
| Global Equities | Broad market indices + exchange rates |

**Note:** In this topic we only consider modelling VaR at the portfolio level – or indeed, at the single-asset level. Topics 5, 6 and 7 cover the process of **risk factor mapping** – the mathematics of portfolio mapping on the type of portfolio


**Four Steps for VaR Estimation**

1. Set the first parameter: the holding period *h*
2. Create a probability distribution for the *discounted* portfolio returns (or P&L) over the next *h* days
3. Set the second parameter: the significance level *α*
4. Estimate VaR as −1 × *α*-quantile of this distribution

Different assumptions for step 2 ⇒ different VaR models


**Three Main VaR Models**

1.  **Normal VaR:** Assumes the distribution of returns is N(μ, σ²) – We use mean and standard deviation of returns over a recent sample as estimates for μ and σ
2.  **Historical VaR:** Build a histogram of historical of returns (or P&L) and read off the VaR from a quantile
3.  **Monte Carlo VaR:** Assume that returns have some parametric distribution, then simulate lots of returns from this distribution, read off the % VaR as a quantile

Note: It is possible to apply any of these models to P&L distributions too – which is necessary for portfolios with short positions – but for portfolios with only long positions, it is always better to use returns, measure VaR in %, and then multiply by the portfolio value (at the time the VaR is measured) to obtain the final $ VaR

**Which VaR Model?**

*   **Normal VaR:** Applies only to a linear portfolio. Here the returns (or P&L) are assumed to have a normal distribution
*   **Historical Simulation:** Applies to all portfolios, including those containing options. It employs historical data without any parametric assumptions about their returns (or P&L)
*   **Monte Carlo Simulation:** Typically used for complex option-like portfolios, an alternative to historical simulation


**Normal VaR Model**

**Z ~ N(0, 1) is the standard normal variable**

*   **φ = density function (pdf)**
*   **φ(z) = $\frac{1}{\sqrt{2\pi}} \exp(-0.5z^2)$**

*   **Φ = distribution function (cdf)**
*   **Values of Φ(z) are given in statistical tables**

**Interpretation of Standard Normal Quantile**

For the standard normal distribution: (in Excel)

= NORMSDIST(x) gives the value Φ(z)
= NORMSINV(α) gives a quantile zα of the standard normal distribution, such that P(Z < zα) = α
e.g. NORMSDIST(0.15)=0.56 and NORMSINV(0.56)=0.15

Φ distribution function


**Quantiles and Critical Values**

*   $\Phi(z) \in (0, 1)$ is the distribution function for $Z \sim N(0, 1)$
*   The inverse function $\Phi^{-1}(\alpha)$ for $\alpha \in (0, 1)$ is the $\alpha$-quantile $z_\alpha$
*   When $\alpha$ is near 0 or 1 we call the quantile a **critical value**
*   We often use the following critical values of $N(0, 1)$:
    *   $\Phi^{-1}(0.99) = 2.326, \Phi^{-1}(0.975) = 1.960, \Phi^{-1}(0.95) = 1.645$
    *   $\Phi^{-1}(0.01) = -2.326, \Phi^{-1}(0.025) = -1.960, \Phi^{-1}(0.05) = -1.645$
*   Because normal distributions are symmetric we have
    *   $\Phi^{-1}(1 - \alpha) = -\Phi^{-1}(\alpha)$


**Calculating a Quantile: Three Ways**

1.  **Normal VaR:** Use the $\alpha$-quantiles of the standard normal distribution denoted $\Phi^{-1}(\alpha)$ and apply the **standard normal transformation** to convert them into quantiles of a $N(\mu, \sigma^2)$ distribution
2.  **Historical VaR:** Use the **= PERCENTILE** function in Excel on the time series of historical portfolio returns or P&L
3.  **Monte Carlo VaR:** Use the **= PERCENTILE** function in Excel on the simulated data for portfolio returns or P&L, based on some parametric assumption


## 4.3 Building VaR Models

**Data Requirements for Building the Distribution**

*   Typically, the probability distribution for the (discounted) portfolio returns (or P&L) over the next $h$ days is based on data for the recent history of the portfolio returns (or P&L) – assuming these are indicative of future returns (or P&L)
*   Banking regulation (Basel III) recommends that banks use about 3–5 years of daily data to build this distribution. A minimum of 1 year of data daily must be used
*   The amount of data required depends on the model: **historical** VaR models need lots and lots of data, especially when $\alpha$ is small – but other models are based on **parameters** which can be estimated using not very much data at all – or even made up


**Formula for Normal VaR**

Assumption on portfolio *h*-day returns:
$$X_h \overset{i.i.d.}{\sim} N(\mu_h, \sigma_h^2)$$

Then:
$$\text{VaR}_{h,\alpha} = \Phi^{-1}(1 - \alpha)\sigma_h - \mu_h$$

When *h* is small we often assume that $\mu_h = 0$

For example, if $X_1 \overset{i.i.d.}{\sim} N(0, 0.8^2)$ then
$$\text{VaR}_{1,5\%} = \Phi^{-1}(0.95) \times 0.8 = 1.645 \times 0.8 = 1.316\%$$

Note: VaR is given as a percent of the current portfolio value, since the model is based on returns


**Proof of Normal VaR Formula**

Recall the standard normal transformation:
$$X \sim N(\mu, \sigma^2) \Rightarrow \frac{X - \mu}{\sigma} \sim N(0, 1)$$

*   Suppose $X_h \sim N(\mu_h, \sigma_h^2)$ and let $x_{h,\alpha}$ be the $\alpha$-quantile of $X_h$:
    $$\text{Prob}[X_h < x_{h,\alpha}] = \alpha$$

*   Then, using the **standard normal transformation**:
    $$\text{Prob}[X_h < x_{h,\alpha}] = \text{Prob}\left[Z < \frac{x_{h,\alpha} - \mu_h}{\sigma_h}\right] = \alpha$$

where $Z \sim N(0, 1)$


**Normal VaR in $ Terms**

We prefer to measure % VaR (if possible) – but then convert to $ VaR by multiplying the % VaR by the current portfolio value $P_t$

$$\$\text{VaR}_{h,\alpha} = P_t [\Phi^{-1}(1 - \alpha)\sigma_h - \mu_h]$$

Example: If the % VaR is 8% and the portfolio value is $20m then the $ VaR is 8% × $20m = $160,000

But for portfolios which might have zero or negative values, returns do not make sense, so we cannot calculate $\mu_h$ and $\sigma_h$. Instead:

$$\$\text{VaR}_{h,\alpha} = \Phi^{-1}(1 - \alpha)\sigma_h^{\$} - \mu_h^{\$}$$

where $\mu_h^{\$}$ and $\sigma_h^{\$}$ are the mean and standard deviation of the P&L


**Example 1**

Calculate the 1% 1-day VaR for a portfolio with value $1m which is expected to return the discount rate with volatility 20%. Assume the discounted returns are normally i.i.d. distributed and that there are 250 trading days per annum.

1.  The 1-day standard deviation of returns is
    $\sigma = 0.2/\sqrt{250} = 0.01265$

2.  The 1% 1-day VaR (measured a % of portfolio value) is
    $-\Phi^{-1}(0.01) \times 0.01265 = 2.32635 \times 0.01265 = 0.029426 = 2.9426\%$

3.  The 1% 1-day VaR in value terms is therefore **$29,426**


**Example 2**

What is the 10% VaR over a 1-year horizon of $2 million invested in a fund whose annual returns in excess of the discount rate are assumed to be normally distributed with mean 5% and volatility 12%?

The return VaR is given by

VaR = Φ⁻¹(0.9) × 0.12 − 0.05 = 1.281552 × 0.12 − 0.05 = 10.3786%.

In terms of P&L we have

VaR = 10.3786% × $2m = $207,572.


**Other VaR Models**

*   The normal VaR model assumes the portfolio is a **linear function** of its assets or risk factors
*   But the price of an **option** is a **non-linear function** of the underlying asset price. Hence normal VaR cannot be used for options portfolios
*   Another problem with normal VaR is that is assumes the asset (or risk factor) returns are **normally distributed**, which is an unrealistic assumption
*   Therefore we need other methods for computing VaR


**Historical VaR – Two Ways**

There are two ways to get historical data on a portfolio that we currently hold:

*   **No rebalancing:** the current portfolio **holdings** (e.g. the **numbers** of each share in the portfolio) are kept constant ⇒ weights change over time. But we don't use this method because VaR is difficult to scale to different risk horizons
*   **Rebalancing to constant weights:** the current portfolio **weights** on each asset is kept constant ⇒ holdings change over time. Then VaR is easy to scale to different risk horizons
*   Similar definitions apply in other contexts, e.g. **constant** sensitivities to risk factors


## 4.4
## 4.5
## 4.6