---
Title: Digital Logic Design Lecture 19
Status: 
marker: 
tags: 
Date: 2024.10.08
Time: 13:08
---
# Digital Logic Design Lecture 19
Conversion JK flip Flop practice
### Derivation of excitation table for JK Flip Flop
| J   | K   | P S $Q_n$ | N.S. $Q_{nm}$ |                           |
| --- | --- | --------- | ------------- | ------------------------- |
| 0   | 0   | X         | $Q_n$         | No change                 |
| 0   | 1   | X         | 0             | Reset                     |
| 1   | 0   | X         | 1             | Set                       |
| 1   | 1   | X         | $Q_n$         | Present state with toggle |

| J   | K   | $Q_n$  | $Q_{n+1}$ |
| --- | --- | ------ | --------- |
| 0   | 0   | 0<br>1 |           |
| 0   | 1   | 0<br>1 | 0<br>0    |
| 1   | 0   | 0<br>1 | 1<br>1    |
| 1   | 2   | 0<br>1 |           |
# Excitation Table for JK Flip-Flop

### Truth Table of JK Flip-Flop:

| J   | K   | P.S. $(Q_n$ | N.S. \$(Q_{n+1}$\) | Description                                                  |
| --- | --- | ----------- | ------------------ | ------------------------------------------------------------ |
| 0   | 0   | X           | $Q_n$              | No change                                                    |
| 0   | 1   | X           | 0                  | Reset                                                        |
| 1   | 0   | X           | 1                  | Set                                                          |
| 1   | 1   | X           | $\overline{Q_n}$   | Present state with toggle $0 \rightarrow 1, 1 \rightarrow 0$ |

---

### JK Flip-Flop State Transitions:

| J  | K  | \(Q_n\) | \(Q_{n+1}\) |
|----|----|---------|-------------|
| 0  | 0  | 0       | 0           |
| 0  | 0  | 1       | 1           |
| 0  | 1  | 0       | 0           |
| 0  | 1  | 1       | 0           |
| 1  | 0  | 0       | 1           |
| 1  | 0  | 1       | 1           |
| 1  | 1  | 0       | 1           |
| 1  | 1  | 1       | 0           |

---

### Excitation Table of JK Flip-Flop:

| \(Q_n\) | \(Q_{n+1}\) | J | K  |
|---------|-------------|---|----|
| 0       | 0           | 0 | X  |
| 0       | 1           | 1 | X  |
| 1       | 0           | X | 1  |
| 1       | 1           | X | 0  |

---

| $Q_n$ | $Q_{n+1}$ | J   | K   |
| ----- | --------- | --- | --- |
| 0     | 0         | 0   | 0   |
| 0     | 1         | 1   | 0   |
| 1     | 0         | 0   | 1   |
| 1     | 1         | 1   | 0   |


# References


###### Information
- date: 2024.10.08
- time: 13:08