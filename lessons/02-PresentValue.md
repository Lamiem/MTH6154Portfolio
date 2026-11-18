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

### Small business equipment investment

You spend £5,000 today on bakery equipment that pays you back £2,000 at the end of the first year and £4,000 at the end of the second year. The bank or market interest rate you could get elsewhere is 6% per year.

I want to find out if buying this equipment is actually worth it compared to putting your money in the market.

**Questions:**

1. What is the present value of the cash returns at the 6% market rate?
2. What is the total rate of return and the equivalent effective annual rate over the two years?
3. What is the internal rate of return (IRR)?
4. Is it a good investment compared to the market rate?

## Solutions

**1) Present value of the returns**

Since the cash returns arrive at different times, I discount each payment back to today and sum them up, using the formula:

$$PV(\mathbf{a}) = \sum_{i=1}^n \frac{a_i}{(1+r)^i}$$

$$PV = \frac{2{,}000}{(1 + 0.06)^1} + \frac{4{,}000}{(1 + 0.06)^2} = \frac{2{,}000}{1.06} + \frac{4{,}000}{1.1236} = 1{,}886.79 + 3{,}559.99 = 5{,}446.78$$

The present value of the returns is £5,446.78, meaning the future cash you get back is worth more today than the £5,000 you paid upfront.

**2) Rate of return and effective annual rate**

To measure the overall gain, I use the rate of return formula, and to turn it into a yearly rate I use the equivalent effective annual rate formula:

$$R = \frac{P_{final} - P}{P} \quad \text{and} \quad r = \left(\frac{P_{final}}{P}\right)^{1/T} - 1$$

$$R = \frac{(2{,}000 + 4{,}000) - 5{,}000}{5{,}000} = \frac{1{,}000}{5{,}000} = 0.20 \text{ (or 20\%)}$$

$$r = \left(\frac{6{,}000}{5{,}000}\right)^{1/2} - 1 = (1.2)^{0.5} - 1 \approx 1.0954 - 1 = 0.0954 \text{ (or 9.54\%)}$$

The total rate of return is 20% over two years, which works out to an equivalent effective annual growth rate of 9.54%. This calculation treats the whole £6,000 as if it arrived at the end of year 2, which ignores that £2,000 arrives a year earlier, explaining why the true internal rate of return (11.65%) is higher than 9.54%.

**3) Internal rate of return (IRR)**

The IRR is the rate that makes the present value of the cash flows equal to the initial investment, so I set up the equation:

$$P = \sum_{i=1}^n \frac{a_i}{(1+r)^{t_i}} \implies 5{,}000 = \frac{2{,}000}{1+r} + \frac{4{,}000}{(1+r)^2}$$

Setting $x = 1+r$, multiplying by $x^2$, and rearranging gives the quadratic equation $5x^2 - 2x - 4 = 0$. Solving for the positive root gives $x \approx 1.1165$, so $r = 1.1165 - 1 = 0.1165$.

The internal rate of return is 11.65%, which is the exact discount rate that makes the present value of the payments equal your starting £5,000 cost.

**4) Investment decision**

To decide, I compare the IRR with the market rate: $\text{IRR} (11.65\%) > \text{Market Rate} (6.00\%)$.

Since the internal rate of return beats the 6% market rate, buying the equipment is a good investment.
