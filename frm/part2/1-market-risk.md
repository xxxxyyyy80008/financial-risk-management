### **Reading 63: Estimating Market Risk Measures: An Introduction and Overview**
#### **Key Concepts & Definitions**
*   **Geometric Returns**: Account for the compounding effects of investment returns, providing a more precise measure of investment performance over time than arithmetic returns.
*   **Coherent Risk Measures**: Must satisfy four properties: subadditivity, positive homogeneity, translation invariance, and monotonicity. Expected Shortfall (ES) is coherent; VaR is **not** (due to lack of subadditivity).
*   **Skewness & VaR**: A negatively skewed distribution has a long left tail. For a long position, VaR will be higher than for a short position because of the higher probability of extreme losses.
*   **Standard Error of VaR**: Measures the precision of the VaR estimate. It depends on the probability density function $f(q)$, sample size $n$, and probability level $p$.

#### **Key Formulas**
*   **Parametric VaR (Normal Distribution)**:  

$$VaR(\alpha) = (-\mu_{r} + \sigma_{r} \times Z_{\alpha}) \times P_{t-1}$$ 

    Or for P/L:  
    
    $VaR = -\mu_{P/L} + \sigma_{P/L}Z_{\alpha}$

*   **Lognormal VaR**: 
    $$VaR = P \times (1 - e^{\mu - \sigma Z_{\alpha}})$$
*   **Standard Error of a Quantile (VaR)**: 
    $$se(q) = \frac{\sqrt{p(1-p)/n}}{f(q)}$$

---

### **Reading 64: Non-parametric Approaches**
#### **Key Concepts & Definitions**
*   **Historical Simulation (HS)**: Relies on actual historical data. **Drawbacks**: Discreteness of data (cannot estimate VaR between data points, e.g., 95.5%), ghost/shadow effects, and assumes past distribution equals future distribution.
*   **Bootstrapping**: Resampling *with replacement* from an existing dataset to estimate the distribution of a statistic. Assumes the empirical distribution represents the true population.
*   **Non-parametric Density Estimation**: Smooths historical data points to allow VaR estimation at non-discrete confidence levels, solving the discreteness drawback of basic HS.
*   **Age-Weighted (Hybrid) HS**: Assigns more weight to recent observations and less to distant ones using a decay factor ($\lambda$).

#### **Key Formulas**
*   **Age-Weighted HS Weight**: 
    $$w_i = \frac{\lambda^{i-1}(1-\lambda)}{1-\lambda^n}$$ 
    (Where $\lambda$ is decay factor, $i$ is days ago, $n$ is total days in window)
*   **Volatility-Adjusted Return**: 

$$r^*_{t,i} = \left( \frac{\sigma_{T}}{\sigma_{t}} \right) r_{t,i}$$ 

    (Adjusts historical returns to reflect current volatility $\sigma_T$) 

---

### **Reading 65: Parametric Approaches (II): Extreme Value**
#### **Key Concepts & Definitions**
*   **Extreme Value Theory (EVT)**: Focuses exclusively on the tail behavior of the distribution. Does not assume a unique distribution for the entire range of values.
*   **GEV (Generalized Extreme Value)**: Combines Gumbel ($\xi=0$), Fréchet ($\xi>0$, heavy-tailed), and Weibull ($\xi<0$, light-tailed) distributions.
*   **POT (Peaks-Over-Threshold)**: More data-efficient than GEV. Models exceedances over a high threshold $u$. Converges to the **Generalized Pareto Distribution (GPD)**.
*   **Tail Dependence**: Clustering of high-severity risks (extreme events).

#### **Key Formulas**
*   **POT VaR**: 
    $$VaR = u + \frac{\beta}{\xi} \left[ \left( \frac{N}{N_u}(1-\alpha) \right)^{-\xi} - 1 \right]$$
*   **POT Expected Shortfall (ES)**: 
    $$ES = \frac{VaR}{1-\xi} + \frac{\beta - \xi u}{1-\xi}$$

---

### **Reading 66: Backtesting VaR**
#### **Key Concepts & Definitions**
*   **Backtesting**: Comparing historical VaR forecasts to actual (realized) returns to verify model adequacy.
*   **Basel Traffic Light Approach**:
    *   **Green Zone (0-4 exceptions)**: Model is accurate. Multiplier = 3.
    *   **Yellow Zone (5-9 exceptions)**: Model may be flawed. Multiplier increases progressively from 3.4 to 3.85.
    *   **Red Zone (10+ exceptions)**: Model is rejected. Multiplier = 4.
*   **Reasons for Exceptions**: Model lacks basic integrity, intraday trading, bad luck, potential for improving model accuracy.

#### **Key Formulas**
*   **Binomial Test Statistic (for exceptions)**: 
    $$Z = \frac{x - pT}{\sqrt{p(1-p)T}}$$ 
    (Where $x$ = observed exceptions, $p$ = VaR significance level, $T$ = number of days)

---

### **Reading 67: VaR Mapping**
#### **Key Concepts & Definitions**
*   **VaR Mapping**: Replacing complex portfolio positions with exposures to selected primitive risk factors to reduce dimensionality and avoid rank correlation problems. Must preserve both **market value** and **market risk**.
*   **Mapping Approaches**: Principal Mapping (simplest, maps to average life), Duration Mapping, Cash Flow Mapping (most accurate, decomposes into zero-coupon cash flows).
*   **Tracking Error VaR**: Measures the maximum potential deviation between a portfolio and its benchmark under normal market conditions.
*   **Forward Contracts**: Economically equivalent to buying the asset and holding it for one period vs. entering a forward contract to buy it in one period.

#### **Key Formulas**
*   **Tracking Error VaR**: 
    $$TE\text{-}VaR = \alpha\sqrt{(x - x_0)'\Sigma(x - x_0)}$$
*   **Variance Improvement**: 
    $$1 - \left( \frac{TE\text{-}VaR}{\text{Absolute Risk of Index}} \right)^2$$
*   **Forward Exchange Rate**: 
    $$F = S \times \frac{1 + r_{domestic}}{1 + r_{foreign}} \quad \text{or} \quad F_t = S_t e^{(r-y)\tau}$$

---

### **Reading 68: Messages from the Academic Literature on Risk Measurement for the Trading Book**
#### **Key Concepts & Definitions**
*   **Intra-horizon VaR**: Combines VaR over the regulatory horizon with P&L fluctuations within the short term. Divergence from standard VaR is larger for derivative exposures.
*   **Liquidity Risk**:
    *   *Exogenous*: Normal variation of bid/ask spreads (beyond trader's control).
    *   *Endogenous*: Impact on prices of the liquidation of a specific position. Most troublesome for complex trading positions.
*   **Expected Shortfall (ES)**: Averages losses that exceed the VaR threshold. Coherent (sub-additive) and reduces the influence of a single confidence level.

#### **Key Formulas**
*   **Leverage**: 
    $$L = \frac{\text{Assets}}{\text{Equity}} = \frac{1}{\lambda} \times \frac{A}{VaR}$$ 
    *(Where $\lambda$ is the proportion of capital to be held per total VaR)*

---

### **Reading 69: Correlation Basics: Definitions, Applications, and Terminology**
#### **Key Concepts & Definitions**
*   **Correlation Swap**: Pays the difference between realized and fixed correlation.
*   **Quanto Option**: Allows a domestic investor to receive payoff in domestic currency at a fixed exchange rate, hedging currency risk.
*   **Systemic vs. Correlation Risk**: Highly dependent. During crises, correlations tend to approach 1 (assets fall together), increasing correlation risk.
*   **Concentration Ratio**: Lower ratio = higher diversification = lower default risk of the creditor.

#### **Key Formulas**
*   **Correlation Swap Payoff**: 
    $$\text{Payoff} = N \times (\rho_{realized} - \rho_{fixed})$$
*   **Realized Correlation**: 
    $$\rho_{realized} = \frac{2}{n^2 - n} \sum_{i>j} \rho_{i,j}$$
*   **Joint Probability of Default**: 
    $$PD_{AB} = \rho_{AB}\sqrt{PD_A(1-PD_A)PD_B(1-PD_B)} + PD_A \times PD_B$$

---

### **Reading 70: Empirical Properties of Correlation: How Do Correlations Behave in the Real World?**
#### **Key Concepts & Definitions**
*   **Mean Reversion**: The tendency of a variable (like correlation or interest rates) to return to its long-term mean.
*   **Autocorrelation**: The degree to which a variable is correlated to its past values.
*   **Relationship**: $\text{Mean Reversion Rate} + \text{Autocorrelation Rate} = 1$
*   **Distributions**: Equity correlation distribution is best modeled by the **Johnson SB** distribution.

#### **Key Formulas**
*   **Mean Reversion Model**: 
    $$S_t - S_{t-1} = a(\mu - S_{t-1}) \implies S_t = a(\mu - S_{t-1}) + S_{t-1}$$

---

### **Reading 71: Financial Correlation Modeling—Bottom-Up Approaches**
#### **Key Concepts & Definitions**
*   **Copula**: A function that joins multiple univariate marginal distributions to form a single multivariate distribution, preserving the correlation structure.
*   **Gaussian Copula**: Maps marginal distributions to a standard multivariate normal distribution. Widely used but fell into disgrace during the 2007 crisis due to mismanagement of tail correlations.
*   **Cholesky Decomposition**: Used to derive correlated default times in simulations by transforming independent standard normal variables into correlated ones.

#### **Key Formulas**
*   **Gaussian Default Time Copula**: 
    $$C_{GD}[Q_1(t),..., Q_n(t)] = M_n[N^{-1}(Q_1(t)),..., N^{-1}(Q_n(t)); \rho_M]$$

---

### **Reading 72: Empirical Approaches to Risk Metrics and Hedging**
#### **Key Concepts & Definitions**
*   **TIPS**: Treasury Inflation-Protected Securities. Principal adjusts with inflation. Do *not* provide an inflation risk premium.
*   **DV01 (Dollar Value of 01)**: Change in bond price for a 1bp change in yield.
*   **Principal Component Analysis (PCA)**: Reduces dimensionality. PCs are **uncorrelated (orthogonal)** and capture maximum variance. Highly practical for empirically-based hedges for large portfolios.

#### **Key Formulas**
*   **Hedge Ratio**: 
    $$HR = \frac{DV01_{\text{initial position}}}{DV01_{\text{hedging tool}}}$$

---

### **Reading 73: The Science of Term Structure Models**
#### **Key Concepts & Definitions**
*   **Arbitrage-Free Models**: Match current market prices (initial term structure). Used for pricing derivatives.
*   **Equilibrium Models**: Start with economic assumptions (drift, risk premium). E.g., Vasicek, CIR.
*   **OAS (Option-Adjusted Spread)**: Constant spread added to risk-neutral rates to make model price = market price. If options expire, OAS = Z-spread.
*   **Convexity**: Measures the curvature of the price-yield relationship. Decreases bond yields in theory and practice. Securities with greater convexity perform better when yields change *a lot*.

#### **Key Formulas**
*   **Forward Rate from Spot Rates**: 
    $$(1 + s_2)^2 = (1 + s_1)(1 + y_1)$$

---

### **Reading 74: The Evolution of Short Rates and the Shape of the Term Structure**
*(Note: Concepts overlap with Readings 75 & 76 in the text)*
#### **Key Concepts & Definitions**
*   **Model 1**: No drift, normal distribution.
*   **Model 2**: Constant drift.
*   **Vasicek Model**: Mean-reverting, normal distribution. Allows negative rates.
*   **CIR Model**: Mean-reverting. Standard deviation is proportional to $\sqrt{r}$. **Prevents negative interest rates** (volatility = 0 when $r=0$, drift is positive).

#### **Key Formulas**
*   **Vasicek Model Dynamics**: 
    $$dr = k(\theta - r)dt + \sigma dw$$ 
    (Where 
    $$\theta = r_{\infty} + \frac{\lambda}{k}$$ 
    is the risk-neutral long-term mean)
*   **Half-Life of Mean Reversion**: 
    $$\text{Half-Life} = \frac{\ln(2)}{k}$$
*   **Expected Short Rate after $T$ years (Vasicek)**: 
    $$E[r_T] = r_0 e^{-kT} + \theta(1 - e^{-kT})$$
*   **Standard Deviation of Terminal Distribution (Vasicek)**: 
    $$\sigma_T = \sqrt{\frac{\sigma^2}{2k}(1 - e^{-2kT})}$$

---

### **Reading 75: The Art of Term Structure Models: Drift**
#### **Key Concepts & Definitions**
*   **Time-Dependent Drift**: Represents some combination of the risk premium and expected changes in the short-term rate. Varies from date to date.

---

### **Reading 76: The Art of Term Structure Models: Volatility and Distribution**
#### **Key Concepts & Definitions**
*   **Time-Dependent Volatility**: Volatility of the short-rate depends on time.
*   **CIR Model Property**: Basis-point volatility equals zero when the short rate is zero, joined with the condition that drift is positive when the rate is zero, guaranteeing the short rate cannot become negative.
*   **Black-Karasinski Model**: A lognormal model with mean reversion. Allows volatility, mean reversion, and short rate’s central tendency to depend on time (making it arbitrage-free). Assumes the natural logarithm of the short rate is normally distributed.

#### **Key Formulas**
*   **CIR Model**: 
    $$dr = k(\theta - r)dt + \sigma\sqrt{r}dw$$
*   **Black-Karasinski Model**: 
    $$d[\ln(r)] = k(t)[\ln\theta(t) - \ln(r)]dt + \sigma(t)dw$$

---

### **Reading 77: Volatility Smiles**
#### **Key Concepts & Definitions**
*   **Volatility Smile**: Plot of implied volatility against strike price for options with the same maturity.
*   **Put-Call Parity**: Implied volatility of a European call equals the implied volatility of a European put if strike and maturity are identical.
*   **Volatility Surface**: Combination of volatility smile (strike price) and volatility term structure (time to maturity).
*   **Equity Options Smirk**: Caused by leverage effect (firm value drops $\rightarrow$ leverage increases $\rightarrow$ equity becomes riskier $\rightarrow$ volatility increases).

#### **Key Formulas**
*   **Put-Call Parity**: 
    $$p + S_0 e^{-qT} = c + K e^{-rT}$$
*   **Dollar Error Pricing**: 
    $$P_{BS} - P_{mkt} = C_{BS} - C_{mkt}$$

---

### **Reading 78: Fundamental Review of the Trading Book (FRTB)**
#### **Key Concepts & Definitions**
*   **FRTB Core Changes**:
    1. Replaces **VaR** with **Expected Shortfall (ES)** at **97.5% confidence** (better captures tail risk).
    2. Introduces **Liquidity Horizons** (10, 20, 60, 120, 250 days) based on asset tradability.
    3. Strict boundary between **Trading Book** (Mark-to-Market) and **Banking Book** (Historical Cost) to eliminate regulatory arbitrage.
    4. Backtesting uses **1-day VaR** (because 10-day ES and Stressed ES are impossible to backtest directly).
*   **Standardized Approach (SA) Components**:
    1. Sensitivities-based method (Delta, Vega, Curvature risks).
    2. Default risk charge.
    3. Residual risk add-on.
*   **Incremental Risk Charge (IRC)**: Recognizes **Credit Spread Risk** and **Jump-to-Default Risk**.

#### **Key Rules / Thresholds**
*   **Stressed Period**: 250-day window of stressed market conditions.
*   **Internal Models Approach (IMA) Exit**: If backtesting exceeds **12 exceptions at 99%** or **30 exceptions at 97.5%** over 12 months, the bank must revert to the Standardized Approach.
*   **Trading Book Allocation Criteria**: Bank must be able to physically manage risks on the trading desk, and day-to-day price fluctuations must affect the bank's equity/solvency.