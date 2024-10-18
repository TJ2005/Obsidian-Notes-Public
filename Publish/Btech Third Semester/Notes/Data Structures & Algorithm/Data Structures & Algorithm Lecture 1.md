---
Title: Data Structures & Algorithm Lecture 1
Status: 
marker: 
tags: 
Date: 2024-07-17
Time: 2014-07-17T00:00:00
---
# Data Structures & Algorithm Lecture 1

## Index
- [Intro](#intro)
- [Content](#content)
  - [Data Structures](#data-structures)
  - [Algorithm](#algorithm)
  - [Documentations](#documentations)
- [Clients and Users](#clients-and-users)
  - [Clients](#clients)
  - [Users](#users)
- [Feasibility](#feasibility)
- [Complexity](#complexity)
  - [Time](#time)
  - [Space](#space)
- [Linear Data Structure](#linear-data-structure)
- [Static & Dynamic](#static--dynamic)
  - [Static](#static)
  - [Dynamic](#dynamic)
- [Revise](#revise)
  - [Graphical Representation of Data Structures](#graphical-representation-of-data-structures)
  - [Hashing](#hashing)
  - [Binary Search](#binary-search)
  - [Nodes](#nodes)
- [Stack](#stack)
- [References](#references)

## Intro
- Only Algorithms in theory paper
- Core subject revolves around placements.
- There is not a specific programming language required, i.e., you can choose it.

## Content
### Data Structures
Data structures refer to the ways of organizing and storing data in a computer so that it can be accessed and modified efficiently. Common examples include arrays, linked lists, stacks, queues, trees, and graphs.

### Algorithm
An algorithm is a step-by-step procedure or formula for solving a problem. It is written to provide functionality to a program. Algorithms are often written in pseudocode or represented using flowcharts, DFDs (Data Flow Diagrams) for structured programming, or UML (Unified Modeling Language) diagrams for OOP (Object-Oriented Programming).

- Pseudocode: Industry standard for algorithm representation.
- DFD: Used for structured programming languages.
- UML Diagrams: Used for object-oriented programming.

### Documentations
Documentation is essential in software development to provide clear and comprehensive details about the system, its requirements, design, and usage.

- SRS (Software Requirements Specification): A document that describes what the software will do and how it will be expected to perform.

## Clients and Users
### Clients
Clients are the individuals or organisations who request a specific kind of algorithm or software solution to make their tasks easier.

### Users
Users are the end-users who will use the software or algorithm to manage their data or perform specific tasks.

## Feasibility
Feasibility refers to the analysis and evaluation of a proposed project to determine if it is technically, economically, and operationally viable. It includes:

- **Technical Feasibility:** Can the project be developed with the available technology?
- **Economic Feasibility:** Is the project cost-effective?
- **Operational Feasibility:** Will the project function as intended within the organisation's operations?

## Complexity
Complexity in algorithms refers to the amount of computational resources (time and space) that an algorithm requires to complete its task. It is analysed in terms of worst case, best case, and average case scenarios.

### Time Complexity
Time complexity refers to the amount of time an algorithm takes to complete as a function of the length of the input.

- **Best Case:** The minimum time an algorithm takes to complete. Example: Finding an element in the first position of an array.
- **Worst Case:** The maximum time an algorithm takes to complete. Example: Searching for an element that is not in the array (linear search).
- **Average Case:** The expected time an algorithm takes to complete, considering all possible inputs.

### Space Complexity
Space complexity refers to the amount of memory space an algorithm uses in relation to the input size.

- **Linear Space Complexity:** An algorithm uses space proportional to the input size.
- **Exponential Space Complexity:** An algorithm uses space that grows exponentially with the input size.

## Linear Data Structure
A linear data structure is a type of data structure where elements are arranged in a sequential manner, and each element is connected to its previous and next element.

- Examples: Arrays, Linked Lists, Stacks, Queues.

## Static & Dynamic
### Static
Static data structures have a fixed size, which is defined before runtime. They are efficient in terms of memory but lack flexibility.

- Example: Arrays.

### Dynamic
Dynamic data structures can grow and shrink during runtime, providing more flexibility but may be less efficient in terms of memory usage.

- Example: Linked Lists.

## Revise
### Graphical Representation of Data Structures
Graphical representations, such as trees and graphs, help visualize the relationships and organization of data.

### Hashing
Hashing is a technique used to uniquely identify a specific item from a group of similar items. It involves mapping data to a fixed-size value or key using a hash function.

### Binary Search
Binary search is an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing the search interval in half.

### Nodes
Nodes are fundamental units in data structures like linked lists, trees, and graphs. Each node contains data and references (links) to other nodes.

## Stack
A stack is a linear data structure that follows the Last In, First Out (LIFO) principle.

- **Operations:**
  - **Push:** Adds an element to the top of the stack.
  - **Pop:** Removes the top element from the stack.
  - **Peek/Top:** Returns the top element without removing it.


## References
Lectures, Korth
Continued to [[Data Structures & Algorithm Lecture 2]]....