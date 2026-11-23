# 4. Bonds and the Term Structure of Interest Rates

[Back to contents](../README.md)

## Summary

### 1. What a bond is

When you buy a bond, you pay an issue price today, and in return you get regular coupon payments (say every year or half-year) and then the final redemption payment (usually the face value) at the expiry date. The face value is the amount that the coupon rate and the redemption are based on. If the bond pays coupons $m$ times a year, each payment is the annual coupon ($\text{coupon rate} \times \text{face value}$) split into $m$ payments. The coupon rate is separate from the market interest rate. At the end, you receive the redemption payment, $R$ times the face value. Most bonds are redeemable at par ($R = 1$). A zero-coupon bond skips the regular coupons and just pays one lump sum at expiry.

### 2. Present value of a bond

To work out what a bond is worth today, I just discount each future payment back to now and add them all together, leaving out the initial issue price you paid at the start. If the bond pays coupons $C_1, \dots, C_n$ at times $T_1, \dots, T_n$ and a final redemption payment $RP$ (where $P$ is the face value) at expiry $T_n$, we multiply each payout by its discount factor $D(T)$, the discount factor for money received at time $T$:

$$PV = D(T_1)C_1 + D(T_2)C_2 + \dots + D(T_n)C_n + D(T_n)RP$$

For a zero coupon bond with face value 1 that is redeemable at par and matures at time $T$, there are no coupons, so its present value is simply $D(T)$.


## My example

## Solved Exercises

## Spreadsheet
