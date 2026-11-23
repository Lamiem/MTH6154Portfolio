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

## Solved exercises

### Exercise 2 (Week 3 exercise sheet)

The interest rate is $4\%$, continuously compounded, so a payment $C$ at time $t$ has present value $Ce^{-0.04t}$. For continuous compounding, the effective duration equals the duration.

**(a) Investment: £1,000 at the end of year 2 and £500 at the end of year 3**

Present values:

$$PV_2 = 1{,}000e^{-0.04 \times 2} \approx £923.12, \qquad PV_3 = 500e^{-0.04 \times 3} \approx £443.46$$

$$V = 923.12 + 443.46 = £1{,}366.58$$

Duration (the average time to receive the money, weighted by present values):

$$D = \frac{2(923.12) + 3(443.46)}{1{,}366.58} \approx 2.324 \text{ years}$$

Effective duration, which measures how sensitive the value is to a change in the interest rate:

$$\nu = D \approx 2.324 \text{ years}$$

Convexity:

$$c = \frac{2^2(923.12) + 3^2(443.46)}{1{,}366.58} \approx 5.623 \text{ years}^2$$

**(b) Liability: £1,500 at the end of years 3 and 4**

$$PV_3 = 1{,}500e^{-0.04 \times 3} \approx £1{,}330.38, \qquad PV_4 = 1{,}500e^{-0.04 \times 4} \approx £1{,}278.22$$

$$V = 1{,}330.38 + 1{,}278.22 = £2{,}608.60$$

$$D = \frac{3(1{,}330.38) + 4(1{,}278.22)}{2{,}608.60} \approx 3.49 \text{ years}$$

$$\nu = D \approx 3.49 \text{ years}$$

$$c = \frac{3^2(1{,}330.38) + 4^2(1{,}278.22)}{2{,}608.60} \approx 12.43 \text{ years}^2$$

### Exercise 3 (Week 3 exercise sheet)

The pension fund owes £20 million in 10 years and £40 million in 15 years under a continuously compounded rate of $r = 7\%$. To cover this, it puts £$Q$ million into a bank account (held as cash, so its duration is 0) and buys 25-year zero-coupon bonds paying £$P$ million at maturity.

**(a) Present values and durations**

Present value of the liabilities:

$$PV_{10} = 20e^{-0.07 \times 10} \approx 9.932, \qquad PV_{15} = 40e^{-0.07 \times 15} \approx 13.998$$

$$V_L \approx 23.929 \text{ million}$$

Duration of the liabilities:

$$D_L = \frac{10(9.932) + 15(13.998)}{23.929} \approx 12.925 \text{ years}$$

The 25-year bonds have present value $Pe^{-1.75}$ and duration 25. The bank money has present value $Q$ and duration 0. To match the durations:

$$25 \times Pe^{-1.75} = 10(9.932) + 15(13.998) \approx 309.28$$

$$Pe^{-1.75} \approx 12.371, \qquad P = \frac{12.371}{e^{-1.75}} \approx 71.2 \text{ million}$$

To match the present values:

$$Pe^{-1.75} + Q = 23.929 \quad \Rightarrow \quad 12.371 + Q = 23.929 \quad \Rightarrow \quad Q \approx 11.56 \text{ million}$$

**(b) Convexities**

Liabilities:

$$c_L = \frac{10^2(9.932) + 15^2(13.998)}{23.929} \approx 173.12$$

Assets:

$$c_A = \frac{25^2(12.371)}{23.929} \approx 323.12$$

We already lined up the present values and durations in part (a), and since $c_A = 323.12 > 173.12 = c_L$, all three conditions are met and Redington immunisation holds.

**(c) 5-year bonds instead**

Switching to 5-year bonds means the portfolio only holds assets maturing at 0 years (the bank balance) and 5 years (the bonds). Because the duration of a mix always sits between its shortest and longest maturity, the assets' duration can never exceed 5 years, so it cannot reach the liabilities' $12.925$-year duration, making first-order immunisation impossible.

## Spreadsheet

[03-Immunisation.xlsx](../spreadsheets/03-Immunisation.xlsx)

This spreadsheet checks Redington immunisation for my example: a £10,000 liability due in 5 years, matched with 2-year and 8-year zero-coupon bonds at 5% interest, continuously compounded. The yellow cells are the only inputs, and everything else recalculates from them. The payments $P$ and $Q$ are found by splitting the liability's present value between the two bonds so that their total value and duration match the liability, then converting each share into a payment at maturity.

The three Yes/No checks confirm the conditions hold: the present values and durations match, and the assets' convexity is 34, above the liability's 25. The table and chart show that asset value never falls below liability value as the rate moves from 3% to 7%. At 6% the spreadsheet gives £3.33, while my example page says £3.34, because the spreadsheet uses unrounded values and the page used rounded ones. To explore it, try changing the long bond maturity in B8 (keep it above 5, because the mix needs one bond longer than the liability) and watch $P$ and $Q$ change.
