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








## My example


## Solved exercises


## Spreadsheet
