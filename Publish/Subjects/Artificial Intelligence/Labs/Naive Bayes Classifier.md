---
Title: "Naive Bayes Classifier"
Status: 
marker: 
tags: 
Date: "2025.09.11"
Time: "12:23"
---
# **Naive Bayes Classifier**

* **Why “Naive”?** → It is called *naive* because it assumes that the features are **independent** of each other given the class label.
* **Usefulness** → Popular for **real-world Machine Learning (rML)** tasks.
* **Conditional Probability** → Works on the principle of **Bayes’ theorem**.
* **Assumption** → All attributes are considered **equally independent** in their contribution.
* **Impact** → Each attribute makes its own **independent impact** on the classification.

---

In [[DWM Naive Bayes]] we have worked on **Gaussian Naive Bayes**.

### **Handling Continuous Data**

* When the dataset contains continuous values, we either:
  * Use **Gaussian Naive Bayes** (assumes normal distribution), or
  * **Discretize the values into groups/categories**.

**Example – Salary**

* Convert continuous salary values into **slabs (categories)** such as:
  * Low
  * Medium
  * High


### Types of naive bayes models
- Gaussian Naive Baye
	- Used with normal distribution thus called Gaussian
	- Fitted with the **Mean** and **Standard Deviation**
- MultiNomial Naive Baye
	- **Discrete Data** such as frequency count
- Bernoullis Naive Baye
	- Boolean Attributes


Got it 👍
I’ll write it step-by-step, with **dummy data → table → math → explanation**.

---

## **Steps for Naive Bayes (Continuous → Binned Example)**

### **1. Dummy Dataset**

| Gender | Income | Illness |
| ------ | ------ | ------- |
| Male   | 20,000 | Yes     |
| Male   | 25,000 | Yes     |
| Male   | 50,000 | No      |
| Female | 22,000 | Yes     |
| Female | 45,000 | No      |
| Female | 60,000 | No      |

---

### **2. Binning Continuous Feature**

* Income is continuous → create bins:

  * **Low**: ≤ 25,000
  * **Medium**: 25,001 – 45,000
  * **High**: > 45,000

| Gender | Income | Bin    | Illness |
| ------ | ------ | ------ | ------- |
| Male   | 20,000 | Low    | Yes     |
| Male   | 25,000 | Low    | Yes     |
| Male   | 50,000 | High   | No      |
| Female | 22,000 | Low    | Yes     |
| Female | 45,000 | Medium | No      |
| Female | 60,000 | High   | No      |

---

### **3. Frequency / Likelihood Table**

For **Illness = Yes**:

* Gender: Male → 2, Female → 1
* Income Bin: Low → 3, Medium → 0, High → 0

For **Illness = No**:

* Gender: Male → 1, Female → 2
* Income Bin: Low → 0, Medium → 1, High → 2

---

### **4. Classification Example**

Suppose we want to classify:

$$
X = \{ \text{Gender = Female, Income = High} \}
$$

We calculate:

$$
P(\text{Illness=Yes} \mid X) \propto P(\text{Female}\mid Yes) \cdot P(\text{High}\mid Yes) \cdot P(Yes)
$$

$$
P(\text{Illness=No} \mid X) \propto P(\text{Female}\mid No) \cdot P(\text{High}\mid No) \cdot P(No)
$$

---

### **5. Compute with Dummy Probabilities**

* Prior:

  $$
  P(Yes) = \frac{3}{6}, \quad P(No) = \frac{3}{6}
  $$

* Likelihoods:

  $$
  P(\text{Female} \mid Yes) = \frac{1}{3}, \quad P(\text{High} \mid Yes) = \frac{0}{3} = 0
  $$

  $$
  P(\text{Female} \mid No) = \frac{2}{3}, \quad P(\text{High} \mid No) = \frac{2}{3}
  $$

* Multiply:

$$
P(Yes \mid X) \propto \frac{1}{3} \cdot 0 \cdot \frac{1}{2} = 0
$$

$$
P(No \mid X) \propto \frac{2}{3} \cdot \frac{2}{3} \cdot \frac{1}{2} = \frac{2}{9}
$$

Prediction = **Illness = No**

---

### **6. Role of Likelihood (Continuous Case with Gaussian)**

If instead of bins, we use raw income values:

$$
P(x \mid C_k) = \frac{1}{\sqrt{2\pi\sigma_k^2}} \exp\left( -\frac{(x-\mu_k)^2}{2\sigma_k^2} \right)
$$

* $\mu_k$ = mean income for class $C_k$
* $\sigma_k$ = standard deviation for class $C_k$
* This likelihood tells us how probable it is to see a specific **income value** under each class distribution.

Then we multiply likelihoods across features (Gender, Income, etc.) with the prior to get final classification.

---

In short:

* **Likelihood** measures how well a data point fits within a class.
* **Mean & SD** define the shape of the Gaussian curve for continuous features.
* Classification = Pick the class with the **highest posterior probability**.
```mermaid
flowchart TD

A["Start: Dataset with Features & Class Label"] --> B["Handle Continuous Features"]
B -->| "Option 1: Discretize" | C["Convert into Bins ('Low'/'Medium'/'High')"]
B -->| "Option 2: Gaussian" | D["Compute Mean μ & Std Dev σ for Each 'Class'"]

C --> E["Build Frequency Table for Each 'Class'"]
D --> E["Build Likelihood Function P(x|C)"]

E --> F["Compute Prior Probability P('C')"]
F --> G["Compute Posterior: P('C'|X) ∝ P('C') × ∏ P(xi|'C')"]

G --> H{"Compare Posteriors"}
H -->| "Max Posterior" | I["Final 'Class' Prediction"]

```

Got it. I’ll rewrite the note so all math is in `$$$$ … $$$$` blocks for clarity.

---

# Naive Bayes – Benefits and Disadvantages

## Benefits

1. **No heavy preprocessing**
   Works directly on raw data. For categorical features:

   $$
   P(\text{Male} \mid \text{Illness = Yes}) = \frac{\text{Count(Male and Yes)}}{\text{Count(Yes)}}
   $$

2. **Feature selection not critical**
   Irrelevant features are treated independently and do not strongly affect results.

3. **Single-scan training**
   Only one pass is required to compute frequency tables or mean and variance for continuous data.

   $$
   \mu = \frac{1}{n}\sum_{i=1}^n x_i, \qquad
   \sigma^2 = \frac{1}{n}\sum_{i=1}^n (x_i - \mu)^2
   $$

---

## Disadvantages
1. **Independence assumption**
   Assumes all features are conditionally independent given the class, which is rarely true.
2. **Continuous data handling**
   Requires assuming a distribution, most often Gaussian. If data is not Gaussian-like, probabilities may be inaccurate.
   $$
   P(x \mid C) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left( -\frac{(x-\mu)^2}{2\sigma^2} \right)
   $$
3. **Zero-frequency problem**
   If a feature value does not occur with a class, the probability becomes zero and nullifies the posterior.
   Example:
   $$
   P(X \mid C) = P(\text{Income = High} \mid \text{Yes}) \cdot P(\text{Gender = Female} \mid \text{Yes})
   $$
   If
   $$
   P(\text{Income = High} \mid \text{Yes}) = 0
   $$
   then
   $$
   P(X \mid C) = 0
   $$
   **Solution: Laplace smoothing**
   $$
   P(x_i \mid C) = \frac{\text{count}(x_i, C) + 1}{\text{count}(C) + k}
   $$
   where $k$ is the number of possible feature values.
---
# References


###### Information
- date: 2025.09.11
- time: 12:23