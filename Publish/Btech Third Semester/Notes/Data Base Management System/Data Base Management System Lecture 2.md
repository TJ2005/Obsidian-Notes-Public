---
Title: Data Base Management System Lecture 2
Status: 
marker: 
tags: 
Date: 2024.07.24
Time: 15:00
---
# Data Base Management System Lecture 2

# Main note

## Looking back
Weak entity 
Strong entity
Whenever there is a strong entity in the DB we create an entity.

## Converting Strong Entity TYpes

- Each [[Entity type]] becomes a [[table]].
- We Underline the [[primary key]].
- each single valued attribute becomes a column
- Derived Attributes are ignored
- [[Composite attributes]] are represented by components.
- [[Multi Valued attributes]] are represented by a separate table.
- The [[key attribute]] of the entity becomes the primary key of the table.

![[Data Base Table1.excalidraw]]
Here we have multiple variables. 
- other entities with multiple attributes have their own table.

## Converting Weak Entity
##### Definition
The weak entities only exist if the [[strong entity]] related to it exists.
##### Relevance
If the [[strong entity]] is deleted then the [[weak entity]] related to it will get destroyed as well.
![[Dependancy.excalidraw]]

## Converting Relationships

### Binary 1:1
![[Conversion 1isto1.excalidraw]]
### Binary 1:N
![[1istoN.excalidraw]]

### Binary M:N

### Self Refencing 1:1
### Self Referencing M:N

 
# References


###### Information
- date:: 2024.07.24
- time:: 15:0615:0615:06