---
tags: [finance, quant]
---

2025-09-14 00:37

Status: #Adult 

Tags: [[Quant]] [[Calculus]] [[Taylor Series]]

# Module 1- The language of Market - Applied Calculus & Probability

**Calculus Primer - The physics of Price Change**

**Topic 1: Derivatives (Rate of Change)**

Derivatives is the rate of change -> our example of this is the speedometer on the car. - your speed at one specific instant is the derivative.

In finance we do the same with stock price.

- Average Change: If a stock from $100 to $102 in a day, its Average Change is $2 per day.

- Instantaneous Change (the Derivative): But what if we want to know how fast the price changing right now, at this very second? is the momentum of buying picking up or slowing down? The instantaneous rate of change is the derivative of the stock price.


A derivative is just the instantaneous speed of a changing value, like stock price.

**Topic 2: Integral (Summing Changes)**

If Derivative was looking at your speedometer to find instantaneous speed. Integrals is looking at instantaneous speed to find the distance travelled.

It is the process of accumulating an infinite number of tiny changes to find the total change.

How does this apply to finance?

Lets say we have a model that gives us the expected instantaneous changes (the derivative) of a stock price at every second for the next week. we use an integral to "sum up" all those tiny second by second changes to get the cumulative result.

So to summarize our analogy: Derivative: Given the total distance travelled over time, find the instantaneous speed. Integral: Given the instantaneous speed at every moment, find the total distance travelled.

**An integral adds up to a series of tiny changes to tell you the final result.**

**Topic 3: Taylor Series (Approximating function)**

Taylor Series -> Think of it like this: you're looking at a detailed satellite map of the Himalayas. The terrain is incredibly complex. But if you zoom in on a single football field, you can pretty much treat it as a flat rectangle. You've approximated a complex surface with a simple one.

A Taylor series does this mathematically. It allows us to approximate any well-behaved complex function using a simple polynomial (a sum of terms like C0​+C1​x+C2​x2+C3​x3+…). The more terms we add to our polynomial, the better the approximation becomes, and the further it remains accurate from our starting point.

Why is this a "cheat code" in finance?

Many of the formulas that describe financial instruments (especially options) are horrendously complicated. By using a Taylor Series, we can create much simpler, approximate formulas that are easier to calculate and work with. It allows us to say, "This option pricing formula is too hard, but I can create a simple quadratic equation that gets me 99.9% of the way there."

This concept is the absolute key to understanding Ito's Lemma later on, which is the cornerstone of modern quantitative finance.

So, the key takeaway is: **A Taylor series lets us approximate a complex function with a simple polynomial.**





# References
