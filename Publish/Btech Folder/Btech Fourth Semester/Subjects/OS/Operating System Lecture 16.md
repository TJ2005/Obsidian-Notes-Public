---
Title: "Operating System Lecture 13"
Status: 
marker: 
tags: 
Date: "2025.02.22"
Time: "12:22"
---
# Dining Philosophers Problem
The set up is a round table where there is rice on the centre of the table. There are philosophers seating at the table in a circle. 
There are objects called
- **Chopsticks** : Resources
- **Philosopher :** Processes

The philosophers have two states Eating, Think state. 
- Eating State : Need Two chop sticks to eat
- Think State : Thinking state if resources are not available.

If you think about it if one philosopher is in a eating state then the neighbouring two will have a missing chop sticks to eat thus entering a forceful thinking state.
But the one that is two chairs away can also enter the eating state. The philosopher can only pick one chopstick at a time. 

When a philosopher picks a chopstick a `wait()` signal is sent to immediate neighbours and when they release it `Signal()` is sent.

![[IMG-20250730000528848.png|center]]

```js
do{
	wait(chopstick[i]);
	wait(chopstick[i+1]%5);
	// eat

	signal(chopstick[i]);
	signal(chopstick[i+1]%5);
	// thinking
}while(True);
```

## Deadlock Handling
- Allow at most 4 philosophers to be sitting simultaneously at the table.
- Allow a philosopher to pick up the forks only if both are available. That is in a [[Operating System Lecture 11#Critical Section|Critical Section]]
- Use an asymmetric solution. 
	- An odd numbered philosopher picks up first the left chopstick and then the right chopstick or even.

# Monitors
High level abstraction that provides a convenient and effective mechanism for process synchronization.

In the diagram the the initialization code can have values like `wrt=1` or `0` depending on the needs or `mutex = 1` or `0` from the value. 
![[IMG-20250730000545654.png|center|300]]
```java
monitor DiningPhillosphers
{
	enum{ THINKING; HUNGRY; EATING}
}
```
# References


###### Information
- date: 2025.02.22
- time: 12:22