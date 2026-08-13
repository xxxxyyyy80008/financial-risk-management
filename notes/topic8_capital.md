# Study Notes on **Financial Risk Management** by Professor Carol Alexander 

Original resource: [youtube](https://www.youtube.com/watch?v=mXC5yJ5MKwM&list=PL_V1gySvrP_ums2nxs_YuKY5Ufdmhyoh7&index=6)

# Topic 8: Capital Reserves for Market Risk

### **Outline**

1. Balance Sheets and Capital Reserves for Banks
2. Minimum Capital Ratios for Banks
3. Fundamental Review of the Trading Book
4. Validation of Internal Risk Models
5. Statistical Backtests
6. Scenario Analysis and Stress Testing Portfolios
   
## 8.1 Balance Sheets and Capital Reserves for Banks

---

### **Why Must Banks Hold Capital Reserves?**

The Basel Accords require banks to hold minimum levels of capital to cover credit, market, and operational risks, to:

- **Absorb unexpected losses**: enough capital allows banks to continue processing payments in times of stress
- **Maintain confidence**: strong capital reassures customers and markets that banks can meet their obligations
- **Limit risk taking behaviour**: minimum capital ratios prevent banks from taking excessive risks
- **Support financial stability**: a well-capitalized banking system reduces the chance contagion (systemic risk)
  
---

### **Which Other Firms Hold Capital Reserves?**

- **Building societies**: have a **banking book** of deposits and loans; must meet Basel-style **minimum capital ratios**
- **Investment firms**: have a **trading book** regulated using Basel principles; called **Investment Firms Prudential Regime (IFPR)** in UK
- **Insurance companies**: regulated under **Solvency II**; focus on long-term liabilities not trading risks. No banking/trading book division
- **Hedge funds and pension funds**: still have capital requirements, but lighter than Basel IV or Solvency II. No banking/trading book division
- **Central counterparties (CCPs)**: meet strict capital rules under **European Market Infrastructure Regulation (EMIR)**. No banking/trading book division
  
---

### **Accounting Balance Sheets for Banks**

Every bank has an ordinary balance sheet to comply with International Financial Reporting Standards (IFRS) and/or Generally Accepted Accounting Principles (GAAP) – here is a simplified example:

**Assets**
- Cash and reserves held at the central bank
- Loans to customers and other banks
- Investments like corporate or government bonds
- Buildings, equipment, and other property

**Liabilities**
- Customer deposits
- Borrowings from other banks or raised by issuing bonds
- Other obligations such as expenses


---

### **Shareholders' Equity = Assets – Liabilities**

- **Shareholders’ equity** is money raised by bank in initial public offering (IPO) – it is not the current market value of these shares.
- Two types: **common equity** – money from shares sold to ordinary shareholders, and **preference equity** – money from shares sold to preference shareholders.
- **Loss absorption order**:
    1. Holders of bonds (from senior secured to junior unsecured)
    2. Holders of preference shares
    3. Holders of ordinary shares
- Common equity is used to calculate the part of total **regulatory capital** called **Common Equity Tier 1 (CET1)**
- Preference equity may be included in **Additional Tier 1 (AT1)** or **Tier 2** regulatory capital – but only if properly structured.

---

### **Regulatory Balance Sheets for Banks**

- Every bank has a **regulatory** balance sheet used for calculating requirements for how much Tier 1 (CET1 + AT1) and Tier 2 capital it must hold.
- It takes items from the accounting balance sheet and **adjusts them for risk**, recording only **risk-weighted assets**, exposures (what the bank could lose) and **regulatory filters** – e.g. if a bank owns its own shares, they show up as assets in accounting but are not entered here because a bank can’t use its own shares to absorb losses.
- It is not divided as assets vs liabilities; instead it uses a **banking book vs trading book division**:
    - **Banking book** records long-term loans and deposits, usually valued from PV of expected cash flows. Has mainly **credit risk**
    - **Trading book** records assets held for trading, valued at current market prices (**mark-to-market**). Has mainly **market risk**


---


### **Example: Derivatives**

- Banks use derivatives to hedge their risks and for proprietary trading.
- **Notional amounts** are face or reference values used to calculate payments (e.g., £10 million notional on an interest rate swap). They are neither assets nor liabilities, so are not recorded on any balance sheet.
- **Mark-to-market (MtM) P&Ls** of derivative positions **are** entered into both balance sheets:
    - In the accounting balance sheet they are recorded as assets when the P&L is positive or liabilities when the P&L is negative.
    - In the regulatory balance sheet they enter the banking book when they hedge credit risks; and the trading book when they hedge market risks or used for proprietary trading.

---

### **Risk-Weighted Assets (RWA)**

RWA is calculated as total assets adjusted for risk using **weights** that reflect their risk exposure.

**Low-Risk Assets**
- Cash held at central bank: 0%
- Government bonds from stable countries: 0 – 20%
- Short-term interbank loans to high-quality banks: 20%
- Fully secured mortgages with strong collateral: 35%

**High-Risk Assets**
- Corporate loans without good collateral: 100%
- Equity investments or shares: 100%+
- Subordinated or risky bonds: 150%
- Derivatives and off-balance-sheet exposures: variable weights

---

### **Example: Calculating RWA in the Banking Book**

Suppose a bank holds the following assets in its banking book:

- £10 million in cash (0% weight)
- £20 million in government bonds (20% weight)
- £30 million in residential mortgages (35% weight)
- £40 million in corporate loans (100% weight)

$RWA = (10 \times 0\%) + (20 \times 20\%) + (30 \times 35\%) + (40 \times 100\%)$

$= 0 + 4 + 10.5 + 40 = \mathbf{£54.5} \text{ million}$

## 8.2 Minimum Capital Ratios for Banks

---

### **Origins of Global Banking Standards**

*   1975 G10 central banks established the Basel Committee on Banking Supervision (BCBS) to coordinate global regulation
*   Focus on maintaining global financial stability through capital buffers and risk control
*   Member nations implement BCBS rules domestically: UK Capital Adequacy Directive (CAD), EU Capital Requirements Regulation (CRR) and Capital Requirements Directive (CRD), and in the US the Basel Endgame under Regulation Q

---

### **Basel I Accord (1988)**

*   Introduced standardized rules for calculating Risk-Weighted Assets (RWA) in banking book and Minimum Capital Ratios to cover credits risks only
*   To this end, Basel I introduced two capital tiers:
    *   Tier 1 capital is common equity – the money put in by ordinary shareholders – and profits retained rather than paying them out as dividends, and contingent convertible (CoCo) bonds the bank has issued that can be written off or converted to shares if the bank gets into trouble
    *   Tier 2 capital is borrowed money that can still help protect depositors when things go wrong. This may include subordinated bonds the bank has issued, preference equity raised by selling preference shares, and loss reserves, namely money the bank has set aside for bad loans

---

### **Minimum Capital Ratios (Basel I)**

*   Tier 1 capital must be at least 4% of RWA
*   Tier 1 capital + Tier 2 capital must be at least 8% of RWA
*   E.G. 8% of £54.5m = £4.36m in Tier 1 + Tier 2 capital
*   The ratio of capital to RWA is called the minimum capital ratio (MCR)
*   Under Basel I, capital reserves were only required cover credit risks in the banking book

---

### **1996 Market Risk Amendment to Basel I**

*   Extended scope to cover market risk of trading book exposures
*   Banks used either standardized rules for RWA calculation, or approved internal model – at that time also called a Value-at-Risk (VaR) model for minimum capital requirement (MCR):
    *   $MCR_t = \max\{m_1 VaR_t, VaR_t^*\} + s_t$
    *   $VaR_t$ is the 1% 10-day total systematic VaR on day t
    *   $VaR_t^*$ is the average 1% 10-day total VaR over the last 60 days
    *   $s_t$ is an add-on for specific risks not captured by factor model
    *   $3 \le m_1 \le 4$ depending on backtesting results
    *   Then $RWA_t = 12.5 \times MCR_t$

---

### **Basel II (2004)**

*   Introduced the Three-Pillar Framework
    *   Pillar 1 – minimum capital for credit, market and operational risks
    *   Pillar 2 – supervisory review process
    *   Pillar 3 – market discipline through disclosure
*   Allowed standardized rules for RWA to be replaced by Internal Ratings Based (IRB) models for credit minimum capital requirements

---

### **Basel II.5 (2009)**

*   Strengthened capital requirements to cover securitized loans, asset-backed securities, and structured products like Collateralized Debt Obligations (CDOs)
*   Highlighted VaR's failure to capture extreme tail events
*   Introduced stress testing using historical stress periods
*   Paved the way for the Fundamental Review of the Trading Book (FRTB)

---

### **Basel III (2010)**

Tier 1 capital now divided into two parts:
*   Common Equity Tier 1 (CET1) – money provided by ordinary shareholders when they bought shares, plus profits the bank has kept rather than paid out as dividends
*   Additional Tier 1 – contingent convertible (CoCo) bonds that can be converted to equity or written off

| Eligible Capital | MRC |
| :--- | :--- |
| CET1 | 4.5% |
| Tier 1 | 6% |
| Tier 1 + Tier 2 | 8% |

*   For instance, CET1 must now be ≥ 4.5% RWA

---

### **Capital Buffers**

*   Capital buffers determine how much is added-on to the MCR:
    *   Conservation (stress) buffer: 2.5% of RWA
    *   Counter-cyclical buffer: up to 2.5% of RWA
    *   Systemic bank surcharge: between 1% and 3.5% of RWA
*   Large banks typically operate with CET1 capital around 10 – 12% of RWA and total regulatory capital around 12 – 15% of RWA

---

### **Basel IV (2025)**

*   Basel IV revised Credit Valuation Adjustment (CVA) framework for credit-risk instruments
*   Expanded Pillar 3 disclosure and supervisory reporting
*   Revised credit and operational risk approaches
*   Implemented FRTB for market risks – changes include:
    *   Re-calibration of standardized rules for market risk capital requirement – now called Standardized Capital for short
    *   Introducing floor for risk capital calculated using internal models:
        *   Internal Model Capital ≥ 72.5% of Standardized Capital

## 8.3 Fundamental Review of the Trading Book


---

### Fundamental Review of the Trading Book (2013–2025)


*   The **Fundamental Review of the Trading Book (FRTB)** recommended substantial changes to the way that minimum capital requirements are calculated for market risks.
*   **Expected Shortfall (ES)** replaces VaR as the primary measure of market risk.
*   Desk-level MCR aggregates ES across several different components corresponding to risk factor categories.
*   The 10-day holding period is now **liquidity adjusted** to reflect the different times it takes to hedge – or close – positions during times of crisis, depending on risk factor type.
*   For example, during a crash, equities may be less liquid than interest rate swaps (or other cash-flow instruments) so the holding period should be longer for equities than it is for cash flows.

---

### Within-Desk Risk Factor Categories


Each trading desk contains distinct risk factor categories that contribute to its overall ES calculation – for example:

*   **Rates Desk:** Short-term money market rates, swap rates, yield curves
*   **FX Desk:** Spot rates, forward rates, volatility surfaces, cross-currency basis spreads
*   **Equities Desk:** Domestic large-cap equities, small-cap equities, foreign equity indices
*   **Commodities Desk:** Oil, metals, and agricultural commodity prices, commodity volatility surfaces
*   **Credit Desk:** Sovereign credit spreads, corporate bond spreads, credit index tranches



---

### Basel IV Internal Models Approach

*   ES and **stress testing** are two applications of internal models which form the core of Basel IV’s new approach.
*   VaR is just a point threshold loss – corresponding to a quantile of a returns or P&L distribution – so it ignores the dispersion of losses that exceed VaR.
*   ES is the **average loss beyond the VaR threshold** so it takes the actual size of the large losses into account.
*   Stress testing also goes beyond VaR, to calculate the (so-called) **worst case loss** that a portfolio can make, according to a given internal model.
*   ES and stress testing aim to capture heavy-tailed loss distributions and reward banks (with lower capital requirements) for robust hedging practices.


---

### Mathematical Definition of ES


*   ES is the **expected loss**, given that the loss exceeds the VaR.

$$ ES_{h,\alpha} = -\mathbb{E}[X_h | X_h < -\text{VaR}_{h,\alpha}] $$

*   If $X_h$ is the $h$-day return, then ES and VaR are expressed as %; If $X_h$ is the $h$-day P&L, then ES and VaR are expressed in $ amounts;
*   In general, ES is found by taking minus **the average of the losses which exceed the VaR** – this is the way it is calculated using historical simulation (or Monte Carlo VaR).



---

### Formula for ES in the Normal Model


As well as a formula for VaR, there is a formula for ES in the normal model:

$$ ES_{h,\alpha} = \alpha^{-1} \varphi(\Phi^{-1}(\alpha)) \sigma_h - \mu_h $$

where $\varphi$ denotes the standard normal density function and $\Phi$ denotes the distribution function.

**Example:** A portfolio is expected to return the risk-free rate with a volatility of 12%. Assuming the returns are normal and i.i.d., find the 1% annual ES as a percentage of the portfolio value.

$$
\begin{aligned}
ES_{0.01} &= 0.01^{-1} \varphi(\Phi^{-1}(0.01)) \times 0.12 \\
&= 100 \times \varphi(-2.32635) \times 0.12 \\
&= 100 \times 0.026652 \times 0.12 = 31.98\%
\end{aligned}
$$



### Liquidity Adjustments and ES Aggregation


Suppose desk $d$ has $k_d$ risk factors $i = 1, ..., k_d$. Then:

$$ ES_d = \sqrt{ \frac{h^d}{10} \sum_{i=1}^{k_d} (ES_{10, 0.025}^i)^2 } $$

*   $h^d$ is the holding period (in days) appropriate to desk $d$:

| Category | $h^i$ |
| :--- | :--- |
| Interest rates | 10 |
| Foreign exchange | 10 |
| Equities | 20 |
| Commodities | 20 |
| Credit spread ($\ge$ BBB) | 40 |
| Credit spread (< BBB) | 60 |

*   $ES_{10, 0.025}^i$: ES of the $i^{th}$ **within-desk** risk factor category using a 10-day holding period, at the 2.5% significance level.


---

###  Basel IV MCR Formula


Each trading desk $d$ calculates its minimum capital requirement as:

$$ MCR_d = \max\{m \cdot ES_d + ES_d^+ + s_d, MCR_d^*\} $$

*   $ES_d$: Aggregate expected shortfall at 97.5% confidence level (2.5% significance level) computed using **internal risk models**.
*   $ES_d^+$: Additional capital charge for **non-modellable risk factors** – those lacking sufficient data – determined via **stress testing**.
*   $m$: Regulatory multiplier $\ge 1.5$ – set subject to success of backtesting and P&L attribution tests.
*   $s_d$ is an add-on to cover specific risks and stress-testing shortfalls.
*   $MCR_d^*$: Capital charge under the standardized approach, for when the internal model fails validation.

---

###  Bank-Level Aggregation of Trading Desk MCR

The overall minimum capital requirement (MCR) for market risk for the bank is aggregated across all desks for $d = 1, ..., D$, allowing limited diversification effects:

$$ MCR = \sqrt{ \sum_{d=1}^{D} \sum_{e=1}^{D} \rho_{de} MCR_d MCR_e } $$

where $\rho_{de}$ is correlation between desks $d$ and $e$, typically capped at 0.5.

*   Supervisors may reduce the correlation cap if diversification benefits appear overstated.
*   Desks failing their model validation are excluded and capital is computed separately using the standardized approach.



## 8.4 Validation of Internal Risk Models

---

**Backtesting Approach**

*   Fix a **candidate portfolio**
*   Fix an **estimation period** to estimate internal model parameters
*   Use a **rolling window** approach to repeatedly forecast VaR and then compare the predicted VaR with the realized return or P&L
    *   Total sample divided into smaller rolling windows

---

**Exceedances and Indicator Function**

How can we test whether a particular VaR methodology is accurate?

*   **Intuition:** If the internal model is accurate then the α% VaR should be exceeded on α% of the observations in a sample
*   Backtests are based on **exceedances**
*   Use 0-1 **indicator function** where 1 denotes that P&L exceeded VaR and 0 denotes otherwise
*   Do this day by day over a long historical period and keep a record of the exceedances
*   For example, 00000001000010000011000000000

---

**Backtesting Methodology**

1.  Produce a time series of $n$ estimates for 1-day α% VaR and set

$$I_{\alpha,t} = \begin{cases} 1 & \text{if } X_{t+1} < -\text{VaR}_{1,\alpha,t} \\ 0 & \text{otherwise} \end{cases}$$

2.  If the internal model is accurate then $I_{\alpha,t}$ should follow an independent process with **success** probability α, so $S_{n,\alpha} = \sum_t I_{\alpha,t}$ has a **binomial distribution** with

$$\mathbb{E}[S_{n,\alpha}] = n\alpha \quad \mathbb{V}[S_{n,\alpha}] = n\alpha(1-\alpha).$$

3.  A two-sided 95% confidence interval for $S_{n,\alpha}$ when $n$ is large is:

$$\left( n\alpha - 1.96\sqrt{n\alpha(1-\alpha)}, n\alpha + 1.96\sqrt{n\alpha(1-\alpha)} \right)$$


---

**Guidelines from Banking Regulators**

*   Banking supervisors only allow internal models for calculating minimum capital requirements for market risk if they pass **backtests** of 2.5% and 1% daily VaR over a minimum period of 250 days
*   For 1% daily VaR tested on 250 days the expected number of exceedances is $0.01 \times 250 = 2.5$ and the standard deviation is $\sqrt{250 \times 0.01 \times 0.99} = 1.57$
*   This is why regulators only allow the minimum value of $m = 1.5$ to be applied when the internal model used exhibits no more than 4 exceedances of 1% daily VaR over 250 days (pro-rata for larger samples)


---

**Traffic Light Zones and Multiplier Adjustment**

Under Basel IV, the capital multiplier $m$ in:

$$MCR_d = \max \{ m \cdot ES_d + ES_d^+ + s_d, MCR_d^* \}$$

is adjusted based on the backtesting performance of the 1% daily VaR of the **entire bank**, i.e. aggregated VaR over all trading trading desks

| Exceptions (out of 250) | Zone   | Multiplier $m$       |
| :---------------------- | :----- | :------------------- |
| 0–4                     | Green  | $m = 1.5$            |
| 5–9                     | Yellow | $m \in [1.5, 2.0]$   |
| 10+                     | Red    | $m \ge 2.0$          |


---

**Desk-Level Backtesting and Internal Model Eligibility**

*   Desk-level exceedances **do not affect the multiplier** $m$ — they only determine whether the desk can use its internal model
*   Each trading desk must pass two backtests over 250 trading days:
    *   1% VaR: desk loses model approval if there are > **12** exceptions
    *   2.5% VaR: desk loses model approval if there are > **30** exceptions
*   If a desk fails either test, it must switch to the **standardized approach** for market risk capital

---

**P&L Attribution**

*   The **P&L Attribution (PLA)** test is new under Basel IV
*   It checks whether a trading desk’s internal model really captures the risks that drive its daily P&L
*   Each day, a trading desk produces two historical P&L time series:
    *   **Hypothetical P&L**: what the desk’s P&L *would* be if only market risk factors changed, using today’s positions – this is the P&L explained by the risk model
    *   **Actual P&L**: the real P&L that includes *all* effects from market movements, fees, intraday trades, and valuation adjustments



---

**PLA Test**

*   The test checks how well the model explains daily P&L movements by comparing the actual P&L time series with the hypothetical P&L time series
    *   If the model's risk factors capture most of what drives P&L, the hypothetical and actual P&L series should move closely together
    *   If they diverge too much, it means the model is missing key risks or using incorrect sensitivities
*   The PLA test has two parts:
    *   The **correlation test**: correlation between actual and hypothetical P&L must exceed a threshold (typically 0.8)
    *   The **unexplained P&L ratio**: unexplained portion of P&L must stay below a tolerance band



## 8.5 Statistical Backtests


---

### **Binomial Distribution**

- Suppose you have a coin that is unfair, meaning the probability $\pi$ of getting a head is not 0.5 but instead $\pi = 0.3$. The probability of tails is therefore $1 - \pi = 0.7$. You decide to flip this coin 10 times and are interested in the number of heads you get.

- This is an example of the **binomial distribution**, which models the number of successes in a fixed number $n$ of independent trials, each with the same probability of success. In this case, the number of heads $X \sim B(10, 0.3)$.

- If $X$ represents the number of successes, then $X$ follows a binomial distribution with parameters $n$ (number of trials) and $\pi$ (probability of success). We write $X \sim B(n, \pi)$.

---

### **Binomial Likelihood Function**

- “Likelihood” is another term for the height of a density function.

- The probability of getting exactly $k$ successes in $n$ trials is given by:

$$
P(X = k) = \binom{n}{k} \pi^k (1 - \pi)^{n-k}
$$

where

$$
\binom{n}{k} = \frac{n!}{k!(n-k)!}
$$

and the **factorial** $n!$ is $n(n-1)(n-2)\dots$

- A binomial variable has mean $\mathbb{E}(X) = n\pi$ and variance $\mathbb{V}(X) = n\pi(1-\pi)$. For example, if $X \sim B(10, 0.3)$, the mean is 3 and the variance is $10 \times 0.3 \times 0.7 = 2.1$.

---

### **Numerical Example**

- If $X \sim B(5, 0.4)$, what is $P(X = 3)$? Using the likelihood function:

$$
P(X = 3) = \binom{5}{3} (0.4)^3 (1 - 0.4)^{5-3}
$$

- The binomial coefficient is:

$$
\binom{5}{3} = \frac{5!}{3!(5-3)!} = 10
$$

- Calculate $P(X = 3)$:

$$
P(X = 3) = 10 \times (0.4)^3 \times (0.6)^2 = 10 \times 0.064 \times 0.36 = 0.2304
$$

---

### **Likelihood Ratio (LR) Tests**

- These are statistical tests for whether observed data fit the data we would expect under a particular model. The LR test is based on the ratio of two likelihoods: $L_0$ is the **expected** maximum likelihood under the model and $L_1$ is the **observed** maximum likelihood from the data.

- The LR test statistic is:

$$
\lambda = \frac{L_0}{L_1}
$$

- We often use the log likelihood ratio:

$$
-2 \ln(\lambda) = -2 (\ln L_0 - \ln L_1) \sim \chi^2_q
$$

which follows a **chi-squared distribution** with degrees of freedom $q$.

---

### **Statistical Backtests**

- Kupiec (1995) and Christoffersen (1998) devise likelihood ratio tests with the null hypothesis that the exceedance process has success probability $\alpha$. The test statistic is:

$$
LR_{uc} = \frac{\pi_{exp}^{n_1} (1 - \pi_{exp})^{n_0}}{\pi_{obs}^{n_1} (1 - \pi_{obs})^{n_0}}
$$

where $\pi_{exp}$, the expected proportion of exceedances, is the same as the significance level $\alpha$ of the VaR measures, $\pi_{obs}$ is the observed proportion of exceedances, $n_1$ is the number of exceedances and $n_0 = n - n_1$ where $n$ is the backtest sample size.

- The asymptotic distribution is $-2 \ln LR_{uc} \sim \chi^2_1$, namely, it is chi-squared distributed with one degree of freedom.


---

### **Example: Unconditional Coverage Test I**

A backtest of 2.5% VaR with sample size 500 yields 20 exceedances. Perform an unconditional coverage test on these results, given that the 1% and 5% critical values for the chi-squared distribution with 1 degree of freedom are 6.6349 and 3.8415.

We have $\pi_{exp} = 0.025$ and $\pi_{obs} = 20/500 = 0.04$ and $n_1 = 20$ and $n_0 = 480$, so

$$
LR_{uc} = \frac{0.025^{20} \cdot 0.975^{480}}{0.04^{20} \cdot 0.96^{480}} = 0.141132
$$

So

$$
-2 \ln LR_{uc} = -2 \ln 0.141132 = 3.916
$$

---

### **Example: Unconditional Coverage Test II**

- We have $-2 \ln LR_{uc} = -2 \ln 0.141132 = 3.916$

- This exceeds the $\chi^2_1$ critical value at 5% (of 3.841) but not at 1% (it is 6.634).

- So we reject the null hypothesis that the internal model is accurate at 5%, but not at the 1% significance level.

- We should also perform backtests for significance levels other than $\alpha = 0.025$.


---

### **Calculator Problem?**

It may be that your calculator cannot calculate the ratio, because the numerator and denominator are too small.

In this case you should calculate $-2 \ln(LR)$ directly using:

$$
\ln(LR_{uc}) = \ln\left(\pi_{exp}^{n_1} (1 - \pi_{exp})^{n_0}\right) - \ln\left(\pi_{obs}^{n_1} (1 - \pi_{obs})^{n_0}\right)
$$

and then note that

$$
\ln\left(\pi_{exp}^{n_1} (1 - \pi_{exp})^{n_0}\right) = n_1 \ln(\pi_{exp}) + n_0 \ln(1 - \pi_{exp})
$$

and similarly

$$
\ln\left(\pi_{obs}^{n_1} (1 - \pi_{obs})^{n_0}\right) = n_1 \ln(\pi_{obs}) + n_0 \ln(1 - \pi_{obs})
$$


---

### **Exceedances and Clusters**

- If the internal model is accurate, exceedances do not come in clusters!


---

### **Independence Test**

- Christoffersen also derived this test for independence of the exceedances:

$$
LR_{ind} = \frac{\pi_{obs}^{n_1} (1 - \pi_{obs})^{n_0}}{\pi_{01}^{n_{01}} (1 - \pi_{01})^{n_{00}} \pi_{11}^{n_{11}} (1 - \pi_{11})^{n_{10}}}
$$

where $n_{ij}$ is the number of indicator $i$ followed by indicator $j$, $\pi_{01} = n_{01}/(n_{00} + n_{01})$ and $\pi_{11} = n_{11}/(n_{10} + n_{11})$.

- The asymptotic distribution is $-2 \ln LR_{ind} \sim \chi^2_1$, also chi-squared with one degree of freedom. There must be at least one cluster of exceedances for this test.

---

### **Conditional Coverage Test**

- The test statistic is:

$$
LR_{cc} = \frac{\pi_{exp}^{n_1} (1 - \pi_{exp})^{n_0}}{\pi_{01}^{n_{01}} (1 - \pi_{01})^{n_{00}} \pi_{11}^{n_{11}} (1 - \pi_{11})^{n_{10}}}
$$

- We have:

$$
-2 \ln LR_{cc} = -2 \ln LR_{uc} + -2 \ln LR_{ind}
$$

- The asymptotic distribution is $-2 \ln LR_{cc} \sim \chi^2_2$, namely chi-squared distributed with **two** degrees of freedom.

---

### **Example (By Hand)**

- A backtest of 1% VaR with 100 observations yields 20 exceedances.

- There are **three** groups of two exceedances (0000110000), **one** group of three (00001110000) and **one** group of four (00011110000). The other **seven** exceedances are **isolated** (000010000).

- Compute the conditional, independence and unconditional coverage statistics for this backtest. What do you conclude?

$$
n = 100, \quad n_0 = 80, \quad n_1 = 20, \quad n_{11} = 8, \quad n_{10} = 12, \quad n_{01} = 12,
$$
$$
n_0 = n_{00} + n_{01} \rightarrow n_{00} = n_0 - n_{01} = 80 - 12 = 68
$$

---

### **Solution I**

$$
n = 100, \quad n_0 = 80, \quad n_1 = 20, \quad n_{11} = 8, \quad n_{10} = 12, \quad n_{01} = 12, \quad n_{00} = 68
$$

Hence

$$
\pi_{obs} = 0.2, \quad \pi_{01} = 12/80 = 0.15, \quad \pi_{11} = 8/20 = 0.4
$$

and for a 1% VaR backtest, $\pi_{exp} = \alpha = 0.01$ and so using a calculator or Excel we get:

$$
-2 \ln LR_{uc} = 85.7344 \\
-2 \ln LR_{ind} = 5.5266 \\
-2 \ln LR_{cc} = 91.2609
$$

---

### **Solution II**

- Since the $\chi^2_1$ critical values at 1% and 5% are 6.6349 and 3.8415, we reject the unconditional coverage test at 1%.

- However, we can only reject the independence test at 5%.

- Also, we need the $\chi^2_2$ critical values for the conditional coverage test. These are 9.2103 at 1% and 13.8155 at 0.1%.

- Hence, we can even reject the conditional coverage test at 0.1%.


## 8.6 Scenario Analysis and Stress Testing Portfolios


### Examples of Historical Stress Scenarios

- 1987: Global equity crash
- 1992: European Exchange Rate Mechanism crisis
- 1994 and 2003: Bond market sell-offs
- 1997: Asian property crisis
- 1998: Russian debt default
- 1998: Threat of insolvency of the LTCM hedge fund
- 2000: Burst of the technology stock bubble
- 2001: Terrorist attacks on the US
- 2007: Credit crunch
- 2008: Banking crisis
- 2011: Euro debt crisis
- 2020: Covid-19


### Examples of Hypothetical Scenarios

- Parallel shift in a yield curve of ±100 basis points
- Linear tilt in a yield curve of ±25 basis points
- Parallel change in credit spreads of ±20 basis points
- Stock index return of ±10%
- Return of ±6% on a major currency pair, or of ±20% for a minor currency against another currency
- Relative change in volatility of ±20%


### Stressed Covariance Matrices

- Banking regulators require stress tests to be performed using stressed risk factor covariance matrices
- Such matrices may come from a crisis period in the past
- Example: use a covariance matrix for the FTSE 100 and S&P 500 from around the 1987 global stock market crash
- Alternatively, one can hypothetically adjust the volatilities and correlations between the risk factors
- But be careful – the covariance matrix must always be positive definite, which means that all quadratic forms x'Vx must be positive (so, we can take the square root in the normal VaR formula)


### Reverse Stress Testing

- Reverse stress testing starts with an adverse outcome, such as a capital ratio falling below minimum level, and works backwards to identify which type of risk factor shocks could cause this
- First define adverse outcome, e.g., CET1 falls below 4.5% of RWA
- Next, try out many scenarios of shocks to:
  1. Interest rate risk factors
  2. Equity risk factors
  3. FX risk factors
  4. Commodity risk factors
- Find out which individual shocks make the bank’s overall portfolio lose so much that the CET1 ratios fall below 4.5% of RWA. And which combinations of shocks do likewise?
- Supervisors use these scenarios to test resilience to extreme but plausible events and to highlight vulnerable business lines

### Stress Testing to Find “ES” for NMRFs

- Each non-modellable risk factor (NMRF) is assigned one or more stress windows like the 2008 banking crisis to use for data input to the internal model
- How much could we lose if this risk factor moved as it did during this stress window?
- To answer this, we compute the loss using today’s positions and the stressed scenario(s)
- The “ES” is then set equal to the average loss across the most severe scenarios
- In practice this gives a conservative estimate of potential loss where data are scarce, ensuring capital covers even poorly understood risks