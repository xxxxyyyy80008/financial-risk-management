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

   **Note:** You can also use the $\beta$ 

$$\beta = \frac{1}{3} \times 1.2 + \frac{2}{3} \times 0.8 = 0.93$$ 

to calculate a % VaR then $\times 3m \Rightarrow$ same dollar VaR as above.


---

### Historical Equity VaR

- Historical simulation gives equity VaR based on:
  - A **historical time series** on the market index daily returns (or P&L)
  - The **current estimate** $\hat{\beta}$ of the portfolio beta

- For any holding period $h$ and significance level $\alpha$ we again use

$$\text{Equity VaR}_{h,\alpha} = \hat{\beta} \times \text{Market VaR}_{h,\alpha}$$

- But now the market VaR is calculated using historical simulation


### Decomposition of Total VaR into Equity and Specific VaR

- In the context of market risk, the terms **specific** and **idiosyncratic** are used interchangeably

- Recall from slide 14 that, if $\text{Cov}(X, \varepsilon) = 0$:

  $\text{Total Variance} = \text{Equity Variance} + \text{Specific Variance}$

- Hence, in the normal VaR model, where VaR is a multiple of the **square root** of the variance, we can calculate specific VaR as:

  $\text{Specific VaR} = \sqrt{\text{Total VaR}^2 - \text{Equity VaR}^2}$

- We use the same equation to find the specific VaR in the **historical VaR model**


## 6.3 Equity VaR with Multiple Risk Factors

### **Multiple Risk Factors for Equity Portfolios**

*   Large linear portfolios with equity exposure may contain shares, and/or exchange traded funds (ETFs), index funds, stock futures and/or index futures
*   Risk factors include different types of market index (e.g. **small, medium, large cap indices**), and/or sector-specific indices (e.g. **tech stock index, pharmaceutical stock index**) and/or drivers of economic value
*   For instance, risk factors for a portfolio of large international oil company shares (Shell, BP, Texaco, ...):
    *   the exchange rate for each country
    *   a large cap stock index for each country
    *   the oil price in domestic currency


---

### **Mapping Equity Portfolios to Risk Factors**

*   Risk factor mapping is based on the **General Linear Model (GLM)**:

$$ Y_t = \alpha + \beta_1 X_{1t} + \beta_2 X_{2t} + ...... + \beta_m X_{mt} + \varepsilon_t, $$

$$ \varepsilon_t \sim i.i.d (0, \sigma^2), \quad t = 1, ..., T $$

or, in matrix form, $\mathbf{y} = \boldsymbol{\alpha} + \mathbf{X}\boldsymbol{\beta} + \boldsymbol{\varepsilon}$

*   Here $\boldsymbol{\beta} = (\beta_1, ..., \beta_m)'$ are the **sensitivities** to returns on different equity risk factors $\mathbf{X} = (X_{ij})$ for $i = 1, ..., T$ and $j = 1, ...., m$

*   The OLS estimates $\hat{\boldsymbol{\beta}} = (\mathbf{X}'\mathbf{X})^{-1}\mathbf{X}'\mathbf{y}$ are obtained using historical data on (i) the risk factor returns (or P&L) for $\mathbf{X}$ and (ii) portfolio returns (or P&L) for $\mathbf{y}$


---

### **Systematic Variance in the Multi-Factor Model**

*   Estimating the GLM yields our risk factor mapping – which can ignore the constant:

$$ \hat{Y}_t = \sum_{i=1}^{m} \hat{\beta}_i X_{it} = \hat{\boldsymbol{\beta}}' \mathbf{x}_t $$

where $\mathbf{x}_t = (X_{1t}, ...., X_{mt})'$

*   Applying the variance operator we have

$$ \mathbb{V}[\hat{Y}] = \sum_{i=1}^{m} \hat{\beta}_i^2 \mathbb{V}[X_i] + 2 \sum_{i=1}^{m} \sum_{j>i}^{m} \hat{\beta}_i \hat{\beta}_j \text{Cov}[X_i, X_j] = \hat{\boldsymbol{\beta}}' \mathbf{V} \hat{\boldsymbol{\beta}} $$

where $\mathbf{V}$ denotes the covariance matrix of the risk factor returns

---

### **How to Scale a Covariance Matrix**

*   Typically we use daily or weekly returns in our risk factor mapping, and we **scale the covariance matrix using $h$** (not $\sqrt{h}$), e.g.
    *   Risk factor mapping uses daily returns $\Rightarrow h$-day covariance matrix $= h\mathbf{V}$
    *   Risk factor mapping uses weekly returns $\Rightarrow h$-day covariance matrix $= \frac{h}{5}\mathbf{V}$

*   For example, if $Y$ and $X_i$ are **daily returns** and $\mu_h = 0$ we have:

$$ \text{Equity VaR}_{h,\alpha} = \Phi^{-1}(1 - \alpha) \sqrt{h\hat{\boldsymbol{\beta}}'\mathbf{V}\hat{\boldsymbol{\beta}}} $$

---

### **Example: Equity VaR with Two Risk Factors**

An investor buys \$7m of shares in small cap stocks with portfolio beta of 2 relative to a small cap index risk factor, and \$3m worth of shares in large cap stocks with a portfolio beta – relative a large cap index risk factor – of 1.25. Find the dollar betas for each risk factor

Suppose the volatilities of the small cap and large cap risk factors are 20% and 10% respectively, and their correlation is 0.7

(a) What is the 1% 1-day total equity VaR in \$ terms?
(b) Find the small cap VaR and the large cap VaR and sum them
(c) Why is the sum of the two equity VaRs greater than the total equity VaR?


### **Solution (By Hand)**

**(a) What is the 1% 1-day total equity VaR in $ terms?**

*   Dollar betas are $7 \times 2\text{m}$ and $3 \times 1.25\text{m}$, i.e. **$\$14\text{m}$** for small cap and **$\$3.75\text{m}$** for large cap

*   Volatilities are 20% and 10% with correlation 0.7, so the portfolio variance in annual terms, in $\$m$ is

$$ 14^2 \times 0.2^2 + 3.75^2 \times 0.1^2 + 2 \times 14 \times 3.75 \times 0.7 \times 0.2 \times 0.1 = \mathbf{9.450625} $$

*   Hence, the 1-day stdev is $\sqrt{\frac{9.450625}{250}} = \$0.194429\text{m}$, or **$\$194,429$**

*   Using the normal VaR model, we have a 1% 1-day VaR of
    $$ 2.32635 \times \$194,429 = \mathbf{\$452,309} $$


(b) Find the small cap VaR and the large cap VaR and add them

*   Small cap VaR = $2.32635 \times \$14 \times 0.2 \times \sqrt{\frac{1}{250}} = \$0.411967\text{m}$
*   Large cap VaR = $2.32635 \times \$3.75 \times 0.1 \times \sqrt{\frac{1}{250}} = \$0.55174\text{m}$
*   Sum of VaR = $\$411,967 + \$55,174 = \$467,141$

(c) Why is the sum of equity VaRs greater than total equity VaR?

*   Sum of VaRs = $\$467,141 > \$425,309 = \text{Total Equity VaR}$ because **the portfolio is diversified** i.e. the correlation between small cap and large cap is less than one


## 6.4 VaR for International Equity Portfolios


---

### **Currency (or Foreign Exchange) Risk**

Currency (or foreign exchange) risk is the uncertainty in the value of an investment due to fluctuations in exchange rates

*   This risk arises from trading international assets where the foreign currency differs from the domestic one
*   Foreign exchange is commonly abbreviated to FX, or forex
*   This risk affects:
    *   Exporters of products and services
    *   Investors buying/selling assets traded in another country
    *   A multinational corporation

---

### **Risk Factors for an International Stock Portfolio**

*   Suppose a UK hedge fund holds a portfolio containing UK, US and European stocks
*   There are three equity risk factors and two FX risk factors, because each country portfolio is mapped to a broad market index, and the foreign portfolios also have an FX risk factor
*   Since the hedge fund is in the UK:
    *   UK portfolio: 1 risk factor $\rightarrow$ FTSE100
    *   US portfolio: 2 risk factors $\rightarrow$ S&P500 and USD/GBP rate
    *   European portfolio: 2 risk factors $\rightarrow$ STOXX50 and GBP/EUR rate

---

### **Nominal and Percentage FX Betas**

*   To buy foreign stocks we convert domestic to foreign currency
*   For instance, suppose a UK hedge fund wants to buy £5m worth of US stocks and £3m worth of European stocks
*   First it must convert 5m GBP into USD and 3m GBP into EUR
*   Now, even if the US and EUR stock prices didn't change at all, the hedge fund could make or lose money on these FX rates
*   Percentage FX betas are always 1
*   And the nominal FX betas are the amount of domestic currency needed to buy the stocks at the time of the investment – in this case the nominal betas are £5m and £3m respectively

---

### **Illustration**

*   Suppose the USD/GBP FX rate is 1 USD = 0.8 GBP when a fund invests £5m, which is $\$5/0.8 = \$6.25\text{m}$ in US stocks
*   Now suppose USD strengthens by 12.5% so that 1 USD is now equivalent to $0.8 \times 1.125 = 0.9$ GBP
*   Even if the fund hadn't yet bought the stocks it makes a 12.5% return just from the change in the FX rate, because the £5m now converts back to $6.25 \times 0.9 = \text{£}5.625\text{m}$ and $(5.625 - 5)/5 = 12.5\%$
*   So the 12.5% increase in USD vs GBP translates into a 12.5% return, regardless of any stock price movements
*   This shows that the % FX beta is always 1 – so the $ beta is the $ amount invested in that country

---

### **Example**

**Systematic VaR with 1 Equity and 1 FX Risk Factors**

*   Suppose a US investor buys $2m of shares in a portfolio of UK stocks and the portfolio's equity beta is 1.5
*   Suppose the FTSE 100 and USD/GBP volatilities are 15% and 20% respectively, and their correlation is 0.3
*   Calculate the 1% 10-day systematic VaR in USD, based on the normal VaR model
*   Decompose the total systematic VaR of the previous example into FX and equity VaR components
*   Compare the sum of the FX VaR and the equity VaR with the total systematic VaR and comment on your result
*   Express your answers in both % and $ terms


---

### **Solution (By Hand)**

1.  The risk-factor mapping is $\hat{Y} = 1.5 X_1 + X_2$ where $Y$ is the portfolio return, $X_1$ is the return on the FTSE 100 and $X_2$ is the return on USD/GBP exchange rate
2.  Using the square-root-of-time rule, the 10-day standard deviations of $X_1$ and $X_2$ are $0.15/5 = 0.03$ and $0.2/5 = 0.04$, respectively
3.  Hence the systematic 10-day variance is:

$$ \mathbb{V}[\hat{Y}] = 1.5^2 \times 0.03^2 + 0.04^2 + 2 \times 1.5 \times 0.3 \times 0.03 \times 0.04 = 0.00471 $$

4.  Since we use percentage betas the 1% 10-day systematic VaR is expressed as a % of the portfolio value – namely

$$ 2.3263 \times \sqrt{0.00471} = 15.9571\% $$

5.  The 1% 10-day systematic VaR is $15.9571\% \times \$2m = \mathbf{\$319,142}$

---

### **Equity and FX VaR with Multiple Risk Factors**

*   The risk factor mapping is

$$ \hat{Y} = \sum_{i=1}^{n} \hat{\beta}_i X_i = \left( \hat{\beta}_1 X_1 + \dots + \hat{\beta}_m X_m \right) + \left( X_{m+1} + \dots + X_{2m-1} \right) $$

    where $X_1, ..., X_m$ are returns (or P&L) on $m$ equity indices and (assuming the investor holds domestic stocks) $X_{m+1}, ..., X_{2m-1}$ are the returns (or P&L) on the corresponding $m-1$ FX rates

*   Taking variances yields

$$ \mathbb{V}[\hat{Y}] = \hat{\boldsymbol{\beta}}' \mathbf{V} \hat{\boldsymbol{\beta}} $$

    where $\mathbf{V}$ is the covariance matrix of the risk factor returns and

$$ \hat{\boldsymbol{\beta}} = \left( \hat{\beta}_1, ..., \hat{\beta}_m, 1, ..., 1 \right)' = \left( \hat{\boldsymbol{\beta}}_{EQ}, \mathbf{1} \right)' $$


---

### **Partitioning the Risk Factor Covariance Matrix**

Partition the large risk factor covariance matrix into four as:

$$ \mathbf{V} = \left[ \begin{array}{c|c} \mathbf{V}_{EQ} & \mathbf{V}_{EQ-FX} \\ \hline \mathbf{V}_{FX-EQ} & \mathbf{V}_{FX} \end{array} \right] $$

where:
*   $\mathbf{V}_{EQ}$ is the $m \times m$ covariance matrix of equity risk factor returns
*   $\mathbf{V}_{FX}$ is the $(m-1) \times (m-1)$ covariance matrix of FX risk factor returns, and
*   The covariances between equity and FX risk factors are placed in the $(m-1) \times m$ and $m \times (m-1)$ matrices $\mathbf{V}_{FX-EQ}$ and $\mathbf{V}_{EQ-FX}$
---

### **Decomposing Systematic VaR into Equity and FX VaR**

Assuming returns are daily and normal i.i.d. we have:

$$ \text{Total Systematic VaR}_{h,\alpha} = \Phi^{-1}(1 - \alpha) \sqrt{h \hat{\boldsymbol{\beta}}' \mathbf{V} \hat{\boldsymbol{\beta}}} $$

This may be decomposed into two component VaRs:

$$ \text{Equity VaR}_{h,\alpha} = \Phi^{-1}(1 - \alpha) \sqrt{h \hat{\boldsymbol{\beta}}_{EQ}' \mathbf{V}_{EQ} \hat{\boldsymbol{\beta}}_{EQ}} $$

and

$$ \text{FX VaR}_{h,\alpha} = \Phi^{-1}(1 - \alpha) \sqrt{h \mathbf{1}' \mathbf{V}_{FX} \mathbf{1}} $$

where $\mathbf{V}_{EQ}$ and $\mathbf{V}_{FX}$ are the equity and FX portions of the covariance matrix, respectively.

---

### **Example**

**Systematic VaR with 2 Equity and 1 FX Risk Factors**

*   Suppose a US investor buys \$2m of shares in a portfolio of UK stocks with a beta of **1.5** and \$3m in US with a beta of **2**
*   As before, the FTSE 100 and USD/GBP volatilities are **15%** and **20%** respectively, and their correlation is **0.3**
*   Now suppose the S&P500 volatility is **10%** and the correlation between S&P500 returns and FTSE 100 returns is **0.8**
*   Suppose the correlation between S&P500 returns and the USD/GBP exchange rate is **0.5**
*   Calculate the 1% 10-day systematic VaR in US dollars, based on the normal VaR model, and decompose this total systematic VaR into equity and FX VaR components


---

### **Total Systematic VaR Disaggregation into Component VaRs**

*   Disaggregation of **total systematic VaR** allows us to attribute this total to an **equity VaR** component and an **FX VaR** component
*   We may also attribute total equity VaR and/or total FX VaR to component VaR for different **countries**,
*   The total VaR takes account of **diversification** which arises because risk factors have correlations less than one, and so

$$ \text{Sum of Component VaRs} \ge \text{Total VaR} $$

    for instance, $\text{Equity VaR} + \text{FX VaR} \ge \text{Total Systematic VaR}$
*   Similarly, the **sum of equity VaR components** such as US, UK and European equity VaRs is $\ge$ **total equity VaR**


### **Total Systematic VaR Disaggregation into Marginal VaRs**

*   There is a different way to decompose total systematic that is **always additive**, and that is to use **marginal VaRs** in place of component VaRs
*   Marginal VaR measures how much the total systematic VaR of a portfolio changes **after a small increment in the exposure** to a particular systematic risk factor, holding all other exposures constant – so marginal VaR shows a risk factor’s **incremental** contribution to total systematic risk
*   Total systematic VaR **is** the sum of marginal VaRs, after weighting each marginal VaR it’s risk factor sensitivity
*   For instance,

$$ \text{Total Equity VaR} = \sum_{i=1}^{m} \beta_i \times \text{Marginal VaR of Equity Factor}_i $$



## 6.5 VaR for Commodity Portfolios

---

### **Commodity Risk**

Commodity risk is the uncertainty in the market value of a portfolio due to changes in commodity risk factors

*   Commodities are typically categorized into four main groups: **agricultural, energy, metals, and livestock**
*   Here we cover **linear** commodity portfolios, which means a collection of positions on spot commodities and corresponding futures contracts – no options!
*   Commodity risk affects companies that buy and sell commodities, such as airlines (buy jet oil), refineries (buy crude oil, sell refined products)
*   These companies are exposed to spot price risk, which they usually hedge using futures contracts
*   Hedged portfolios typically contain **long (buy)** and **short (sell)** positions – no need to use **repo**

---

### **Commodity Risk Factors**

*   To capture exposures at different times in the future we need spot prices and a whole **term structure** of commodity futures prices
*   This is similar to cash flow portfolios – except that time series data on interest rates of different maturities can be downloaded directly, whereas time series data on futures with fixed maturities need to be constructed using **linear interpolation**
*   This way, the **constant-maturity** futures prices are calculated as a weighted sum of the prices of the two **traded contracts** with maturities **either side** the target constant maturity


---

### **Linear Interpolation Between Two Points**

$$ P^* = \frac{d_2 P_1 + d_1 P_2}{d_1 + d_2} $$

---

### **Linear Interpolation for Constant Maturity Futures Prices**

*   For example, suppose today is 1 September and I want to construct a 1-month (30-day) futures price
*   There are two contracts whose maturities are either side of 30 days – the September futures which expires on 23 September and the October futures which expires on 21 October
*   Let $P_1$ be the price of of the September futures and $P_2$ be the price of the October futures
*   The September futures expires in 22 days and the October futures expires in 50 days
*   22 is closer to 30 than 50 is, so we need to place more weight on $P_1$ than $P_2$. Under linear interpolation our 30-day futures price will be

$$ 22/28 \times P_1 + 8/28 \times P_2 $$

---

### **Commodity Futures Term Structures**


---

### **Commodity Risk Factors**

Select $n$ vertices of constant maturities as risk factors, with prices

$$ P_{1t}, ... P_{nt} $$

---

### **Risk Factor Mapping**

*   Consider a position of size $\$N_i$ on a futures with maturity $T_i$
*   From historical P&L data $\Delta P_{it}$ we estimate its variance $\sigma_i^2$
*   As we did with cash flows in Topic 5, we now select two vertices with maturities straddling $T_i$, say $T_1 \le T_i \le T_2$
*   Historical data on $\Delta P_{1t}$ and $\Delta P_{2t}$ gives estimates $\sigma_1^2, \sigma_2^2$ and $\sigma_{12}$
*   Then we find $p$, with $0 \le p \le 1$ such that

$$ \sigma_i^2 = \sigma_1^2 p^2 + \sigma_2^2 (1-p)^2 + 2p(1-p)\sigma_{12} $$

*   Finally, we map $\$pN_i$ to the vertex at $T_1$ and $\$(1-p)N_i$ to the vertex at $T_2$

---

### **Calculating VaR – One Underlying**

*   After mapping every position in the portfolio, and including spot positions which do not require mapping, we have a representation

$$ \mathbf{p} = (p_0, p_1, p_2, ....p_n)' $$

    of spot and futures on the same underlying commodity
*   From historical daily data on $\Delta P_{0t}, \Delta P_{1t}, ..., \Delta P_{nt}$ we:
    *   Estimate the covariance matrix $\mathbf{V}$, then set

$$ \text{Normal VaR}_{h,\alpha} = \Phi^{-1}(1-\alpha)\sqrt{h \mathbf{p}' \mathbf{V} \mathbf{p}} $$

    *   Create a time series of historical P&L for the position $\mathbf{p}$ as $(\Delta P_{0t}, \Delta P_{1t}, ..., \Delta P_{nt})\mathbf{p}$ and set:

$$ \text{Historical VaR}_{h,\alpha} = -1 \times \sqrt{h} \times \alpha\text{-quantile of this time series} $$


---

### **Commodity Trading**

*   **Commodity trading houses** manage large portfolios of futures across energy, metals, and agricultural markets
*   Trade both spot and futures markets to arbitrage, hedge, or speculate on price movements
*   Actively manage **basis risk**, **calendar spreads**, and **cross-commodity exposures**
*   Use complex multi-factor VaR models and **stress testing** to manage exposures across multiple correlated commodity and FX markets

---

### **Commodity Trading Houses in London**

*   **Glencore**: London office is central to its metals risk management and compliance with London Metal Exchange (LME) positions and margining
*   **Marex**: London office runs risk systems across agriculture, energy, and metals, including clearing services and VaR
*   **ED&F Man**: London office leads enterprise risk, credit risk, and hedging strategies for soft products – sugar, coffee, cocoa, cotton, orange juice etc
*   **Sucden Financial**: London office is core to its clearing, risk, and client hedging solutions in softs and metals
*   **Cargill**: London office hosts teams for risk management, compliance, and policy

