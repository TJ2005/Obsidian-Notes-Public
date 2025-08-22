---
Title: Computer Organization and Architecture Lecture 8
Status: 
marker: 
tags: 
Date: 2025.01.23
Time: 09:18
---
Continued from [[Computer Organization and Architecture Lecture 7]]
# Flow of execution
The image depicts a flowchart explaining the instruction fetch and decode cycles in a computer system, likely as part of a lecture slide. Here's a breakdown of the content:

1. **Fetch Cycle:**
    - **T0:** `MAR ← PC`
        - The Memory Address Register (MAR) is loaded with the contents of the Program Counter (PC), which holds the address of the next instruction to be fetched.
    - **T1:** `IR ← M[MAR], PC ← PC + 1`
        - The Instruction Register (IR) receives the instruction stored at the memory location indicated by MAR. Simultaneously, the PC is incremented to point to the next instruction.
2. **Decode Cycle:**
    - **T2:**
        - `MAR ← IR[0-11]` (Extracting address bits from instruction)
        - `D7...D0 ← IR[12-14]` (Decoding the operation)
        - `I ← IR[15]` (Checking the addressing mode)
3. **Decision Making:**
    - A decision diamond follows, indicating a check for input/output (I/O) reference or memory reference.
    - Depending on the value of the decoded instruction, the control flow diverges based on whether it's a memory reference instruction (`1`) or not (`0`).

![[Computer Organization and Architecture Lecture 7#Architecture and Organization in the Context of Fetch and Decode Cycles]]

```mermaid
flowchart TD
    T0[Start] --> T1[MAR ← PC]
    T1 --> T2[IR ← M[MAR], PC ← PC + 1]
    T2 --> T3[MAR ← IR[0-11]]
    T3 --> T4[D7...D0 ← IR[12-14]]
    T4 --> T5[I ← IR[15]]
    T5 --> Decision{Is it a memory reference?}
    Decision -->|Yes| Mem[Memory Reference]
    Decision -->|No| NonMem[Non-Memory Reference]
    
    style T0 fill:#ffcccc
    style T1 fill:#ffcccc
    style T2 fill:#ffcccc
    style T3 fill:#ffcccc
    style T4 fill:#ffcccc
    style T5 fill:#ffcccc
    style Decision fill:#ffffcc
    style Mem fill:#ccffcc
    style NonMem fill:#ccffcc
```


# References
Continued to [[Computer Organization and Architecture Lecture 9]]

###### Information
- date: 2025.01.23
- time: 09:18