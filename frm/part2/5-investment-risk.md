## Investment Risk



### **Reading 146: Factor Theory**
**Formulas:**
*   **Capital Asset Pricing Model (CAPM):** $E(R_i) = R_f + \beta_i [E(R_m) - R_f]$
*   **Beta ($\beta$):** $\beta_i = \frac{Cov(R_i, R_m)}{\sigma_m^2} = \rho_{im} \frac{\sigma_i}{\sigma_m}$
*   **Market Risk Premium & Risk Aversion:** $E(R_m) - R_f = \bar{\gamma}\sigma_m^2$ *(Where $\bar{\gamma}$ is the average investor's risk aversion coefficient)*
*   **Stochastic Discount Factor (SDF) / Pricing Kernel:** $m = a + bR_m$

**Key Concepts/Definitions:**
*   **CAPM Assumptions:** Investors have homogeneous expectations, the market is in equilibrium, investors hold well-diversified portfolios, no transaction/taxation costs, single-period investment horizon, and information is available to all at no cost.
*   **Systematic vs. Idiosyncratic Risk:** CAPM states only systematic risk (measured by beta) is rewarded with a risk premium. Idiosyncratic risk can be diversified away and is not rewarded.
*   **Multifactor Models:** Evaluate multiple risk factors simultaneously, contain multiple betas, diversify idiosyncratic risk, and can model both linear and non-linear dependencies.
*   **Low-Risk Anomaly:** The empirical observation that low-volatility/low-beta stocks tend to earn *higher* risk-adjusted returns than high-volatility stocks, contradicting CAPM. A primary potential reason is **leverage constraints** (investors wanting high risk overpay for high-beta stocks, lowering their future returns).

---

### **Reading 147: Factors**
**Formulas:**
*   **Fama-French 3-Factor Model:** $E(R_i) = R_f + \beta_{i,MKT}[E(R_m) - R_f] + \beta_{i,SMB}E(SMB) + \beta_{i,HML}E(HML)$
*   **Carhart 4-Factor Model (adds Momentum):** $E(R_i) = R_f + \beta_{i,MKT}[E(R_m) - R_f] + \beta_{i,SMB}E(SMB) + \beta_{i,HML}E(HML) + \beta_{i,WML}E(WML)$

**Key Concepts/Definitions:**
*   **SMB (Small Minus Big):** The size factor; captures the excess returns of small-cap companies over large-cap companies (size premium).
*   **HML (High Minus Low):** The value factor; captures the difference in returns between high book-to-market (value) stocks and low book-to-market (growth) stocks (value premium).
*   **WML / UMD (Winners Minus Losers / Up Minus Down):** The momentum factor; captures the outperformance of past winning stocks over past losing stocks. A positive beta here means the stock moves with the momentum trend.
*   **Value Premium Explanations:** Value firms are less flexible/have unproductive capital in bad times; investor psychological biases (mental accounting, loss aversion); investors underestimate the growth prospects of value stocks.
*   **Dynamic vs. Static Factors:** The value factor is *dynamic* (changes over time based on market conditions/prices). Macroeconomic factors like GDP or economic growth are *static*.

---

### **Reading 148: Alpha (and the Low-Risk Anomaly)**
**Formulas:**
*   **Sharpe Ratio:** $SR = \frac{R_p - R_f}{\sigma_p}$
*   **Treynor Ratio:** $TR = \frac{R_p - R_f}{\beta_p}$
*   **Jensen’s Alpha:** $\alpha_p = R_p - [R_f + \beta_p(R_m - R_f)]$
*   **Information Ratio (IR):** $IR = \frac{R_p - R_b}{\text{Tracking Error}} = \frac{\alpha}{\text{Tracking Error}}$
*   **Grinold’s Fundamental Law of Active Management:** $IR = IC \times \sqrt{BR}$ *(Where $IC$ = Information Coefficient, $BR$ = Breadth of strategy / number of independent bets)*
*   **Total Information Ratio (for N independent managers):** $IR_{total} = IR_i \times \sqrt{N}$
*   **Active Risk Aversion Parameter:** $\lambda_a = \frac{IR}{2 \times \psi_p}$ *(Where $\psi_p$ is active risk / tracking error)*

**Key Concepts/Definitions:**
*   **Alpha:** The intercept in a regression of a fund's excess returns against a benchmark's excess returns. Represents the active return or value added by the manager.
*   **Tracking Error:** The standard deviation of the excess returns of a portfolio relative to a benchmark.
*   **Appropriate Benchmark Properties:** Must be replicable, tradeable, risk-adjusted, and **NOT** equally applied to all risky assets irrespective of their risk exposure.
*   **Absolute Return Funds as Benchmarks:** Unsuitable because their strategies are complex, proprietary, and usually not replicable.
*   **Refining Alphas:** 
    *   *Scaling:* Adjusting alphas to have a mean of 0 and a specific standard deviation.
 *   *Trimming:* Eliminating extreme positive/negative alphas that could unduly influence results.
    *   *Neutralization:* Adjusting alphas to remove influence from common risk factors (e.g., making them industry-neutral by subtracting the cap-weighted industry average alpha from each stock's alpha).
*   **Screen Technique:** Ranking stocks by alpha. *Pros:* Easy to understand, easy to computerize, enhances alphas by concentrating on high-alpha stocks. *Cons:* Ignores magnitude of alpha (only uses rankings), doesn't protect against biases, may result in riskier portfolios.

---

### **Reading 149: Portfolio Construction**
**Formulas:**
*   **Modified Benchmark-Neutral Alpha:** $\alpha_{neutral} = \alpha_{active} - (\alpha_{benchmark} \times \beta_{active})$

**Key Concepts/Definitions:**
*   **Active Management Constraints:** Most active managers construct portfolios subject to constraints (short position limits, sector exposure, tracking error limits), making active management challenging even with "right alphas."
*   **Portfolio Construction Techniques:**
    *   *Screens:* Simple ranking of assets, composing an equal-weighted or capitalization-weighted portfolio.
    *   *Stratification:* Builds on screens by ensuring each category of assets is present in the portfolio.
    *   *Linear Programming:* Chooses a portfolio that closely resembles the benchmark using stratification based on industry characteristics.
    *   *Quadratic Programming:* Models alpha, risk, and transaction costs explicitly; can incorporate complex constraints.
*   **Dispersion:** Variability in returns across different portfolios. Caused by different betas/factor exposures, different number of stocks, and the overall number of portfolios. *Not* caused by identical holdings. Certain levels of dispersion are optimal as they can result in higher average returns.
*   **Transaction Costs:** Should be amortized over the anticipated holding period to fairly compare against annual alpha gains. Annualized transaction cost = round trip cost / holding period in years.

---

### **Reading 150: Portfolio Risk: Analytical Methods**
**Formulas:**
*   **Portfolio VaR (2 Assets):** $VaR_p = \sqrt{VaR_1^2 + VaR_2^2 + 2\rho_{12}VaR_1 VaR_2}$
    *   *Perfectly correlated ($\rho=1$):* $VaR_p = VaR_1 + VaR_2$
    *   *Uncorrelated ($\rho=0$):* $VaR_p = \sqrt{VaR_2^2 + VaR_2^2}$
*   **Number of Covariance Terms (for $n$ securities):** $\frac{n(n-1)}{2}$
*   **Component VaR (CVaR):** $CVaR_i = VaR_p \times \beta_i \times w_i$
*   **Marginal VaR (MVaR):** $MVaR_i = \frac{VaR_p}{\text{Portfolio Value}} \times \beta_i$
*   **Liquidity Duration Statistic (LDS):** $LDS = \frac{\text{Shares in Fund}}{\text{Average Daily Trading Volume} \times \text{Max Daily Volume for Liquidation (\%)}}$

**Key Concepts/Definitions:**
*   **Diversification & Correlation:** Higher covariance reduces diversification benefits. Portfolio VaR is *maximized* when pairwise correlations are perfectly positive. Diversification is still possible with positive covariance, but benefits are lower.
*   **Marginal vs. Incremental VaR:** Marginal VaR assumes linear changes (good for small additions). Incremental VaR is more accurate for large, non-linear changes (e.g., adding an entire new position).
*   **Component VaR Limitation:** Cannot be calculated by simply adding individual VaRs, as this completely ignores diversification effects.
*   **Hedging with Negative Correlation:** If two securities are negatively correlated, going *long* on both creates a hedged position (gains in one offset losses in the other).
*   **Beta Limitation:** Beta is not an appropriate risk parameter for poorly diversified portfolios, as it only measures systematic risk, ignoring unsystematic risk.

---

### **Reading 151: VaR and Risk Budgeting in Investment Management**
**Formulas:**
*   **Portfolio VaR (General):** $VaR = Z \times \sigma \times W$
*   **Pension Surplus:** $\text{Surplus} = V_{assets} - V_{liabilities}$
*   **Return on Risk Capital (RORC):** $RORC = \frac{\text{Revenues} - \text{Expenses}}{\text{Total Risk Capital}}$
*   **Return on Equity (ROE):** $ROE = \frac{\text{Net Income}}{\text{Assets} - \text{Liabilities}}$
*   **Optimal Allocation to Manager $i$:** $w_i = \frac{IR_i}{IR_p} \times \frac{\text{Portfolio TEV}}{\text{Manager's TEV}}$

**Key Concepts/Definitions:**
*   **VaR Suitability:** Well-suited for investment management due to global diversification needs, complex instruments, and dynamic portfolios. *Not* well-suited for highly illiquid assets (e.g., infrequently traded convertible bonds) due to appraisal/smoothing bias and lack of reliable historical data.
*   **Absolute vs. Relative Risk:** 
    *   *Absolute Risk (Asset Risk):* Risk of a dollar loss over a specific horizon, independent of any benchmark.
    *   *Relative Risk:* Risk of a dollar loss in a fund *relative* to its benchmark (measured by Tracking Error).
*   **Pension Fund Risk:** The appropriate risk parameter is *funding risk* (the risk that assets will not be sufficient to cover fixed liabilities), not just asset volatility. An Asset/Liability Management (ALM) framework is desirable.
*   **Interest Rate Impact on Pension Funds:** If liabilities are nominal payments, a decrease in interest rates increases the value of liabilities (behaving like a short position in a long-term bond) *more* than it increases the value of equities, negatively affecting the surplus.
*   **Three Dimensions of Risk Management:** Risk planning (setting VaR thresholds), risk budgeting (allocating capital/TEV based on IR), and risk monitoring (identifying variations from the budget).

---

### **Reading 152: Risk Monitoring and Performance Measurement**
**Key Concepts/Definitions:**
*   **Risk Monitoring:** A continuous, real-time process to observe risk exposures, identify deviations from expected outcomes/risk thresholds, and promptly report them to stakeholders for timely decision-making.
*   **Risk Management Unit (RMU) Objectives:** Synthesize and routinely circulate risk data to decision-makers, ensure accurate risk data handling, promote risk culture, research emerging risks, develop risk measurement tools, and aid management in understanding portfolio risks.
*   **Style Drift:** When a fund departs from its stated investment style or philosophy (e.g., a "growth" fund secretly buying "value" stocks). Detected via risk decomposition (monitoring acceptable active weights and marginal contributions to risk at stock, industry, sector, and country levels).
*   **Liquidity Duration Statistic (LDS):** Estimates the time (in days) required to liquidate a position without causing a significant market impact. For fixed-income securities, it is often determined through discussions with portfolio managers due to a lack of readily available volume data.
*   **Survivorship Bias:** Focusing only on instances/funds that "survived" a selection process (e.g., poorly performing funds closing and disappearing from databases), leading to an *overestimation* of mean returns and Sharpe ratios.
*   **Appraisal (Smoothing) Bias:** Occurs with illiquid assets (like real estate) that are infrequently appraised. It artificially smooths returns, making volatility and correlations appear lower than they actually are, leading to an *overestimation* of the Sharpe ratio.

---

### **Reading 153: Portfolio Performance Evaluation**
**Formulas:**
*   **Time-Weighted Rate of Return (TWRR):** Geometric mean of holding period returns. $TWRR = [(1+HPR_1)(1+HPR_2)...]^{1/n} - 1$
*   **Dollar-Weighted Rate of Return (DWRR):** The Internal Rate of Return (IRR) of the portfolio, accounting for all cash inflows and outflows.
*   **Return Attribution (Brinson-Fachler):**
    *   *Asset Allocation Effect:* $(w_{pi} - w_{bi}) \times r_{bi}$
    *   *Security Selection Effect:* $w_{pi} \times (r_{pi} - r_{bi})$
    *   *Total Excess Return:* $\sum (w_{pi} \times r_{pi}) - \sum (w_{bi} \times r_{bi})$
*   **Market Timing Regression (Treynor-Mazuy):** $r_p - r_f = \alpha_p + \beta_p(r_m - r_f) + c_p(r_m - r_f)^2 + e_p$ *(A positive $c_p$ indicates successful market timing).*

**Key Concepts/Definitions:**
*   **Performance Measure Selection:**
    *   *Sharpe Ratio:* Best for ranking portfolios competing for the *overall* risky portfolio (uses total risk / standard deviation).
    *   *Treynor Ratio:* Best for ranking *sub-portfolios* that will be mixed to form the overall risky portfolio (uses systematic risk / beta). Produces the same rankings as Jensen’s Alpha.
    *   *Information Ratio:* Best for evaluating a portfolio to be mixed with a *benchmark* portfolio (uses tracking error).
*   **Style Analysis:** Regressing fund returns on style portfolios. The $R^2$ indicates the percentage of variability in the fund's return explained by asset allocation. The remainder is attributed to security selection and market timing.
*   **Peer Group Regression:** Regressing a manager's excess returns against a peer group's excess returns to determine if the manager demonstrates skill over and above peers. Subject to survivorship bias and reduced comparability due to varying fund sizes.

---

### **Reading 154: Hedge Funds**
**Key Concepts/Definitions:**
*   **Hedge Fund Strategies:**
    *   *Global Macro:* Bets on directional movements in macroeconomic variables (exchange rates, interest rates, commodities). Highly active, mimics a diversified hedge fund portfolio.
    *   *Distressed Securities:* Investing in the debt of firms near or in bankruptcy. High upside potential, accepts illiquidity and default risk. (Event-driven).
    *   *Merger (Risk) Arbitrage:* Profits from the price spread between a target company's current stock price and the acquirer's offer price. Primary risk is "deal risk" (the merger fails).
    *   *Convertible Arbitrage:* Market-neutral strategy involving buying undervalued convertible bonds and shorting the underlying common stock.
    *   *Fixed-Income Arbitrage:* Exploiting pricing inefficiencies between related fixed-income securities (e.g., on-the-run vs. off-the-run Treasuries). Highly sensitive to interest rates.
    *   *Managed Futures / Trend Followers:* Systematic trading in commodity and financial futures based on technical trends. Historically resilient during market-wide funding crises (reduces tail risk).
*   **Principal-Agent Problem (Risk-Sharing Asymmetry):** Hedge fund managers (agents) earn performance fees for upside but do not bear the full downside of losses. This incentivizes them to take excessive risks. Mitigated by ensuring managers have a substantial portion of their *personal wealth* invested in their own funds ("skin in the game").
*   **Funds of Hedge Funds (FOHF):** Provide one-stop diversification. Historically the favored route for institutional investors.
*   **Liquid Alternative Beta (LAB):** Products that mimic hedge fund indices/strategies but offer higher liquidity and lower fees without lock-up periods.

---

### **Reading 155: Performing Due Diligence on Specific Managers and Funds**
**Key Concepts/Definitions:**
*   **Due Diligence:** A comprehensive appraisal of a business or fund. Investors should interact with employees of *mixed seniority* to get an accurate picture, not just investor relations staff.
*   **Committee Dynamics:** Large committees or those headed by powerful figures (e.g., a CIO heading both investment and appraisal committees) may suffer from suppressed dissent or groupthink, leading to suboptimal investment decisions.
*   **Ownership Structure:** A firm's ownership structure helps align the interests of fund managers with those of investors. Large personal investments by managers reduce risk-sharing asymmetry.
*   **Hiring Practices:** Independent background checks must be carried out for *every* manager, irrespective of internal referral programs.
*   **Reporting Structure:** Risk managers must report *independently* to the CIO (not to portfolio managers) to avoid conflicts of interest and ensure objective risk assessment.
*   **Valuation Models:** Inputs and assumptions must be revisited periodically and subjected to external audits. Using unaudited proprietary models for illiquid assets is a major warning signal.
*   **Red Flags:** Promising returns way above average (potential fraud/misrepresentation), trading via affiliated brokers (lack of trading independence), and high proportion of illiquid assets without independent valuation audits.

---

### **Reading 156: Finding Bernie Madoff: Preventing Fraud by Investment Managers**
**Key Concepts/Definitions:**
*   **Ponzi Scheme:** A fraudulent operation where returns are paid to existing investors using funds collected from *new* investors, rather than from actual profit. It is unsustainable and collapses when new inflows stop or too many investors cash out.
*   **Madoff Red Flags:** Refusal to provide detailed portfolio information, lack of transparency, using an affiliated broker-dealer (lack of trading independence / custody issues), and using proprietary, unaudited models to value illiquid assets.
*   **Fraud Prediction:** Form ADV data (both current and prior/historical panel data) *can* be used to predict fraud. Models using all prior filings perform better than cross-sectional models. Disclosures related to past regulatory violations, conflicts of interest, and monitoring significantly predict fraud.
*   **Agent vs. Principal Clients:** Firms with a high proportion of agent clients (e.g., pension managers investing on behalf of others) are more likely to commit fraud because agents do not bear the full cost of the fraud and can be swayed by gifts or kickbacks.
*   **Disclosure:** The timely release of all information that could reasonably be expected to influence an investor’s decision (includes business practices, fees, conflicts of interest, and disciplinary info).
*   **Investment Fraud Definition:** Deceptive practices used by managers or firms to extract money from unsuspecting investors.