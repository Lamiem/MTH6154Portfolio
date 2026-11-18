# 2. Present value

[Back to contents](../README.md)

## Summary

### 1. Present Value

Future money is always worth less than money today because cash right now can be put in the bank to earn interest. To find what a future payment is worth right now, you discount it back using the interest rate.

$$PV(V) = (1+r)^{-i}V$$

This formula tells you the exact amount you need to deposit today so it grows to $V$ after $i$ years. Here $r$ is the annual interest rate and $i$ is the number of years.

### 2. Discount Factor

The multiplier used to discount a future payment is called the discount factor. Because positive interest rates mean future money is worth less, this multiplier is always less than one.

$$D(T) = (1+r)^{-T}$$

It represents the present value of exactly one pound received $T$ years from now.

### 3. Present value of a stream

When you have a series of payments happening over multiple years, you cant just add up the face amounts. Instead, you find the present value of each individual payment and sum them all up.

$$PV(\mathbf{a}) = \sum_{i=1}^n \frac{a_i}{(1+r)^i}$$

Here, $a_i$ represents the payment amount made at the end of period $i$, and $n$ is the total number of periods in the stream. You can add these values together because you could replicate the whole payment schedule by setting up separate bank deposits for each individual year.

### 4. Perpetuities

If a cash flow stream pays out the exact same amount every year and never stops, it is called a perpetuity. Even though the payments go on forever, their total present value is a clean, finite number.

$$PV = \frac{a}{r}$$

In this formula, $a$ is the constant annual payment received forever, and $r$ is the interest rate. As long as the interest rate is greater than zero, this gives you the exact lump sum you need today to fund those endless payments.

### 5. Discount factors for different compounding

You can adjust the discount factor to fit different compounding schedules or changing rates over time. Instead of basic annual compounding, you swap in the specific formula for how the bank accumulates interest.

For interest compounded $n$ times a year:

$$D(T) = \left(1 + \frac{r}{n}\right)^{-nT}$$

For continuous compounding:

$$D(T) = e^{-rT}$$

This lets you find the present value of any payment stream whether interest compounds monthly, continuously, or shifts year by year.

### 6. Rate of return

When you invest an amount $P$, the final value $P_{final}$ is called the return. The profit is the cash made on top of your starting amount, defined as $\text{profit} = P_{final} - P$. Dividing that profit by the starting amount gives the rate of return.

$$R = \frac{P_{final} - P}{P}$$

In this formula, $P$ is the starting principal and $P_{final}$ is the final value of the investment. This gives your total percentage gain, but it ignores how long the investment took. That is a problem, because a 30% return is great over two weeks but poor over forty years.

### 7. Annualised rate and equivalent effective interest rate

Because the basic rate of return ignores time, a naive annualised rate simply divides the return by the number of years, $R/T$. However, this ignores compounding. A better approach is finding the equivalent effective interest rate $r$ that a bank would need to offer so that $P(1+r)^T = P_{final}$. Rearranging this equation gives the true annual growth rate. This links directly back to the compounding ideas from Week 1.

$$r = \left(\frac{P_{final}}{P}\right)^{1/T} - 1$$

In this formula, $r$ is the equivalent effective annual interest rate, $P$ is the starting principal, $P_{final}$ is the final value, and $T$ is the time in years. This lets you fairly compare investments of any duration against standard bank rates.

### 8. Internal rate of return (IRR)

When an investment involves a cash flow stream with payments at multiple different times rather than a single lump sum, we use the internal rate of return. The IRR is the hypothetical effective interest rate that makes the present value of all cash flows equal to the initial investment. For positive cash flows, there is exactly one such rate.

$$P = \sum_{i=1}^n \frac{a_i}{(1+r)^{t_i}}$$

In this formula, $P$ is the initial investment, $a_i$ is the payment received at time $t_i$, and $r$ is the internal rate of return.

In general, solving for $r$ is difficult because it requires finding the roots of a polynomial equation, so it is usually done numerically using trial and error or software tools like Excel. You can judge whether an investment is good by comparing its IRR to the market interest rate: if the IRR exceeds the market rate, it is worth making, but if it is lower than the market rate, it is a bad investment.





## My example


## Solved exercises


## Spreadsheet
