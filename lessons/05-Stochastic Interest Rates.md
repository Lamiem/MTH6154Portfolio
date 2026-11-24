# 5. Stochastic Interest Rates

[Back to contents](../README.md)

## My Summary

### 1. Fixed interest rate model

Now interest rates are random (stochastic) rather than known in advance. In the simplest setup, one random rate $R$ applies for the whole $n$ years, so putting £P in gives $P(1 + R)^n$. The main trap is that you can't just plug the average interest rate into the formula:

$$\mathbb{E}\big(P(1 + R)^n\big) = P\,\mathbb{E}\big((1 + R)^n\big) \ge P\big(1 + \mathbb{E}(R)\big)^n$$

The expected payout is always at least as big as what you'd get from the average rate $\mathbb{E}(R)$, and for more than one year they're only equal if $R$ isn't actually random.

### 2. Varying interest rate model

Here each year gets its own random rate $R_i$, which we treat as independent with the same mean $\mu$ and variance $\sigma^2$ (even though real world rates carry over from one year to the next).

For a one off deposit £P at time $0$, the final pot $P S_n = P(1 + R_0)\cdots(1 + R_{n-1})$ has mean and variance:

$$\mathbb{E}(P S_n) = P(1 + \mu)^n$$

$$\mathrm{Var}(P S_n) = P^2 \Big( \big((1 + \mu)^2 + \sigma^2\big)^n - (1 + \mu)^{2n} \Big)$$

If I instead put in fixed amounts $P_i$ every year, the balance $A_n$ builds up step-by-step via $A_n = (A_{n-1} + P_{n-1})(1 + R_{n-1})$ with $A_0 = 0$. Taking expectations gives $\mathbb{E}(A_n) = \big(\mathbb{E}(A_{n-1}) + P_{n-1}\big)\big(1 + \mathbb{E}(R_{n-1})\big)$ (for example, if I pay in £P each year and $\mu = 0$, the expected balance is simply $\mathbb{E}(A_n) = Pn$).





## My example

## Solved exercises

## Spreadsheets

