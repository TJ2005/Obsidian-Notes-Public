---
Title: Digital Logic Design Lab 1
Status: 
marker:
  - "[[btech]]"
tags:
  - BTech
Date: 2024-07-16
Time: 08:56
---
### Experiment: Verification of IC 7408 AND Gate Truth Table

		### Index for Experiment:
1. **[Objective](#objective)**
2. **[Materials Required](#materials-required)**
3. **[Theory](#theory)**
4. **[Pin Configuration of IC 7408](#pin-configuration-of-ic-7408)**
5. **[Procedure](#procedure)**
6. **[Circuit Diagram](#circuit-diagram)**
7. **[Observations](#observations)**
8. **[Conclusion](#conclusion)**

#### Objective
To verify the truth table of the IC 7408 (Quad 2-Input AND Gate) using a breadboard, wires, and LEDs.

#### Materials Required
- IC 7408
- Breadboard
- Connecting wires
- LEDs (4 pieces)
- Resistors (4 pieces, 220 ohms)
- Power supply (5V DC)
- SPST switches (4 pieces)

#### Theory
The IC 7408 contains four independent 2-input AND gates. The truth table for a 2-input AND gate is as follows:

| Input A | Input B | Output |
|---------|---------|--------|
|    0    |    0    |    0   |
|    0    |    1    |    0   |
|    1    |    0    |    0   |
|    1    |    1    |    1   |

#### Pin Configuration of IC 7408
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
1. **Setup Power Supply**: Connect the VCC pin (Pin 14) of the IC 7408 to the positive rail (+5V) on the breadboard and the GND pin (Pin 7) to the negative rail (0V).

2. **Connect Inputs**:
    - Connect SPST switches to Pins 1 (1A) and 2 (1B) for the first AND gate inputs.
    - Connect SPST switches to Pins 4 (2A) and 5 (2B) for the second AND gate inputs.
    - Ensure one side of each switch is connected to +5V and the other side to the input pins.

3. **Connect Outputs**:
    - Connect LEDs in series with 220-ohm resistors from the output pins (3 (1Y) and 6 (2Y)) to ground. This will allow you to see the output of each gate.
    - The longer lead (anode) of the LED goes to the output pin, and the shorter lead (cathode) goes to the resistor, which then connects to ground.

4. **Verify Connections**: Double-check all connections to ensure they match the circuit diagram.

5. **Testing**:
    - Set the inputs for the first AND gate (Pins 1 and 2) and observe the corresponding output on the LED connected to Pin 3.
    - Set the inputs for the second AND gate (Pins 4 and 5) and observe the corresponding output on the LED connected to Pin 6.
    - Record the results for all possible input combinations (00, 01, 10, 11) for both gates.

#### Circuit Diagram

```plaintext
       +5V    +--------------------------+
               |                          |
              ( )                         |
           ----|----                      |
                |                         |
               GND                        |
                |                         |
              ( ) ( ) ( ) ( )             |
          +----|----|----|----+           |
          |    |    |    |    |           |
          |    1A   1B  VCC   GND         |
          |   1    2     14     7         |
          |   +-----------------+         |
          |   |  IC 7408         |        |
          |   |  QUAD 2-INPUT    |        |
          |   |  AND GATE        |        |
          |   +-----------------+         |
          |   |3Y 2B  2A  1Y    |         |
          |   |8   5   4   3    |         |
          |   |     ...          |        |
          |   +-----------------+         |
          |                               |
        LED1                            LED2
        with                            with
      resistor                        resistor

```

#### Observations
Record the LED states (ON/OFF) for each combination of input switches.

| Input A (1A) | Input B (1B) | Output (1Y) |
|--------------|--------------|-------------|
|       0      |       0      |      0      |
|       0      |       1      |      0      |
|       1      |       0      |      0      |
|       1      |       1      |      1      |

Repeat the same for the second AND gate.

#### Conclusion
Compare the observed output with the expected truth table for an AND gate to verify the correct functioning of the IC 7408.

This experiment confirms that the IC 7408 AND gate outputs the correct results according to its truth table for various input combinations.