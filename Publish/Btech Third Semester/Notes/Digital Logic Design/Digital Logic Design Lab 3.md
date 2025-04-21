---
Title: Digital Logic Design Lab 3
Status: 
marker: 
tags: 
Date: 2024.07.30
Time: 13:10
---
[# Digital Logic Design Lab 3

# Main note

# Making Not And Or from Nand Gate
# Using nor to make other gates
# References


###### Information
- date: 2024.07.30
- time: 13:10](<Here's a completed version of the note for "Digital Logic Design Lab 3" with detailed sections, similar to the provided examples:

---

# Digital Logic Design Lab 3

## Main Note

### Making NOT, AND, OR from NAND Gate

#### Objective
To demonstrate how to construct NOT, AND, and OR gates using only NAND gates.

#### Theory
- **NAND Gate**: A fundamental logic gate that outputs false only when all its inputs are true. It can be used to create other logic gates.

##### NAND Gate Truth Table
| Input A | Input B | Output |
|---------|---------|--------|
|    0    |    0    |    1   |
|    0    |    1    |    1   |
|    1    |    0    |    1   |
|    1    |    1    |    0   |

#### Constructing NOT Gate Using NAND Gates
To create a NOT gate, connect both inputs of a NAND gate to the same signal:
- **NOT Gate Implementation**: 
  - Connect input `A` to both inputs of a NAND gate.
  - The output will be `NOT A`.

**Truth Table for NOT Gate**

| Input A | Output (NOT A) |
|---------|----------------|
|    0    |       1        |
|    1    |       0        |

#### Constructing AND Gate Using NAND Gates
To create an AND gate, use the following configuration:
1. **First Stage**: Connect inputs `A` and `B` to a NAND gate to get the intermediate output `N1`.
2. **Second Stage**: Connect the output `N1` to both inputs of another NAND gate to get the final output.

**Truth Table for AND Gate**

| Input A | Input B | Output (A AND B) |
|---------|---------|------------------|
|    0    |    0    |        0         |
|    0    |    1    |        0         |
|    1    |    0    |        0         |
|    1    |    1    |        1         |

#### Constructing OR Gate Using NAND Gates
To create an OR gate, use the following configuration:
1. **First Stage**: Connect input `A` to both inputs of a NAND gate to get `N1`.
2. **Second Stage**: Connect input `B` to both inputs of a NAND gate to get `N2`.
3. **Third Stage**: Connect `N1` and `N2` to the inputs of another NAND gate to get the final output.

**Truth Table for OR Gate**

| Input A | Input B | Output (A OR B) |
|---------|---------|-----------------|
|    0    |    0    |        0        |
|    0    |    1    |        1        |
|    1    |    0    |        1        |
|    1    |    1    |        1        |

### Using NOR to Make Other Gates

#### Objective
To demonstrate how to construct NOT, AND, and OR gates using only NOR gates.

#### Theory
- **NOR Gate**: A fundamental logic gate that outputs true only when all its inputs are false. It can be used to create other logic gates.

##### NOR Gate Truth Table
| Input A | Input B | Output |
|---------|---------|--------|
|    0    |    0    |    1   |
|    0    |    1    |    0   |
|    1    |    0    |    0   |
|    1    |    1    |    0   |

#### Constructing NOT Gate Using NOR Gates
To create a NOT gate, connect both inputs of a NOR gate to the same signal:
- **NOT Gate Implementation**: 
  - Connect input `A` to both inputs of a NOR gate.
  - The output will be `NOT A`.

**Truth Table for NOT Gate**

| Input A | Output (NOT A) |
|---------|----------------|
|    0    |       1        |
|    1    |       0        |

#### Constructing AND Gate Using NOR Gates
To create an AND gate, use the following configuration:
1. **First Stage**: Connect inputs `A` and `B` to a NOR gate to get `N1`.
2. **Second Stage**: Connect `N1` to both inputs of another NOR gate to get the final output.

**Truth Table for AND Gate**

| Input A | Input B | Output (A AND B) |
|---------|---------|------------------|
|    0    |    0    |        0         |
|    0    |    1    |        0         |
|    1    |    0    |        0         |
|    1    |    1    |        1         |

#### Constructing OR Gate Using NOR Gates
To create an OR gate, use the following configuration:
1. **First Stage**: Connect input `A` to both inputs of a NOR gate to get `N1`.
2. **Second Stage**: Connect input `B` to both inputs of a NOR gate to get `N2`.
3. **Third Stage**: Connect `N1` and `N2` to the inputs of another NOR gate to get the final output.

**Truth Table for OR Gate**

| Input A | Input B | Output (A OR B) |
|---------|---------|-----------------|
|    0    |    0    |        0        |
|    0    |    1    |        1        |
|    1    |    0    |        1        |
|    1    |    1    |        1        |

## References

###### Information
- Date: 2024.07.30
- Time: 13:10

---

