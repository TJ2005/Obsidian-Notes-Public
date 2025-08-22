---
Title: Management Accounting for Engineers Lecture 3
Status: 
marker: 
tags: 
Date: 2025.01.28
Time: 10:10
---
# M1 Question Paper Pattern

## Management Accounting (MA)

### 1. **Need of Management Accounting**
   - Management accounting provides critical financial and non-financial information to managers for decision-making, planning, and control.
   - It helps in optimizing resources, improving efficiency, and achieving organizational goals.

### 2. **Importance of MA for Engineering**
   - Engineers often deal with project costing, budgeting, and resource allocation.
   - Management accounting helps engineers make informed decisions by providing cost analysis, profitability reports, and performance metrics.

### 3. **Branches of Accounting**
   - **Financial Accounting:** Focuses on recording and reporting financial transactions for external stakeholders.
   - **Cost Accounting:** Deals with the calculation and control of costs.
   - **Management Accounting:** Provides internal information for managerial decision-making.
   - **Users of Financial Information:** Investors, creditors, management, government, and employees.

### 4. **Limitations of Financial Accounting**
   - Historical in nature; does not provide future-oriented insights.
   - Lacks detailed cost analysis for decision-making.
   - Does not account for non-financial factors like employee morale or market trends.

### 5. **Importance of Management Accounting**
   - Facilitates strategic planning and goal setting.
   - Helps in performance evaluation and control.
   - Provides tools for budgeting, forecasting, and variance analysis.

### 6. **Cost Accounting**
   - **Definition:** A branch of accounting that focuses on capturing, analyzing, and controlling costs.
   - **Distinguish between Cost Accounting and Financial Accounting:**
     - **Purpose:** Cost accounting is for internal use, while financial accounting is for external reporting.
     - **Focus:** Cost accounting focuses on cost control, whereas financial accounting focuses on profitability and financial position.
   - **Items Excluded in Cost Accounting:**
     - Non-operational incomes (e.g., interest earned).
     - Capital expenditures (e.g., purchase of fixed assets).
   - **Advantages of Cost Accounting:**
     - Helps in cost reduction and control.
     - Aids in pricing decisions.
     - Improves profitability and efficiency.
   - **Essentials of a Good Cost Accounting System:**
     - Accuracy in cost allocation.
     - Timely reporting.
     - Flexibility to adapt to changes.
     - Integration with other accounting systems.

### 7. **Cost Classification**
   - **By Nature:** Material, Labor, and Expenses.
   - **By Function:** Production, Administration, Selling, and Distribution.
   - **By Behavior:** Fixed, Variable, and Semi-variable.
   - **By Relevance:** Relevant and Irrelevant Costs.

---

## Inventory Management

### 1. **Inventory as an Asset**
   - Inventory is often the largest asset for manufacturing and trading businesses.
   - Proper inventory management ensures smooth operations and customer satisfaction.

### 2. **Challenges of Holding Inventory**
   - **Inventory Insurance:** Cost of insuring inventory against damage or theft.
   - **Pilferage:** Loss of inventory due to theft or mismanagement.
   - **Storage Costs:** Expenses related to warehousing and handling.
   - **Obsolescence:** Risk of inventory becoming outdated or unsellable.

### 3. **Types of Costs in Inventory Management**
   - **Holding Costs:** Costs associated with storing inventory (e.g., rent, insurance, utilities).
   - **Ordering Costs:** Costs incurred when placing orders (e.g., administrative expenses, shipping).
   - **Shortage Costs:** Costs arising from stockouts (e.g., lost sales, customer dissatisfaction).

### 4. **Inventory Purchase Strategy**
   - **Bulk Purchasing:**
     - Buying more inventory at once can lead to discounts and lower per-unit costs.
     - However, it increases holding costs and risks of obsolescence.
   - **Just-in-Time (JIT):**
     - Minimizes inventory levels by ordering only when needed.
     - Reduces holding costs but requires reliable suppliers.

### 5. **Economic Order Quantity (EOQ)**
   - **Definition:** EOQ is the optimal order quantity that minimizes total inventory costs, including holding and ordering costs.
   - **Formula:**
     $$
     EOQ = \sqrt{\frac{2 \times A \times B}{C}}
     $$
     Where:
     - \( A \) = Annual demand
     - \( B \) = Ordering cost per order
     - \( C \) = Carrying cost per unit per year
   - **Explanation:**
     - The EOQ formula balances the cost of ordering inventory (e.g., administrative and shipping costs) with the cost of holding inventory (e.g., storage and insurance costs).
     - It helps businesses determine the most cost-effective quantity to order at a time.

---
Got it! I will now use **inline LaTeX** formulas within `$` for inline math expressions and **block-level LaTeX** within `$$` for centered or block-level math in markdown, as per your instructions for Obsidian. Here's the updated solution for the illustrations:

---

### **Illustration 4**

#### Given:
- Annual Demand ($A$) = 2,000 units  
- Storage Cost = 2% p.a.  
- Interest Rate = 8% p.a.  
- Unit Price ($P$) = Rs. 20  
- Ordering Cost per Order ($B$) = Rs. 20  

#### Step 1: Calculate Carrying Cost ($C$)
Carrying cost is the sum of storage cost and interest cost:
$$
C = (\text{Storage Cost} + \text{Interest Rate}) \times P
$$
$$
C = (2\% + 8\%) \times 20 = 10\% \times 20 = Rs. 2 \text{ per unit per year}
$$

#### Step 2: Calculate EOQ
Using the EOQ formula:
$$
EOQ = \sqrt{\frac{2 \times A \times B}{C}}
$$
$$
EOQ = \sqrt{\frac{2 \times 2000 \times 20}{2}} = \sqrt{\frac{80000}{2}} = \sqrt{40000} = 200 \text{ units}
$$

#### Step 3: Calculate Total Annual Inventory Cost
Total Annual Inventory Cost = Ordering Cost + Carrying Cost  
$$
\text{Ordering Cost} = \frac{A}{EOQ} \times B = \frac{2000}{200} \times 20 = 10 \times 20 = Rs. 200
$$
$$
\text{Carrying Cost} = \frac{EOQ}{2} \times C = \frac{200}{2} \times 2 = 100 \times 2 = Rs. 200
$$
$$
\text{Total Annual Inventory Cost} = 200 + 200 = Rs. 400
$$

---

### **Illustration 5**

#### Given:
- Annual Demand ($A$) = 45,000 sets  
- Unit Price ($P$) = Rs. 40  
- Annual Cost of Investment in Inventory = 10%  
- Other Holding Cost = Rs. 1 per unit per year  
- Ordering Cost ($B$) = Rs. 5  

#### Step 1: Calculate Carrying Cost ($C$)
Carrying cost is the sum of investment cost and other holding costs:
$$
C = (\text{Investment Cost} \times P) + \text{Other Holding Cost}
$$
$$
C = (10\% \times 40) + 1 = 4 + 1 = Rs. 5 \text{ per unit per year}
$$

#### Step 2: Calculate EOQ
Using the EOQ formula:
$$
EOQ = \sqrt{\frac{2 \times A \times B}{C}}
$$
$$
EOQ = \sqrt{\frac{2 \times 45000 \times 5}{5}} = \sqrt{\frac{450000}{5}} = \sqrt{90000} = 300 \text{ units}
$$

#### Step 3: Calculate Number of Orders
$$
\text{Number of Orders} = \frac{A}{EOQ} = \frac{45000}{300} = 150 \text{ orders}
$$

---

### **Illustration 6**

#### Given:
- Annual Demand ($A$) = 1,000 units  
- Unit Price ($P$) = Rs. 10  
- Interest on Locked-up Capital = 20%  
- Pilferage = 5%  
- Other Holding Cost = 15%  
- Order Processing Cost = Rs. 100  
- Inspection Cost = Rs. 50  
- Follow-up Cost = Rs. 80  
- Other Procurement Cost = Rs. 170  

#### Step 1: Calculate Carrying Cost ($C$)
Carrying cost is the sum of interest, pilferage, and other holding costs:
$$
C = (\text{Interest} + \text{Pilferage} + \text{Other Holding Cost}) \times P
$$
$$
C = (20\% + 5\% + 15\%) \times 10 = 40\% \times 10 = Rs. 4 \text{ per unit per year}
$$

#### Step 2: Calculate Total Ordering Cost ($B$)
Total ordering cost is the sum of all ordering-related costs:
$$
B = \text{Order Processing Cost} + \text{Inspection Cost} + \text{Follow-up Cost} + \text{Other Procurement Cost}
$$
$$
B = 100 + 50 + 80 + 170 = Rs. 400
$$

#### Step 3: Calculate EOQ
Using the EOQ formula:
$$
EOQ = \sqrt{\frac{2 \times A \times B}{C}}
$$
$$
EOQ = \sqrt{\frac{2 \times 1000 \times 400}{4}} = \sqrt{\frac{800000}{4}} = \sqrt{200000} = 447.21 \approx 447 \text{ units}
$$

---

### **Illustration 7**

#### Given:
- Annual Demand ($A$) = 8,000 units  
- Ordering Cost ($B$) = Rs. 200 per order  
- Unit Price ($P$) = Rs. 400  
- Carrying Cost ($C$) = 20% p.a.  
- Quantity Discount = 4% if order size is 4,000 units  

#### Step 1: Calculate EOQ Without Discount
Using the EOQ formula:
$$
EOQ = \sqrt{\frac{2 \times A \times B}{C}}
$$
$$
C = 20\% \times 400 = Rs. 80 \text{ per unit per year}
$$
$$
EOQ = \sqrt{\frac{2 \times 8000 \times 200}{80}} = \sqrt{\frac{3200000}{80}} = \sqrt{40000} = 200 \text{ units}
$$

#### Step 2: Evaluate Quantity Discount Offer
- **Total Cost Without Discount:**
  $$
  \text{Ordering Cost} = \frac{A}{EOQ} \times B = \frac{8000}{200} \times 200 = 40 \times 200 = Rs. 8000
  $$
  $$
  \text{Carrying Cost} = \frac{EOQ}{2} \times C = \frac{200}{2} \times 80 = 100 \times 80 = Rs. 8000
  $$
  $$
  \text{Total Cost} = 8000 + 8000 = Rs. 16000
  $$

- **Total Cost With Discount:**
  - Discounted Price = $400 - (4\% \times 400) = 400 - 16 = Rs. 384$  
  - New Carrying Cost ($C'$) = 20% of 384 = Rs. 76.8  
  - Order Size = 4,000 units  
  $$
  \text{Ordering Cost} = \frac{8000}{4000} \times 200 = 2 \times 200 = Rs. 400
  $$
  $$
  \text{Carrying Cost} = \frac{4000}{2} \times 76.8 = 2000 \times 76.8 = Rs. 153600
  $$
  $$
  \text{Total Cost} = 400 + 153600 = Rs. 154000
  $$

#### Step 3: Decision
- The total cost without the discount is **Rs. 16,000**, while the total cost with the discount is **Rs. 154,000**.  
- Since the total cost with the discount is significantly higher, the **quantity discount offer should not be accepted**.

---

Let me know if you need further clarification!
## References
- **Date:** 2025.01.28
- **Time:** 10:10