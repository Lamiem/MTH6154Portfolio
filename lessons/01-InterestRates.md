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

## My example

A situation you made up (your own numbers, not the ones in the lecture
notes), worked step by step.

## Solved exercises

### Exercise 1.x (from Exercise Sheet 1)

Question, then your solution.

## Spreadsheet

[01-InterestRates.xlsx](../spreadsheets/01-InterestRates.xlsx): what it
does, which cells to change and what to look at.
