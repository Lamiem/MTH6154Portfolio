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


## My example

## Solved exercises

## Spreadsheet
