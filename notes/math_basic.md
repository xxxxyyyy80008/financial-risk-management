# Math Foundations

## Partial Derivatives


**Partial Derivatives Example**

$$f(x, y) = x^2y + 2xy^3$$

Partial derivative with respect to $x$:

$$f_x(x, y) = \frac{\partial}{\partial x} \left( x^2y + 2xy^3 \right)$$

$$= 2xy + 2y^3$$

Partial derivative with respect to $y$:

$$f_y(x, y) = \frac{\partial}{\partial y} \left( x^2y + 2xy^3 \right)$$

$$= x^2 + 6xy^2$$

## Log Approximation

**Exponential function**

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

**Natural log function**

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

**Exponential function rules**

- Rules for $e^x$ are the same as the rules for any indices – like  
  2³ × 2⁴ = 2⁷, or 3⁰ = 1  

- So $e^0 = 1$ and exponentials turn sums into products:  
  $$e^{x+y} = e^x e^y, \quad e^{x-y} = e^x e^{-y} = e^x / e^y$$

- Rules for $\ln x$ are inverse of rules for $\exp(x)$ – e.g. $\ln 1 = 0$ and logs turn products into sums:  
  $$\ln(xy) = \ln x + \ln y, \quad \ln(x/y) = \ln x - \ln y$$


**The Log Approximation**

- When $-1 < x \leq 1$ it can be shown that:

$$\ln(1 + x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \frac{x^4}{4} + \dots$$

- Now, when $x$ is small – as it normally is for a daily return – we know that $x$ is much greater than $x^2$, and $x^2$ is much greater than $x^3$ etc….

- And if $x$ is close to zero, $x^2$ is very small and $x^3$ is tiny … so, from the above expansion, we have:

$$\ln(1 + x) \approx x$$