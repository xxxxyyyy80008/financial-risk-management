## Liquidity Risk


### **Reading 127: Liquidity Risk**
**Key Concepts & Definitions**
*   **Liquidity Risk:** The inability of a financial institution to meet its short-term debt obligations without sacrificing capital or income.
*   **Exogenous Bid-Ask Spread:** Determined by the larger market, outside the bank's control (bank's position is too small to influence it).
*   **Endogenous Bid-Ask Spread:** Influenced by the bank's own trading activities (when position is large relative to market).
*   **Liquidity at Risk (LaR):** Worst-case cash outflow at a given confidence level over a holding period.

**Formulas**
*   **Proportional Bid-Ask Spread:** `(Ask Price - Bid Price) / [(Ask Price + Bid Price) × 0.5]`
*   **Liquidity-Adjusted VaR (LVaR) – Constant Spread:** `(V × Z_α × σ) + (0.5 × V × spread)`
*   **LVaR – Stressed Market (Normal Distribution of Spread):** `(-expected return + σ_asset × z-score) + 0.5 × (spread + σ_spread × z-score)`
*   **Cost of Liquidation (Normal Market):** `Σ 0.5 × Proportional Spread_i × Mid-market Value_i`
*   **Cost of Liquidation (Stressed Market):** `Σ [α_j × (μ_j + λσ_j)] / 2` *(Where: α_j = mid-market position, μ_j = mean spread, σ_j = std dev of spread, λ = z-score e.g., 1.645 at 95%, 2.326 at 99%)*
*   **Liquidity Coverage Ratio (LCR):** `High-Quality Liquid Assets (HQLA) / Net cash outflows over 30 days ≥ 100%` *(Stress events include: 3-notch credit downgrade, drawdowns on lines of credit, partial loss of deposits).*
*   **Net Stable Funding Ratio (NSFR):** `Amount of stable funding / Required amount of stable funding ≥ 100%`

---

### **Reading 128: Liquidity and Leverage**
**Key Concepts & Definitions**
*   **Transaction Liquidity Risk:** The risk of moving the price of an asset adversely in the act of buying or selling it.
*   **Balance Sheet Risk (Funding Liquidity Risk):** Risk that creditors withdraw credit or change terms, forcing unwinding of positions.
*   **Systemic Risk:** Risk of widespread disruption in the financial system; failure of one institution causing a domino effect.
*   **Maturity Transformation Risk:** Borrowing short-term while lending long-term.
*   **Matched Funding:** Financing long-term assets with long-term debt.
*   **Rollover Risk:** Risk that short-term debt cannot be refinanced or only on highly disadvantageous terms.
*   **Slippage:** Difference between expected execution price and actual execution price due to market volatility and time delay.
*   **Haircut:** Difference between collateral value and loan amount; the extent to which collateral value can fall and still be fully collateralized.

**Formulas**
*   **Leverage Ratio (L):** `Total Assets / Equity = 1 + (Debt / Equity)`
*   **Return on Equity (ROE):** `(Leverage Ratio × ROA) - [(Leverage Ratio - 1) × Cost of Debt]`
*   **Expected Transaction Cost (99% CI):** `0.5 × P × (S + 2.33σ_s)` *(P = midprice, S = expected proportional spread, σ_s = std dev of spread)*
*   **99% Spread Risk Factor:** `0.5 × (S + 2.33σ_s)`
*   **Liquidity-Adjusted VaR (Multi-Day Liquidation):** `VaR_1-day × √[(1+T)(1+2T) / 6T]` *(T = number of trading days to liquidate)*
*   **Reg T Margin:** Maximum 50% borrowing of the purchase price.

---

### **Reading 129: Early Warning Indicators**
**Key Concepts & Definitions**
*   **Leading Indicator:** Forward-looking indicator that signals potential stress before an event occurs.
*   **Lagging Indicator:** Changes after the economy as a whole does.
*   **Sharp EWI:** A highly granular indicator involving a subset of data to detect subtle changes.
*   **Primary Purpose of EWIs:** Initiate management discussion and necessary corrective action.
*   **Spotlight System:** Red (critical/immediate action), Amber (moderate risk), Green (acceptable).
*   **BCBS Recommended EWIs:** Rapid asset growth funded with volatile liabilities, growing concentrations in assets/liabilities, increase in currency mismatches, *decrease* in weighted average maturity of liabilities, negative publicity/credit rating downgrade/stock price declines, widening debt/CDS spreads, rising wholesale/retail funding costs, counterparties requesting additional collateral, drop in credit lines, increasing retail deposit outflows, increasing CD redemptions before maturity.

---

### **Reading 130: The Investment Function in Financial Services Management**
**Key Concepts & Definitions**
*   **Treasury Bill (T-Bill):** Short-term (< 1 year), sold at discount, no coupon.
*   **Treasury Note:** 2–10 years maturity.
*   **Treasury Bond:** > 10 years maturity.
*   **Money Market Securities:** Mature within 1 year (e.g., T-bills, commercial paper, CDs).
*   **Bankers' Acceptances:** Bank's commitment to pay a specified amount on a future date; among the safest money market instruments. Disadvantage: issued in odd denominations.
*   **Portfolio Immunization:** Protecting returns on purchased securities regardless of interest rate direction by balancing price and reinvestment risks.
*   **Prepayment Risk:** Risk of early loan repayment altering expected cash flows (especially MBS).
*   **Rate Expectation Strategy:** Most aggressive maturity strategy; continuously adjusts securities' maturities based on interest rate forecasts.
*   **Tax Swap:** Selling lower-yielding securities at a loss to reduce taxable income while purchasing higher-yielding securities.
*   **Pledging Requirement:** Legal obligation to pledge securities as collateral for government deposits.

**Formulas**
*   **Yield to Maturity (YTM):** `P = Σ [C / (1+YTM)^t] + [FV / (1+YTM)^n]`
*   **Holding Period Yield (HPY):** `P_0 = Σ [CF_t / (1+HPY)^t]`
*   **Tax-Equivalent Yield (TEY):** `Tax-Exempt Return / (1 - Marginal Tax Rate)`

---

### **Reading 131: Liquidity and Reserves Management**
**Key Concepts & Definitions**
*   **Net Liquidity Position:** Total Cash Inflows − Total Cash Outflows.
*   **Sources and Uses of Funds Approach:** Estimates liquidity surplus/deficit from changes in deposits and loans.
*   **Asset Conversion Method:** Selling assets (e.g., securities) to cover deposit drain → bank size **decreases**.
*   **Liability Management (Purchased Liquidity):** Borrowing to cover liquidity needs → bank size **unchanged** (for deposit drain) or **increases** (for new loans).
*   **Sweep Account:** Contractual agreement to move funds from checking to generate higher returns and lower reserve requirements.
*   **Money Position Manager:** Responsible for maintaining adequate legal reserves.

**Formulas**
*   **Estimated Liquidity Surplus/Deficit:** `ΔTotal Deposits - ΔTotal Loans`
*   **Liability Liquidity Reserve:** `0.75 × (Hot Money - Legal Reserves) + 0.15 × (Vulnerable Funds - Legal Reserves) + 0.10 × (Stable Funds - Legal Reserves) + Loan Liquidity Requirement`
*   **Cash Position Indicator:** `(Cash and Due from Depository Institutions) / Total Assets`
*   **Net Federal Funds Position:** `(Fed Funds Sold - Fed Funds Purchased) / Total Assets`
*   **Federal Reserve Credit Earned:** `Avg Clearing Balance × Annualized Fed Funds Rate × (Days / 360)`
*   **Expected Liquidity Requirement:** `Σ (Probability_i × Liquidity Outcome_i)`

---

### **Reading 132: Intraday Liquidity Risk Management**
**Key Concepts & Definitions**
*   **Intraday Liquidity:** Funds accessible during the business day to meet time-specific obligations.
*   **Nostro Account:** Account a bank holds in a foreign currency at another bank; used to settle transactions.
*   **PCS Systems:** Payment, Clearing, and Settlement systems; single settlement per day (late afternoon).
*   **Contingent Liquidity Arrangements:** Backup credit lines from commercial/central banks for FMUs.
*   **Two Perspectives for Monitoring:** 1) Amount of intraday credit the institution **utilizes**, 2) Amount of intraday credit the institution **extends to clients**.
*   **Key Measures:** Daily maximum intraday liquidity usage, Client intraday credit usage (peak daily overdraft vs. credit line), Total bank intraday credit lines available and usage, Payment throughput, Settlement positions.

---

### **Reading 133: Monitoring Liquidity**
**Key Concepts & Definitions**
*   **Deterministic Cash Flows:** Predictable in both timing and amount (e.g., fixed-rate bonds, mortgages).
*   **Stochastic Cash Flows:** Random/unpredictable in timing and/or amount.
*   **TSECF:** Term Structure of Expected Cash Flows (collection of positive and negative expected cash flows ordered by date).
*   **TSECCF:** Term Structure of Cumulated Expected Cash Flows.
*   **TSAA:** Term Structure of Available Assets.
*   **TSLGC:** Term Structure of Liquidity Generation Capacity.
*   **TSCLGC:** Term Structure of Cumulated Liquidity Generation Capacity.
*   **Liquidity Option Impact:** 1) Impact on the balance sheet, 2) Financial impact (positive or negative) on cash flows.
*   **Transactions Increasing TSAA:** Buy/sell back transactions, Security borrowing transactions.

**Formulas**
*   **TSECCF:** `TSECCF(t_0, t_k) = {Cf+_e(t_0, t_0), Cf-_e(t_0, t_0), ..., Cf+_e(t_0, t_k), Cf-_e(t_0, t_k)}`
*   **Cumulate:** `TSECCF_year n = TSECCF_year n-1 + Net CF_year n`
*   **TSCLGC Inflow (Bond Sale):** `Notional × (Price/100 + Coupon Rate × Fraction of Year)`
*   **Buy/Sell Back – Amount Paid at Start:** `Par Value × Purchase Price % + Par Value × Annual Rate × Fraction of Year`
*   **Buy/Sell Back – Amount Received at End:** `Notional × (Forward Price % + Coupon Rate × Fraction)`
*   **Security Lending Fee:** `Notional × Fee Rate × Maturity (years)`

---

### **Reading 134: Failure Mechanics of Dealer Banks**
**Key Concepts & Definitions**
*   **Dealer Bank:** Intermediates between issuers and investors (primary market) and between sellers and buyers (secondary market).
*   **OTC Trades:** Negotiated privately between two parties without exchange oversight.
*   **Repo Haircut:** Risk mitigation reflecting the risk/liquidity of collateral securities.
*   **"Too Big to Fail":** Implicit government guarantee → moral hazard → taking more inefficient risks.
*   **Matched Book:** Dealer offsets client-initiated derivative positions with counterbalancing trades; profits from bid-offer spread.
*   **Key Mechanisms of Collapse:** Flight of short-term creditors, departure of prime brokerage clients, cash-draining by derivatives counterparties, loss of clearing-bank privileges.
*   **Policy Tools for Social Costs:** Regulatory supervision & risk-based capital requirements, Deposit insurance, Regulatory resolution mechanisms.
*   **Key Facts:** Total market value of all derivatives = zero; derivatives cause net losses only through frictional costs (bankruptcy, legal fees); Interest-rate swaps are the most widely held derivatives by banks; counterparty exposure reduced through collateral.

---

### **Reading 135: Liquidity Stress Testing**
**Key Concepts & Definitions**
*   **Stress Testing Process:** Begins with identifying risk and event analysis → scenario development → assumptions → execution.
*   **Operational Liquidity:** Cash for daily funding and orderly payment clearance.
*   **Contingent Liquidity:** Funds set aside for unexpected needs.
*   **Strategic Liquidity:** Cash for acquisitions, new ventures.
*   **Organizational Scope:** Parent organization, subsidiary legal entities, shared service centers, lines of business (separate tests needed).
*   **Currency Consideration:** Must consider liquidity impact of currency conversion to avoid mismatch for offshore subsidiaries.
*   **Time Horizon Disadvantage:** Longer horizons → more susceptible to forecast errors based on baseline budgeting.
*   **Scenario Characteristics:** Define the scenario, distinguish systematic vs. idiosyncratic risk, distinguish levels of severity. *(Sources of liquidity are NOT typically considered in scenario development).*
*   **Key Assumptions:** Overall stress level, nature of scenario, impact on cash flows. *(Expected returns and deposit inflows are NOT key assumptions).*
*   **Governance Roles:** 
    *   **Treasury:** Recommends stress testing scenarios.
    *   **ALCO:** Designs liquidity risk policy limits, escalates exceptions.
    *   **Model Risk Management:** Independent validation of stress testing model.
    *   **Internal Audit:** Periodical review of framework, procedures, controls.
*   **Integration with Capital Stress Testing:** Must incorporate essential capital infusions from subsidiary entities.

---

### **Reading 136: Liquidity Risk Reporting**
**Key Concepts & Definitions**
*   **Deposit Tracker Report:** Weekly/monthly report with month-end actuals by customer type, month-end changes, and forecasts. *(Does NOT include annual LTD ratio).*
*   **Mismatch Report:** Reflects maturity gap for all assets/liabilities per time bucket with adjustment for liquid securities; comprises cumulative liquidity cash flow.
*   **Large Depositor Concentration:** "Large" = deposit of 5% of total liabilities.
*   **Liquidity Gap:** Mismatch in supply/demand for a security or maturity dates of securities.
*   **Funding Yield Curve:** Rising significantly beyond peers → indicates funding stress.
*   **Off-Balance Sheet Items:** Liquidity lines, Letters of credit, Revolving credit facilities. *(Liquid assets are NOT off-balance sheet).*
*   **Liability Profile Includes:** Customer individuals, Highly liquid security repos, Asset-backed securities. *(Highly liquid assets are NOT part of liability profile).*
*   **Regulatory Treatment:** Current accounts and rolling deposits = short-term liabilities. Exception: If demonstrated to behave as long-term in "behavioral" terms, may be treated as long-term. 50% of deposits can be treated as long-term if evidently stable over time. UK regulations: Derivative values/notionals are NOT included in liquidity ratio for off-balance sheet items.

**Formulas**
*   **Loan-to-Deposit Ratio (LTD):** `Total Customer Loans / Total Customer Deposits`

---

### **Reading 137: Contingency Funding Planning (CFP)**
**Key Concepts & Definitions**
*   **CFP Framework Components:** Governance & oversight, Contingent actions, Monitoring & escalation, Scenario & liquidity gap analysis. *(Liquidity monitoring is NOT a CFP component).*
*   **First Escalation Level:** Elevated monitoring of market conditions and effect on business performance (not survival mode).
*   **Integrated Frameworks:** Enterprise Risk Management (ERM), Business continuity and crisis management, Capital management. *(Financial management is NOT part of CFP integration).*
*   **CFP Stakeholders:** Risk and capital committee, Management committee (ALCO, investment committee), Operations and technology. *(Internal audit committee is NOT a CFP stakeholder).*
*   **EWI Factors for CFP:** Macro-environment measures, Industry measures, Institution-specific measures. *(Financial measures are NOT typically used as EWIs in CFP).*
*   **Events with Negative Liquidity Impact:** Predatory trade, Unavailability of FHLB funding, Exceeding intraday debit cap. *(Shifting from short-term to long-term funding does NOT have negative impact).*
*   **Liquidity Health Ratios:** Used Capacity to Total Borrowing Capacity (measures borrowing capacity available based on used vs. total capacity). Indicate institution's liquidity base and strength.
*   **Scenario Alignment:** CFP scenarios should align with liquidity stress testing framework AND recovery/resolution plans. Should cover both systemic and institution-specific risks.

---

### **Reading 138: Managing and Pricing Deposit Services**
**Key Concepts & Definitions**
*   **Cost-Plus Pricing:** Charge enough to cover all costs + profit margin.
*   **Relationship Pricing:** Price based on number of services used; increases customer dependency/loyalty.
*   **Conditional Pricing:** Fee schedule based on maintaining minimum balance.
*   **Marginal Cost Deposit Pricing:** Weighted average cost of NEW funds; preferred over historical average because it reflects current market conditions.
*   **FDIC Insurance:** $250,000 per depositor, per insured bank, per ownership category. After merger, deposits separately insured for 6 months grace period.

**Formulas**
*   **Cost-Plus Unit Price:** `Operating Expense per Unit + Overhead Expense per Unit + Planned Profit Margin per Unit`
*   **Adjusted Operating Expenses (with balance savings):** `Original OpEx - (Savings % × Original OpEx)`
*   **APY (Truth in Savings Act):** `100 × [ (1 + Interest Earned / Average Account Balance)^(365 / Days in Period) - 1 ]`
*   **Average Account Balance:** `Σ (Balance_i × Days_i) / 365`
*   **Marginal Cost of New Deposits:** `Change in Total Interest Cost / Change in Funds Raised`

---

### **Reading 139: Managing Nondeposit Liabilities**
**Key Concepts & Definitions**
*   **Commercial Paper:** Unsecured, short-term (overnight to ~270 days), issued by well-known companies at discount.
*   **Primary Credit:** Fed loan to financially sound institutions; rate higher than fed funds rate.
*   **Secondary Credit:** For smaller, less secure institutions.
*   **Seasonal Credit:** For small institutions with seasonal swings.
*   **Yankee CDs:** Negotiable CDs issued by foreign banks in the US.
*   **Overnight Loan:** Unwritten, often uncollateralized, negotiated by phone, repaid next day.

**Formulas**
*   **RP Interest Cost:** `Amount Borrowed × RP Rate × (Days / 360)`
*   **Negotiable CD Amount Due:** `Principal + Principal × (Days to Maturity / 360) × Annual Rate`
*   **Available Funds Gap (AFG):** `(Current & Projected Loans + Investments) - (Current & Expected Deposit Inflows + Other Funds)`
*   **Effective Cost Rate:** `(Interest Cost + Noninterest Cost) / Net Investable Funds`
*   **Break-Even Cost Rate:** `Total Funding Costs / Earning Assets`
*   **Weighted Average Overall Cost of Capital:** `Break-Even Cost + [ (After-Tax Cost of Stockholders' Investment / (1 - Tax Rate)) × (Stockholders' Investment / Earning Assets) ]`
*   **Pooled-Funds Marginal Cost:** `All Expected Operating Expenses / All New Funds Expected`
*   **Hurdle Rate:** `All Expected Operating Costs / Dollars Available for Earning Assets`

---

### **Reading 140: Repurchase Agreements and Financing**
**Key Concepts & Definitions**
*   **Repo:** Short-term collateralized loan; seller sells securities and agrees to repurchase at higher price.
*   **Reverse Repo:** From the buyer's perspective (lending cash, receiving securities).
*   **General Collateral (GC):** Lender accepts any security within broad categories.
*   **Trading Special:** Bonds most in demand to be borrowed; lender initiates repo to obtain specific security.
*   **Margin Call:** In declining markets, borrower must provide additional collateral; in advancing markets, borrower may withdraw collateral.
*   **Day Count Convention:** Actual/360 for repos.
*   **Key Facts:** Repos are money market instruments. "Buy back" price is fixed at inception. Repos are short-term (typically overnight to 21 days, up to ~1 year). During 2007/2008 crisis: firms borrowed at low rates using low-quality collateral. Repos are more secure than stocks due to short maturity + high-quality collateral.

**Formulas**
*   **Repurchase Price:** `Invoice Price × (1 + (Repo Rate × Days) / 360)`
*   **Financing Value (Special Spread):** `Market Value × (Days at Special / 360) × Special Spread`
*   **Lending Value:** `Cash Amount × (Days × Spread) / 360`

---

### **Reading 141: Liquidity Transfer Pricing (LTP)**
**Key Concepts & Definitions**
*   **LTP Cost Components:** Liquidity risk costs, Costs of liquidity cushion, Costs of liquidity reserves. *(Expense costs are NOT an LTP component).*
*   **Pooled Average Costs Approach:** Chosen for simplicity and to minimize net interest income deviation.
*   **Matched-Maturity Marginal Cost of Funds:** Converts fixed-rate borrowing cost to floating; aligns cost with maturity.
*   **GFC Problems with Bank Liquidity:** Failed to use stress-testing outcomes for liquidity cushion size, assumed cushion assets were highly liquid and correlated, preferred short-term funding (overnight). *(NOT a problem: Banks that properly accounted for costs, benefits, and risks of liquidity).*
*   **Steps for Improved LTP:** Centralizing wholesale funding via treasury, developing trading book procedures and policies, applying higher funding rates on net funding needs upon breaching limits.

**Formulas**
*   **Contingent Liquidity Risk Rate:** `[(Limit - Drawn Amount) / Limit] × Likelihood of Drawdown × Cost of Funding Liquidity Cushion`
*   **Amortizing Loan Funding Liquidity Charge:** `Σ (i × Term Liquidity Premium_i) / Σ i`
*   **Monthly Amortization Payment:** `R = (P × i) / [1 - (1+i)^-n]` *(where i = r/m, n = m × t)*

---

### **Reading 142: US Dollar Shortage in Global Banking**
**Key Concepts & Definitions**
*   **Cross-Currency Funding:** Banks invest in one currency and fund in another via FX swaps.
*   **Carry Trade:** Borrowing in low-yielding currency, investing in high-yielding currency.
*   **US Dollar Funding Gap:** Amount of USD invested in longer-term assets not supported by longer-term USD liabilities.
*   **Maturity Transformation:** Converting short-term liabilities into long-term assets; excessive mismatch → vulnerable to funding risks.
*   **International Lending of Last Resort:** Fed extends loans using foreign currency collateral to foreign central banks; banks access funds via USD auction in their jurisdiction.
*   **Safe Haven Currency:** USD acts as peg for other countries due to high liquidity, high value, and stable political system.
*   **Causes of USD Shortage During GFC:** 1) Increased appetite for foreign currency assets by non-US investors, 2) Cross-currency funding (European/Japanese banks), 3) US dollar funding gap (non-US banks lacked stable dollar deposit base).
*   **International Policy Response Success:** Mitigated upward pressure and interbank rate volatility on the USD.
*   **Challenges Solved by Swap Arrangements:** 1) Fed and foreign counterparts can create any amount of money (vs. limited global institution resources), 2) Swap network does not have information issues leading to moral hazards.
*   **Key Facts:** Banks' foreign claims grew from $10T (2000) to $34T (2007). Financial innovation period included: hedge fund growth, financial structures, universal banking. *(Auctioning of USD was NOT part of financial innovation; it was a policy response).*

---

### **Reading 143: Covered Interest Rate Parity & Cross-Currency Basis**
**Key Concepts & Definitions**
*   **Covered Interest Rate Parity (CIP):** No-arbitrage condition where nominal interest rates in two countries are equal once FX risk is hedged.
*   **Cross-Currency Swap:** Exchange of principal and interest in different currencies; involves exchange and re-exchange of principal (unlike interest rate swaps → bears more counterparty risk).
*   **FX Swap:** Agreement to exchange currencies and reverse at a later date; primarily for short-term FX exposure.
*   **Cross-Currency Basis:** Persistent post-GFC due to balance sheet costs of arbitrage; incorporates financing costs of arbitrageurs.
*   **FX Quote Convention:** GBP/USD = 1.25 means 1 GBP = 1.25 USD.

**Formulas**
*   **CIP Formula:** `F / S = (1 + r_quote) / (1 + r_base)`
*   **Forward Rate:** `F = S × [ (1 + r_quote × T/360) / (1 + r_base × T/360) ]`
*   **Interest Rate Differential:** `r_foreign - r_domestic`
*   **Solving for Foreign Rate:** `r* = (1+r) × (S/F) - 1`
*   **Cross-Currency Swap Cost:** `LIBOR_received currency + |LIBOR_paid currency| + |Basis|` *(Note: If LIBOR is negative, the lender pays interest, not the borrower).*

---

### **Reading 144: ALM and Duration Techniques**
**Key Concepts & Definitions**
*   **Net Interest Margin (NIM):** Net interest income / Total earning assets.
*   **Interest-Sensitive Gap (IS Gap):** IS Assets − IS Liabilities.
*   **Relative IS Gap:** IS Gap / Total Assets.
*   **Interest-Sensitive Ratio (ISR):** ISA / ISL.
*   **Duration Gap:** Dollar-weighted duration of assets − Dollar-weighted duration of liabilities × (Total Liabilities / Total Assets).
*   **Zero Duration Gap:** Fully hedged position; changes in rates affect assets and liabilities equally.
*   **Key Facts:** Sensitivity to interest rates is higher when: coupon is lower, duration is higher, overall interest rates are lower. Duration matching (immunization) is costly and time-consuming. Duration alone is inaccurate for large rate changes without convexity. IS gap fails to consider implications on equity positions (duration gap addresses this).

**Formulas**
*   **Net Interest Margin:** `(Interest Revenue - Interest Cost) / Total Earning Assets`
*   **Change in Net Interest Income (Gap Analysis):** `Cumulative Gap × Δ Interest Rate`
*   **Dollar IS Gap:** `ISA - ISL`
*   **Relative IS Gap:** `IS Gap / Total Assets`
*   **Leverage-Adjusted Duration Gap (DGAP):** `D_A - D_L × (L / A)`
*   **Change in Net Worth:** `[-D_A × (Δr / (1+r)) × A] - [-D_L × (Δr / (1+r)) × L]`
*   **Dollar-Weighted Duration:** `Σ [(Amount_i / Total) × D_i]`
*   **Bank Discount Rate (DR):** `[(FV - P) / FV] × (360 / Days)`
*   **YTM Equivalent Yield:** `[(FV - P) / P] × (360 / Days)`

---

### **Reading 145: Illiquid Assets**
**Key Concepts & Definitions**
*   **Illiquid Assets:** Cannot be easily bought/sold without substantial price change; characterized by information asymmetry.
*   **Selection Bias:** Returns observed only when underlying asset values are high → overestimates alpha, underestimates beta.
*   **Survivorship Bias:** Poorly performing funds stop reporting/are excluded → overestimates returns, underestimates risk.
*   **Infrequent Trading/Sampling Bias:** Assets not traded regularly → stale prices → risk estimates (volatility, beta, correlation) are too low.
*   **Autocorrelation:** Current values influenced by past values; prevalent in illiquid markets where valuations rely on past sales/appraisals.
*   **Appraisal Index:** Constructed using expert valuation estimates rather than actual transaction prices.
*   **Unsmoothing:** Process to account for infrequent trading by adding noise back to reported returns to uncover true returns.
*   **Reporting Bias:** Only reporting returns of funds that generated adequate returns → inflates reported returns.
*   **Key Facts:** Illiquid assets can generate excess returns because they allow transfer of idiosyncratic risk from liquid markets (information asymmetry can be exploited). Illiquid assets have higher transaction costs. Including the full population of funds can theoretically eliminate survivorship and reporting bias. Multifactor risk models make alpha and beta estimates more robust for illiquid assets. Availability bias does NOT directly cause overstatement of returns/understatement of risk for illiquid assets.
*   **Vayanos and Wang (2012) Sources of Market Illiquidity:** 1) Transaction costs, 2) The effect of prices, 3) Search frictions. *(Symmetric information is NOT a source; it promotes liquidity).*