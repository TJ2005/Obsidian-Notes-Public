---
Title: Introduction to Cryptography Lecture 5
Status: true
marker: 
tags: 
Date: 2025.01.18
Time: 11:11
---
---
## **Transposition Ciphers**

- **Definition:** A transposition cipher rearranges the characters in the plaintext to form the ciphertext.

### **Rail Fence Cipher**

It's a keyless cipher.

1. **Process:**
    - Write the plaintext in two rows, alternating characters row by row.
    - Read the ciphertext row-wise (across).
2. **Illustration:**
    
    1. ![[IMG-20250730000529051.png]]
    
    - Plaintext: **HELLO WORLD**
        
    - Write it as:
        
        ```
        H L O O L
        E L W R D
        ```
        
    - Ciphertext: **HLOOL ELWRD**
        

```python
def rail_fence_cipher(plaintext):
    # Removing spaces from plaintext
    plaintext = plaintext.replace(" ", "")
    
    # Writing plaintext in two rows
    row1 = []
    row2 = []
    
    for i in range(len(plaintext)):
        if i % 2 == 0:
            row1.append(plaintext[i])
        else:
            row2.append(plaintext[i])
    
    # Reading ciphertext row-wise
    ciphertext = ''.join(row1) + ''.join(row2)
    return ciphertext

# Test
plaintext = "HELLO WORLD"
ciphertext = rail_fence_cipher(plaintext)
print("Rail Fence Cipher:", ciphertext)
```

#### **Key Points:**

- The order of characters is altered but their identity remains unchanged.
- It is a **permutation cipher**, not a substitution cipher.

---

### **Row Change Transposition Cipher**

- **Definition:** In a row change transposition cipher, the plaintext is written in rows of fixed length, and the order of the rows is rearranged according to a key to form the ciphertext.

#### **Steps to Perform:**

1. Write the plaintext in rows of equal length.
2. Rearrange the rows based on a predetermined key (key specifies the order of rows).
3. Read the rows in the new order to form the ciphertext.

#### **Example:**

- **Plaintext:** ATTACK AT DAWN
    
- Arrange in rows:
    
    ```
    Row 1: ATTAC
    Row 2: KATDA
    Row 3: WNXXX (fill with dummy characters "X")
    ```
    
- **Key:** 3, 1, 2 (Rearrange rows in this order)
    
- New arrangement:
    
    ```
    Row 3: WNXXX
    Row 1: ATTAC
    Row 2: KATDA
    ```
    
- **Ciphertext:** WNXXXATTACKATDA
    

#### **Key Points:**

- The rows are **reordered**, and dummy characters are added to fill the last row if needed.
- The key determines the order of rows and must be known for decryption.

---

## **Column Change Transposition Cipher**

- **Definition:** In a column change transposition cipher, the plaintext is written in a grid of fixed column width, and the order of the columns is rearranged according to a key to form the ciphertext.

#### **Steps to Perform:**

1. Write the plaintext in a grid with a fixed number of columns.
2. Rearrange the columns based on a predetermined key (key specifies the order of columns).
3. Read the columns in the new order to form the ciphertext.

#### **Example:**

- **Plaintext:** ATTACK AT DAWN
- Arrange in columns (e.g., 4 columns):
    
    ```
    A T T A  
    C K   A  
    T   D A  
    W N X X  
    ```
    
- **Key:** 3, 1, 4, 2 (Rearrange columns in this order)
- New arrangement:
    
    ```
    T A A T  
    K C A   
      T A D  
    N W X X  
    ```
    
- **Ciphertext:** TKNA CTWW AAXA TDXX

### **Code**

```python
def row_change_transposition(plaintext, key):
    # Fill plaintext into rows of fixed length
    row_length = len(key)
    rows = [plaintext[i:i + row_length] for i in range(0, len(plaintext), row_length)]
    
    # Add padding with "X" if necessary
    while len(rows[-1]) < row_length:
        rows[-1] += 'X'
    
    # Reorder rows based on the key
    ordered_rows = [rows[i - 1] for i in key]
    
    # Join rows to form ciphertext
    ciphertext = ''.join(ordered_rows)
    return ciphertext

# Test
plaintext = "ATTACK AT DAWN"
key = [3, 1, 2]
ciphertext = row_change_transposition(plaintext, key)
print("Row Change Transposition Cipher:", ciphertext)
```

---

### **Row Change Transposition Cipher with Multiple Keys**

- **Definition:** In a multi-key row change transposition cipher, the rows and columns are rearranged using multiple keys, making the cipher more secure by adding complexity.

#### **Steps to Perform:**

1. Write the plaintext in rows of fixed length.
2. Rearrange the **rows** based on **Key 1**.
3. Rearrange the **columns** within the rows based on **Key 2**.
4. Read the rearranged grid row-wise to form the ciphertext.

---

#### **Example:**

- **Plaintext:** ATTACK AT DAWN
    
- Arrange in a grid with dummy characters ("X") to fill:
    
    ```
    A T T A C
    K A T D A
    W N X X X
    ```
    
- **Key 1 (Row Order):** 3, 1, 2 (Reorder rows)
    
    ```
    W N X X X
    A T T A C
    K A T D A
    ```
    
- **Key 2 (Column Order):** 5, 3, 1, 4, 2 (Reorder columns)
    
    ```
    X X W X N
    C T A A T
    A T K D A
    ```
    
- **Ciphertext:** XXWXNCTAATAKTDA
    

---

#### **Key Points:**

- **Key 1** defines the new row order.
- **Key 2** defines the new column order.
- Both keys are needed for encryption and decryption.

---

## **Columnar Transposition Cipher**

#### **Definition:**

A columnar transposition cipher arranges the plaintext into a grid with a fixed number of columns. The columns are then rearranged according to a key, and the ciphertext is obtained by reading the columns in the new order.

---

#### **Steps to Perform:**

1. Choose a key (e.g., a word or number) that determines the order of columns.
2. Write the plaintext row by row in a grid of fixed columns (padding with dummy characters if necessary).
3. Rearrange the columns based on the alphabetical order of the key (or numerical order for number keys).
4. Read the columns in the new order to generate the ciphertext.

---

#### **Example:**

- **Plaintext:** "DEFEND THE EAST WALL"
- **Key:** WORD (Assign numbers based on alphabetical order: W = 4, O = 3, R = 2, D = 1)
- Arrange the plaintext in a grid (pad with "X" if necessary):
    
    ```
    D E F E N
    D T H E A
    S T W A L
    L X X X X
    ```
    
- **Key Order:** 1 (D), 2 (R), 3 (O), 4 (W)  
    Rearrange the columns based on this order:
    
    ```
    Column 1: D D S L
    Column 2: E T T X
    Column 3: F H W X
    Column 4: E A A X
    ```
    
- Read columns in the new order: **Ciphertext:** DDSLETHTXFWXAAAX

---

```python
def columnar_transposition(plaintext, key):
    # Write plaintext in a grid
    num_columns = len(key)
    rows = [plaintext[i:i + num_columns] for i in range(0, len(plaintext), num_columns)]
    
    # Add padding with "X" if necessary
    while len(rows[-1]) < num_columns:
        rows[-1] += 'X'
    
    # Order the columns based on the key (alphabetical/numerical order)
    key_order = sorted(range(len(key)), key=lambda x: key[x])
    
    # Reorder columns
    grid = list(zip(*rows))  # Transpose rows to columns
    ordered_grid = [grid[i] for i in key_order]
    
    # Transpose back to rows and read the grid row-wise to get ciphertext
    ciphertext = ''.join([''.join(row) for row in zip(*ordered_grid)])
    return ciphertext

# Test
plaintext = "DEFEND THE EAST WALL"
key = "WORD"
ciphertext = columnar_transposition(plaintext, key)
print("Columnar Transposition Cipher:", ciphertext)
```

#### **Key Points:**

- **Key Length:** Determines the number of columns.
- Dummy characters are added to fill incomplete rows.
- Decryption requires the exact key to reorder columns back to their original positions.

---

This method is simple but effective, especially when combined with multiple encryption layers.

Continued to [[Stream and Block Cipher]]