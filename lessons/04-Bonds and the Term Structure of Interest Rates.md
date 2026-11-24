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

**Question:** Work out the no-arbitrage price of a 3-year bond with face value £20,000, redeemed at par, paying 5% annual coupons, when the spot rates are $s_1 = 4$%, $s_2 = 4.5$% and $s_3 = 5$%.

**How I do it:**

First, each annual coupon is 5% of the £20,000 face value:

$$C = 0.05 \times 20{,}000 = £1{,}000$$

Since it's redeemed at par ($R = 1$), the final redemption payment in year 3 is £20,000.

By the law of one price, the no-arbitrage price equals the present value of the cash flows, discounted with the spot rates. Next, I find the discount factor for each year using $D(t) = (1 + s_t)^{-t}$:

$$D(1) = (1.04)^{-1} \approx 0.96154$$

$$D(2) = (1.045)^{-2} \approx 0.91573$$

$$D(3) = (1.05)^{-3} \approx 0.86384$$

Now I discount every cash flow back to today and add them up:

$$PV = 1{,}000\big(D(1) + D(2) + D(3)\big) + 20{,}000\,D(3)$$

$$PV \approx 1{,}000(0.96154 + 0.91573 + 0.86384) + 20{,}000\,D(3) \approx 2{,}741.11 + 17{,}276.75 = £20{,}017.86$$

(The discount factors above are rounded to 5 decimal places. I used the unrounded values on my calculator, so the redemption term is £17,276.75 rather than the £17,276.80 I would get from $20{,}000 \times 0.86384$.)

So the no-arbitrage price is £20,017.86 (to the nearest penny), slightly above £20,000 because the spot rates in years 1 and 2 are below the 5% coupon rate. If all the spot rates were flat at 5%, the bond would trade at par, for exactly £20,000.


## Solved Exercises

### Exercise 5 (Coursework 4)

**Question:** Suppose that the 1, 2 and 3-year LIBOR rates are 3.5%, 4% and 4.7%, respectively. Suppose also that the forward rates $f_{3,5}$ and $f_{4,5}$ are 5% and 4.9% respectively. Calculate:

* (a) The spot rates $s_1, s_2$ and $s_3$ and the forward rate $f_{3,4}$.
* (b) The spot rate $s_4$.
* (c) The present value of a cash-flow stream consisting of two payments of £100 after 3 and 4 years, respectively.

**(a) Spot rates $s_1, s_2, s_3$ and forward rate $f_{3,4}$**

LIBOR rates are quoted as annualised nominal rates $r_T$, so I convert them into effective annual spot rates using $s_T = (1 + r_T T)^{1/T} - 1$:

$$s_1 = (1 + 0.035 \times 1)^{1/1} - 1 = 0.035$$

$$s_2 = (1 + 0.04 \times 2)^{1/2} - 1 = (1.08)^{0.5} - 1 \approx 0.03923$$

$$s_3 = (1 + 0.047 \times 3)^{1/3} - 1 = (1.141)^{1/3} - 1 \approx 0.04495$$

So $s_1 = 3.5$%, $s_2 \approx 3.923$% and $s_3 \approx 4.495$%.

To get $f_{3,4}$, I chain the consecutive forward rates from year 3 to year 5 so they multiply out to the rate over the whole period:

$$(1 + f_{3,4})(1 + f_{4,5}) = (1 + f_{3,5})^2$$

$$(1 + f_{3,4})(1.049) = (1.05)^2$$

$$1 + f_{3,4} = \frac{1.1025}{1.049} \approx 1.051001$$

So $f_{3,4} \approx 0.05100$, which is 5.100%.

**(b) Spot rate $s_4$**

Using the forward rate formula $(1 + f_{n_1, n_2})^{n_2 - n_1} = \frac{(1 + s_{n_2})^{n_2}}{(1 + s_{n_1})^{n_1}}$ with $n_1 = 3$ and $n_2 = 4$:

$$(1 + s_4)^4 = (1 + s_3)^3 (1 + f_{3,4})$$

From part (a), $(1 + s_3)^3 = 1.141$ and $1 + f_{3,4} = \frac{1.1025}{1.049}$:

$$(1 + s_4)^4 = 1.141 \times \frac{1.1025}{1.049} \approx 1.199192$$

$$s_4 = (1.199192)^{1/4} - 1 \approx 0.04646$$

So $s_4 \approx 4.646$%.

**(c) Present value of the cash-flow stream**

By the law of one price, I discount each £100 payment back to today using $D(T) = (1 + s_T)^{-T}$ and add them up:

$$PV = 100\,D(3) + 100\,D(4) = \frac{100}{(1 + s_3)^3} + \frac{100}{(1 + s_4)^4}$$

Using the exact values $(1 + s_3)^3 = 1.141$ and $(1 + s_4)^4 \approx 1.199192$:

$$PV \approx \frac{100}{1.141} + \frac{100}{1.199192} \approx 87.6424 + 83.3895 = £171.03$$

to the nearest penny.

### Exercise 10 (Coursework 4)

**Question:** A bond is said to be ex coupon if it is sold under the proviso that the investor will not be paid the next coupon from the bond. Suppose an investor purchases an ex-coupon bond with face value of £100, redeemable at par, which pays semi-annual coupons at a rate of 8% per annum. There are 8 days until the next coupon (which will not be paid) and the bond expires 7 years after this coupon. If the bond yield is 6%, calculate the purchase price of the bond.

**How I do it:**

First, I work out the size of each coupon. Because it pays semi-annual coupons ($m = 2$) at 8% per annum on a £100 face value, each half-yearly coupon is:

$$C = \frac{0.08 \times 100}{2} = £4$$

Since the bond is redeemable at par ($R = 1$), the final redemption payment at expiry is £100.

Next, I figure out which payments I actually get and when they arrive. The very next coupon is in 8 days, which is $\frac{8}{365}$ years away, and because the bond is ex-coupon, I skip that one. The bond expires 7 years after that skipped coupon, so over those 7 years there are $7 \times 2 = 14$ semi-annual coupons left that I will receive.

To make the discounting clean, I first find the value of all those remaining payments as of the next coupon date (8 days from now). From that date, the 14 remaining £4 coupons arrive at $0.5, 1, 1.5, \dots, 7$ years, plus the £100 redemption at year 7. Using the bond yield $r = 0.06$, the value on that date is:

$$PV_{\text{next coupon date}} = \sum_{k=1}^{14} \frac{4}{(1.06)^{k/2}} + \frac{100}{(1.06)^7}$$

Using the geometric series formula $\sum_{k=1}^{14} x^k = \frac{x(1 - x^{14})}{1 - x}$ with $x = (1.06)^{-0.5} \approx 0.97128586$:

$$\sum_{k=1}^{14} \frac{1}{(1.06)^{k/2}} = \frac{0.97128586\big(1 - (1.06)^{-7}\big)}{1 - 0.97128586} \approx \frac{0.97128586(1 - 0.66505711)}{0.02871414} \approx 11.32979$$

So the value 8 days from now is:

$$PV_{\text{next coupon date}} \approx 4(11.32979) + 100(0.66505711) \approx 45.3192 + 66.5057 = £111.8249$$

Finally, by the law of one price, I discount this amount back by the remaining 8 days ($\frac{8}{365}$ years) to get today's purchase price $P_0$:

$$P_0 = \frac{PV_{\text{next coupon date}}}{(1.06)^{8/365}} \approx \frac{111.8249}{1.0012779} \approx £111.68$$

to the nearest penny. (I kept unrounded values on my calculator in the intermediate steps so there is no rounding error.)

So the purchase price of the bond is £111.68 (above par because the 8% coupon rate is higher than the 6% yield, even after missing the imminent coupon).

## Spreadsheet
