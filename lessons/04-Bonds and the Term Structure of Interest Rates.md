# 4. Bonds and the Term Structure of Interest Rates

[Back to contents](../README.md)

## Summary

### 1. What a bond is

When you buy a bond, you pay an issue price today, and in return you get regular coupon payments (say every year or half-year) and then the final redemption payment (usually the face value) at the expiry date. The face value is the amount that the coupon rate and the redemption are based on. If the bond pays coupons $m$ times a year, each payment is the annual coupon ($\text{coupon rate} \times \text{face value}$) split into $m$ payments. The coupon rate is separate from the market interest rate. At the end, you receive the redemption payment, $R$ times the face value. Most bonds are redeemable at par ($R = 1$). A zero-coupon bond skips the regular coupons and just pays one lump sum at expiry.

### 2. Present value of a bond

To work out what a bond is worth today, I just discount each future payment back to now and add them all together, leaving out the initial issue price you paid at the start. If the bond pays coupons $C_1, \dots, C_n$ at times $T_1, \dots, T_n$ and a final redemption payment $RP$ (where $P$ is the face value) at expiry $T_n$, we multiply each payout by its discount factor $D(T)$, the discount factor for money received at time $T$:

$$PV = D(T_1)C_1 + D(T_2)C_2 + \dots + D(T_n)C_n + D(T_n)RP$$

For a zero coupon bond with face value 1 that is redeemable at par and matures at time $T$, there are no coupons, so its present value is simply $D(T)$.

### 3. No arbitrage and the law of one price

An arbitrage is basically a free lunch, a risk free profit at no cost. In a frictionless market (no trading costs or restrictions), we assume no arbitrage, because if a free profit ever popped up, traders would jump on it until the price gap closed.

From that comes the law of one price: if two investments give you the exact same future cash flows, they have to sell for the same price today. Because we could replicate a bond's payouts by putting its present value in a bank account, a bond's fair price has to equal its present value. It also means the price $V_T$ of a unit zero coupon bond paying £! at expiry $T$ equals the discount factor $D(T)$, so we can price any coupon bound by adding up each payment times the price of the zero coupon bond that expires on the date:

$$PV = V_[T_1]C_1 + \dots + V_{T_n}C_n + V_{T_n}RP$$

### 4. Bond yield

If I don't know the market interest rate, I can't work out a bond's present value directly, so instead I take the bond's quoted issue price $P_0$ and work backwards to find the single hypothetical interest rate $r$ that makes the present value equal to $P_0$. That rate is the bond yield, which is really just the internal rate of return (IRR) of buying the bond:

$$P_0 = \sum_{i=1}^{n} \frac{C_i}{(1+r)^{t_i}} + \frac{RP}{(1+r)^{t_n}}$$

This equation has exactly one solution, for the same reason the IRR does. If the yield is higher than the market interest rate, the bond is a good investment, and if it's lower, it isn't. In general, the bond yield will not equal the coupon rate.

### 5. Spot rates and the term structure

In real life, interest rates usually depend on how long you're borrowing or depositing for (the term), mostly because of supply and demand: if lots of people want long loans, long rates go up, and if there's plenty of short cash around, short rates drop. That variation across terms is the term structure of interest rates. Markets usually quote annualised nominal rates $r_T$, where putting £$P$ in for term $T$ years pays back $P(1 + r_T T)$, so to compare terms fairly I turn them into effective annual rates called spot rates ($s_T$):

$$s_T = (1 + r_T T)^{1/T} - 1 \quad \text{or} \quad (1 + s_T)^T = 1 + r_T T$$

With spot rates, the discount factor to time $T$ is $D(T) = (1 + s_T)^{-T}$. I can also get spot rates straight from unit zero-coupon bond prices via $s_T = V_T^{-1/T} - 1$.

### 6. Forward rates

A forward rate $f_{n_1, n_2}$ is the fair, no-arbitrage interest rate I agree to today for a deposit or loan running from time $n_1$ to time $n_2$ (in years) in the future (a forward rate agreement, or FRA, where there's no option to back out once signed). Even though it feels like a guess about future rates, it isn't: it's completely fixed by today's spot rates (and zero-coupon bond prices) so that rolling over shorter investments ends up giving the same return as one longer investment:

$$(1 + f_{n_1, n_2})^{n_2 - n_1} = \frac{(1 + s_{n_2})^{n_2}}{(1 + s_{n_1})^{n_1}} = \frac{V_{n_1}}{V_{n_2}}$$

A forward rate starting right now ($n_1 = 0$) is just the spot rate ($f_{0,T} = s_T$), and chaining consecutive forward rates together multiplies out to the forward rate over the whole period (for example $(1+f_{2,4})^2(1+f_{4,7})^3 = (1+f_{2,7})^5$).

## My example

## Solved Exercises

## Spreadsheet
