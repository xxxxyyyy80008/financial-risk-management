# Study Notes on **Financial Risk Management** by Professor Carol Alexander 

Original resource: [youtube](https://www.youtube.com/watch?v=mXC5yJ5MKwM&list=PL_V1gySvrP_ums2nxs_YuKY5Ufdmhyoh7&index=6)

# Topic 3: Portfolios Returns and their Distributions

## 3.1 Profit and Loss (P&L) and Returns



**Definition of Market Risk**

- Market risk is the uncertainty in the future value of a portfolio arising from movements in an interest rate or the price of a financial asset.

- Such portfolios are priced by marking-to-market in the trading book — or, if trading liquidity is insufficient to mark-to-market (MtM), they are valued by marking-to-model.

- The portfolio price (or value) feeds into the measurement of market risk through the distribution of the future profit & loss (P&L) or returns for the portfolio from now until the risk horizon, denoted $h$.



**Profit and Loss (P&L)**

- Typically, market risk is based on daily price data – converted into daily profit and loss (P&L) and/or daily returns

- Let $P_t$ denote the price of an asset or portfolio on day $t$

- The (backward-looking) $h$-day P&L between time $t - h$ and time $t$ is $P_t - P_{t-h}$. This is **observed** at time $t$

- The (forward-looking) $h$-day P&L between time $t$ and time $t + h$ is $P_{t+h} - P_t$. This is **forecast** at time $t$

- When market risk is based on P&L it is expressed in the same units as the price, such as USD ($)



**Two Kinds of Returns**

Returns only make sense when prices are positive

- A log return is a difference in log price, e.g. if prices are daily, the $h$ backward-looking return is  
  $$\ln P_t - \ln P_{t-h}$$

- Log returns are not realized but they are easy to work with mathematically – for instance, the $h$-day log return is the sum of $h$ consecutive 1-day log returns.

- The realised return is the percentage change in price:  
  $$\frac{P_t - P_{t-h}}{P_{t-h}} \quad \text{or} \quad \frac{P_{t+h} - P_t}{P_t}$$

- When market risk is based on returns – rather than P&L – it is expressed as a % of the asset or portfolio price

---


**Reminder 1**

The number  
$$e = 2.71828182845904523536028747135266249 \dots$$

is between 2 and 3, so the graph of the exponential function $e^x$ lies between $2^x$ and $3^x$

The exponential function $e^x$ is also denoted $\exp(x)$

---

**Graph Details:**
- **X-axis**: $x$
- **Y-axis**: $\exp(x)$
- **Range**: $x$ ranges from -2.0 to 2.0
- **Values**: 
  - At $x = -2.0$: $\exp(-2.0) \approx 0.135$
  - At $x = -1.5$: $\exp(-1.5) \approx 0.35$
  - At $x = -1.0$: $\exp(-1.0) \approx 0.7$
  - At $x = -0.5$: $\exp(-0.5) \approx 1.4$
  - At $x = 0.0$: $\exp(0.0) \approx 1.6$
  - At $x = 0.5$: $\exp(0.5) \approx 2.0$
  - At $x = 1.0$: $\exp(1.0) \approx 2.8$
  - At $x = 1.5$: $\exp(1.5) \approx 3.6$
  - At $x = 2.0$: $\exp(2.0) \approx 4.5$

---

**Reminder 2**

The natural log function $\ln x$ is the inverse function of $e^x$, meaning:

$$\ln(e^x) = x \quad \text{and} \quad e^{\ln x} = x$$

and the graph of $\ln x$ is the reflection of $y = e^x$ in the line $y = x$

---

**Graph Annotations:**
- **Blue Line**: $y = e^x$
- **Red Line**: $\ln(x)$
- **Green Dashed Line**: $y = x$ (line of symmetry)

**Axes Labels:**
- **Horizontal Axis**: $x$
- **Vertical Axis**: $\ln(x)$

---

**Reminder 3**

- Rules for $e^x$ are the same as the rules for any indices – like  
  2³ × 2⁴ = 2⁷, or 3⁰ = 1  

- So $e^0 = 1$ and exponentials turn sums into products:  
  $$e^{x+y} = e^x e^y, \quad e^{x-y} = e^x e^{-y} = e^x / e^y$$

- Rules for $\ln x$ are inverse of rules for $\exp(x)$ – e.g. $\ln 1 = 0$ and logs turn products into sums:  
  $$\ln(xy) = \ln x + \ln y, \quad \ln(x/y) = \ln x - \ln y$$

---

**Something New: The Log Approximation**

- When $-1 < x \leq 1$ it can be shown that:

$$\ln(1 + x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \frac{x^4}{4} + \dots$$

- Now, when $x$ is small – as it normally is for a daily return – we know that $x$ is much greater than $x^2$, and $x^2$ is much greater than $x^3$ etc….

- And if $x$ is close to zero, $x^2$ is very small and $x^3$ is tiny … so, from the above expansion, we have:

$$\ln(1 + x) \approx x$$



**Approximation of Realised Return by Log Return**

- Consider the case where $x$ in the previous slide is a daily, forward-looking realised return:

$$R_t = \frac{P_{t+1} - P_t}{P_t}$$

and rewrite this as

$$1 + R_t = \frac{P_{t+1}}{P_t}$$

- Taking logs yields

$$\ln(1 + R_t) = \ln P_{t+1} - \ln P_t$$

and so if the realised return $R_t$ is small then it is approximately equal to the log return, by the log approximation, i.e.:

$$\ln(1 + R_t) \approx R_t$$

- Also, the log return is always less than the realised return.

---