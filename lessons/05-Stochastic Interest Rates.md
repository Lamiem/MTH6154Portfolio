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

### Exercise 1 (Coursework 5)

**Question:** The interest rate applicable in one year's time for a one year deposit is modelled by the random variable

$$R = \begin{cases} 0.03 & \text{with probability } 0.3 \\ 0.035 & \text{with probability } 0.7 \end{cases}$$

(with $R$ equal to 3% or 3.5%). I place a deposit of £P in a year's time for one year. Find how much money I will have at the end of the deposit term, and its expected value, under each of the following conventions:

* (a) $R$ is the continuously compounded rate, so that cash grows by a factor of $\exp(R)$.
* (b) $R$ is the effective (spot) rate, so that cash grows by a factor of $1 + R$.

**(a) Continuously compounded rate**

Here, cash grows by a factor of $\exp(R)$, so the amount of money I will have at the end of the term is $V_a = P e^R$. Depending on which rate happens, my final balance will be:

$$V_a = \begin{cases} P e^{0.03} \approx 1.030455P & \text{with probability } 0.3 \\ P e^{0.035} \approx 1.035620P & \text{with probability } 0.7 \end{cases}$$

To find the expected value, I take the weighted average of these two outcomes:

$$\mathbb{E}[V_a] = P \mathbb{E}(e^R) = P \left( 0.3 e^{0.03} + 0.7 e^{0.035} \right)$$

$$\mathbb{E}[V_a] = P \left( 0.3(1.030455) + 0.7(1.035620) \right)$$

$$\mathbb{E}[V_a] = P (0.309136 + 0.724934) = 1.034070P$$

So the expected amount at the end of the term is $1.03407P$.

**(b) Effective (spot) rate**

Here, cash grows by a factor of $1 + R$, so my final amount is $V_b = P(1 + R)$. Looking at the two possible rates, my final balance will be:

$$V_b = \begin{cases} P(1 + 0.03) = 1.03P & \text{with probability } 0.3 \\ P(1 + 0.035) = 1.035P & \text{with probability } 0.7 \end{cases}$$

Next, I calculate the expected value:

$$\mathbb{E}[V_b] = P \mathbb{E}(1 + R) = P \left( 0.3(1.03) + 0.7(1.035) \right)$$

$$\mathbb{E}[V_b] = P (0.309 + 0.7245) = 1.0335P$$

So the expected amount at the end of the term is $1.0335P$. The two conventions give slightly different expected values ($1.03407P$ and $1.0335P$), because $e^R$ and $1 + R$ are different growth factors.

### Exercise 2 (Coursework 5)

**Question:** Take the same random interest rate $R$ as in Exercise 1,

$$R = \begin{cases} 0.03 & \text{with probability } 0.3 \\ 0.035 & \text{with probability } 0.7 \end{cases}$$

(that is, 3% with probability 0.3 and 3.5% with probability 0.7), and treat it as a continuously compounded annual rate, so that over one year a deposit grows by the factor $\exp(R)$.

* (a) Find the expected rate $\mathbb{E}(R)$.
* (b) Find $\exp(\mathbb{E}(R))$, the growth factor of your deposit using the expected rate.
* (c) Find $\mathbb{E}(\exp(R))$, the expected growth factor.
* (d) Should $\mathbb{E}(\exp(R))$ not be the same as $\exp(\mathbb{E}(R))$?

**(a) Expected rate $\mathbb{E}(R)$**

To find the expected interest rate, I take the weighted average of the two possible rates:

$$\mathbb{E}(R) = 0.3(0.03) + 0.7(0.035) = 0.009 + 0.0245 = 0.0335$$

which is 3.35%.

**(b) Growth factor using the expected rate**

Plugging my expected rate $\mathbb{E}(R) = 0.0335$ into the exponential growth factor gives:

$$\exp(\mathbb{E}(R)) = e^{0.0335} \approx 1.034067$$

**(c) Expected growth factor**

From Exercise 1(a), the expected growth factor is the weighted average of the individual growth factors:

$$\mathbb{E}(\exp(R)) = 0.3 e^{0.03} + 0.7 e^{0.035} \approx 0.3(1.030455) + 0.7(1.035620) = 1.034070$$

**(d) Should $\mathbb{E}(\exp(R))$ not be the same as $\exp(\mathbb{E}(R))$?**

No, they shouldn't be the same. Because $e^x$ curves upwards, $\mathbb{E}(\exp(R))$ will be larger than $\exp(\mathbb{E}(R))$ whenever $R$ is random, and here the two values are very close (about $0.000003$ apart) simply because $R$ has such a small spread, making the difference look tiny even though it is still positive. This is the same idea from Section 4.1 of my summary, where the expected accumulated value is higher than the value calculated using the mean interest rate.


## Spreadsheets

