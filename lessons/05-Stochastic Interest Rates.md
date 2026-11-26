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


Suppose I deposit £2,000 into a bank account for $n = 4$ years. The annual interest rate $R$ stays fixed over the 4 years, but is uncertain and follows this probability distribution:

$$R = \begin{cases} 0.03 & \text{with probability } 0.25 \\ 0.05 & \text{with probability } 0.50 \\ 0.08 & \text{with probability } 0.25 \end{cases}$$

I want to find the expected value and standard deviation of my deposit after 4 years, and compare the expected value to what I would get at the average rate.

**Solution:**

Let $S_4 = (1 + R)^4$, so the unknown value of my deposit after 4 years is:

$$P(4) = 2{,}000 \times S_4$$

First, I calculate the expected value of $S_4$:

$$\mathbb{E}(S_4) = 0.25 \times 1.03^4 + 0.50 \times 1.05^4 + 0.25 \times 1.08^4$$

$$\mathbb{E}(S_4) = 0.25(1.125509) + 0.50(1.215506) + 0.25(1.360489)$$

$$\mathbb{E}(S_4) = 0.281377 + 0.607753 + 0.340122 = 1.229253$$

Using linearity, my expected final value is:

$$\mathbb{E}[P(4)] = 2{,}000 \times 1.229253 = 2{,}458.51$$

so about £2,458.51.

Next, to get the standard deviation, I find $\text{Var}(S_4) = \mathbb{E}(S_4^2) - (\mathbb{E}(S_4))^2$, where $S_4^2 = (1 + R)^8$:

$$\mathbb{E}(S_4^2) = 0.25 \times 1.03^8 + 0.50 \times 1.05^8 + 0.25 \times 1.08^8$$

$$\mathbb{E}(S_4^2) = 0.25(1.266770) + 0.50(1.477455) + 0.25(1.850930)$$

$$\mathbb{E}(S_4^2) = 0.316693 + 0.738728 + 0.462733 = 1.518153$$

So the variance of $S_4$ is:

$$\text{Var}(S_4) = 1.518153 - (1.229253)^2 = 1.518153 - 1.511062 = 0.007091$$

Taking the square root gives $\text{sd}(S_4) = \sqrt{0.007091} = 0.084208$. Therefore, the standard deviation of my deposit is:

$$\text{sd}(P(4)) = 2{,}000 \times 0.084208 = 168.42$$

so £168.42. After 4 years, the expected value of my £2,000 deposit is £2,458.51, with a standard deviation of £168.42.

Finally, I compare this expected value to what I would get if I just used the average interest rate. The mean rate is:

$$\mathbb{E}(R) = 0.25(0.03) + 0.50(0.05) + 0.25(0.08) = 0.0525$$

which is 5.25%. If my deposit grew at this steady average rate for 4 years, the accumulated value would be:

$$2{,}000 \times (1 + \mathbb{E}(R))^4 = 2{,}000 \times (1.0525)^4 = 2{,}454.25$$

so £2,454.25. This shows that my expected final value (£2,458.51) is higher than the accumulated value at the average rate (£2,454.25), matching the inequality $P\,\mathbb{E}((1+R)^n) \geq P(1+\mathbb{E}(R))^n$ from my summary.
## Solved exercises

## Spreadsheets

