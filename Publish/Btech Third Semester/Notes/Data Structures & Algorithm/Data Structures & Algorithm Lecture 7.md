---
Title: Data Structures & Algorithm Lecture 7
Status: false
marker: 
tags: 
Date: 2024.08.09
Time: 09:14
---
# Data Structures & Algorithm Lecture 7

# Main note

## Queues
#### Queue in ADT
Imagine a queue. For example the line in the canteen. The person foremost gets accessed first and the new data always comes at the end. This is same logic can be applied to understanding Queue Abstract Data Type.  

Implementation in code.
- We use `f` for the front index of the queue
- We use `r` for the rear index of the queue

##### Functions
- `enqueue(int)` Adds an element to the end
- `dequeue(int)` removes the element at the front of the queue.

#### Types of queues
- Linear Queues: A simple queue add to the end remove from the front.
- Circular Queues: 
- Double Ended Queues:
- Priority Queue:
##### Difference
The difference from stack here is how the operates only on the ends. It adds elements to the end and removes from the end. Here the elements are popped from front and added to the end.


### Functions of queue
#### Checking Size of queue with CPP
```cpp
int queue[max];
/* assume that queue has a class attribute of f and r as stated in implementations of code */
int isEmpty(queue)
{
	if((queue.f==-1) && (queue.r==-1))
	{
		return 1;
	}
	else
	{
		return 0;
	}
}
```

#### Checking size of Queue with CPP
```cpp
int queue[max];
int size(){
	if((queue.f==-1)&&(queue.r==-1))
	{
		return 0;
	}
	else
	{
		int size=r-f;
		return size;
	}
	
}
```

#### Enqueueing element

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
			queue.r++;
		}
		else{
		// Rear end to be incremented to make space in queue
			queue.r++;
		}
	)

}
```

#### Dequeueing Element
```cpp
void dequeue(queue)
{
    if (isEmpty(q))
    {
        cout << "Error: Queue Underflow" << endl;
        return;
    }
    else
    {
	    i
	    if (queue[queue.f]==)
        {
            // Queue becomes empty after this operation
            q.f = -1;
            q.r = -1;
            int dequeuedElement = queue[queue.f];
	        // for returning the front element
	        return dequeuedElement;
        }
        else
        {
	        int dequeuedElement = queue[queue.f]
            q.f++; // Move the front pointer to the next element
        }
    }
}

```

#### FrontQueue
```cpp
int frontq()
{
	if(isEmpty())
	{
		cout<<"Nothing to show here";
		
	}
	else
	{
		return queue[f];
	}

}
```

### Applications of Queues
# References

First Come First Serve
Shortest Program first
Starvation due to waiting
Array Based Queue


### Algorithm for Insertion Operations

##### Enqueue
```pseudo
IF REAR=MAX-1, then;
	Write OVERFLOW
	Goto step4
[END OF IF]

IF FRONT==-1 and REAR==-1, then
	SET FRONT=REAR=0
ELSE
	SET REAR=REAR+1
	END OF IF

SET QUEUE[REAR]=NUM

EXIT
```

#### Dequeue
```pseudo
IF REAR==-1 and FRONT==-1
	Write UNDERFLOW
	Goto Exit
IF(FRONT==REAR)
	SET VAL = QUEUE[FRONT]
	SET FRONT = REAR = -1
ELSE
	SET VAL = QUEUE[FRONT]
	SET FRONT = FRONT + 1
```

### Circular Queue Concept
Contd... 

###### Information
- date: 2024.08.09
- time: 09:14