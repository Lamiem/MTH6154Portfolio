# 1. Interest rates

[Back to contents](../README.md)

## Summary
### 1.Interest Rates
If we borrow or invest an amount P, at nominal interest r, after one year we pay the original plus interest which is $P + rP = P(1+r)$. However when interest is compounded n times per year, interest is charged at rate r/n, once every 1/nth of a year, which means after one year the amount grows to $P(1+\frac{r}{n})^n$. 

The total amount owed or earned is higher when interest is compounded because interest is being charged on top of interest that has already been added. To compare interest rates with different compounding frequencies fairly, we use the effective interest rate which shows the actual percentage growth over a full year. 

The formula is $r_{eff} = \left(1+\frac{r}{n}\right)^n- 1$. The effective rate r_eff is bigger than r whenever n>1.
### 2. Continuous Compounding
If interest is added more and more often in a year, the number of compounding periods increases towards infinity and we say interest is continuously compounded. This means interest is continuously building over time, with each new amount of interest being included in the balance straight away.

The formula for continuously compounded interest is: $A = Pe^{rT}$, where P is the initial amount, r is the annual nominal interest rate and T is the time in years. 

The effective interest rate for continuously compounded interest rate is: $r_{eff}=e^r - 1$. This shows the actual yearly increase after accounting for continuous compounding.
### 3. Doubling Rule and Rule of 72
If an investment grows constantly at an interest rate r, the doubling rule tells us how many years it takes for the original amount to become twice as large. To find T which represents the number of years it takes the investment to double we start with the equation: $Pe^{rT} =2P$, then dividing both sides by P we get $e^{rT} = 2$ then taking natural logs we get $rT = \ln 2$ and then finally solving for T gives: $T = \frac{\ln 2}{r} \approx \frac{0.693}{r}$.

Also, we can use the Rule of 72 to get a quick estimate of how many years it takes for an investment to double by dividing 72 by the interest rate given as a percentage. The formula is: $T \approx\frac{72}{R}$. For example, if r = 0.12 then $R=12$, where R is the rate as a percentage, so $T \approx 72/12 = 6$ years.
### 1.2 Variable Interest Rates
Interest rates do not always stay the same over time and they can increase or decrease, so we use (r(t)) to show the interest rate at a particular moment in time. This is called the instantaneous rate. We assume that interest is continuously compounded, meaning that interest is added constantly and the initial amount deposited or borrowed is P(0) and P(t) represents the amount after time t. We use the formula: $P'(t) = P(t)r(t)$


## My example

### Savings account
Suppose I deposit £3,500 into a savings account offering a nominal interest rate of 5%, compounded monthly. I leave the money in the account for 4 years without making any withdrawals or additional deposits.

I want to investigate how much the savings will grow, how the effective interest rate compares with the nominal rate, and how inflation affects the value of the savings.

## Questions:**

1. How much will I have in my account after 4 years?
2. What is the effective annual interest rate?
3. How much would I have if the interest was continuously compounded instead?
4. If inflation is 3% per year, what is the real interest rate?

## Solutions

**1) Amount after 4 years**
Interest is compounded monthly so I use the formula:
$$A = P\left(1+\frac{r}{n}\right)^{nT}$$

So using the values:

$$A = 3500\left(1+\frac{0.05}{12}\right)^{12(4)}$$

$$A = 3500(1.0041667)^{48}$$

$$A = £4273.13$$

Therefore, after 4 years, my savings will grow to approximately £4,273.13.

**2) Effective interest rate**

The formula for the effective interest rate is:

$$r_{eff} = \left(1+\frac{r}{n}\right)^n -1$$

Using the values:

$$r_{eff} = \left(1+\frac{0.05}{12}\right)^{12} - 1$$

$$r_{eff} = 0.05116$$

$$r_{eff} = 5.1162\%$$

The effective interest rate is approximately 5.1162%, which is slightly higher than the nominal rate of 5% because interest is added monthly.

**3) Continuous Compounding**

Formula for continuously compounded interest:

$$A = Pe^{rT}$$

So:

$$A = 3500e^{0.05(4)}$$

$$A = 3500e^{0.2}$$

$$A = £4274.91$$

This is slightly higher than monthly compounding because interest builds up continuously.

**4) Real interest rate**

Inflation reduces the purchasing power of money, so I use the Formula for real interest rate:

$$r_a = \frac{r_{eff} - r_{inf}}{1 + r_{inf}}$$

where $r_{inf}$ is the inflation rate.

So, substituting the values give me:

$$r_a = \frac{0.0511619 - 0.03}{1 + 0.03} = 0.0205455$$

$$r_a = 2.0546\%$$

Therefore, after accounting for inflation, the real annual return on my savings is approximately 2.0546%.

## Solved exercises

### Exercise 6 (Week 1 exercise sheet): Credit card companies

**Question:** Company A charges a 23.4% nominal rate compounded daily, company B charges a 23.5% compounded monthly, and company C charges 24.2% compounded annually. Which company offers the best deal?

**Solution:**

In order to compare which company has the best deal, we have to use the effective annual interest rate formula:

$$r_{eff} = \left(1+\frac{r}{n}\right)^n -1$$

The best deal is the one with the lowest effective interest rate, as it means paying the least total interest over a year.

**Company A:** nominal rate $r = 23.4\% = 0.234$, compounded daily so $n = 365$.

$$r_{eff,A} = \left(1+\frac{0.234}{365}\right)^{365} - 1\approx (1.000641)^{365} -1 = 0.263550 = 26.36\%$$

**Company B:** nominal rate $r = 23.5\% = 0.235$, compounded monthly so $n = 12$.

$$r_{eff,B} = \left(1+\frac{0.235}{12}\right)^{12} - 1 \approx (1.019583)^{12} - 1 = 0.26204 = 26.20\%$$

**Company C:** nominal rate $r = 24.2\% = 0.242$, compounded annually so $n = 1$.

$$r_{eff,C} = \left(1+\frac{0.242}{1}\right)^{1} - 1 = 0.24200 = 24.20\%$$

**Conclusion:**


| Company | Effective rate |
|---|---|
| A | 26.36% |
| B | 26.20% |
| C | 24.20% |


Therefore, company C offers the best deal because it has the lowest effective interest rate.

### Exercise 11 (Week 1 exercise sheet)

**Question:** In 1626 Peter Minuit bought Manhattan for goods worth 24 dollars. Find the value of this sum in the year 2026 at 5% compounded (a) continuously and (b) annually.

**Solution:**

The time is $T = 2026 - 1626 = 400$ years, the principal is $P = 24$ and the rate is $r = 5\% = 0.05$.

**(a) Continuously compounded**

The formula for continuously compounded interest is:

$$A = Pe^{rT}$$

$$A = 24 \times e^{0.05 \times400}$$

$$A = 24e^{20}$$

$$e^{20} \approx 485{,}165{,}195.41$$

$$A = 24 \times 485{,}165{,}195.41 \approx 11{,}643{,}964{,}689.83$$

So the value is approximately 11.64 billion dollars.

**(b) Compounded annually**

The formula for annual compounding is:

$$A = P(1+r)^T$$

$$A = 24 \times (1+0.05)^{400}$$

$$A = 24 \times (1.05)^{400}$$

$$(1.05)^{400} \approx 299{,}033{,}351.25$$

$$A = 24 \times 299{,}033{,}351.25 \approx 7{,}176{,}800{,}429.97$$

So the value is approximately 7.18 billion dollars.

**Conclusion:**

Compounding continuously gives a noticeably bigger total than annual compounding, showing how compounding more frequently makes a massive difference over long periods of time.



## Spreadsheet

[01-InterestRates.xlsx](../spreadsheets/01-InterestRates.xlsx): what it
does, which cells to change and what to look at.
