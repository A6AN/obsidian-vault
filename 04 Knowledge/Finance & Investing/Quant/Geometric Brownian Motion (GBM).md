---
tags: [finance, quant]
---

2025-09-14 01:33

Status: #Teen 

Tags: [[Quant]] [[Brownian Motion]] [[Random Walk]] [[Calculus]] [[Random Variable]] [[Random Variable & The Normal Distribution]]

# Geometric Brownian Motion (GBM)

**Topic 3: Geometric Brownian Motion (GBM)**

Breaking the Name we get:

- **Brownian Motion**: We already know this. It's an engine of randomness, the "random walk" component.
- **Geometric**: This is a crucial addition. It means that the randomness is proportional to the current stock price.

Think of it as -> a stock like MRF which trades for around ₹1,25,000 will have daily swings measured in thousands of rupees, while a stock like Vodafone Idea/machine at ₹16, will have swings measured in paise.

The random "shock" the stock takes isn't a fixed amount; it is a percentage of its current value. A 1% random move in MRF is huge, while a 1% move in Vodafone is tiny. This proportional scaling is what "geometric" means, and it ensures our model is realistic (e.g. it prevents stock prices to be negative).

So, Geometric Brownian Motion (GBM) is a model that describes the movement of stock over time. It is defined by a simple equation:

$dSt​=μSt​dt+σSt​dWt​$

here

- $dSt$​: The tiny change in stock price (S) over a tiny period of time (t).
- $μSt​dt$: This is the "drift" component. It's a predictable push.
    
    - $μ$ ($mu$) is the expected return of the stock.
        
    - This part is essential for saying that over a long bit of time we expect the price to trend up by a certain return.
        
- $σSt​dWt$​: The Random Component
    
    - $σ$ (sigma) is volatility (standard deviation) of the stock's return.
        
    - $dWt$​ represents the random step from Brownian Motion. This part essentially adds a random shock whose size is determined by the stock's volatility.
        

In summary, GBM says that the next move in a stock price is the sum of a small, predictable trend and a larger, unpredictable random shock.

This model is the workhorse of quantitative finance. It is the fundamental assumption behind the famous Black-Scholes option pricing model.

## Example

**GT Ltd.**

Current Stock Price ($S0$​) = ₹20,000 
Expected Annual Return ($μ$) = 12% (or 0.12) 
Annual Volatility ($σ$) = 25% (or 0.25)

Using GBM find the possible price of this stock over the next two days.

**GT Ltd.**

Current Stock Price ($S_0$) = ₹20,000
Expected Annual Return ($\mu$) = 12% (or 0.12)
Annual Volatility ($\sigma$) = 25% (or 0.25)

Using GBM find the possible price of this stock over the next two days.

$S_t = S_{t-\Delta t} \exp\left(\left(\mu - \frac{\sigma^2}{2}\right)\Delta t + \sigma\sqrt{\Delta t} Z\right)$

* **Annotations:**
    * $S_t$: The stock price at time $t$
    * $S_{t-\Delta t}$: The stock price one time step prior
    * $\left(\mu - \frac{\sigma^2}{2}\right)\Delta t$: Deterministic drift term or trend
    * $\sigma\sqrt{\Delta t} Z$: Random Shock
    * $Z$: a random number from a Standard Normal distribution (mean = 0, deviation = 1).

**Step by Step**

$\Delta t = 1/252 \approx 0.003968$. (since there are approx 252 trading days)

**For Day 1**

* $S_0 = 20000$
* $\mu = 0.12$
* $\sigma = 0.25$
* $\Delta t = 1/252$
* $Z_1 = 0.52$ (Random)

Drift term: $\left(\mu - \frac{\sigma^2}{2}\right)\Delta t = \left(0.12 - \frac{0.25^2}{2}\right) \times \frac{1}{252} \approx 0.000352$

Diffusion term: $\sigma\sqrt{\Delta t} Z_1 = 0.25 \times \sqrt{\frac{1}{252}} \times 0.52 \approx 0.008189$

$S_1 = S_0 \times \exp(\text{Drift term} + \text{Diffusion term})$
$S_1 = 20000 \times \exp(0.008541)$
$S_1 = 20000 \times 1.008577$
$S_1 \approx 20171.54$

**For Day 2**

* $S_1 \approx 20171.54$
* $Z_2 = -0.89$ (Negative Shock this time)
* Drift term = $0.000352$
* Diffusion = $0.25 \times \sqrt{0.003968} \times (-0.89) \approx -0.01401$

$S_2 = 20171.54 \times \exp(0.000352 - 0.01401)$
$S_2 = 20171.54 \times 0.986436$
$S_2 \approx 19897.48$




# References

