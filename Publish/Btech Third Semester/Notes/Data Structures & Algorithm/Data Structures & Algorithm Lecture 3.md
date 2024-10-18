---
Title: Data Structures & Algorithm Lecture 3
Status: 
marker: 
tags: 
Date: 2024.07.24
Time: "{time:HH:mm}}"
---
# Data Structures & Algorithm Lecture 3

## Index
- [Main Note](#main-note)
  - [Stack](#stack)
    - [Main Stack Operation](#main-stack-operation)
    - [Auxiliary Stack Operation](#auxiliary-stack-operation)
    - [Error Conditions](#error-conditions)
    - [IsEmpty Function](#isempty-function)
    - [Size Function](#size-function)
    - [Push Function](#push-function)
    - [Pop Function](#pop-function)
    - [Peek Function](#peek-function)
- [References](#references)
- [Information](#information)

## Main Note

### Stack
We can define a stack of any data type. In lab implementations, we typically use integers. The Stack ADT (Abstract Data Type) is defined with a maximum value called MAX.

#### Main Stack Operation

- **Push**: Inserts a new element.
  - `void push(int newElem)`: Inserts an element `newElem`.
- **Pop**: Removes and returns the last inserted element.
  - `int pop()`: Removes and returns the last inserted element.

#### Auxiliary Stack Operation

- **Peek**: Returns the last inserted element without removing it.
  - `int peek()`: Returns the last inserted element.
- **Size**: Returns the number of elements stored.
  - `int size()`: Returns the number of elements in the stack.
- **IsEmpty**: Indicates if the stack is empty or not.
  - `bool isEmpty()`: Returns `true` if the stack is empty, otherwise `false`.

#### Error Conditions

- **Stack Overflow**: Occurs when there are more elements than the designated amount in the stack.
- **Stack Underflow**: Occurs when there are fewer elements than the given designated MAX amount in the stack.

When a stack is empty, the top index is -1.

#### IsEmpty Function
Returns a boolean value. If the size is 0 or top is -1, then it returns true.

```cpp
bool isEmpty() {
    return top == -1;
}
```

#### Size Function
Returns the value of `top + 1` to check the size of the stack.

```cpp
int size() {
    return top + 1;
}
```

#### Push Function
Checks if there is stack overflow; if not, increments the top value and assigns a new element to `stack[top]`.

```cpp
void push(int num) {
    if (top == MAX - 1) {
        cout << "stack overflow";
    } else {
        stack[++top] = num;
    }
}
```

#### Pop Function
To pop the last element after checking for underflow. If not underflow, deletes the last element and returns it.

```cpp
int pop() {
    if (isEmpty()) {
        cout << "stack underflow";
        return -1; // Indicating error
    } else {
        return stack[top--];
    }
}
```

#### Peek Function
To peek at the last element. First checks if the stack is empty or not.

```cpp
int peek() {
    if (isEmpty()) {
        cout << "stack underflow";
        return -1; // Indicating error
    } else {
        return stack[top];
    }
}
```

#### IsEmpty
Checks if the top variable is -1 to check if the stack is empty or not.

```cpp
bool isEmpty() {
    return top == -1;
}
```

## References
- [Stack Data Structure - GeeksforGeeks](https://www.geeksforgeeks.org/stack-data-structure/)
- [Stack (abstract data type) - Wikipedia](https://en.wikipedia.org/wiki/Stack_(abstract_data_type))

## Information
- Date: 2024.07.24
- Time: 14:06