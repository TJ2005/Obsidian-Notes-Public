---
Title: Digital Logic Design Lecture 18
Status: 
marker: 
tags: 
Date: 2024.10.03
Time: 08:34
---
# Digital Logic Design Lecture 18

## Clock Cycle
AC Input that is quantized

# SR Flip-Flop: Excitation Table and Truth Table

## Truth Table of SR Flip-Flop
| S | R | PS (Qn) | NS (Qn+1) | Condition               |
|---|---|---------|-----------|-------------------------|
| 0 | 0 |    0    |     0     | No change condition     |
| 0 | 1 |    0    |     0     | Reset                   |
| 1 | 0 |    0    |     1     | Set                     |
| 1 | 1 |    0    |     ?     | Indeterminate condition  |

**Legend:**
- PS → Present State
- NS → Next State

## Excitation Table for SR Flip-Flop

- Excitation tables are used for flip-flop conversion.
- The excitation table shows, for a particular combination of present state and next state, what the mandatory inputs must be.

| PS (Qn) | NS (Qn+1) | S   | R   |     |
| ------- | --------- | --- | --- | --- |
| 0       | 0         | 0   | X   |     |
| 0       | 1         | 1   | 0   |     |
| 1       | 0         | 0   | 1   |     |
| 1       | 1         | X   | 0   |     |

**Notes:**
- S, R are the mandatory inputs for each state transition.
- X represents "don't care."



## Additional Notes
- **S, R, Mandatory Inputs:** For each state transition, these inputs are required to achieve the next state.



# Conversion
## Flip-Flop Conversions: SR Flip-Flop to D Flip-Flop

## SR Flip-Flop to D Flip-Flop Conversion:
- **SR**: Source Flip-Flop
- **D**: Destination Flip-Flop

## Truth Table for D Flip-Flop:
| D | PS (Qn) | NS (Qn+1) |
|---|---------|-----------|
| 0 |    0    |     0     |
| 1 |    1    |     1     |

## Excitation Table for SR Flip-Flop:
| PS (Qn) | NS (Qn+1) | S | R |
|---------|-----------|---|---|
|    0    |     0     | 0 | X |
|    0    |     1     | 1 | 0 |
|    1    |     0     | 0 | 1 |
|    1    |     1     | X | 0 |

- `X` represents "Don't care" and can be either `0` or `1`.

## Combined Table for SR to D Conversion:
| D | PS (Qn) | NS (Qn+1) | S | R |
|---|---------|-----------|---|---|
| 0 |    0    |     0     | 0 | X |
| 0 |    1    |     0     | 0 | 1 |
| 1 |    0    |     1     | 1 | 0 |
| 1 |    1    |     1     | X | 0 |

- In the conversion process, the values of `S` and `R` are derived based on the desired next state and the present state.

# References


###### Information
- date: 2024.10.03
- time: 08:34