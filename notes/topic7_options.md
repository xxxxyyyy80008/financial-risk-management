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

**Solution:**

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

**Partial Derivatives Example**

$$f(x, y) = x^2y + 2xy^3$$

Partial derivative with respect to $x$:

$$f_x(x, y) = \frac{\partial}{\partial x} \left( x^2y + 2xy^3 \right)$$

$$= 2xy + 2y^3$$

Partial derivative with respect to $y$:

$$f_y(x, y) = \frac{\partial}{\partial y} \left( x^2y + 2xy^3 \right)$$

$$= x^2 + 6xy^2$$


**Identity Matrices**

- An identity matrix $I$ acts like the number 1 in that, for any other square matrix $A$ of the same dimension $AI = IA = A$

- The identity matrix of order $n$ denoted $I_n$ is a square, $n \times n$ diagonal matrix which contains only 1's. For instance the $2 \times 2$ identity matrix is:

$$I_2 = 
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}$$

- And the $3 \times 3$ identity matrix is:

$$I_3 = 
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}$$



**Inverting a Matrix**

- The inverse of a square matrix $A$ is the matrix $A^{-1}$ such that:

$$AA^{-1} = A^{-1}A = I$$

- Inverses only exist for square matrices – but not all square matrices have an inverse.

- Only non-singular square matrices have an inverse.

- A quick test to determine whether a matrix is non-singular is to show that its determinant is non-zero.



**Summary of Matrix Operations in Excel**

- **Transpose**: TRANSPOSE (cell refs)  
- **Addition/Subtraction**: cell refs +/- cell refs  
- **Dot product**: SUMPRODUCT (cell refs, cell refs)  
- **Matrix multiplication**: MMULT (cell refs, cell refs)  
- **Matrix inverse**: MINVERSE (cell refs)  
- **Determinant**: MDETERM (cell refs)


# Solving Simultaneous Linear Equations

*   Write the simultaneous equations in matrix form:

    $$a_{11}x_1 + \dots + a_{1n}x_n = b_1$$
    $$\vdots$$
    $$a_{n1}x_1 + \dots + a_{nn}x_n = b_n$$

    $$\Rightarrow \quad \mathbf{Ax} = \mathbf{b}$$

    with
    $$\mathbf{A} = (a_{ij}) \quad \mathbf{x} = (x_1, \dots, x_n)' \quad \mathbf{b} = (b_1, \dots, b_n)'$$

*   If **A** is non-singular the solution is given by:

    $$\mathbf{x} = \mathbf{A}^{-1}\mathbf{b}$$


**Example**

Solve the equations:
$$2x - y + z = 4$$
$$x - 2y + z + 1 = 0$$
$$3x - y - 2z = 1$$

**Solution:**

$$ \mathbf{A} = \begin{pmatrix} 2 & -1 & 1 \\ 1 & -2 & 1 \\ 3 & -1 & -2 \end{pmatrix} \quad \mathbf{b} = \begin{pmatrix} 4 \\ -1 \\ 1 \end{pmatrix} \quad \mathbf{A}^{-1} = \begin{pmatrix} 0.5 & -0.3 & 0.1 \\ 0.5 & -0.7 & -0.1 \\ 0.5 & -0.1 & -0.3 \end{pmatrix} $$

$$ \Rightarrow \mathbf{x} = \mathbf{A}^{-1}\mathbf{b} = \begin{pmatrix} 0.5 & -0.3 & 0.1 \\ 0.5 & -0.7 & -0.1 \\ 0.5 & -0.1 & -0.3 \end{pmatrix} \begin{pmatrix} 4 \\ -1 \\ 1 \end{pmatrix} = \begin{pmatrix} 2.4 \\ 2.6 \\ 1.8 \end{pmatrix} $$


**Taylor Expansion About a Point $x_0$**

*   To approximate a smooth function $f(x)$ near $x_0$, we expand it in powers of $(x - x_0)$:

    $$f(x) = f(x_0) + f'(x_0)(x - x_0) + \frac{1}{2}f''(x_0)(x - x_0)^2 + \dots$$

*   Truncating after the second term gives a straight-line (tangent) approximation; truncating after after the third term gives a quadratic approximation, after the fourth term gives a cubic polynomial etc...

*   The more terms we include, the closer $f(x)$ is to its actual local shape near $x_0$ and the broader the range for the approximation to be relatively accurate



**Examples of Second-Order Approximations**

*   **Example 1:** $f(x) = e^x$ about $x_0 = 0$

    $$f'(x) = e^x, \quad f''(x) = e^x$$
    $$\Rightarrow e^x \approx 1 + x + \frac{1}{2}x^2$$

    A simple and accurate local approximation near $x = 0$

*   **Example 2:** $f(x) = \ln x$ about $x_0 = 1$

    $$f'(x) = \frac{1}{x}, \quad f''(x) = -\frac{1}{x^2}$$
    $$\Rightarrow \ln x \approx (x - 1) - \frac{1}{2}(x - 1)^2$$

    Good for $x$ close to 1; diverges when $x$ far from 1

## 7.5 Hedging Options


**Delta-Gamma-Vega Neutrality**

*   Option market makers balance their books so that the net position Greeks are all near zero
*   That is, their hedge their book against the effects of changes in the price of the underlying (net delta and net gamma near zero) and against changes in volatility (net vega near zero)
*   In other words, their book is delta-gamma-vega neutral
*   Gamma neutral and vega neutral positions are both achieved by buying/selling other options on the same underlying
*   After this, delta-neutral positions are achieved by
    *   buying the underlying if net position delta < 0,
    *   selling the underlying if net position delta > 0



**Delta Hedging**

*   A delta hedge **matches** each unit of the option with delta units of the underlying
*   For instance, if I hold a long position on a portfolio of put stock options with a position delta of -20, I must buy 20 shares
*   More generally, if I have a portfolio of long or short positions on call or put options with a net position delta of $\delta$, I must **buy or sell $\delta$ units of the underlying** according as $\delta < 0$ or $\delta > 0$
*   A **delta-hedged portfolio** is called **delta-neutral** because the portfolio value will remain **approximately** unchanged for small changes in the underlying price



**Example of Delta Hedge**

*   I have a short position on an ATM call option to buy 10 shares
*   Suppose the position delta is $-1 \times 10 \times 0.5 = -5$
*   Then a delta hedge must **buy 5 shares**

    To see how this works:

*   Suppose the share price is $100 and the ATM call option to buy 10 shares costs $\$9 \times 10 = \$90$
*   Then the delta-hedged portfolio has a long position in 5 shares, with value $\$100 \times 5 = \$500$ and a short position with value $-\$90$
*   So the value of the delta-hedged portfolio is $\$500 - \$90 = \$410$



**Example of Delta Hedge**

*   So, our delta-hedged portfolio starts with value $410 – but now suppose the share price **increases by $2**
*   Then the call option price should **increase by about** $2 \times 0.5 \times 10 = \$10$
*   The delta-hedged portfolio is **long** 5 shares with value $\$102 \times 5 = \$510$ and **short** the call option, now with value about $-(\$90 + \$10) = \$100$
*   So the value of the delta-hedged portfolio is still about $410
*   And if the share price were to **fall by $3**, so the value of 5 shares becomes $\$97 \times 5 = \$485$ then the **call option price should also fall, by about** $\$3 \times 0.5 \times 10 = \$15$ so the value of our short position on this option becomes $-(\$90 - \$15) = -\$75$ and the delta-hedged portfolio value is (approximately) $\$485 - \$75 = \$410$, again



**Gamma and Vega Hedging**

*   Delta changes whenever the underlying price and volatility change
*   If the portfolio cannot be **continuously rebalanced** so that it is delta-neutral all the time, the gamma and vega of the position become relevant
*   So **before** delta hedging the net position with the underlying, make the net position gamma and vega **both** zero by buying or selling other options on the same underlying
*   Note that there is a **linear relationship between the BS gamma and vega**, which means that must use two options of **different maturities** for the gamma and vega hedges


**Example**

*   Suppose you are short 50 call options on a stock:
    *   Option 1: call with $\delta = 0.6$, $\gamma = 0.2$ and $\nu = 0.16$
*   Two other options on the same stock are available:
    *   Option 2: call with $\delta = 0.2$, $\gamma = 0.1$ and $\nu = 0.1$
    *   Option 3: put with $\delta = -0.8$, $\gamma = 0.3$ and $\nu = 0.2$
*   Each option is for 10 shares
*   How many of options 2 and 3 should I buy or sell to make the position gamma-vega neutral?
*   How many shares should I buy or sell so that the total position is delta-gamma-vega neutral?

**Solution (By Hand)**

*   Each position Greek is calculated by multiplying the number of shares the option contracts to buy or sell by the position in the option, and then also by the option delta, gamma or vega
*   The positions on options 2 and 3, which we want to solve for, are denoted $x$ and $y$:

| Option | No. Shares | Position | Position Delta | Position Gamma | Position Vega |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Option 1 | 10 | -50 | -300 | -100 | -80 |
| Option 2 | 10 | $x$ | $2x$ | $x$ | $x$ |
| Option 3 | 10 | $y$ | $-8y$ | $3y$ | $2y$ |

*   We now find the positions in options 2 and 3 that make the portfolio gamma and vega neutral by solving two simultaneous equations in $x$ and $y$


**Solution (By Hand)**

1.  Summing the columns gives
    *   Net position gamma = $-100 + x + 3y$
    *   Net position vega = $-80 + x + 2y$

2.  Hence for gamma and vega neutrality:
    $$x + 3y = 100$$
    $$x + 2y = 80$$

3.  The solution is:
    $$ \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 1 & 3 \\ 1 & 2 \end{pmatrix}^{-1} \begin{pmatrix} 100 \\ 80 \end{pmatrix} = \begin{pmatrix} -2 & 3 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} 100 \\ 80 \end{pmatrix} = \begin{pmatrix} 40 \\ 20 \end{pmatrix} $$

4.  Hence buy 40 of option 2 and buy 20 of option 3 to make the position gamma-vega neutral


**Solution (By Hand)**

*   So far we have a portfolio with three positions:
    *   Short 50 of option 1
    *   Long 40 of option 2
    *   Long 20 of option 3
*   Finally we calculate the net delta for the portfolio of all three options to find the delta hedge
*   The net delta is
    $$-300 + (40 \times 2) + (20 \times -8) = -300 + 80 - 160 = -380$$
*   Hence **buying** 380 shares makes the portfolio delta-gamma-vega neutral


**Title:** Solution (In Excel)

**Main Calculation Table**

| Option | No. Shares | Delta | Gamma | Vega | Position | Position Delta | Position Gamma | Position Vega |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 10 | 0.6 | 0.2 | 0.16 | -50 | -300.0 | -100.0 | -80.0 |
| 2 | 10 | 0.2 | 0.1 | 0.1 | 40.0 | 80.0 | 40.0 | 40.0 |
| 3 | 10 | -0.8 | 0.3 | 0.2 | 20.0 | -160.0 | 60.0 | 40.0 |
| | | | | | **Net** | **-380.0** | **0** | **0** |

**Matrix Inputs (Left Side)**

*   **Gamma-Vega Matrix:**
    $$ \begin{matrix} 1 & 3 \\ 1 & 2 \end{matrix} $$
*   **Gamma-Vega Vector:**
    $$ \begin{matrix} 100 \\ 80 \end{matrix} $$

**Rounded Results Table (Right Side)**

| | Position | Position Delta | Position Gamma | Position Vega |
| :--- | :--- | :--- | :--- | :--- |
| | -50 | -300.0 | -100.0 | -80.0 |
| | 40 | 80.0 | 40.0 | 40.0 |
| | 20 | -160.0 | 60.0 | 40.0 |
| **Net** | | **-380.0** | **0** | **0** |


## 7.6 Measuring VaR for an Options Portfolio


**Delta-Gamma-Vega Approximation**

*   Writing the option price as a function $f(S, \sigma)$, the **delta-gamma-vega approximation** for the change in option price, for a small change $h_s$ in $S$ and a small change $h_\sigma$ in $\sigma$, is:
    $$f(S + h_s, \sigma + h_\sigma) - f(S, \sigma) \approx h_s\delta + 0.5h_s^2\gamma + h_\sigma\nu$$

*   This way, given any pricing model $f(S, \sigma)$ for any option, we can compute the delta, gamma and vega and then use this to approximate a new option price $f(S + h_s, \sigma + h_\sigma)$.

*   The most important risk factor for short-term standard European options is $S$, so for such options it is quite common to use only a **delta-gamma approximation**



**Example**

*   Consider a 30-day OTM European call option with strike 105 on an asset that pays no dividends and has no carry cost. The current asset price is 100 and its volatility is 35%. The 30-day risk-free interest rate is 5%
*   Suppose the asset price falls from 100 to 95 and the volatility increases from 35% to 37%
*   Find the delta-gamma approximation, and the delta-gamma-vega approximation, to the **change** in the option price as a result of these changes to $S$ and $\sigma$



**Solution (By Hand)**

1.  We have $h_s = -5$, $h_\sigma = 2$ (or, 2% if you have not divided vega by 100) and from the Greeks example we have
    $$ \delta_{BS} = 0.34638, \quad \gamma_{BS} = 0.03677, \quad \nu_{BS} = 0.10579 $$

2.  Delta-gamma approximation to change in option price is:
    $$ \Delta f = -5 \times 0.34638 + 0.5 \times 25 \times 0.03677 = -1.27224 $$

3.  Delta-gamma-vega approximation is:
    $$ \Delta f = -5 \times 0.34638 + 0.5 \times 25 \times 0.03677 + 2 \times 0.10579 = -1.06067 $$



**Solution (In Excel)**

| BS Formula and Greeks | Inputs | BS Model | Call | Put |
| :--- | :--- | :--- | :--- | :--- |
| Market Price of Underlying | 100 | d1 | -0.39511 | -0.39511 |
| Volatility | 35% | d2 | -0.49545 | -0.49545 |
| Strike | 105 | Price | 2.20688 | 6.77626 |
| Maturity (Days) | 30 | Delta | 0.34638 | -0.65362 |
| Dividend Yield | 0% | Gamma | 0.03677 | 0.03677 |
| Risk Free Rate | 5% | Vega | 0.10579 | 0.10579 |
| | | | | |
| Change in Underlying price | -5 | Delta-Gamma Approx | -1.27224 | 3.72776 |
| Change in Volatility | 2% | New Option Price | 0.93464 | 10.50402 |
| | | Delta-Gamma-Vega Approx | -1.06067 | 3.93933 |
| | | New Option Price | 1.14621 | 10.71559 |

Adding the approximate change to the original price yields an approximation to the new price. Including the vega term to the delta and gamma terms increases the accuracy of this approximation.


**Delta-Gamma-Vega VaR for an Options Portfolio**

Based on Historical Simulation

1.  Find the portfolio's net position delta, gamma and vega
2.  Use the delta-gamma-vega approximation to the P&L:
    $$f(S + h_s, \sigma + h_\sigma) - f(S, \sigma) \approx h_s \delta + 0.5h_s^2 \gamma + h_\sigma \nu$$
3.  Find long historical time series for both $h_s$, the daily change in price on the underlying, and $h_\sigma$, the daily change in **implied volatility** to approximate an historical series of daily P&L (or drop the vega term and just use the delta-gamma approximation)
4.  Compute the $\alpha\%$ $h$-day VaR using the PERCENTILE function in the usual way



**Example**

*   Compute the historical delta-gamma VaR of an S&P 500 options portfolio, with a net position delta of $-0.75$ and a net position gamma of $0.3$
*   Use 5 years of daily closing price data on the S&P 500 index to compute the $1\%$ 10-day historical VaR for the portfolio, using a delta-gamma approximation for the change in portfolio value $\Delta P_t$ when the S&P index changes by $h_s = \Delta S_t$
*   Solution is in the Excel workbook