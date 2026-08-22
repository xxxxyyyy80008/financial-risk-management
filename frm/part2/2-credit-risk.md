## Credit Risk


### **Reading 79: Fundamentals of Credit Risk**
*   **Key Concepts**: 
    *   **Credit Risk**: The probability of financial loss due to a counterparty's failure to meet agreed financial obligations.
    *   **Insolvency vs. Bankruptcy**: Insolvency is a financial state where liabilities exceed assets. Bankruptcy is a formal legal declaration and court-supervised process.
    *   **Default**: Failure to meet specific financial obligations (e.g., missed payments).
    *   **Accounts Receivable Financing Risk**: The primary risk is the default of the client's customers (the original debtors of the receivables).

### **Reading 80: Governance**
*   **Key Concepts**:
    *   **Credit Origination**: The initial phase of identifying potential lending opportunities and understanding client needs (distinct from assessment or approval).
    *   **Credit Committee**: Responsible for reviewing/approving significant credit transactions, setting credit policies, and defining risk appetite.
    *   **Governance Framework**: Includes Guidelines (clear, concise, regularly updated), Limits (dynamic, linked to market volatility/AI), Skills (multi-stage analysis, stress testing), and Oversight (independent committee reporting to the board).

### **Reading 81: Credit Risk Management**
*   **Key Concepts**:
    *   **Lending Policies**: Must be tailored to regional economic trends and borrower profiles.
    *   **Related Party Lending**: Total credit to related parties should be restricted to a specific percentage of the bank's Tier 1 capital to mitigate conflicts of interest.
    *   **Collateral & LTV**: Loan-to-Value (LTV) ratios must be periodically adjusted based on the marketability and pricing of securities. Less marketable securities require lower LTVs (higher margins).
    *   **Accounting for Restructured Loans**: Must be measured at net realizable value, with the reduction charged to the income statement immediately.
    *   **Interest in Suspense**: Uncollected interest on nonperforming loans should be suspended and categorized as "interest in suspense" (offsetting accrued interest) to prevent asset/income overstatement.

### **Reading 82: Capital Structure in Banks**
*   **Formulas**:
    *   **Expected Loss (EL)**: $EL = PD \times EAD \times LR$ *(Loss Rate / LGD)*
    *   **Unexpected Loss (UL)**: $UL = EAD \times \sqrt{PD \times \sigma_{LR}^2 + LR^2 \times \sigma_{PD}^2}$
    *   **Binomial Variance of Default**: $Var(X) = n \times PD \times (1 - PD)$
*   **Key Concepts**:
    *   **Beta Distribution**: Used for credit loss modeling due to its flexibility (bounded between 0 and 1). Often combined with **Monte Carlo Simulation** for tail-fitting extreme loss scenarios.
    *   **Economic Capital**: Derived to cover *unexpected* losses at a predetermined confidence level (Expected losses are covered by provisions/pricing).

### **Reading 83: Introduction to Credit Risk Modeling and Assessment**
*   **Key Concepts**:
    *   **CAMEL Rating System**: Regulatory assessment framework: **C**apital adequacy, **A**sset quality, **M**anagement, **E**arnings, **L**iquidity.
    *   **Uncertainties in Lending**:
        *   *Adverse Selection*: High-interest rates discourage good borrowers, leaving a pool of high-risk borrowers.
        *   *Moral Hazard*: Borrower engages in riskier behavior *after* receiving a loan.
        *   *Occasional Uncertainty*: Unforeseen external events (e.g., job loss, economic downturn).
        *   *Cognitive Uncertainty*: Borrower's misunderstanding of their financial capacity or loan terms.

### **Reading 84: Credit Scoring and Rating**
*   **Key Concepts**:
    *   **Credit Scoring**: Internal, numerical, automated, primarily for retail/SME.
    *   **Credit Rating**: External, ordinal (e.g., AAA, BBB), combines quantitative and qualitative analysis, used by investors for corporate/sovereign debt.
    *   **TTC (Through-the-Cycle)**: Stable, long-term view, insulated from short-term economic volatility. Preferred for long-term loan portfolios.
    *   **PIT (Point-in-Time)**: Highly responsive to current economic conditions. Preferred for short-term trading.
    *   **CRA Criticisms**: Issuer-pays model (conflict of interest/upward bias), herd behavior (mimicking leading agencies), lagging indicators (slow to downgrade during crises).

### **Reading 85: Credit Scoring and Retail Credit Risk Management**
*   **Key Concepts**:
    *   **Retail vs. Corporate Exposure**: Retail exposures are "bite-sized" and highly diversified (single default doesn't threaten the bank). Corporate exposures are large and concentrated.
    *   **CFPA (Qualified Mortgages)**: Must not have excess upfront points/fees, DTI ratio $\le$ 43%, no interest-only or negative amortization features, max 30-year term.
    *   **Subprime Crisis Causes**: Relaxation of underwriting standards, low interest rates, fierce competition, and reliance on collateral rather than income verification.

### **Reading 86: Country Risk**
*   **Key Concepts**:
    *   **Sovereign Default Implications**: Increases the likelihood of domestic banking crises (due to sovereign bond holdings) and political turnover.
    *   **Market Indicators**: CDS spreads provide real-time, market-driven assessments of sovereign default risk (unlike lagging credit ratings).
    *   **Herd Behavior**: CRAs following the initial rating adjustments of a leading agency, reducing the value of independent assessments.

### **Reading 87: Estimating Default Probabilities**
*   **Formulas**:
    *   **Recovery Rate (RR) & LGD**: $RR = 1 - \frac{Defaulted\ Amount}{Total\ Exposure}$ ; $LGD = 1 - RR$
    *   **Hazard Rate ($\lambda$) Unconditional PD**: $PD = 1 - e^{-\lambda \times t}$
    *   **Conditional PD**: $\frac{e^{-\lambda \times t_1} - e^{-\lambda \times t_2}}{e^{-\lambda \times t_1}}$
    *   **Merton Model PD**: $PD = N\left[ \frac{\ln(F) - \ln(V) - (\mu)(T-t) + 0.5\sigma^2(T-t)}{\sigma\sqrt{T-t}} \right]$
    *   **Credit Spread**: $CS = -\frac{1}{T-t} \ln\left(\frac{D}{F}\right) - R_f$
    *   **Vulnerable Option Value**: $(1 - PD) \times c + PD \times RR \times c$
*   **Key Concepts**:
    *   **Merton Model**: Views equity as a call option on the firm's assets (strike = debt face value). Debt is viewed as risk-free debt minus a put option.
    *   **Subordinated Debt Payoff**: $D - \max(D - V, 0)$ (Senior debt gets paid first; subordinated gets the residual).

### **Reading 88: Credit Value at Risk**
*   **Formulas**:
    *   **Vasicek Model (Worst-Case Default Rate)**: $V(X, T) = N\left( \frac{N^{-1}(PD) + \sqrt{\rho}N^{-1}(X)}{\sqrt{1-\rho}} \right)$
    *   **Regulatory Capital**: $EAD \times V(X, T) \times LGD$
*   **Key Concepts**:
    *   **Credit VaR**: Maximum potential credit loss over a specified time at a given confidence level (encompassing defaults and rating migrations).
    *   **Transition Matrices**: Used to estimate the likelihood of rating migrations. Multi-year matrices are derived by squaring the 1-year matrix (Markov chain assumption).
    *   **Gaussian Copula**: Used to model joint default probabilities and correlation structures in portfolios.

### **Reading 89: Portfolio Credit Risk**
*   **Formulas**:
    *   **Joint Default Probability**: $\pi_{12} = \rho_{12}\sqrt{\pi_1(1-\pi_1)}\sqrt{\pi_2(1-\pi_2)} + \pi_1\pi_2$
    *   **Default Correlation**: $\rho_{12} = \frac{\pi_{12} - \pi_1\pi_2}{\sqrt{\pi_1(1-\pi_1)}\sqrt{\pi_2(1-\pi_2)}}$
    *   **Portfolio Expected Loss**: $EL_P = \sum (PD_i \times EAD_i \times LGD_i)$
*   **Key Concepts**:
    *   **Diversification Benefit**: Portfolio UL is less than the sum of individual ULs unless correlation is perfect ($\rho = 1$).
    *   **Perfect Correlation ($\rho = 1$)**: The portfolio behaves as a single credit; either all default or none default.

### **Reading 90: Credit Risk (xVA Framework)**
*   **Key Concepts**:
    *   **CVA (Credit Value Adjustment)**: Market value of counterparty credit risk (reduces portfolio value).
    *   **DVA (Debit Value Adjustment)**: Adjustment reflecting the firm's *own* credit risk (increases portfolio value if own credit deteriorates).
    *   **FVA (Funding Value Adjustment)**: Cost differential from actual funding requirements vs. idealized risk-free rates.
    *   **MVA (Margin Value Adjustment)**: Costs associated with posting collateral/margin.
    *   **KVA (Capital Value Adjustment)**: Cost of holding regulatory capital against potential future credit losses.

### **Reading 91: Credit Derivatives**
*   **Key Concepts**:
    *   **Credit Default Swap (CDS)**: Transfers credit risk. *First-to-Default Basket* pays on the first default in a basket. *Add-up Basket* pays on any individual default.
    *   **Total Return Swap (TRS)**: Exchanges total economic performance of an asset (income + capital gains) for a floating rate.
    *   **CDS Options**: Call option (right to buy protection); Put option (right to sell protection).
    *   **Synthetic CDO**: Repackages credit risk into tranches using CDS rather than cash bonds.

### **Reading 92: Derivatives & Central Clearing Mechanics**
*   **Key Concepts**:
    *   **Exchange vs. OTC**: Exchanges offer standardization, transparency, and CCP clearing. OTC offers customization but carries bilateral counterparty risk.
    *   **Novation**: CCP replaces the original bilateral contract with two new ones (CCP becomes buyer to every seller, seller to every buyer).
    *   **Compression**: Eliminating redundant/offsetting contracts to reduce notional exposure while maintaining net economic risk.

### **Reading 93: Counterparty Risk and Beyond**
*   **Formulas**:
    *   **CCR Exposure**: $\max(Value - VM - IM_R, 0)$
    *   **Funding Risk Exposure**: $MTM - VM + IM_P$
*   **Key Concepts**:
    *   **Bilateral Exposure**: Both parties face risk depending on whether the MtM is positive or negative.
    *   **Settlement Risk**: Timing difference in final exchange of obligations.
    *   **Wrong-Way Risk (WWR)**: Exposure to a counterparty is *adversely* correlated with their credit quality (exposure increases as default probability rises).
    *   **Right-Way Risk (RWR)**: Favorable correlation (exposure decreases as default probability rises).

### **Reading 94: Netting, Close-out, and Related Aspects**
*   **Key Concepts**:
    *   **ISDA Master Agreement**: Standardized legal framework for OTC derivatives (covers netting, default events, close-out).
    *   **Close-out Netting**: Terminating all agreements with an insolvent counterparty and offsetting values into a single net payable/receivable amount.
    *   **Break Clause (ATE)**: Allows termination of a trade if creditworthiness deteriorates *before* bankruptcy.
    *   **Walk-away Feature**: Allows a party to cease payments without settling amounts payable to a defaulting counterparty.

### **Reading 95: Margin (Collateral) and Settlement**
*   **Formulas**:
    *   **Collateral Required (with Haircut)**: $\frac{Required\ Collateral\ Call}{1 - Haircut}$
*   **Key Concepts**:
    *   **CSA (Credit Support Annex)**: Regulates collateral posting (Thresholds, Independent Amounts, Minimum Transfer Amounts).
    *   **Threshold**: Level of unsecured exposure a party is willing to accept before calling for collateral.
    *   **Independent Amount (Initial Margin)**: Upfront security deposit against potential future exposure.
    *   **Title Transfer vs. Security Interest**: Title transfer changes legal ownership (allows rehypothecation); security interest creates a lien (ownership remains with poster).
    *   **Haircut**: Discount applied to collateral value to account for market volatility/liquidity risk.

### **Reading 96: Central Clearing**
*   **Key Concepts**:
    *   **CCP Loss Waterfall**: 1. Defaulter's Initial Margin $\rightarrow$ 2. Defaulter's Default Fund $\rightarrow$ 3. CCP's "Skin-in-the-game" $\rightarrow$ 4. Non-defaulters' Default Fund $\rightarrow$ 5. Variation Margin Haircutting.
    *   **Skin-in-the-game**: CCP's own capital committed to the waterfall to align incentives and mitigate moral hazard.
    *   **Auctions & Porting**: Mechanisms to neutralize/transfer a defaulter's portfolio to solvent members.

### **Reading 97: Future Value and Exposure**
*   **Formulas**:
    *   **Netting Factor**: $\frac{\sqrt{n + n(n-1)\bar{\rho}}}{n}$ *(Lower factor = higher netting benefit)*
*   **Key Concepts**:
    *   **Expected Exposure (EE)**: Mean of the distribution of exposures at a future date.
    *   **Expected Positive Exposure (EPE)**: Time-weighted average of EE over the life of the contract.
    *   **Potential Future Exposure (PFE)**: Maximum exposure expected at a future date at a given confidence level (e.g., 95% or 99%).
    *   **EEE & EEPE**: Effective Expected Exposure / Effective EPE. Introduced by Basel to address the underestimation of exposure for short-dated transactions (roll-over risk).

### **Reading 98: CVA (Part A)**
*   **Formulas**:
    *   **CVA (Running Spread)**: $CVA = EPE \times Credit\ Spread$
    *   **Running Spread**: $\frac{Upfront\ CVA}{Duration}$
    *   **Bilateral CVA (BCVA)**: $BCVA = -EPE \times Spread_c - (ENE \times Spread_p)$
    *   **Unilateral CVA**: $CVA_n = LGD_n \sum_{j=1}^T EE_n(t_j) \times q_n(t_{j-1}, t_j)$
    *   **Stress Loss**: $CVA_S - CVA$
*   **Key Concepts**:
    *   **Marginal / Incremental CVA**: Used to allocate CVA to individual trades within a netting set (CVA within a netting set is *non-additive* due to offsetting).

### **Reading 99: CVA (Part B – Wrong-way Risk)**
*   **Key Concepts**:
    *   **WWR Modeling**: *Jump approaches* are more realistic for specific WWR where exposure increases abruptly (e.g., FX crises, sovereign defaults). *Continuous approaches* (intensity/structural) may underestimate WWR during market jumps.
    *   **Mitigation**: Initial Margin requirements reduce WWR exposure by lowering uncollateralized credit risk, though they do not eliminate it entirely during sudden jumps.

### **Reading 100: Stress Testing Counterparty Exposures**
*   **Key Concepts**:
    *   **Stress Testing**: Simulation technique evaluating portfolio impact under extreme but plausible events.
    *   **Stressed Current Value**: Created by assuming a scenario of underlying risk factor changes and re-pricing the portfolio.
    *   **Limitations**: Aggregating individual stressed current exposures overestimates losses because it implicitly assumes *all* counterparties default simultaneously (ignores correlation and WWR).

### **Reading 101: Structured Credit Risk**
*   **Key Concepts**:
    *   **Securitization & Tranching**: Pooling assets and dividing cash flows into tranches (Equity/First-loss, Mezzanine/Junior, Senior).
    *   **Waterfall Structure**: Rules dictating top-down priority of cash flow distribution (Senior $\rightarrow$ Mezzanine $\rightarrow$ Equity).
    *   **Attachment/Detachment Points**: Define the loss thresholds where a tranche begins to absorb losses and where it is completely wiped out.
    *   **Credit Enhancements**: *Internal* (Overcollateralization, Excess Spread, Holdback) vs. *External* (Letters of Credit, Pool Insurance, Monolines).

### **Reading 102: An Introduction to Securitization**
*   **Formulas**:
    *   **CPR & SMM**: $CPR = 1 - (1 - SMM)^{12} \implies SMM = 1 - (1 - CPR)^{1/12}$
    *   **Prepayment Amount**: $SMM \times (Outstanding\ Principal - Scheduled\ Monthly\ Principal\ Payment)$
    *   **PSA Benchmark CPR**: $6\% \times \frac{m}{30}$ *(for months $m \le 30$, then levels at 6%)*
    *   **Delinquency Ratio**: $\frac{Receivables\ > 90\ days\ past\ due}{Total\ receivables}$
    *   **Default Ratio**: $\frac{Written\ off\ receivables}{Total\ receivables}$
    *   **Debt Service Coverage Ratio (DSCR)**: $\frac{Net\ Operating\ Income}{Debt\ Payments}$
    *   **Weighted Average Coupon (WAC)**: $\frac{\sum (Amount_i \times Coupon_i)}{\sum Amount_i}$
    *   **Weighted Average Maturity (WAM)**: $\frac{\sum (Amount_i \times Maturity_i)}{\sum Amount_i}$
*   **Key Concepts**:
    *   **CMBS vs. RMBS**: CMBS loans are typically *non-recourse* (fully secured by the commercial property, issuer not personally liable). RMBS are generally recourse.
    *   **Basel I**: Requires banks to hold at least 8% capital against risk-weighted assets ($8 of capital for every $100 of RWA).