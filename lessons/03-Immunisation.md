# 3. Immunisation

### Summary

### 1. Immunisation

When you have money coming in or going out in the future, interest rate changes shift what those payments are worth today. Immunisation is setting up your cash flows so that small changes in interest rates do not leave you worse off.

### 2. Present value under changing rates

If we have a stream of $n$ payments $C_i$ at times $t_i$, their present value depends on the current interest rate $r$. We find it by multiplying each payment by its discount factor and adding them all up:

$$V(r) = \sum_{i=1}^{n} C_i D(t_i; r)$$

Here $D(t_i; r)$ is the discount factor, equal to $e^{-rt_i}$ for continuous compounding or $(1+r)^{-t_i}$ for yearly compounding. Whenever all payments are positive, a higher interest rate lowers $V(r)$ because each future payment gets discounted more heavily.

### 3. Effective duration and duration

When interest rates go up, the present value of a payment stream drops, and we can use derivatives to see how fast that happens. Instead of leaving the first derivative in pounds or dollars, effective duration divides by $V(r)$ so you get a measure in years rather than money. . The minus sign is there so the result comes out positive when all cash flows are positive, though negative payments can make it negative.

$$\nu = -\frac{V'(r)}{V(r)}$$

Duration is another way to look at when payments happen, defined whenever the present value is greater than zero.

$$\tau = \frac{\sum_{i=1}^{n} t_i C_i D(t_i; r)}{V(r)}$$

When all the payments are positive, duration acts like a weighted average of the payment times, where each payment time is weighted by the present value of that payment.

Effective duration and duration are closely tied together: with continuous compounding we get $\nu = \tau$, and with yearly compounding we get $\nu = \beta\tau$, where $\beta = 1/(1+r)$. Since $\nu$ is just a multiple of $\tau$, a larger duration means the present value falls faster when interest rates rise.



## My example

## Solved Exercises

## Spreadsheet

