# 3. Immunisation

[Back to contents](../README.md)

## Summary

### 1. Immunisation

When you have money coming in or going out in the future, interest rate changes shift what those payments are worth today. Immunisation is setting up your cash flows so that small changes in interest rates do not leave you worse off.

### 2. Present value under changing rates

If we have a stream of $n$ payments $C_i$ at times $t_i$, their present value depends on the current interest rate $r$. We find it by multiplying each payment by its discount factor and adding them all up:

$$V(r) = \sum_{i=1}^{n} C_i D(t_i; r)$$

Here $D(t_i; r)$ is the discount factor, equal to $e^{-rt_i}$ for continuous compounding or $(1+r)^{-t_i}$ for yearly compounding. Whenever all payments are positive, a higher interest rate lowers $V(r)$ because each future payment gets discounted more heavily.

### 3. Effective duration and duration

When interest rates go up, the present value of a payment stream drops, and we can use derivatives to see how fast that happens. Instead of leaving the first derivative in pounds or dollars, effective duration divides by $V(r)$ so you get a measure in years rather than money. The minus sign is there so the result comes out positive when all cash flows are positive, though negative payments can make it negative.

$$\nu = -\frac{V'(r)}{V(r)}$$

Duration is another way to look at when payments happen, defined whenever the present value is greater than zero.

$$\tau = \frac{\sum_{i=1}^{n} t_i C_i D(t_i; r)}{V(r)}$$

When all the payments are positive, duration acts like a weighted average of the payment times, where each payment time is weighted by the present value of that payment.

Effective duration and duration are closely tied together: with continuous compounding we get $\nu = \tau$, and with yearly compounding we get $\nu = \beta\tau$, where $\beta = 1/(1+r)$. Since $\nu$ is just a multiple of $\tau$, a larger duration means the present value falls faster when interest rates rise.

### 4. Redington immunisation

If a company holds assets to pay off future liabilities, matching their present values at the current interest rate $r_0$ only guarantees balance at that exact rate, and it can fail as soon as $r$ moves. To stop a small rate move from leaving the company short, we line up three things.

First, the present value of the assets equals the present value of the liabilities at the starting interest rate $r_0$:

$$V_A(r_0) = V_L(r_0)$$

Second, even if both sides have the same value right now, one side might drop faster than the other when interest rates move. Matching the effective durations makes sure both sides react by the same amount to a first approximation:

$$\nu_A = \nu_L$$

Third, because present value curves rather than moving in a straight line, effective duration only covers the initial slope. Convexity measures how much that curve bends:

$$c = \frac{V''(r)}{V(r)}$$

Making sure the assets have at least as much convexity as the liabilities means any extra bend in the curve works in the company's favour. So, up to tiny errors, the company's value won't fall:

$$c_A \ge c_L$$

When all three of these conditions hold, up to very small errors, a small change in interest rates will not cause the company's net position to fall.

### 5. Immunising in practice

To put immunisation into practice, a company can use zero-coupon bonds, which pay one set amount on a single set date. Choosing how much to hold of two different maturities gives two equations to solve for the two bond amounts so that present values and durations match. Once those amounts are found, you still need to check that the convexity condition holds. Because any mix of bonds has a duration sitting between its earliest and latest maturity dates, you won't be able to match durations if your liabilities' duration falls outside that range. When interest is compounded yearly instead, the same ideas still apply using $\beta = 1/(1+r)$ in the present value sum:

$$V(r) = \sum_{i=1}^{n} C_i \beta^{t_i}$$


## My example

I owe £10,000 in 5 years, and I want assets that stay at least as valuable if rates change. Suppose the interest rate is $r = 5\%$ ($0.05$) and is compounded continuously, giving the discount factor $\beta = e^{-0.05} \approx 0.9512$. My liability has a present value of $10{,}000\beta^5 \approx £7{,}788.01$, a duration of 5 years, and a convexity of $5^2 = 25$.

To build the assets, I pick 2-year and 8-year zero-coupon bonds paying $P$ and $Q$. I chose one maturity shorter than 5 years and one longer so the mix can have a duration of 5. Because interest is continuously compounded, effective duration equals duration ($\nu = \tau$). The first equation matches present values, and the second matches effective durations:

$$P\beta^2 + Q\beta^8 = 10{,}000\beta^5$$

$$2P\beta^2 + 8Q\beta^8 = 50{,}000\beta^5$$

Subtracting twice the first equation from the second removes $P$ and leaves $6Q\beta^8 = 30{,}000\beta^5$. Solving for $Q$ and then $P$ gives $Q = 5{,}000\beta^{-3} \approx £5{,}809.17$ and $P = 5{,}000\beta^3 \approx £4{,}303.54$.

Next, I check convexity using the continuous-compounding formula:

$$c_A = \frac{2^2 P\beta^2 + 8^2 Q\beta^8}{10{,}000\beta^5} = \frac{4(5{,}000\beta^5) + 64(5{,}000\beta^5)}{10{,}000\beta^5} = 34$$

Since $V_A = V_L$, $\nu_A = \nu_L$, and $c_A = 34 \ge 25 = c_L$, Redington immunisation is satisfied.

To see how it behaves if rates move to $6\%$ ($r = 0.06$, continuous compounding):

* Liability present value: $10{,}000 e^{-0.06 \times 5} = 10{,}000 e^{-0.30} \approx £7{,}408.18$.
* 2-year bond present value: $P e^{-0.06 \times 2} \approx 4{,}303.54 \times 0.8869 \approx £3{,}816.90$.
* 8-year bond present value: $Q e^{-0.06 \times 8} \approx 5{,}809.17 \times 0.6188 \approx £3{,}594.62$.
* Total asset present value: about £7,411.52.

The assets come out about £3.34 ahead of the liabilities (£7,411.52 against £7,408.18), which is what Redington immunisation predicts. This means a small change in interest rates does not hurt my net position.

## Solved Exercises

## Spreadsheet

