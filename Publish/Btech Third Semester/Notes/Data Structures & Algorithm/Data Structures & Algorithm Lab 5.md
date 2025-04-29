---
Title: Data Structures & Algorithm Lab 2
Status: 
marker: 
tags: 
Date: 2024.07.27
Time: 12:30
---
# Data Structures & Algorithm Lab 2

# Main Problem

## Problem Statement
Write a Menu driven Program to implement [[Stack ADT]] using array.
### Main Stack Operations

- `void push(int)`: Inserts an element
- `int pop()`: Removes and returns the last inserted element

### Auxiliary Stack Operations

- `int peek()`: Returns the last inserted element without removing it
- `int size()`: Returns the number of elements stored
- `int isEmpty()`: Indicates whether the stack contains elements or not

### Solution
#### Code 1 : The main file that calls the header files
```cpp
// main.cpp

#include "mystack.h"

#include <iostream>

void holdProgram() {

std::cout << "Press Enter to continue...";

std::cin.get();

}

void arrayReversal(int arr[], int size)

{

myStack stck;

for (int i = 0; i < size; i++)

{

// Pushing each element of the array into the stack

std::cout << "Pushing array element ";

std::cout<< i << "::" << arr[i] << std::endl;

stck.push(arr[i]);

std::cout << "Stack Elements now: ";

stck.display();

std::cout << std::endl;

}

for (int i = 0; i < size; i++)

{

std::cout << "Popping Stack element " << i << " :: " << stck.peek() << std::endl;

arr[i] = stck.pop();

std::cout << "Stack Elements now: ";

stck.display();

std::cout << std::endl;

}

}

  

void decimal2Binary(int num)

{

myStack stck;

}

  

int main()

{

int arr[10];

for (int i = 0; i < 10; i++)

{

std::cout << "Enter the element for array element: " << i << std::endl;

std::cin >> arr[i];

}

std::cout << "The given array is now: ";

for (int i = 0; i < 10; i++)

{

std::cout << arr[i] << " ";

}

std::cout << std::endl;

  

arrayReversal(arr, 10);

for (int i = 0; i < 10; i++)

{

std::cout << "Element for array index " << i << ": " << arr[i] << std::endl;

}

holdProgram();

return 0;

}
```
### myStack.cpp the file that contains the source code for header file
```cpp
// myStack.cpp

#include "mystack.h"

#include <iostream>

  

myStack::myStack() : top(-1) { } // Constructor implementation

  

void myStack::menu() {

int choice = 0;

while (choice != 8) {

std::cout << std::endl;

std::cout << std::endl;

std::cout << "Enter 1 to push an element" << std::endl;

std::cout << "Enter 2 to pop an element" << std::endl;

std::cout << "Enter 3 to peek the top element" << std::endl;

std::cout << "Enter 4 to peek at a specific position" << std::endl;

std::cout << "Enter 5 to get the size of the stack" << std::endl;

std::cout << "Enter 6 to check if the stack is empty" << std::endl;

std::cout << "Enter 7 to display the stack" << std::endl;

std::cout << "Enter 8 to exit" << std::endl;

std::cin >> choice;

  

int x;

switch (choice) {

case 1:

std::cout << "Enter the element you want to push:" << std::endl;

std::cin >> x;

push(x);

display();

break;

case 2:

std::cout << pop() << " has been popped" << std::endl;

display();

break;

case 3:

std::cout << "The top element is: " << peek() << std::endl;

break;

case 4:

int pos;

std::cout << "Enter the position you want to peek at:" << std::endl;

std::cin >> pos;

std::cout << "The element at position " << pos << " is " << peek(pos) << std::endl;

break;

case 5:

std::cout << "The size of the stack is " << size() << std::endl;

break;

case 6:

if (isEmpty()) {

std::cout << "The stack is empty" << std::endl;

} else {

std::cout << "The stack is not empty" << std::endl;

}

break;

case 7:

display();

break;

case 8:

std::cout << "Exiting" << std::endl;

break;

default:

std::cout << "Invalid choice" << std::endl;

}

}

}

  

void myStack::display() {

for (int i = 0; i <= top; i++) {

std::cout << arr[i] << " ";

}

}

  

int myStack::pop() {

if (top == -1) {

std::cout << "The stack is empty" << std::endl;

std::cout << "Stack Underflow" << std::endl;

return 0;

} else {

int poppedElement = arr[top];

top--;

return poppedElement;

}

}

  

void myStack::push(int x) {

if (top == MAX - 1) {

std::cout << "The stack is full" << std::endl;

std::cout << "Stack Overflow" << std::endl;

} else {

top++;

arr[top] = x;

}

}

  

int myStack::peek() {

if (top == -1) {

std::cout << "The stack is empty" << std::endl;

std::cout << "Stack Underflow" << std::endl;

return 0;

} else {

return arr[top];

}

}

  

int myStack::peek(int pos) {

if (top == -1) {

std::cout << "The stack is empty" << std::endl;

std::cout << "Stack Underflow" << std::endl;

return 0;

} else {

return arr[pos];

}

}

  

int myStack::size() {

return top + 1;

}

  

bool myStack::isEmpty() {

return top == -1;

}

  

int myStack::getTop(){

return top;

}
```

#### File Stack.h
```cpp
// myStack.h

#ifndef MYSTACK_H

#define MYSTACK_H

  

#define MAX 20

  

class myStack {

private:

int arr[MAX];

int top;

  

public:

myStack(); // Constructor to initialize top

void menu();

void display();

int pop();

void push(int x);

int peek();

int peek(int pos);

int size();

bool isEmpty();

int getTop();

};

  

#endif // MYSTACK_H
```

### Auxiliary Code
```cpp
// main.cpp

#include <iostream>

#include "mystack.h"

  

// Function to reverse an array using myStack

void reverseArray(int arr[], int n) {

myStack stack;

for (int i = 0; i < n; i++) {

stack.push(arr[i]);

}

for (int i = 0; i < n; i++) {

arr[i] = stack.pop();

}

}

  

// Function to convert decimal to binary using myStack

void decimalToBinary(int num) {

myStack stack;

while (num > 0) {

stack.push(num % 2);

num /= 2;

}

while (!stack.isEmpty()) {

std::cout << stack.pop();

}

std::cout << std::endl;

}

  

// Function to check if expression has balanced parentheses using myStack

bool isBalancedParentheses(const std::string& expr) {

myStack stack;

for (char ch : expr) {

if (ch == '(') {

stack.push(ch);

} else if (ch == ')') {

if (stack.isEmpty()) {

return false;

}

stack.pop();

}

}

return stack.isEmpty();

}

  

int main() {

int choice;

do {

std::cout << "Menu:\n";

std::cout << "1. Reverse an array\n";

std::cout << "2. Convert decimal to binary\n";

std::cout << "3. Check balanced parentheses\n";

std::cout << "4. Exit\n";

std::cout << "Enter your choice: ";

std::cin >> choice;

  

switch (choice) {

case 1: {

int n;

std::cout << "Enter the number of elements in the array: ";

std::cin >> n;

int arr[n];

std::cout << "Enter the elements of the array:\n";

for (int i = 0; i < n; i++) {

std::cin >> arr[i];

}

reverseArray(arr, n);

std::cout << "Reversed array: ";

for (int i = 0; i < n; i++) {

std::cout << arr[i] << " ";

}

std::cout << std::endl;

break;

}

case 2: {

int num;

std::cout << "Enter a decimal number: ";

std::cin >> num;

std::cout << "Binary of " << num << " is: ";

decimalToBinary(num);

break;

}

case 3: {

std::string expr;

std::cout << "Enter an expression: ";

std::cin >> expr;

if (isBalancedParentheses(expr)) {

std::cout << "The expression " << expr << " has balanced parentheses." << std::endl;

} else {

std::cout << "The expression " << expr << " does not have balanced parentheses." << std::endl;

}

break;

}

case 4:

std::cout << "Exiting..." << std::endl;

break;

default:

std::cout << "Invalid choice. Please try again." << std::endl;

}

} while (choice != 4);

  

return 0;

}
```


## **Output**
```shell
Enter the element for array element: 0
Enter the element for array element: 1
Enter the element for array element: 2
Enter the element for array element: 3
Enter the element for array element: 4
Enter the element for array element: 5
Enter the element for array element: 6
Enter the element for array element: 7
Enter the element for array element: 8
Enter the element for array element: 9
The given array is now: 1 2 3 4 5 6 7 8 9 9 
Pushing array element 0::1
Stack Elements now: 1 
Pushing array element 1::2
Stack Elements now: 1 2 
Pushing array element 2::3
Stack Elements now: 1 2 3 
Pushing array element 3::4
Stack Elements now: 1 2 3 4 
Pushing array element 4::5
Stack Elements now: 1 2 3 4 5 
Pushing array element 5::6
Stack Elements now: 1 2 3 4 5 6 
Pushing array element 6::7
Stack Elements now: 1 2 3 4 5 6 7 
Pushing array element 7::8
Stack Elements now: 1 2 3 4 5 6 7 8 
Pushing array element 8::9
Stack Elements now: 1 2 3 4 5 6 7 8 9 
Pushing array element 9::9
Stack Elements now: 1 2 3 4 5 6 7 8 9 9 
Popping Stack element 0 :: 9
Stack Elements now: 1 2 3 4 5 6 7 8 9 
Popping Stack element 1 :: 9
Stack Elements now: 1 2 3 4 5 6 7 8 
Popping Stack element 2 :: 8
Stack Elements now: 1 2 3 4 5 6 7 
Popping Stack element 3 :: 7
Stack Elements now: 1 2 3 4 5 6 
Popping Stack element 4 :: 6
Stack Elements now: 1 2 3 4 5 
Popping Stack element 5 :: 5
Stack Elements now: 1 2 3 4 
Popping Stack element 6 :: 4
Stack Elements now: 1 2 3 
Popping Stack element 7 :: 3
Stack Elements now: 1 2 
Popping Stack element 8 :: 2
Stack Elements now: 1 
Popping Stack element 9 :: 1
Stack Elements now: 
Element for array index 0: 9
Element for array index 1: 9
Element for array index 2: 8
Element for array index 3: 7
Element for array index 4: 6
Element for array index 5: 5
Element for array index 6: 4
Element for array index 7: 3
Element for array index 8: 2
Element for array index 9: 1

```

```bash
tj@tj-ROG-Zephyrus-G15-GA503RW:/media/drive1/Productivity/Programming/btech/dsa/lab2$ ./main
Menu:
1. Reverse an array
2. Convert decimal to binary
3. Check balanced parentheses
4. Exit
Enter your choice: 1
Enter the number of elements in the array: 4
Enter the elements of the array:
1
2
3
4
Reversed array: 4 3 2 1 
Menu:
1. Reverse an array
2. Convert decimal to binary
3. Check balanced parentheses
4. Exit
Enter your choice: 2
Enter a decimal number: 20
Binary of 20 is: 10100
Menu:
1. Reverse an array
2. Convert decimal to binary
3. Check balanced parentheses
4. Exit
Enter your choice: 3
Enter an expression: 1+2(2+4(5*2))
The expression 1+2(2+4(5*2)) has balanced parentheses.
Menu:
1. Reverse an array
2. Convert decimal to binary
3. Check balanced parentheses
4. Exit
Enter your choice: 4
Exiting...
```
# References


###### Information
- date: 2024.07.27
- time: 12:30