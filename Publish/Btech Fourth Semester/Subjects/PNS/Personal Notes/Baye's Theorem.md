---
Title: Baye's Theorem
Status: 
marker:
  - "[[mathematics]]"
  - "[[Probability and Statistics (PNS)]]"
tags: 
Date: 2025.02.03
Time: 09:23
---
# Bayes' Theorem

Bayes' Theorem allows us to calculate conditional probabilities. It relates the conditional probability $P(D_n \mid E)$ (the probability of event $D_n$ occurring given event $E$) to the reverse conditional probability $P(E \mid D_n)$, and it can be expressed as:

$$
P(D_n \mid E) = \frac{P(D_n \cap E)}{P(E)} = P(D_n) \times P(E \mid D_n)
$$

### Explanation:

- $P(D_n \mid E)$ is the probability that event $D_n$ occurs given that event $E$ has occurred.
- $P(D_n \cap E)$ is the joint probability that both events $D_n$ and $E$ occur.
- $P(E)$ is the total probability that event $E$ occurs.
- $P(D_n)$ is the prior probability of event $D_n$.
- $P(E \mid D_n)$ is the likelihood, or the conditional probability of $E$ given $D_n$.

This formula allows us to update our beliefs about the probability of $D_n$ based on the new evidence $E$.

### Extended Form:

If there are multiple events $D_1, D_2, \dots, D_n$, then Bayes' Theorem can be generalized as:

$$
P(D_n \mid E) = \frac{P(D_n) \cdot P(E \mid D_n)}{\sum_{i=1}^{n} P(D_i) \cdot P(E \mid D_i)}
$$

In this case, we consider all possible events $D_1, D_2, \dots, D_n$ and compute the sum of their contributions to the evidence $E$.



# Applications

1. **Medical Diagnosis**: Updates disease probabilities based on test results.
2. **Spam Filtering**: Classifies emails as spam using word frequencies.
3. **Machine Learning**: Used in Naive Bayes classifiers for text classification.
4. **Finance**: Assesses market risks based on new data.
5. **Quality Control**: Predicts product defects from inspection results.
6. **Forensic Science**: Evaluates evidence strength in criminal cases.
7. **Search Engines**: Ranks search results based on relevance.
8. **Weather Forecasting**: Updates predictions with new data.
9. **NLP**: Used in language translation and speech recognition.
10. **Decision Making**: Informs decisions under uncertainty.


> [!Questions Related to Baye's Theorem]
> - [[Basic Probability#Basic Probability]]




# References


###### Information
- date: 2025.02.03
- time: 09:23