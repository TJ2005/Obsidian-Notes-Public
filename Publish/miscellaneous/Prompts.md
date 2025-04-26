---
Title: Prompts
Status: 
marker: 
tags: 
Date: 2024.08.09
Time: 23:32
---
The source of the notes is giveen further below in the message 
u are a note writer in obsidian 
You will use mathjax markdown tables Links to relate common stuff and include a 


in all the notes 


These are the related notes for context if u ever feel like linking them

No need to do \# to link titles btw

#### Unit 1 Introduction
- [[Introduction, Security goals (CIA triad)]]
- [[Goals of cryptography, principles of modern cryptography]]
- [[Perfectly secret encryption, one time pad and Shannon’s theorem]]
- [[Cryptographic applications]]
Start writing notes for unit 2 seperate
#### Unit 2 Classic CryptoSystems
- [[Shift Ciphers, Affine Ciphers]]
- Polyalphabetical Cipher
	- [[The Vigenere Cipher, Playfair Ciphers]]
- [[Substitution Ciphers, Transposition Ciphers]]
- [[Stream and block ciphers, Cryptanalysis]]

# Prompts
# Latex

---

**MathJax LaTeX Formatting Guide:**

### **Inline LaTeX:**

- **Always use a single `$`** to start and end inline LaTeX, **without any spaces** between the delimiters and the content.
- **This is crucial** for proper rendering in MathJax.

For example:

```markdown
$x^2 + y^2 = z^2$
```

Make sure to **never** include spaces between the `$` symbols and the content.

---

### **Centered or Block-level LaTeX:**

- For block-level LaTeX, **use `$$`** to enclose the LaTeX code, placed on its own line.
- **Include a newline** before and after the `$$` delimiters to ensure proper formatting.

Example:

```markdown
$$
\text{Latex content here}
$$
```

Notice how block-level LaTeX starts and ends with a newline for proper rendering.

---

### **What to Avoid:**

- **Never** use `\(`, `\)`, `\[`, or `\]` for LaTeX in MathJax.
    
- These are not compatible and may cause rendering issues.
    
- Always use:
    
    - `$` for **inline** LaTeX
    - `$$` for **block** or **centered** LaTeX

---

### **Tables with LaTeX Content:**

When including LaTeX in tables, follow this format:

```markdown
| $Column1$         | $Column2$       | $Column3$       |
|-------------------|-----------------|-----------------|
| $Cell1_1$         | $Cell1_2$       | $Cell1_3$       |
| $Cell2_1$         | $Cell2_2$       | $Cell2_3$       |
```

---


# Latex Prefix

---

**MathJax LaTeX Formatting Guide:**

For **inline LaTeX**, always start and end with `$` without any spaces between the delimiters and the content. For example:

```markdown
$x^2 + y^2 = z^2$
```

For **centered or block-level LaTeX**, use `$$` with the LaTeX code placed on its own line. Make sure to include a newline before and after the `$$` delimiters:

```markdown
$$
\text{Latex content here}
$$
```

Notice how the block-level LaTeX starts and ends with a newline. This ensures proper rendering in MathJax.

Do not use `\(`, `\)`, `\[`, or `\]` as these are not compatible with MathJax and can cause rendering issues. Instead, use `$` for inline expressions and `$$` for block or centered expressions.

For **tables with LaTeX content**, the format should be as follows:

```markdown
| $Column1$         | $Column2$       | $Column3$       |
|--------------------|-----------------|-----------------|
| $Cell1_1$         | $Cell1_2$       | $Cell1_3$       |
| $Cell2_1$         | $Cell2_2$       | $Cell2_3$       |
```

---


# Making Index
**Prompt:**
Please create an index for the provided note using the format `[[#Title#Heading#Subheading]]`. In this format:
- `Title` is the main subject of the note.
- `Heading` represents primary sections.
- `Subheading` includes any subsections or detailed points.

In the index:
- Include all titles and subheadings as examples.
- Exclude the "References" and "Information" sections from the index.

**Example:**
Given the following note:

```
# Solar Energy
Solar energy is harnessed from the sun and converted into electricity or heat.

#### Introduction
Solar energy has become a significant topic in renewable energy sources due to its sustainability and environmental benefits.

#### Types of Solar Energy Systems
There are several types of solar energy systems:
- **Photovoltaic Systems**: Convert sunlight directly into electricity.
- **Solar Thermal Systems**: Use sunlight to heat fluids, which then produce steam to drive a turbine.

#### Benefits of Solar Energy
- **Environmental Impact**: Reduces greenhouse gas emissions.
- **Cost Savings**: Decreases electricity bills over time.

#### Challenges and Considerations
- **Initial Costs**: High upfront costs for installation.
- **Weather Dependency**: Efficiency can be affected by weather conditions.

---

# References


###### Information
- date: 2024.08.06
- time: 18:00
```

**The index should be:**

- [Solar Energy](#solar-energy)
  - [Introduction](#introduction)
  - [Types of Solar Energy Systems](#types-of-solar-energy-systems)
    - [Photovoltaic Systems](#photovoltaic-systems)
    - [Solar Thermal Systems](#solar-thermal-systems)
  - [Benefits of Solar Energy](#benefits-of-solar-energy)
  - [Challenges and Considerations](#challenges-and-considerations)

Use this format to create the index for your note, including all titles and subheadings.

### Making Index for Cross embed
---

**Prompt:**

Please format the provided text by creating headings and subheadings in the style `[[#Title#Heading#Subheading]]`. Each section or subsection should be converted into this format. 

For instance, given a text that includes:

```
# topic

This section introduces the topic and its relevance.

#### Overview
Here we discuss the general aspects of the topic.

#### Details
This section provides a deeper dive into the specifics.

#### Examples
Examples illustrating key points are included here.

#### Additional Information
Any supplementary details or references related to the topic.
```

Please format it as:

```
![[topic#topic#Introduction]]
![[topic#topic#Overview]]
![[topic#topic#Details]]
![[topic#topic#Examples]]
![[topic#topic#Additional Information]]
```

The `Title` should be the main title or subject of the document, the `Heading` should be the primary sections, and the `Subheading` should reflect any subsections or detailed points under each heading.

# Latex
For Obsidian 
always inline latex starts with $and ends with $ do not add space between Dont use ` or dont use \[ or \] as well
Similarly for centered latex use $$Latex$$


Please use inline LaTeX formulas within `$` for inline math expressions and `$$` for centered or block-level math in markdown when writing for Obsidian.

Please use inline LaTeX formulas within `$` for inline math expressions and `$$` for centered or block-level math in markdown when writing for Obsidian. Avoid using `\(`, `\)`, `\[`, or `\]` for math expressions, as these can cause issues with rendering in Obsidian by being treated as simple brackets rather than LaTeX delimiters. This results in improper display or ignored content. Using `$` for inline math and `$$` for block math ensures correct rendering in Obsidian.

# Latex 2
Always use **inline LaTeX** for Obsidian with `$` to start and end inline math expressions, ensuring no spaces between the delimiters and the content (e.g., `$x^2 + y^2 = z^2$`). For block or centered math expressions, enclose them in `$$` (e.g., `$$E=mc^2$$`). Do not use `\(`, `\)`, `\[`, or `\]` under any circumstances, as these will not render properly in Obsidian.

For **tables with LaTeX content**, use the following strict format:

- Each cell must have LaTeX content enclosed in `$`.
- Use markdown table syntax with `|` to separate columns and `---` for the header separator row.

**Example:**

```
| $Column1$         | $Column2$       | $Column3$       |
|--------------------|-----------------|-----------------|
| $Cell1_1$         | $Cell1_2$       | $Cell1_3$       |
| $Cell2_1$         | $Cell2_2$       | $Cell2_3$       |
```

Strictly adhere to this structure for inline, block-level, and tabular LaTeX content in Obsidian.


Here’s a refined and structured prompt for your Python script request:

---

**Python Script for Automated Transaction Classification in Excel**

### **Objective:**

Develop a **self-learning Python program** that classifies bank transactions from an **Excel file** based on **Narration/Chq. Ref. No.** and maintains a **local database (JSON file)** to remember previous classifications.

### **Classification Rules:**

#### **1. Income Sources:**

- **Salary**
- **Mom (Family Transfers)**
- **Unclassified (Default for unknown sources)**

#### **2. Expenses:**

- **Investment**
- **Food**

#### **3. Purchases:**

- **General Purchases**
    - **Food Purchases**
    - **Travel Purchases**
    - **Clothes Purchases**
    - **Miscellaneous:**
        - **Stationery**
        - **Heap (for unclassified items)**

### **Functionality Requirements:**

1. **Read transactions from an Excel sheet** containing:
    
    - `Date`
    - `Narration Chq./Ref.No.`
    - `Value Dt`
    - `Withdrawal Amt.`
    - `Deposit Amt.`
    - `Closing Balance`
2. **Classify transactions based on Narration/Chq. Ref. No.**
    
    - If the **narration already exists** in the JSON database, use its **previous classification**.
    - If the **narration is new**, prompt the user to **assign a category**.
3. **Store & Load Transactions from JSON:**
    
    - Maintain a **local JSON file** to remember the classifications.
    - When the program runs again, it should **load existing classifications** before processing new transactions.
4. **Handle Unclassified Transactions:**
    
    - If the same **narration appears multiple times** but with different **classification possibilities**, ask the user to **manually categorize it**.
    - Provide an **option to reclassify** transactions if needed.
5. **Output the classified transactions** in an updated **Excel file**.
    

---

Would you like any additional features, such as **summary reports**, **graphical analysis**, or **automated folder organization** for categorized transactions?

# References


###### Information
- date: 2024.08.09
- time: 23:32