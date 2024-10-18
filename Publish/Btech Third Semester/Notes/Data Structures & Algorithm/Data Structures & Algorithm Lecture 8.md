---
Title: Data Structures & Algorithm Lecture 8
Status: 
marker: 
tags: 
Date: 2024.08.14
Time: 14:12
---
# Data Structures & Algorithm Lecture 8

# Circular Queue
## **Algorithm**
Deletion is solved 
Important Variables
- Front = 0
- Rear = Max -1
- MAX is the MAXIMUM NUMBER OF ELEMENTS

```pseudocode
STEP 1 
IF(FRONT=0 and REAR=MAX-1) or REAR = FRONT -1 then
	Write "OVERFLOW"
		Goto step 4
		END
STEP 2
SET VAL = QUEUE(FRONT)
IF FRONT = REAR
	FRONT = REAR = -1
	ELSE
IF FRONT = MAX -1
	SET FRONT = 0
ELSE
	SET FRONT = FRONT+1
[END OF IF]

```
Front is = 0 and Rear = Max -1

#### Display Function
```cpp
void display(){
	if(isEmpty()){
		std::cout<<"Q Empty";
		
	}
	for(i=f;i<=r;i++){
		std::cout<<Q[i];
	}
	for(i=f;i<max;i++){
		std::cout<<Q[i];
	}	
}
```

### size function
```cpp
int size(){
	if(isEmpty){
		std::cout<<"No size return value invalid
	}
	else if(f=r){
		return 1;
	}
	else if(f<r){
		return r-f+1;
	}
	else
	{
		return max-f+r+1;
	}

}
```

#### Enqueue Function
Referring from the previous enqueue function
![[Data Structures & Algorithm Lecture 7#Enqueueing element]]
```cpp
void enqueue(queue,element)
{
	if(queue.size()==max)
	{
		//check for overflow 
		return overflowError;
	}
	else(
		if(isEmpty()){
		// If the queue is empty, both front and rear need to be set to 0            (start position)
			queue.f++;
			queue.r=(r+1)%MAX;
		}
		else{
		// Rear end to be incremented to make space in queue
			queue.r++;
		}
	)

}
```
### Dequeue
```
```

# References


###### Information
- date: 2024.08.14
- time: 14:12