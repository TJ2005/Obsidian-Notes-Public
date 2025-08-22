---
Title: Digital Logic Design Lab 4
Status: 
marker: 
tags: 
Date: 2024.08.06
Time: 10:07
---
# Digital Logic Design Lab 4

# Main note

De morgans law using IC


# References


###### Information
- date: 2024.08.06
- time: 10:07](<Here's a detailed note for "Digital Logic Design Lab 4" on De Morgan's Laws using ICs:

---

# Digital Logic Design Lab 4

## Main Note

### De Morgan's Laws Using ICs

#### Objective
To demonstrate De Morgan's Laws using digital logic ICs. De Morgan's Laws are fundamental rules in Boolean algebra that relate the AND and OR operations through negation. The goal is to verify these laws by implementing them with logic gate ICs.

#### Theory

**De Morgan's Laws**:
1. **First Law**: \[ \text{NOT}(A \text{ AND } B) = (\text{NOT } A) \text{ OR } (\text{NOT } B) \]
2. **Second Law**: \[ \text{NOT}(A \text{ OR } B) = (\text{NOT } A) \text{ AND } (\text{NOT } B) \]

These laws can be verified using ICs that implement NOT, AND, and OR gates.

#### Materials Required
- IC 7400 (Quad 2-input NAND gate)
- IC 7402 (Quad 2-input NOR gate)
- IC 7404 (Hex inverter/NOT gate)
- IC 7408 (Quad 2-input AND gate)
- IC 7432 (Quad 2-input OR gate)
- Breadboard
- Connecting wires
- LEDs (4 pieces)
- Resistors (4 pieces, 220 ohms)
- Power supply (5V DC)
- SPST switches (4 pieces)

#### Pin Configuration

**IC 7400 (Quad 2-input NAND Gate)**:
```
        +---+--+---+
    1A  |1  +--+ 14| VCC
    1B  |2       13| 4B
    1Y  |3       12| 4A
    2A  |4       11| 4Y
    2B  |5       10| 3B
    2Y  |6        9| 3A
   GND  |7        8| 3Y
        +----------+
```

**IC 7402 (Quad 2-input NOR Gate)**:
```
        +---+--+---+
    1A  |1  +--+ 14| VCC
    1B  |2       13| 4B
    1Y  |3       12| 4A
    2A  |4       11| 4Y
    2B  |5       10| 3B
    2Y  |6        9| 3A
   GND  |7        8| 3Y
        +----------+
```

**IC 7404 (Hex Inverter/NOT Gate)**:
```
        +---+--+---+
    1A  |1  +--+ 14| VCC
    1Y  |2       13| 6A
    2A  |3       12| 6Y
    2Y  |4       11| 5A
    3A  |5       10| 5Y
    3Y  |6        9| 4A
   GND  |7        8| 4Y
        +----------+
```

**IC 7408 (Quad 2-input AND Gate)**:
```
        +---+--+---+
    1A  |1  +--+ 14| VCC
    1B  |2       13| 4B
    1Y  |3       12| 4A
    2A  |4       11| 3B
    2B  |5       10| 3A
    2Y  |6        9| 3Y
   GND  |7        8| 2Y
        +----------+
```

**IC 7432 (Quad 2-input OR Gate)**:
```
        +---+--+---+
    1A  |1  +--+ 14| VCC
    1B  |2       13| 4B
    1Y  |3       12| 4A
    2A  |4       11| 3B
    2B  |5       10| 3A
    2Y  |6        9| 2Y
   GND  |7        8| 1Y
        +----------+
```

#### Procedure

**Verification of De Morgan's First Law: \[ \text{NOT}(A \text{ AND } B) = (\text{NOT } A) \text{ OR } (\text{NOT } B) \]**

1. **Setup ICs**:
   - Use IC 7408 (AND gate) to perform \( A \text{ AND } B \).
   - Use IC 7404 (NOT gate) to invert the output of the AND gate.
   - Use IC 7404 (NOT gates) to invert inputs \( A \) and \( B \).
   - Use IC 7432 (OR gate) to perform \( (\text{NOT } A) \text{ OR } (\text{NOT } B) \).

2. **Connect the Circuit**:
   - Connect inputs \( A \) and \( B \) to the inputs of the IC 7408.
   - Connect the output of IC 7408 to one input of an IC 7404.
   - Connect the other input of IC 7404 to ground (for NOT operation).
   - Connect \( A \) and \( B \) to IC 7404 for NOT operations and then to IC 7432 for OR operation.

3. **Testing**:
   - Set the switches to different combinations of \( A \) and \( B \) (0 and 1).
   - Observe the output of the NAND gate, the output of the NOT gate, and compare it with the output of the OR gate.

4. **Record Observations**:
   - Verify that the output of \( \text{NOT}(A \text{ AND } B) \) matches \( (\text{NOT } A) \text{ OR } (\text{NOT } B) \) for all combinations of \( A \) and \( B \).

**Verification of De Morgan's Second Law: \[ \text{NOT}(A \text{ OR } B) = (\text{NOT } A) \text{ AND } (\text{NOT } B) \]**

1. **Setup ICs**:
   - Use IC 7432 (OR gate) to perform \( A \text{ OR } B \).
   - Use IC 7404 (NOT gate) to invert the output of the OR gate.
   - Use IC 7404 (NOT gates) to invert inputs \( A \) and \( B \).
   - Use IC 7408 (AND gate) to perform \( (\text{NOT } A) \text{ AND } (\text{NOT } B) \).

2. **Connect the Circuit**:
   - Connect inputs \( A \) and \( B \) to the inputs of the IC 7432.
   - Connect the output of IC 7432 to one input of an IC 7404.
   - Connect the other input of IC 7404 to ground (for NOT operation).
   - Connect \( A \) and \( B \) to IC 7404 for NOT operations and then to IC 7408 for AND operation.

3. **Testing**:
   - Set the switches to different combinations of \( A \) and \( B \) (0 and 1).
   - Observe the output of the OR gate, the output of the NOT gate, and compare it with the output of the AND gate.

4. **Record Observations**:
   - Verify that the output of \( \text{NOT}(A \text{ OR } B) \) matches \( (\text{NOT } A) \text{ AND } (\text{NOT } B) \) for all combinations of \( A \) and \( B \).

## References

###### Information
- Date: 2024.08.06
- Time: 10:07
