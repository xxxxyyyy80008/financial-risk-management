# Study Notes on **Financial Risk Management** by Professor Carol Alexander 

Original resource: [youtube](https://www.youtube.com/watch?v=mXC5yJ5MKwM&list=PL_V1gySvrP_ums2nxs_YuKY5Ufdmhyoh7&index=6)

# Topic 7: Risk Management for Options Portfolios

## 7.1 Introduction to Options



**What is an Option?**

- Call and put options are bets on a stochastic “underlying”

- The **underlying** is anything measurable (e.g. a stock price, an exchange rate or a futures contract but it could also be temperature, or rainfall, etc...)

- A **call** is a right to buy the underlying, a **put** is the right to sell

- Unlike futures, **options** do not have to be exercised

- So an option is like a ticket – it can be thrown away i.e. not exercised and the holder only loses the price he paid for the option – which is a small fraction of the underlying price



**How Much Would You Pay?**

Suppose the underlying price is 100.  
What would you pay for these options?

- **Type = Call**  
  Strike = 120  
  Maturity = 0.5  

- **Type = Put**  
  Strike = 90  
  Maturity = 0.25  

Both these options are currently out-of-the-money. What would the strikes of in-the-money options be, for example?



**Option Characteristics and Pay-offs**

- A standard European call (or put) option has two characteristics:
  - The strike price \( K \) that you buy (or sell) the option for, and
  - The expiry time which is the date when you can exercise the right to buy (or sell), called the option maturity, \( T \)

- The pay-off is the profit or loss that would be made if you do exercise the option at maturity

- So the pay-off for a call option is \(\max\{S_T - K, 0\}\) and the pay-off for a put option is \(\max\{K - S_T, 0\}\) where \(S_T\) is the underlying price at the time of expiry

- A standard American option can be exercised at any time on or before the expiry time



**Moneyness of Options**

- At-the-Money (ATM) options have a strike which is close to the current price of the underlying.

- In-the-Money (ITM) options are those whose pay-offs would be positive if the option were exercised now, namely **low-strike calls** and **high-strike puts**.

- Out-of-the-Money (OTM) options are those whose pay-offs would be zero if the option were exercised now, namely **high-strike calls** and **low-strike puts**.

- Naturally, OTM options have lower prices than ATM options, which have lower prices than ITM options.


**Market vs Model Prices**

- Deep OTM puts, namely **very low** strike puts cost very little  
- Typically on a stock, or a stock index, for which a deep OTM put is an insurance against a large price fall  
- Demand for these options (and therefore also their market price) rises when investors fear a stock market crash  
- But the Black-Scholes model price of an option assumes the log return on the underlying is normally distributed, not heavy-tailed  
- The model price of an option is derived using a principle called risk-neutral valuation.

---


**Risk-Neutral Valuation (RNV)**

- The RNV principle rests on two assumptions

  1. **Geometric Brownian Motion (GBM)**: This means that the underlying’s log returns have an i.i.d. normal distribution  
  2. **Risk-Neutral Measure**: This means that the expected total return (including dividends, or less carry costs) is equal to the risk-free rate  

- Under these assumptions the risk of holding a standard European option can be perfectly hedged  

- Therefore, the value of an option doesn’t depend on risk attitude – namely, whether the owner is risk-averse, risk-loving or risk-neutral  

- Therefore, there is a unique model price, which is the same for all investors – and so we may as well price the option for a risk-neutral investor


## 7.2 The Black–Scholes Model



**Assumptions for the Black-Scholes Model**

- The expected pay-off under the risk-neural measure depends on the current price of the underlying \( S_0 \) and on \( S_t \), the underlying price at some time \( t \) in future.

- The Black-Scholes model assumes that the log return on the underling is i.i.d. normal, having **total** expected return (including dividends or carry costs, \( y \)) equal to the risk-free rate \( r \):

\[\ln \left( \frac{S_t}{S_0} \right) \sim N \left( (r - y)t, \sigma^2t \right)\]



**Measures of Moneyness**

- The moneyness of an options is (usually) measured as  
  \[  M_t = \frac{S_t e^{-y(T-t)}}{K e^{-r(T-t)}}\]

- Call options are in-the-money (ITM), at-the-money (ATM) or out-of-the-money (OTM) according as \( M_t \) is > 1, = 1, < 1  

- Put options are in-the-money (ITM), at-the-money (ATM) or out-of-the-money (OTM) according as \( M_t \) is < 1, = 1, > 1  

- Equivalently, use **log** moneyness:  
  \[  m_t = \ln M_t\]

- Then \( m_t > 0 \) for ITM, \( = 0 \) for ATM, \( < 0 \) for OTM call options (and conversely for put options)



**Black-Scholes Formula**

Call option price:

\[C_t = e^{-y(T-t)}S_t\Phi(d_{1t}) - e^{-r(T-t)}K\Phi(d_{2t})\]

Put option price:

\[P_t = -e^{-y(T-t)}S_t\Phi(-d_{1t}) + e^{-r(T-t)}K\Phi(-d_{2t})\]

where

\[d_{1t} = \frac{m_t}{\sigma\sqrt{T-t}} + \frac{\sigma\sqrt{T-t}}{2}\]

\[d_{2t} = \frac{m_t}{\sigma\sqrt{T-t}} - \frac{\sigma\sqrt{T-t}}{2}\]


**Why do we Need a Model Price?**

- The market price of anything, in our case an option, is always determined by supply and demand, namely the natural laws of economics

- Exchange-traded options are highly liquid so we can rely on market prices. Why, then, do we need a model?

- Because the market makers, whose job it is to keep the market liquid, need to **hedge** their risks – they make their money from the bid-ask spread

- Therefore, we need an option pricing model to derive the best hedge ratios, which we call the Greeks because they are denoted by Greek letters



**Interpretation of BS Formula**

- Setting \( r = y = 0 \) we have  
  \[  C_t = S_t \Phi(d_{1t}) - K \Phi(d_{2t}), \quad P_t = K \Phi(-d_{2t}) - S_t \Phi(-d_{1t})\]
  with  
  \[  d_{1t} = \frac{m_t}{\sigma \sqrt{T-t}} + \frac{\sigma \sqrt{T-t}}{2}, \quad d_{2t} = d_{1t} - \sigma \sqrt{T-t}\]

- Case 1: Deep ITM Call, Deep OTM Put:  
  \[  \Rightarrow \Phi(d_{1t}) \approx \Phi(d_{2t}) \to 1, \quad \Phi(-d_{1t}) \approx \Phi(-d_{2t}) \to 0\]
  so  
  \[  C_t \to S_t - K \text{ and } P_t \to 0\]

- Case 2: Deep OTM Call, Deep ITM Put:  
  \[  \Rightarrow \Phi(d_{1t}) \approx \Phi(d_{2t}) \to 0, \quad \Phi(-d_{1t}) \approx \Phi(-d_{2t}) \to 1\]
  so  
  \[  C_t \to 0 \text{ and } P_t \to K - S_t\]

## 7.3 The Greeks

## 7.4 Mathematical Background

## 7.5 Hedging Options

## 7.6 Measuring VaR for an Options Portfolio