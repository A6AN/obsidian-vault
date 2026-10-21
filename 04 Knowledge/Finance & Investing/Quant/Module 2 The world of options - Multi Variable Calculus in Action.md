---
tags: [finance, quant]
---

2025-09-15 02:45

Status: #Teen 

Tags: [[Quant]] [[Calculus]] [[Option Trading]] [[Stock Market]] [[Partial Derivatives]]

# Module 2 The world of options - Multi Variable Calculus in Action

### Module 2
**The world of options - Multi Variable Calculus in Action**

In module 1, we talked about stock prices which is function of time but the world of finance is more complicated. The value of many financial instruments, like options, depend on many variables at once.

**Partial Derivatives Primer: The Greeks**

Imagine standing out on your balcony. The temperature you feel is a function of both temperature & humidity. (feels like Temperature = function(temperature, humidity)).

If you want to know how much hotter it will be if temperature rises by 1°C then you will take into consideration the temperature holding the humidity constant.

The act of measuring the change caused by a single variable while holding all other variables constant is the essence of partial derivation.

Applying this to an option, we realize that stock option is a value that is a function of at least five different things:

1. The underlying stock's price ($S$)
2. The time remaining until the option expires ($t$)
3. The volatility of the stock ($\sigma$)
4. The Strike price of the option ($K$)
5. The risk-free interest rate ($r$)

So, Option Price = Function ($S, t, \sigma, K, r$).

As a Quant or a trader, your biggest job is to manage risk. You need to know exactly how your option's price will change if any one of these factors move. For this, we use partial derivatives and in finance, we give them cool Greek names.

These are **The Greeks**.

* **Delta ($\Delta$):** This is the partial with respect to the Stock price.
    * The Question it Answers: "If the stock price goes up by $1, how much will my option's price change, holding everything else constant?"
    * The most important greek, it tells you your directional exposure.

* **Theta ($\Theta$):** This is the partial derivative with respect to time.
    * The Question it Answers: "As one day passes and my option gets closer to expiring, how much value will it lose due to time decay, holding everything else constant?"
    * Theta is usually negative because time is an enemy to an option holder.

* **Vega ($\mathcal{V}$):** This is the partial derivative with respect to volatility.
    * The Question it Answers: "If the market's expectation of future volatility goes up by 1%, how much will my option's price increase, holding everything else constant?"
    * Vega is crucial for tracking during uncertain times & before major events like earning announcements.

There are others, like Gamma (which measures how fast Delta changes) and Rho (for interest rates), but these are the pillars.

**The Key Takeaway:** The Greeks are partial derivatives of the option pricing function. They are the mathematical tools we use to isolate and measure each specific risk an option is exposed to.



# References

