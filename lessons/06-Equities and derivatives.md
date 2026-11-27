# 6. Equities and derivatives

[Back to contents](../README.md)

## My summary

### 1. Log-normal rates (from section 4.3 of lecture notes)

A random variable $Y$ is log-normal if its logarithm is normal, written $Y \sim \text{LogNormal}(\mu, \sigma^2)$. This means $\ln Y \sim \mathcal{N}(\mu, \sigma^2)$, or equivalently $Y = e^X$ where $X \sim \mathcal{N}(\mu, \sigma^2)$. This model is really useful here because multiplying independent log-normal variables together gives another log-normal variable, meaning we know the exact distribution of the accumulation factor $S_n$ rather than just its mean and variance.

If the annual growth factors $1 + R_i \sim \text{LogNormal}(\mu, \sigma^2)$ are independent and identically distributed, then:

$$S_n = \prod_{i=0}^{n-1} (1 + R_i) \sim \text{LogNormal}(n\mu, n\sigma^2)$$

Note that here $\mu$ and $\sigma^2$ are the mean and variance of $\ln(1+R_i)$, not of $R_i$ itself.

Using this result, I can find probabilities for $S_n$ directly using the standard normal c.d.f. $\Phi$:

$$\mathbb{P}(S_n \le x) = \Phi\left(\frac{\ln x - n\mu}{\sqrt{n}\,\sigma}\right)$$

### 2. Shares

Owning a share (or stock) means owning a small slice of a company. I write $S(t)$ for the share price at time $t$, which behaves randomly over time. Today's price $S(0)$ is known, while any future price $S(T)$ is uncertain. Although some shares pay dividends, I stick to non dividend paying shares so that the only way to make money from holding one is through the share price changing. Using the frictionless market hypothesis from earlier in the course, I make these standard assumptions:

* I can buy or sell shares in any amount (even fractional amounts) at any time with zero transaction costs.
* There is no bid-ask spread, meaning the buying and selling price of a share at any given moment is identical.
* I can short-sell, which means borrowing a share to sell it now and buying it back later to return it (basically holding a negative number of shares, allowing me to profit if the price falls).

Finally, an investor's portfolio can hold both shares and risk-free cash (a zero-coupon bond or a bank account), which sets up how I price forwards next.

## My example

## Solved exercises

## Spreadsheet
