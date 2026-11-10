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

## My example

A situation you made up (your own numbers, not the ones in the lecture
notes), worked step by step.

## Solved exercises

### Exercise 1.x (from Exercise Sheet 1)

Question, then your solution.

## Spreadsheet

[01-InterestRates.xlsx](../spreadsheets/01-InterestRates.xlsx): what it
does, which cells to change and what to look at.
