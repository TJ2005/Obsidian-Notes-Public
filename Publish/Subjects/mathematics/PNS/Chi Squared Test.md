---
Title: "Chi Squared Test"
Status: 
marker: 
tags: 
Date: "2025.04.02"
Time: "14:10"
---
w# Chi Squared Test

## Test for independence of attributes

|         | $A$ | $A_1$       | $\dots$ | $A_r$      | Total   |
| ------- | --- | ----------- | ------- | ---------- | ------- |
| $B$     |     |             |         |            | $(b_1)$ |
| $B_1$   |     | $(A_1 B_1)$ |         | $(A_rB_1)$ | $(B_1)$ |
| $\dots$ |     |             |         |            |         |
| $B_s$   |     | $(A_1B_s)$  |         | $(A_rB_s)$ | $(B_s)$ |
| Total   |     | $(A_1)$     |         | $(A_r)$    | $N$     |
### Test Statistic
The values in the contingency table are called **observed values**. $(O_i)$.
The **expected Value**s or the **theoretical values** are calculated using the formulae:
$$
\text{expected frequency} = \frac{{\text{row total} \times \text{column total}}}{overal total ( N )}
$$

Formulae for test statistic is 
$$\chi^2=\sum\left( \frac{{O_{i}-E_{i}}}{E_{i}} \right)$$
Critical Value from the table


Degrees of freedom = $(r-1)\times (s-1)$

## Questions
Two sample polls of votes for two candidates A and B for a public office are taken one from among the rural areas and the other from urban areas. The result are given in the following table

|       | Vote For |     |
| ----- | -------- | --- |
|       | A        | B   |
| Rural | 620      | 380 |
| Urban | 550      | 450 |
Examine whether the nature of the area is related to the voting preference in this election.
#### Solution

|       | Vote For |     |       |
| ----- | -------- | --- | ----- |
|       | A        | B   | Total |
| Rural | 620      | 380 | 1000  |
| Urban | 550      | 450 | 1000  |
|       | 1170     | 830 | 2000  |


# References


###### Information
- date: 2025.04.02
- time: 14:10