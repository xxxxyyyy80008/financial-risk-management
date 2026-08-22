# Study Notes on **Financial Risk Management** by Professor Carol Alexander 

Original resource: [youtube](https://www.youtube.com/watch?v=mXC5yJ5MKwM&list=PL_V1gySvrP_ums2nxs_YuKY5Ufdmhyoh7&index=6)

# Topic 6: International Equity and Commodity Portfolios

## 6.1 Single Index Model


### **Equity Risk**

Equity risk is the uncertainty in the market value of a portfolio due to changes in equity risk factors

* Here we cover **linear** equity portfolios, which means a collection of shares, and/or equity futures, and/or exchange-traded funds (ETFs) – basically, no options!
* Equity risk affects the companies that issue the shares, and any investors in equity markets, such as asset managers, hedge funds, pensions funds and corporate treasury
* Portfolios may contain **long** (buy) or **short** (sell) positions (a short position in a share is achieved using **repo**)


---

### **Risk Factors for Equity Portfolios**

1. A **general market risk factor** is a broad, market-wide index or instrument which captures the overall market risk of a large portfolio, such as the S&P 500 (US stocks) or FTSE 100 (UK stocks)
2. Domestic equity portfolios can have a single risk factor – that's what we cover in Section 2 – and in Section 3 we consider using **sector indices** so that risk can be disaggregated to a more granular level
3. In Section 4 we show how equity portfolios which include investments in foreign stocks must also have the relevant **exchanges rates** as risk factors



---

### **Risk Factor Mapping is Based on Regression**

* Recall that the aim of linear regression is to test the influence of one or more **independent** variables – also referred to as **regressors** or **explanatory variables** – on one particular variable, known as the **dependent** variable, which is usually labelled $Y$
* With only one risk factor we use the **simple linear model (SLM)**:

$$ Y_t = \alpha + \beta X_t + \varepsilon_t \quad \varepsilon_t \sim i.i.d(0, \sigma^2) \quad t=1, \dots, T $$

* The coefficient $\beta$ measures the effect of $X$ on $Y$ – it is the **change in Y per unit change in X** and if $\beta = 0$ then $X$ has no effect on $Y$
   
---
### **Residuals**

A residual $e_t$ is an observation on the error $\varepsilon_t$. It is the difference between the **actual** and **fitted** values of $y$ at time $t$:

$$ e_t = y_t - \hat{y}_t = y_t - (\hat{\alpha} + \hat{\beta}x_t) $$

where $\hat{\alpha}$ and $\hat{\beta}$ are the **estimated** intercept and slope of the regression line:
*(Note: Includes a scatter plot with regression line and residual for a low y-point.)*

---

### **Ordinary Least Squares (OLS) Estimation**

* Data on $X$ and $Y$ allow one to estimate the model parameters $\hat{\alpha}, \hat{\beta}$ and $\hat{\sigma}$ by minimizing the **residual sum of squares (RSS)** given by

$$ RSS = \sum_{t=1}^{T} e_t^2 $$

* This gives the OLS formulae:

$$ \hat{\alpha} = \bar{y} - \hat{\beta}\bar{x}; \quad \hat{\beta} = \frac{s_{xy}}{s_x^2}; \quad \hat{\sigma} = \sqrt{\frac{RSS}{T-2}} $$

* $\hat{\sigma}$ is the **standard error of the regression** – why do we divide by $T-2$ and not $T-1$?

---

### **Beta vs Correlation**

* The OLS estimate of the slope of the regression line is related to $r_{xy}$, the correlation between $X$ and $Y$ and to $s_y/s_x$, the **relative volatility** of $Y$ and $X$:

$$ \hat{\beta} = \frac{s_{xy}}{s_x^2} = \frac{r_{xy}\hat{s}_x s_y}{s_x^2} = r_{xy} \left( \frac{s_y}{s_x} \right) $$

* **Beta** captures the change in $Y$ per unit change in $X$. It has the same sign as the sample correlation
* But the beta may be greater than 1 or less than $-1$


---

### **Single Index Model (SIM)**

The SIM is a simple linear regression

$$ Y_t = \alpha + \beta X_t + \varepsilon_t $$

where $Y_t$ is the return (or P&L) on a **stock**, or a **stock portfolio**, and $X_t$ is the return (or P&L) on an **equity market index**

*(Note: Includes a scatter plot of stock return vs. S&P100 return.)*

---

### **Percentage and Nominal Betas**

* Using the SIM, we find beta by doing an OLS regression – or equivalently, using the formula **correlation × relative volatility** on slide 9
* This yields a % beta if the SIM is based on returns, or a **nominal** ($) beta if the SIM is based on P&L. We can convert % betas to nominal betas by multiplying by the current stock or portfolio price
* For example, suppose a fund has £10m in UK stocks, £5m in US stocks and £3m in European stocks. If the **percentage** betas are 1.2, 1.5 and 2 then the **nominal** betas are £10×1.2 = 12m, £5×1.5 = 7.5m and £3×2 = 6m, respectively

---

### **Stock Betas → Portfolio Beta**

* Let the weights be $\mathbf{w} = (w_1, \dots, w_n)'$ and the (percentage or nominal) stock betas – all with respect to the same equity risk factor – be $\boldsymbol{\beta} = (\beta_1, \dots, \beta_n)'$
* Then the portfolio beta is:
  
$$ \beta_p = \mathbf{w}'\boldsymbol{\beta} = \sum_{i=1}^n w_i \beta_i $$
  
* For example, suppose the weights are 0.25 and 0.75 and the % betas are 0.8 and 2. Then the % portfolio beta is

$$ 0.25 \times 0.8 + 0.75 \times 2 = 0.2 + 1.5 = 1.7 $$

  Now suppose the portfolio value is $5m. Then the **nominal** beta is $1.7 \times 5 = \mathbf{\$8.5m}$

* An alternative calculation uses nominal betas of 0.8 \times 5 = \$4$m and 2 \times 5 = \$10$m, then the nominal beta:

$$ 0.25 \times 4 + 0.75 \times 10 = 1 + 7.5 = \mathbf{\$8.5m} $$


## 6.2 VaR with One Equity Risk Factor


---

### Systematic and Specific Risk in the SIM

- Assuming $\text{Cov}(X, \varepsilon) = 0$, taking variances of $Y_t = \alpha + \beta X_t + \varepsilon_t$ yields:

  $\mathbb{V}(Y_t) = \beta^2 \mathbb{V}(X_t) + \sigma^2$

- Thus, there are 3 components to the total market risk of a stock, or stock portfolio:

  1. The stock or portfolio’s **sensitivity**, or ‘risk relative to the market’ – captured by the **equity beta**
  2. The **systematic risk** which is undiversifiable – captured by $\mathbb{V}(X_t)$
  3. The **specific risk**, also called ‘idiosyncratic’ or ‘diversifiable’ risk – captured by $\sigma^2$


---


### Normal Equity VaR

- Risk measurement focuses on the **systematic** part of the portfolio return, i.e. $\hat{\alpha} + \hat{\beta} X_t$ with all the risk coming from the second term (because $\hat{\alpha}$ is a constant and therefore has zero variance)

- So

$$ \text{Equity VaR}_{h,\alpha} = \hat{\beta} \times \text{Market VaR}_{h,\alpha}$$

- If **daily returns** are $X_t \stackrel{i.i.d.}{\sim} N(\mu, \sigma^2)$ then:

  $\text{Equity VaR}_{h,\alpha} = \hat{\beta} \left( \Phi^{-1}(1 - \alpha) \sigma_h - \mu_h \right)$

  where, by the square root of time rule:

  $\mu_h = h\mu \quad \text{and} \quad \sigma_h = \sqrt{h}\sigma$




### Example: Normal Equity VaR

- A portfolio contains cash positions on two stocks: `$1` million is invested in a stock with a beta of 1.2 and $2 million is invested in a stock with a beta of 0.8, both betas with respect to a broad market index, e.g. the S&P 500

- Suppose the excess returns on the index are i.i.d. and normally distributed with expectation 5% and volatility 20% per annum

- Calculate the 1% 10-day equity VaR of the portfolio

### Solution

1. The net portfolio beta is measured in dollar terms as

$$\beta_\$ = 1m \times 1.2 + 2m \times 0.8 = 2.8m$$

2. The 10-day expected excess return on the market index is

   $\mu_{10} = 0.05 \times 10/250 = 0.2\%,$

   and the 10-day std dev of the excess returns on the market index is

   $\sigma_{10} = 0.2 \times \sqrt{10/250} = 0.2/5 = 4\%$

3. Hence, the 1% 10-day equity VaR is

   $2.8m \times (2.32635 \times 4\% - 0.2\%) = \254,951$

   **Note:** You can also use the $\beta 
$$\beta = \frac{1}{3} \times 1.2 + \frac{2}{3} \times 0.8 = 0.93$$ to calculate a % VaR then $\times \$3m \Rightarrow$ same dollar VaR as above.


---

### Historical Equity VaR

- Historical simulation gives equity VaR based on:
  - A **historical time series** on the market index daily returns (or P&L)
  - The **current estimate** $\hat{\beta}$ of the portfolio beta

- For any holding period $h$ and significance level $\alpha$ we again use

  $\text{Equity VaR}_{h,\alpha} = \hat{\beta} \times \text{Market VaR}_{h,\alpha}$

- But now the market VaR is calculated using historical simulation


### Decomposition of Total VaR into Equity and Specific VaR

- In the context of market risk, the terms **specific** and **idiosyncratic** are used interchangeably

- Recall from slide 14 that, if $\text{Cov}(X, \varepsilon) = 0$:

  $\text{Total Variance} = \text{Equity Variance} + \text{Specific Variance}$

- Hence, in the normal VaR model, where VaR is a multiple of the **square root** of the variance, we can calculate specific VaR as:

  $\text{Specific VaR} = \sqrt{\text{Total VaR}^2 - \text{Equity VaR}^2}$

- We use the same equation to find the specific VaR in the **historical VaR model**

## 6.3 Equity VaR with Multiple Risk Factors
## 6.4 VaR for International Equity Portfolios
## 6.5 VaR for Commodity Portfolios