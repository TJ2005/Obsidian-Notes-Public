---
Title: Types of Learning
Status: true
marker:
  - "[[Artificial Intelligence Index]]"
tags:
Date: 2025.07.29
Time: 10:29
---
# Types of Learning
Long story short there are three types.
- **Supervised Learning**
	- **Labeled Data**: We already know what is the classification of a data.
	- **Direct Feedback:** Since we already know the classification we can constantly check if the guesses are wrong / right.
		- We constantly make adjustment based on the correctness of the model.
	- **[[#Predicting Future with Supervised Learning|Predict Outcome/Future]]:** Once the model is completely trained it can predict outcomes/future for new Un-Labeled Data based on the patterns from learned Data.
- **Unsupervised Learning**
	- **No Labels/Targets**
	- **No Feedback:** Due to absence of label the model cannot directly evaluate if its output is right or wrong.
	- **Find Hidden Structures in Data:** Used to find Association, Clusters, Dimensionality Reduction between two unique instances.
- **Reinforcement Learning**
	- Its kind of like training a dog. Giving it treats when correct movements and nothing when incorrect.
	- Penalties/Reward Based
	- **Decision Process:** Observes the state of environment and decides the correct choice.
	- **Reward System:** Provides a numerical reward after each action. Agent tries to maximize reward
	- **Learn Series of Actions:** Learns how to sequence multiple actions/decisions.

## Predicting Future with Supervised Learning
- Supervised Learning = where the desired outputs already known
- Modeling the relationship between the data inputs and the labels
- Supervised Learning = Labeled Learning
- Regression is another form of Supervised learning where new data
![[IMG-20250918102236697.png|center]]

# A few basic Concepts in Machine Learning

## Supervised Learning
### Classification for class Labels
- **Goal :** to predict the **categorical class** of new instances or data points based on past observations.
- Classification Labels are **Discrete**, **Unordered**.
- Example : Spam Mail Classification
- Identifying categories for each instance of data.
- Graph Shows how we drew a graphical representation of each data point and the line represents where the classification of one category happens.
- When a new instance ? Shows up its position will reveal its classification.
- Need Not be Binary There can be more than two classes.
![[IMG-20250918102236847.png|center]]

## Regression
Used for predicting **continuous outcomes**. 
- **Example** : SAT Scores of students.
	- Relation between **Time Spent** and **Score**
	- We get a plot of graph with a slope
![[IMG-20250918102236963.png| center]]

### Reinforcement Learning
- **Goal :** Develop a system that rewards itself when the model is making correct decisions/ other success flags.
- **Reward Function:** Each State can be given a positive or negative reward.
- Maximizing Reward is the focus.

### Other Methods
- Discovering hidden structures with unsupervised learning
	- Dealing with unlabeled data or unknown structured.
	- Finding Structures with some meaning to understand the data better.
- **Finding Subgroups with Clustering**
	- Clustering is exploratory data analysis or pattern discovery. 
	- We basically put information into meaningful subgroups.
	- We mostly can do this with 0 information about the group membership to begin with.
	- The similar grouped items have some kind of similarity.
![[IMG-20250918102237038.png|center]]

# References


###### Information
- date: 2025.07.29
- time: 10:29