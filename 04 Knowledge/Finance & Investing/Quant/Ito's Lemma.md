---
tags: [finance, quant]
---

2025-09-14 01:30

Status: #Teen 

Tags: [[Calculus]] [[Quant]] [[Brownian Motion]] [[Random Walk]] [[Ito's Lemma]]

# Ito's Lemma

1. Primer Calculus's Derivatives & Taylor series to analyze functions that are smooth & predictable.
2. Probability Primer -> Brownian Motion that describes things are jagged & random.

What happens when you have a smooth function that depends on a random variable? For e.g. the price of an option is a smooth function of the stock's price, but the stock's price itself follows a random walk.

If you try to apply the rules of normal calculus to a random walk, the math breaks down. The "speed" at any given moment is technically infinite because its path is so jagged. We need a new set of rules.

The New set of Rules: ITO'S Lemma

The change in the value of a financial instrument is determined by three things:

1. A term for the passage of time (This is called Theta in option pricing)
2. A term for the predictable "drift" or trend of the underlying stock (related to Delta)
3. An extra, non-obvious term that is purely a gift from volatility (related to Gamma).

This third term is revolutionary part. It says that randomness itself, the simple act of the stock price bouncing around (volatility), creates a predictable "push" or "drag" on the value of the derivative. Even if a stock is expected to go nowhere on average (zero drift) an option on that stock can systematically gain or lose value just because of the volatility.

The key Takeaway: Ito's Lemma is the bridge between the random walk of a stock and its price derivative. It is the mathematical engine that tells us precisely how to account for the impact of volatility. Without it, we could not price options. It is the foundation upon which the entire derivatives industry is built.




# References

