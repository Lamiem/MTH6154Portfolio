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

To decide, I compare the IRR with the market rate. The IRR is 11.65%, which is higher than the market rate of 6%.

Since the internal rate of return beats the 6% market rate, buying the equipment is a good investment.

### Exercise 2 (Week 2 exercise sheet): Job offers

**Question:** After graduation you have two job offers, both for a fixed term of 3 years:

- Company A offers you a salary of £65,000 at the end of the first year, £75,000 at the end of the second year, and £115,000 at the end of your final year.
- Company B offers you a signing bonus of £15,000 when you start the job, and then a constant salary of £79,000 at the end of each of the three years.

- By comparing the present values of the pay packages, determine which company offers the better deal if the interest rate is 3.75% and is compounded (i) annually, (ii) continuously.

**Solution:**

The term is $T = 3$ years and the interest rate is $r = 3.75\% = 0.0375$.

**(i) Compounded annually**

The formula for the present value of a payment stream with annual compounding is:

$$PV(\mathbf{a}) = \sum_{i=1}^n \frac{a_i}{(1+r)^i}$$

For Company A:

$$PV_A = \frac{65{,}000}{(1 + 0.0375)^1} + \frac{75{,}000}{(1 + 0.0375)^2} + \frac{115{,}000}{(1 + 0.0375)^3}$$

$$PV_A = \frac{65{,}000}{1.0375} + \frac{75{,}000}{(1.0375)^2} + \frac{115{,}000}{(1.0375)^3}$$

$$PV_A \approx 62{,}650.60 + 69{,}676.30 + 102{,}975.41 = 235{,}302.31$$

So the present value of Company A's offer is approximately £235,302.31.

For Company B (including the £15,000 signing bonus at $t = 0$):

$$PV_B = 15{,}000 + \frac{79{,}000}{(1 + 0.0375)^1} + \frac{79{,}000}{(1 + 0.0375)^2} + \frac{79{,}000}{(1 + 0.0375)^3}$$

$$PV_B = 15{,}000 + \frac{79{,}000}{1.0375} + \frac{79{,}000}{(1.0375)^2} + \frac{79{,}000}{(1.0375)^3}$$

$$PV_B \approx 15{,}000 + 76{,}144.58 + 73{,}392.36 + 70{,}739.63 = 235{,}276.57$$

So the present value of Company B's offer is approximately £235,276.57.

Comparing the two, $PV_A > PV_B$, so Company A offers the better deal under annual compounding.

**(ii) Compounded continuously**

The formula for the present value of a payment stream with continuous compounding is:

$$PV(\mathbf{a}) = \sum_{i=1}^n a_i e^{-r t_i}$$

For Company A:

$$PV_A = 65{,}000 e^{-0.0375 \times 1} + 75{,}000 e^{-0.0375 \times 2} + 115{,}000 e^{-0.0375 \times 3}$$

$$PV_A \approx 65{,}000(0.96319) + 75{,}000(0.92774) + 115{,}000(0.89360)$$

$$PV_A \approx 62{,}607.64 + 69{,}580.76 + 102{,}763.69 = 234{,}952.09$$

So the present value of Company A's offer is approximately £234,952.09.

For Company B:

$$PV_B = 15{,}000 + 79{,}000 e^{-0.0375 \times 1} + 79{,}000 e^{-0.0375 \times 2} + 79{,}000 e^{-0.0375 \times 3}$$

$$PV_B \approx 15{,}000 + 79{,}000(0.96319) + 79{,}000(0.92774) + 79{,}000(0.89360)$$

$$PV_B \approx 15{,}000 + 76{,}092.36 + 73{,}291.74 + 70{,}594.19 = 234{,}978.28$$

So the present value of Company B's offer is approximately £234,978.28.

Comparing the two, $PV_B > PV_A$, so Company B offers the better deal under continuous compounding.

**Conclusion:**

Which offer is better depends on the compounding method: Company A wins under annual compounding (£235,302.31 vs £235,276.57), while Company B wins under continuous compounding (£234,978.28 vs £234,952.09). The two packages are extremely close, with a difference of only about £26 either way.

Continuous compounding at a nominal 3.75% produces a higher effective rate (about 3.82%, from $e^{0.0375} - 1$), meaning every future payment is discounted more heavily. This hurts Company A's large year-3 payment more than Company B, whose £15,000 signing bonus is paid today at $t = 0$ and isn't discounted at all.

## Solved exercises

### Exercise 4 (Week 2 exercise sheet): Perpetuity

**Question:** A perpetuity pays £2,500 every year. The effective annual interest rate is 4%. Calculate its present value if: (a) the first payment is in one years time, (b) the first payment is today, (c) the first payment is in 10 years' time.

**Solution:**

The annual payment is $a = 2{,}500$ and the effective annual interest rate is $r = 4\% = 0.04$.

**(a) First payment in one year's time**

The standard perpetuity formula assumes payments start at $t = 1$, so the present value is:

$$PV = \frac{a}{r}$$

$$PV = \frac{2{,}500}{0.04} = 62{,}500$$

So the present value is £62,500.

**(b) First payment today**

Since the first payment arrives immediately at $t = 0$, it is not discounted, and the remaining payments form a standard perpetuity starting in one year's time:

$$PV = a + \frac{a}{r}$$

$$PV = 2{,}500 + \frac{2{,}500}{0.04}$$

$$PV = 2{,}500 + 62{,}500 = 65{,}000$$

So the present value is £65,000.

**(c) First payment in 10 years' time**

If the first payment arrives at $t = 10$, then at $t = 9$ it looks just like a standard perpetuity whose first payment arrives one year later (at $t = 10$). Its value at $t = 9$ is $\frac{a}{r}$, which we then discount back 9 years to today:

$$PV = \frac{a/r}{(1 + r)^9}$$

$$PV = \frac{62{,}500}{(1 + 0.04)^9}$$

$$PV = \frac{62{,}500}{(1.04)^9} \approx \frac{62{,}500}{1.42331} \approx 43{,}911.67$$

So the present value is approximately £43,911.67.

**Conclusion:**

Even though a perpetuity pays forever, its present value is finite and depends heavily on when those payments start: starting today adds a full £2,500 compared to starting next year (£65,000 vs £62,500), while delaying the start by 10 years drops the present value by nearly £18,600 (to £43,911.67) because every payment has to be discounted an extra 9 years.

## Spreadsheet

[My present value spreadsheet](../spreadsheets/02-PresentValue.xlsx)

This sheet works out the present value of returns, net present value, and internal rate of return for an investment, starting with a £5,000 cash outflow for bakery equipment, and tells you whether it beats the market rate. You can adjust the market interest rate and each year's cash flow in the yellow cells to test different scenarios. Look at the present value, net present value, internal rate of return, investment decision, and the net present value chart as you tweak these inputs. The chart shows that net present value drops as interest rates rise, crossing zero right at the internal rate of return.  



