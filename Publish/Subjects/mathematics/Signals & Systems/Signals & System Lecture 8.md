---
Title: Signals & System Lecture 8
Status: 
marker: 
tags: 
Date: 2024.08.08
Time: 09:08
---
# Signals & System Lecture 8

# Main note
Refer [[Signals & System Lecture 7]]
## Static v/s Dynamic
### Static
A system where present output depends only present input is called static systems. Also called non memory system.

### Dynamic
A system where present output depends on present input along with other input ( Past and Future ) such system are called Dynamic System.

## Stable v/s Non-stable ( Unstable )
### Stable 
A system which obeys fundamental principle [BIBO](#BIBO) where it states that if we apply bounded input
$$ X(t)~or~x(n)<\infty$$
Then it produces bounded output then such system is said to be stable system

### Non-stable 
A system which does not obey principle [BIBO](#BIBO) where it states that if we apply bounded input.
Then it produces / does not produce a bounded output then such system is said to be unstable system. 

## BIBO
Bounded input produces Bounded output

## Questions

#### Question 1
Check whether the givens system is static or dynamic.

$y(t-1)=x(t-1)+x(t-1).cos(t-1)$

Since all arguments of I/P and O/P terms are identical the system is non memory

#### Question 2
$y(n-1)=x(n-1)+x(n-1).cos(n)$








# References


###### Information
- date: 2024.08.08
- time: 09:08