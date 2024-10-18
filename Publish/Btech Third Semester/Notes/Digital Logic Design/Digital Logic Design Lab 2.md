---
Title: Digital Logic Design Lab 2
Status: 
marker: 
tags: 
Date: 2024-07-23
Time: 08:17
---
	
### Index

1. [Verification of IC 7408 AND Gate Truth Table](#verification-of-ic-7408-and-gate-truth-table)
2. [Verification of IC 7404 NOT Gate Truth Table](#verification-of-ic-7404-not-gate-truth-table)
3. [Verification of IC 7400 NAND Gate Truth Table](#verification-of-ic-7400-nand-gate-truth-table)
4. [Verification of IC 7402 NOR Gate Truth Table](#verification-of-ic-7402-nor-gate-truth-table)

---
### Experiment: Verification of IC 7404 NOT Gate Truth Table

#### Objective
To verify the truth table of the IC 7404 (Hex Inverter) using a breadboard, wires, and LEDs.

#### Materials Required
- IC 7404
- Breadboard
- Connecting wires
- LEDs (6 pieces)
- Resistors (6 pieces, 220 ohms)
- Power supply (5V DC)
- SPST switches (6 pieces)

#### Theory
The IC 7404 contains six independent NOT gates. The truth table for a NOT gate is as follows:

| Input | Output |
|-------|--------|
|   0   |   1    |
|   1   |   0    |

#### Pin Configuration of IC 7404
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

#### Procedure
1. **Setup Power Supply**: Connect the VCC pin (Pin 14) of the IC 7404 to the positive rail (+5V) on the breadboard and the GND pin (Pin 7) to the negative rail (0V).

2. **Connect Inputs**:
    - Connect SPST switches to Pins 1 (1A), 3 (2A), 5 (3A), 9 (4A), 11 (5A), and 13 (6A) for the inputs of the six NOT gates.
    - Ensure one side of each switch is connected to +5V and the other side to the input pins.

3. **Connect Outputs**:
    - Connect LEDs in series with 220-ohm resistors from the output pins (2 (1Y), 4 (2Y), 6 (3Y), 8 (4Y), 10 (5Y), and 12 (6Y)) to ground. This will allow you to see the output of each gate.
    - The longer lead (anode) of the LED goes to the output pin, and the shorter lead (cathode) goes to the resistor, which then connects to ground.

4. **Verify Connections**: Double-check all connections to ensure they match the circuit diagram.

5. **Testing**:
    - Set the inputs for each NOT gate (Pins 1, 3, 5, 9, 11, and 13) and observe the corresponding output on the LEDs connected to Pins 2, 4, 6, 8, 10, and 12.
    - Record the results for both input states (0 and 1) for all gates.

#### Observations
Record the LED states (ON/OFF) for each input switch state.

##### Images

| Input (1A) | Output (1Y) |
|------------|-------------|
|      0     |      1      |
|      1     |      0      |

Repeat the same for the other five NOT gates.

#### Conclusion
Compare the observed output with the expected truth table for a NOT gate to verify the correct functioning of the IC 7404.

---

### Experiment: Verification of IC 7400 NAND Gate Truth Table

#### Objective
To verify the truth table of the IC 7400 (Quad 2-Input NAND Gate) using a breadboard, wires, and LEDs.

#### Materials Required
- IC 7400
- Breadboard
- Connecting wires
- LEDs (4 pieces)
- Resistors (4 pieces, 220 ohms)
- Power supply (5V DC)
- SPST switches (4 pieces)

#### Theory
The IC 7400 contains four independent 2-input NAND gates. The truth table for a 2-input NAND gate is as follows:

| Input A | Input B | Output |
|---------|---------|--------|
|    0    |    0    |    1   |
|    0    |    1    |    1   |
|    1    |    0    |    1   |
|    1    |    1    |    0   |

#### Pin Configuration of IC 7400
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

#### Procedure
1. **Setup Power Supply**: Connect the VCC pin (Pin 14) of the IC 7400 to the positive rail (+5V) on the breadboard and the GND pin (Pin 7) to the negative rail (0V).

2. **Connect Inputs**:
    - Connect SPST switches to Pins 1 (1A) and 2 (1B) for the first NAND gate inputs.
    - Connect SPST switches to Pins 4 (2A) and 5 (2B) for the second NAND gate inputs.
    - Ensure one side of each switch is connected to +5V and the other side to the input pins.

3. **Connect Outputs**:
    - Connect LEDs in series with 220-ohm resistors from the output pins (3 (1Y) and 6 (2Y)) to ground. This will allow you to see the output of each gate.
    - The longer lead (anode) of the LED goes to the output pin, and the shorter lead (cathode) goes to the resistor, which then connects to ground.

4. **Verify Connections**: Double-check all connections to ensure they match the circuit diagram.

5. **Testing**:
    - Set the inputs for the first NAND gate (Pins 1 and 2) and observe the corresponding output on the LED connected to Pin 3.
    - Set the inputs for the second NAND gate (Pins 4 and 5) and observe the corresponding output on the LED connected to Pin 6.
    - Record the results for all possible input combinations (00, 01, 10, 11) for both gates.

#### Observations
Record the LED states (ON/OFF) for each combination of input switches.

| Input A (1A) | Input B (1B) | Output (1Y) |
|--------------|--------------|-------------|
|       0      |       0      |      1      |
|       0      |       1      |      1      |
|       1      |       0      |      1      |
|       1      |       1      |      0      |

Repeat the same for the second NAND gate.

#### Conclusion
Compare the observed output with the expected truth table for a NAND gate to verify the correct functioning of the IC 7400.

---

### Experiment: Verification of IC 7402 NOR Gate Truth Table

#### Objective
To verify the truth table of the IC 7402 (Quad 2-Input NOR Gate) using a breadboard, wires, and LEDs.

#### Materials Required
- IC 7402
- Breadboard
- Connecting wires
- LEDs (4 pieces)
- Resistors (4 pieces, 220 ohms)
- Power supply (5V DC)
- SPST switches (4 pieces)

#### Theory
The IC 7402 contains four independent 2-input NOR gates. The truth table for a 2-input NOR gate is as follows:

| Input A | Input B | Output |
|---------|---------|--------|
|    0    |    0    |    1   |
|    0    |    1    |    0   |
|    1    |    0    |    0   |
|    1    |    1    |    0   |

#### Pin Configuration of IC 7402
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

#### Procedure
1. **Setup Power Supply**: Connect the VCC pin (Pin 14) of the IC 7402 to the positive rail (+5V) on the breadboard and the GND pin (Pin 7) to the negative rail (0V).

2. **Connect Inputs**:
    - Connect SPST switches to Pins 1 (1A) and 2 (1B) for the first NOR gate inputs.
    - Connect SPST switches to Pins 4 (2A) and 5 (2B) for the second NOR gate inputs.
    - Ensure one side of each