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
  - The strike price $K$ that you buy (or sell) the option for, and
  - The expiry time which is the date when you can exercise the right to buy (or sell), called the option maturity, $T$

- The pay-off is the profit or loss that would be made if you do exercise the option at maturity

- So the pay-off for a call option is $\max\{S_T - K, 0\}$ and the pay-off for a put option is $\max\{K - S_T, 0\}$ where $S_T$ is the underlying price at the time of expiry

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

- The expected pay-off under the risk-neural measure depends on the current price of the underlying $S_0$ and on $S_t$, the underlying price at some time $t$ in future.

- The Black-Scholes model assumes that the log return on the underling is i.i.d. normal, having **total** expected return (including dividends or carry costs, $y$) equal to the risk-free rate $r$:

$$\ln \left( \frac{S_t}{S_0} \right) \sim N \left( (r - y)t, \sigma^2t \right)$$



**Measures of Moneyness**

- The moneyness of an options is (usually) measured as  
  $$M_t = \frac{S_t e^{-y(T-t)}}{K e^{-r(T-t)}}$$

- Call options are in-the-money (ITM), at-the-money (ATM) or out-of-the-money (OTM) according as $M_t$ is > 1, = 1, < 1  

- Put options are in-the-money (ITM), at-the-money (ATM) or out-of-the-money (OTM) according as $M_t$ is < 1, = 1, > 1  

- Equivalently, use **log** moneyness:  
  $$m_t = \ln M_t$$

- Then $m_t > 0$ for ITM, $= 0$ for ATM, $< 0$ for OTM call options (and conversely for put options)



**Black-Scholes Formula**

Call option price:

$$C_t = e^{-y(T-t)}S_t\Phi(d_{1t}) - e^{-r(T-t)}K\Phi(d_{2t})$$

Put option price:

$$P_t = -e^{-y(T-t)}S_t\Phi(-d_{1t}) + e^{-r(T-t)}K\Phi(-d_{2t})$$

where

$$d_{1t} = \frac{m_t}{\sigma\sqrt{T-t}} + \frac{\sigma\sqrt{T-t}}{2}$$

$$d_{2t} = \frac{m_t}{\sigma\sqrt{T-t}} - \frac{\sigma\sqrt{T-t}}{2}$$


**Why do we Need a Model Price?**

- The market price of anything, in our case an option, is always determined by supply and demand, namely the natural laws of economics

- Exchange-traded options are highly liquid so we can rely on market prices. Why, then, do we need a model?

- Because the market makers, whose job it is to keep the market liquid, need to **hedge** their risks – they make their money from the bid-ask spread

- Therefore, we need an option pricing model to derive the best hedge ratios, which we call the Greeks because they are denoted by Greek letters



**Interpretation of BS Formula**

- Setting $r = y = 0$ we have  
  $$C_t = S_t \Phi(d_{1t}) - K \Phi(d_{2t}), \quad P_t = K \Phi(-d_{2t}) - S_t \Phi(-d_{1t})$$
  with  
  $$d_{1t} = \frac{m_t}{\sigma \sqrt{T-t}} + \frac{\sigma \sqrt{T-t}}{2}, \quad d_{2t} = d_{1t} - \sigma \sqrt{T-t}$$

- Case 1: Deep ITM Call, Deep OTM Put:  
  $$\Rightarrow \Phi(d_{1t}) \approx \Phi(d_{2t}) \to 1, \quad \Phi(-d_{1t}) \approx \Phi(-d_{2t}) \to 0$$
  so  
  $$C_t \to S_t - K \text{ and } P_t \to 0$$

- Case 2: Deep OTM Call, Deep ITM Put:  
  $$\Rightarrow \Phi(d_{1t}) \approx \Phi(d_{2t}) \to 0, \quad \Phi(-d_{1t}) \approx \Phi(-d_{2t}) \to 1$$
  so  
  $$C_t \to 0 \text{ and } P_t \to K - S_t$$



**Example**

Find the BS model price of a 30-day OTM European call option with strike 105 on an asset that pays no dividends and has no carry cost. The current asset price is 100 and its volatility is 35%. The 30-day risk-free interest rate is 5%.

- $S = 100,\ \sigma = 0.35,\ K = 105,\ T - t = 30/365,\ r = 0.05,\ y = 0$

- Discount factor:  
  $$e^{-r(T-t)} = e^{-0.05 \times 30/365} = 0.9959$$

- Log moneyness:  
  $$\ln\left(\frac{100}{105 \times 0.9959}\right) = -0.04468 < 0$$

- $T$-period standard deviation of returns,  
  $$\sigma \sqrt{T - t} = 0.35 \times \sqrt{30/365} = 0.10034$$



**Solution (By Hand)**

- Find $d_1$ and $d_2$:

$$d_1 = \frac{-0.04468}{0.10034} + \frac{0.10034}{2} = -0.39511$$

$$d_2 = \frac{-0.04468}{0.10034} - \frac{0.10034}{2} = -0.49545$$

- Use tables (or `NORMSDIST` in Excel) to find $\Phi(d_1)$ and $\Phi(d_2)$:

$$\Phi(d_1) = \text{NORMSDIST}(-0.39511) = 0.34638$$

$$\Phi(d_2) = \text{NORMSDIST}(-0.49545) = 0.31014$$

- BS Call price = $100 \times 0.34638 - 105 \times 0.9959 \times 0.31014 = 2.20688$


## 7.3 The Greeks

**Definitions**

- The ‘Greeks’ of an option are the partial derivatives of a model option price with respect to its risk factors – i.e. the underlying price $S$ and volatility $\sigma$

- They depend on the option, of course, but also on the price process that is assumed – we only cover the Black-Scholes Greeks for a standard European option

- The option model’s delta and gamma are the 1st and 2nd partial derivative of the option price function $f(S_t, \sigma)$ with respect to $S_t$

- The vega is the 1st partial derivative of $f(S_t, \sigma)$ with respect to $\sigma$


**# Partial Derivatives Example**

$$f(x, y) = x^2y + 2xy^3$$

Partial derivative with respect to $x$:

$$f_x(x, y) = \frac{\partial}{\partial x} \left( x^2y + 2xy^3 \right)$$

$$= 2xy + 2y^3$$

Partial derivative with respect to $y$:

$$f_y(x, y) = \frac{\partial}{\partial y} \left( x^2y + 2xy^3 \right)$$

$$= x^2 + 6xy^2$$



**BS Delta (δ), Gamma (γ) and Vega (ν)**

Differentiating the Black-Scholes model price w.r.t. $S_t$ once, and twice and w.r.t. $\sigma$ once, yields:

$$
\text{Call } \delta_{BS} = e^{-y(T-t)} \Phi(d_{1t}),
$$

$$
\text{Put } \delta_{BS} = -e^{-y(T-t)} \Phi(-d_{1t})
$$

$$
\gamma_{BS} = e^{-y(T-t)} \frac{\varphi(d_{1t})}{S\sigma\sqrt{T-t}},
$$

$$
\nu_{BS} = e^{-y(T-t)} \varphi(d_{1t}) S\sqrt{T-t}
$$



**Interpretation of BS Formula**

- Setting $r = y = 0$ we have  
  $$C_t = S_t \Phi(d_{1t}) - K \Phi(d_{2t}), \quad P_t = K \Phi(-d_{2t}) - S_t \Phi(-d_{1t})$$
  with  
  $$d_{1t} = \frac{m_t}{\sigma \sqrt{T-t}} + \frac{\sigma \sqrt{T-t}}{2}, \quad d_{2t} = d_{1t} - \sigma \sqrt{T-t}$$

- Case 1: Deep ITM Call, Deep OTM Put:  
  $$\Rightarrow \Phi(d_{1t}) \approx \Phi(d_{2t}) \to 1, \quad \Phi(-d_{1t}) \approx \Phi(-d_{2t}) \to 0$$
  so  
  $$C_t \to S_t - K \text{ and } P_t \to 0$$

- Case 2: Deep OTM Call, Deep ITM Put:  
  $$\Rightarrow \Phi(d_{1t}) \approx \Phi(d_{2t}) \to 0, \quad \Phi(-d_{1t}) \approx \Phi(-d_{2t}) \to 1$$
  so  
  $$C_t \to 0 \text{ and } P_t \to K - S_t$$



**Black-Scholes Formula**

Call option price:

$$C_t = e^{-y(T-t)} S_t \Phi(d_{1t}) - e^{-r(T-t)} K \Phi(d_{2t})$$

Put option price:

$$P_t = -e^{-y(T-t)} S_t \Phi(-d_{1t}) + e^{-r(T-t)} K \Phi(-d_{2t})$$

where

$$d_{1t} = \frac{m_t}{\sigma \sqrt{T-t}} + \frac{\sigma \sqrt{T-t}}{2}$$

$$d_{2t} = \frac{m_t}{\sigma \sqrt{T-t}} - \frac{\sigma \sqrt{T-t}}{2}$$




**BS Delta (δ), Gamma (γ) and Vega (ν)**

Differentiating the Black-Scholes model price w.r.t. $S_t$ once, and twice and w.r.t. $\sigma$ once, yields:

$$
\text{Call } \delta_{BS} = e^{-y(T-t)} \Phi(d_{1t}),
$$

$$
\text{Put } \delta_{BS} = -e^{-y(T-t)} \Phi(-d_{1t})
$$

$$
\gamma_{BS} = e^{-y(T-t)} \frac{\varphi(d_{1t})}{S\sigma\sqrt{T-t}},
$$

$$
\nu_{BS} = e^{-y(T-t)} \varphi(d_{1t}) S\sqrt{T-t}
$$




**Example**

Find the delta, gamma and vega of the option in the first example

1. We have $S = 100$, $\sigma = 0.35$, $K = 105$, $T - t = 30/365$, $r = 0.05$, $y = 0$

2. Since $y = 0$, and the option is a call option we calculate:

$$
\delta_{BS} = \Phi(d_{1t}), \quad \gamma_{BS} = \frac{\varphi(d_{1t})}{S\sigma\sqrt{T-t}}, \quad \nu_{BS} = \varphi(d_{1t}) S\sqrt{T-t}
$$

3. From above: $d_1 = -0.39511 \Rightarrow \Phi(-0.39511) = 0.34638$

4. For gamma and vega, $\varphi(d_1)$ can be found using NORMDIST($d_1$, 0, 1, FALSE):

$$
\varphi(-0.39511) = 0.36899
$$

5. 

$$
S\sigma\sqrt{T-t} = 35 \times \sqrt{30/365} = 10.03419 \quad \Rightarrow \quad \gamma_{BS} = \frac{0.36899}{10.03419} = 0.03677
$$

6. 

$$
S\sqrt{T-t} = 100 \times \sqrt{30/365} = 28.6691 \quad \Rightarrow \quad \nu_{BS} = 0.36899 \times 0.2867 = 0.10579
$$




**Remarks**

- The Excel workbook shows that – for a call and put of the same strike and maturity – the difference between the call and put deltas is always 1.

- That is, setting $y = 0$ here just for simplicity, we always have  
  $$\Phi(d_{1t}) - (-\Phi(-d_{1t})) = \Phi(d_{1t}) + \Phi(-d_{1t}) = 1
  $$  

as shown on the next slide.

- Also, a put and call of the same strike and maturity have the same gamma and vega.

- Note that vega is quoted as the sensitivity to percentage points – in other words, we divide by 100 (otherwise when we move $\sigma$ by one, it would mean a change of 100%!).




**How does Delta change with S?**

- The delta (i.e. the slope of the BS price function) has the same general shape as $\Phi(\cdot)$, the standard normal distribution function.

- **Call BS delta**: for small $S$, option is deep OTM, $\delta \approx 0$; as $S$ increases to the option strike $K$, option is ATM, $\delta \approx 0.5$; then as $S$ increases further option goes ITM and $\delta \to 1$.

- **Put BS delta**: for small $S$, option is deep ITM, $\delta \approx -1$; as $S$ increases to the option strike $K$, option is ATM, $\delta \approx -0.5$; then as $S$ increases further option goes OTM and $\delta \to 0$.




**Solution (By Hand)**

- Find $d_1$ and $d_2$:

$$
d_1 = \frac{-0.04468}{0.10034} + \frac{0.10034}{2} = -0.39511
$$

$$
d_2 = \frac{-0.04468}{0.10034} - \frac{0.10034}{2} = -0.49545
$$

- Use tables (or NORMSDIST in Excel) to find $\Phi(d_1)$ and $\Phi(d_2)$:

$$
\Phi(d_1) = \text{NORMSDIST}(-0.39511) = 0.34638
$$

$$
\Phi(d_2) = \text{NORMSDIST}(-0.49545) = 0.31014
$$

- BS Call price = $100 \times 0.34638 - 105 \times 0.9959 \times 0.31014 = 2.20688$



**How do Gamma and Vega change with S?**

- The BS gamma (same for call and put) has shape of normal density function. It is always positive. Since gamma is slope of delta, its maximum occurs when $S$ is very close to the option strike $K$, i.e. the gamma is maximum for near ATM options.

- The BS vega (again, same for call and put) also has shape of normal density function. So vega is also positive and at its maximum for near ATM options. In fact, the BS vega and BS gamma are simply related:

$$
\nu_{BS} = \gamma_{BS} \, \sigma \, S^2 \, (T - t)
$$




**Position Greeks**

- A long position on an option allows the holder to buy or sell a certain number of units of the underlying asset.

- The position Greeks are defined as  
  $$w \times N \times \text{ standard Greek}$$

where $w = 1$ for a long and $w = -1$ for a short position; $N$ is the number of options times the number of units in the underlying per option.

- E.g. a short position on 3 puts with gamma 0.5. Each option is to sell 10 units of the underlying. Position gamma = $-15$.

- For many options on the same underlying, the net position Greek is the sum of all the individual position Greeks.




**Example**

Find the net position gamma for two options on the same underlying:

- Option 1 is a long call on 80 shares with a gamma of 0.1,  
- Option 2 is a short put on 50 shares with a gamma of 0.02.

## Solution:
- Option 1 has position gamma $0.1 \times 80 = 8$  
- Option 2 has position gamma $-0.02 \times 50 = -1$  
- Hence the net position gamma is $8 - 1 = 7$




**Example**

Find the net position delta for short positions on two options on the same underlying:

- Option 1 is a call on 100 shares with a delta of 0.6,  
- Option 2 is a put on 120 shares with a delta of -0.25.  

**Solution:**

- Short option 1 has position delta $-0.6 \times 100 = -60$  
- Short option 2 has position delta $-(-0.25) \times 120 = 30$  
- Hence the net position delta is $-60 + 30 = -30$


## 7.4 Mathematical Background

## 7.5 Hedging Options

## 7.6 Measuring VaR for an Options Portfolio