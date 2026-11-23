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

## My example

## Solved Exercises

## Spreadsheet
