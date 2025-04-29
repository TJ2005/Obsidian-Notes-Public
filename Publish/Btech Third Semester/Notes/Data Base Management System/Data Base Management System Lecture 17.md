---
Title: Data Base Management System Lecture 13
Status: 
marker:
  - "[[Data Base]]"
  - "[[Acid Properties]]"
  - "[[Transaction]]"
  - "[[Serialization of tasks]]"
tags:
  - BTech
Date: 2024.09.25
Time: 14:59
---
# Transaction

## Transaction Concept
It is a unit of program execution that accesses and possibly updates various data items.
### Example
1.  Read(A)
2. A:=A-50
3. write(A)
4. read(b)
5. b=b+50
6. Write(B)

### Issues
- Failures of various kinds such as hardware failures and system crashes.
- Concurrent Execution of multiple transactions.
---
# Acid Properties
A **transaction** is a unit of program execution that accesses and possibly updates various data items.To preserve the integrity of data the database system must ensure
### Atomicity Requirement
- If the transaction fails after step 3 and before step 6 money will be lost leading to an incosistent database state.
	- Failure can be due to anything like software or hardware
- The system should ensure that updates of a partially executed transaction are not reflected in the database.

### Durability Requirement
once the user has been notified that the transaction has completed (i.e., the transfer of the $50 has taken place), the updates to the database by the transaction must persist even if there are software or hardware failures.
- **Consistency**: The sum of A and B remains unchanged during the transaction execution.
- **General Consistency Requirements**:
  - **Explicit Integrity Constraints**: Primary keys, foreign keys, etc.
  - **Implicit Integrity Constraints**: e.g., the sum of balances of accounts minus loan amounts should equal cash-in-hand.
  
- **Transaction Behavior**:
  - A transaction must start with a consistent database.
  - The database may become **temporarily inconsistent** during execution.
  - After successful completion, the database must return to a **consistent state**.
  - **Erroneous logic** can lead to database inconsistency.

### Consistency Requirement
- The sum of A and Bis unchanged by execution of the transaction
In general the consistency requirements include:

### Isolation Requirement
If between steps 3 and 6 another transaction T2 is allowed to access the partially updated database It will see an inconsistent database.

# Transaction States
There are multiple transaction states they are as follows.
- **Active**: The initial state. the transaction stays in the state till its executed
- **Partially Committed**: After the final statement for the active its partially committed.
- **Failed**: After the discovery that normal execution can no longer proceed.
- **Aborted**: After the transaction has been rolled back and the database restored to its prior state of transaction.
	- After this only we can either 
		- Restart the transaction
			- can be only done if no logical errors
		- Kill the transaction
- **Committed**: After Successful Completion the data is modified

![[Pasted image 20240925151948.png]]

# Concurrent Executions
In a processor there are multiple units such as ALU, Memory Register, Etc. While the process is reading from memory register our ALU is free so we can execute something else there. This is called **Time Sharing**

Multiple transactions are allowed to run concurrently in the system. 
### Advantages 
- **Increased processor** and **disk utilization**, leading to better transaction throughput
	- e.g., one transaction can be using the CPU while another is reading from or writing to the disk
- Reduced average response time for transactions: short transactions need not wait behind long ones.

### Concurrent Control Schemes
mechanisms to achieve isolation That is, to control the interaction among the concurrent transactions in order to prevent them from destroying the consistency of the database.

# Schedules
a sequences of instructions that specify the chronological order in which instructions of concurrent transactions are executed
- A schedule for a set of transactions must consist of all instructions of those transactions
- Must preserve the order in which the instructions appear in each individual transaction.

A transaction that successfully completes its execution will have a commit instructions as the last statement
- By default transaction assumed to execute commit instruction as its last step

A transaction that fails to successfully complete its execution will have an abort instruction as the last statement

# Serializability
# Reference


###### Information
- date: 2024.09.25
- time: 14:59