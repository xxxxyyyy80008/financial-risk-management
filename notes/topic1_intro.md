# Study Notes on **Financial Risk Management** by Professor Carol Alexander 

Original resource: [youtube](https://www.youtube.com/watch?v=mXC5yJ5MKwM&list=PL_V1gySvrP_ums2nxs_YuKY5Ufdmhyoh7&index=6)

# Topic 1: Introduction to Financial Risk Management

## 1.1 What is Financial Risk Management?


**Definitions of Risk and Financial Risk**

- **Risk in general** is the uncertainty in the value of a random variable at some time in the future  
- **Financial risk** is the uncertainty in the value of a portfolio at the risk horizon  
  - A portfolio could be anything from holding shares in just one stock to having hundreds of positions on various financial assets and financial instruments  
  - The risk horizon is the time period over which risk is forecast  
  - The typical market risk horizon is 1 or 10 days and the typical credit risk horizon is 1 year



**Definition of Investment Horizon**

- This is the time period of an investment: short-term (days to months), medium-term (six months to a few years), or long-term (several years) – although this classification does depend on the market

- It also refers to the time period over which asset managers report returns to their investors – for hedge funds this is usually 1 month, for pension funds this is usually 12 months

- Reported returns may or may not be adjusted for risk – typically risk-adjusted returns are reported by the Sharpe ratio but many other risk-adjusted return metrics exist

- They are reported ex post and/or forecast ex ante

---

**Main Categories of Financial Risks**

1. Market Risk: Financial risk arising from changes in an interest rate or the price of a financial asset or instrument  
2. Credit Risk: The uncertainty in the value of a portfolio arising from default on an obligation or a change in credit rating  
3. Liquidity Risk: The risk that a transaction cannot be made  
4. Operational Risk: The risk of loss associated with non-financial matters, *including* reputational issues like computer hacks and regulatory or compliance issues like fraud  
5. Basis Risk: The risk arising from imperfect hedging



**Liquidity Risk**

The risk that a transaction cannot be made due to lack of funds or insufficient buyers or sellers  

Two types of liquidity risk:  

- **Funding liquidity risk**: A risk that a treasury has insufficient funding to meet commitments as they arise  
  - Example: A company cannot raise funds (by taking new loans) to pay off expiring loans  

- **Trading liquidity risk**: The risk that there are no buyers or sellers for the trade at what they perceive is the fair value  
  - It is related to trading volumes and market depth



**Operational Risk**

The risk of loss associated with non-financial matters  

Two main categories of operational risks:  

- **High Impact – Low Frequency**: An event which occurs rarely but has severe financial consequences  
  - Examples: Fraud, terrorism, cyber crime  

- **Low Impact – High Frequency**: Events which occur frequently but which have minor financial consequences  
  - Examples: Every-day IT system failures, transaction processing


---

**Hedging with Futures**

- Traders can mitigate risks by hedging the risk of a spot position by buying or selling a futures contract

- There are two counterparties to futures contracts, the buyer is long – makes money when the price goes up – and the seller is short – makes money when the price goes down

  - For instance, a farmer need to sell his wheat in August, and to remove uncertainty about the price he gets in August he can fix the price in April, say, by opening a short position on a futures contract

  - Alternatively, an airline needs to buy jet oil one month from today, and to lock in the price now it can take a long position in a futures contract today



**Basis Risk**

The uncertainty due to mismatches in the underlying and the hedging instrument

Two reasons for basis risk:

- First there may be a **difference** between the spot position – here the **underlying** – and the futures contract – here the **hedging instrument**

  - For example, an airline can only buy heating oil futures – because jet oil futures don’t exist

- Secondly, futures contracts have standard **maturities** which may not match the time of buying or selling the spot position

  - For example, the airline needs jet oil on the first of every month, but the heating oil futures mature in the third week of each month

---

**Traditional Activities for Risk Managers**

1. Daily monitoring of profit and loss (P&L)  
2. Daily monitoring of risks using Value-at-Risk (VaR) models  
3. Reporting detailed breakdown of risk exposures to the board  
4. Implementing procedures to limit losses, e.g. stop-loss limits  
5. Independent validation including backtesting of risk models  
6. Independent oversight of trading activities, including stress testing  
7. Independent validation of traders’ pricing and hedging models



**Traditional Roles in Financial Risk Management**

1. **Risk managers**: measure, monitor and control the risks of the traders by setting trading limits

2. **Traders**: execute buy and sell orders in markets and engage in profit-making activities like market making, speculation, arbitrage and hedging

3. **Portfolio managers**: allocate assets to portfolios focusing on long-term strategy and risk management to achieve specific risk-adjusted returns

4. **Auditors**: examine balance sheets, banking books and trading books to ensure accuracy and integrity

5. **Compliance officers**: Work with auditors and risk managers to comply with laws and regulations



---

**Measuring Risk Exposures: Risk Factor Attribution**

- A risk factor is a major market indicator, such as a stock or bond or commodity index, or a currency or a yield curve of interest rates.

- **Systematic risk** is the risk associated with the dependence of a portfolio’s value on changes in its risk factors.

- For example, if the entire **UK LIBOR** curve were to shift up by 10 basis points, by how much would the value of my **interest rate swaps portfolio change**?

- Risk factor attribution is the mapping of **total systematic risk** to component risks corresponding to different types of risk factor to find out how much each risk factor contributes to the total systematic risk.

- **Specific or unsystematic risk** is the part of portfolio risk that is not attributed to changes in risk factors.



**Aggregating Risk**

- A large bank or corporation will have thousands of positions on equity, currency, bond, commodity and derivatives exposures.

- Very large portfolios may be sub-divided into smaller portfolios, e.g. all equities → UK, US and EU exposures.

- The bank or corporation’s exposures are divided into portfolios and risks are estimated for each portfolio.

- Risk may be calculated at the portfolio level and at very granular levels, e.g. at the **desk level**, and even more granular, on each individual trader’s **trading book** so that every trader’s **risk limits** can be monitored.

- Then risk is aggregated using some broad assumptions on the correlations between all these positions and portfolios.

---

## 1.2 Financial Assets and Instruments



**Basic Terminology**

- Some examples of **real assets** are cash currencies, art, real estate – and commodities like copper, wheat, oil etc.

- A **financial asset** is a claim on a real asset. The most common type is a **security**, so-called because it is (a more or less secure) claim on a company or a government.

- There are two kinds of security:
  - Bonds (e.g., corporate bonds, government bonds, but also asset-backed securities)
  - Equities (e.g., shares on common stock, exchange traded funds)



**Capital Markets**

- Markets for securities are called the **capital markets**:

  - Bonds are issued via **underwriting** by investment banks and then traded on secondary markets via **brokers** and **dealers** – often the same entity – major investment banks, but also specialists like Cantor Fitzgerald.

  - Equities are issued via an **initial public offering (IPO)** – also underwritten by an investment bank – and then traded on exchanges in the secondary market.

- The market capitalization (**market cap**) of a bond or a stock is the price per unit × number of units issued.

- At end of 2024 global market caps of equities was $127 tr and of bonds was $145 tr – both exceeding global GDP ($114 tr).



**Bonds**

- Bonds have a defined **maturity** and most carry a regular periodic payment called a **coupon** which is either **fixed** or **floating**.

- Examples of bonds with fixed coupon: US treasury bonds, UK gilts, investment grade company bonds (rated BBB or higher). These can have very long terms – up to 100 years.

- Bonds with variable coupons typically have interest payments linked to the Sterling Overnight Index Average, e.g., **floating rate notes** (typically 2–5 years maturity) whose **spread** over SONIA depends on the issuer’s credit rating.

- Discount bonds have no coupon but they are issued below par, namely at less than 100 and redeemed at 100 (the face value). These tend to be very short-term.

- Bonds are subject to credit risk of the issuer (a company or government) as reflected by their credit rating. In case of a company default, bond holders have a preference claim over shareholders for the capital recovered.



**Equities**

- A cash equity is a **share** of a company’s common stock  
- Shares have an indefinite maturity and typically carry a periodic and variable payment called a **dividend**  
- Subject to **market risk** including **liquidity risk**  
- Stocks are grouped into **stock market indices**, e.g.,  
  - DJIA: Dow Jones Industrial Average (30 large-cap US stocks)  
  - Russell 5000 (5000-stock mixed-cap US index)  
- Indices cannot be traded – but equity instruments such as **index futures** and **exchange-traded funds** (or notes) are very actively traded on exchanges

---

**Financial Instruments**

- A financial instrument is any contract that gives rise to a financial asset of one entity and a financial liability of another entity.

- A loan is a cash instrument not directly traded in capital markets, but can be **securitized** e.g., as **mortgaged-backed securities (MBS)**. These are recorded on a company’s balance sheet, but derivative instruments are not.

- A derivative instrument is just a **bet** on anything that can be measured, e.g. rainfall, temperature, volatility.

- Three broad categories of derivative contracts: futures and forwards, options and swaps.

- Always two counterparties to a derivatives transaction – the buyer and the seller. So, in contrast to a security, the market cap of all derivative contracts outstanding is **zero**.


**Exchange-Traded Funds and Notes**

**Derivative-like exposures for ordinary investors**

- **Exchange-Traded Funds (ETFs)**
  - Passive funds simply track a benchmark (usually an index). Active funds attempt to out-perform their benchmark
  - Examples of popular passive ETFs include stock index ETFs (e.g. Spider, Diamond, Cubes) and commodity ETFs (e.g. gold mining stocks, oil companies)

- **Exchange-Traded Notes (ETNs)**
  - Like ETFs but with finite maturity
  - Subject to credit risk of the issuer
  - Examples include volatility ETNs (e.g. VXX, TVIX)



  ## 1.3 Companies & Institutions in Financial Markets



**Traditional Financial Entities**

Traditional financial markets involve various companies and institutions that play key roles in facilitating the exchange of financial assets, managing risks, and ensuring efficient capital flow.

These entities operate across different segments of traditional financial markets, including equity markets, bond markets, foreign exchange and commodities markets.

Many new types of entities are involved with **fintech**, especially those involved with big data analysis and AI, and with decentralized financial markets based on blockchains and crypto assets.

---

**Commercial Banks**

- **Role**: Provide essential financial services, including taking deposits, making loans, and operating payment systems. They also offer trading and advisory services in investment products and foreign exchange.

- **Examples**: JPMorgan Chase, Bank of America, HSBC.

- **Function**: They act as intermediaries by issuing loans to businesses and individuals, helping create liquidity, and investing in financial instruments on behalf of clients.


**Investment Banks**

- **Role**: Specialize in services such as underwriting, facilitating mergers and acquisitions (M&A), and providing advisory services for large transactions.

- **Examples**: Goldman Sachs, Morgan Stanley, Deutsche Bank.

- **Function**: Investment banks help companies raise capital through initial public offerings (IPOs) and bond issues, provide strategic advisory, and facilitate large, complex financial transactions.



**Central Banks**

- **Role**: Regulate monetary policy, control inflation, and manage national currency reserves. Central banks also influence interest rates and oversee the stability of the financial system.

- **Examples**: US Federal Reserve, European Central Bank (ECB), Bank of England (BoE).

- **Function**: Central banks influence financial markets by adjusting key interest rates, buying or selling government bonds, and intervening in currency markets to stabilize the economy.

**Exchanges**


- **Role**: Organized marketplaces where financial assets and derivatives are bought and sold

- **Examples**: New York Stock Exchange (NYSE), NASDAQ, London Stock Exchange (LSE), Chicago Mercantile Exchange (CME)

- **Function**: Exchanges provide the infrastructure for trading financial instruments ensuring transparency, liquidity, and fair price discovery.

    - **Example of a transaction**: The exchange provides a platform for buyers and sellers to trade securities. For example, if you want to buy shares of a company, you would place an order with a broker who would then execute the trade on your behalf.

    - The exchange also provides information about the prices of securities, which can be used by investors to make informed decisions. Additionally, exchanges help to ensure that all parties involved in a transaction meet certain standards of conduct and ethics.



**Hedge Funds**

- **Role**: Pool funds from wealthy investors and institutions to engage in advanced investment strategies, such as short selling, leveraging, and derivatives trading.

- **Examples**: Bridgewater Associates, Citadel, Renaissance Technologies.

- **Function**: Hedge funds aim to generate high returns by taking both speculative and hedged positions in a wide range of assets. Their high-risk strategies can impact market prices and liquidity.


**Asset Managers**

- **Role**: Collect funds from many investors to invest in a diversified portfolio of stocks, bonds, or other securities.

- **Examples**: Vanguard, BlackRock (iShares), Fidelity.

- **Function**: These institutions allow individual investors access to diversified portfolios, lowering the risk associated with investing in single securities.



**Pension Funds**

- **Role**: Manage retirement savings for employees, investing in a range of financial assets to ensure long-term growth and income.

- **Examples**: Universities Superannuation Scheme (USS), Canada Pension Plan Investment Board (CPPIB).

- **Function**: Pension funds are major institutional investors that allocate capital to stocks, bonds, real estate, and alternative investments.



**Insurance Companies**

- **Role**: Provide financial protection against risks (e.g., life, health, property) and invest premiums in financial assets to meet future claims  

- **Examples**: MetLife, Prudential, Allianz  

- **Function**: Insurance companies are significant investors in long-term assets like government bonds, corporate bonds, and real estate to generate returns that meet their liabilities



**Regulatory Authorities**

- **Role**: Oversee financial markets and institutions to ensure fair practices, transparency, and compliance with laws and regulations.

- **Examples**: US Securities and Exchange Commission (SEC), UK Financial Conduct Authority (FCA), US Commodity Futures Trading Commission (CFTC).

- **Function**: Regulatory authorities protect investors, maintain market integrity, and reduce systemic risk by enforcing rules and conducting market surveillance.