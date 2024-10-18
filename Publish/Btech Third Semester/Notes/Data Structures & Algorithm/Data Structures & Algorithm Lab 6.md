---
Title: Data Structures & Algorithm Lab 6
Status: 
marker:
  - "[[Lab]]"
  - "[[Algorithm]]"
  - "[[Linked List]]"
tags:
  - BTech
Date: 2024.09.21
Time: 12:39
---
# Data Structures & Algorithm Lab 6
## Header File
```cpp
#ifndef STRUCT_H
#define STRUCT_H
  

#include <iostream>

  

// Define a struct called Node

struct Node {

int data; // Data stored in the node

Node* next; // Pointer to the next node

};

  

// Define a class called LinkedList

class LinkedList {

private:

Node* head; // Pointer to the head of the linked list

  

public:

// Constructor to initialize the head to nullptr

LinkedList() : head(nullptr) {}

  

// Function to create a new node with the given data

Node* createNode(int data) {

Node* node = new Node; // Allocate memory for the new node

node->data = data; // Set the data of the new node

node->next = nullptr; // Set the next pointer to nullptr

return node; // Return the new node

}

  

// Function to display the elements of the linked list

void display() {

if (head == nullptr) { // Check if the list is empty

std::cout << "List is empty." << std::endl;

return;

}

Node* temp = head; // Create a temporary pointer to traverse the list

while (temp != nullptr) {

std::cout << temp->data << " "; // Print the data of the current node

temp = temp->next; // Move to the next node

}

std::cout << std::endl;

}

  

// Function to insert a new node at the head of the linked list

void insertAtHead(int data) {

Node* node = createNode(data); // Create a new node with the given data

node->next = head; // Set the next pointer of the new node to the current head

head = node; // Update the head to point to the new node

}

  

// Function to insert a new node at the tail of the linked list

void insertAtTail(int data) {

Node* node = createNode(data); // Create a new node with the given data

if (head == nullptr) { // Check if the list is empty

head = node; // If empty, set the head to the new node

} else {

Node* temp = head; // Create a temporary pointer to traverse the list

while (temp->next != nullptr) {

temp = temp->next; // Move to the next node

}

temp->next = node; // Set the next pointer of the last node to the new node

}

}

// Function to insert a new node at a given position in the linked list

void insertAtPosition(int data, int position) {

if (position <= 0) { // Check if the position is invalid

std::cout << "Invalid position." << std::endl;

return;

}

if (position == 1) { // If position is 1, insert at the head

insertAtHead(data);

return;

}

Node* node = createNode(data); // Create a new node with the given data

Node* temp = head; // Create a temporary pointer to traverse the list

int currentPosition = 1;

while (temp != nullptr && currentPosition < position - 1) {

temp = temp->next; // Move to the next node

currentPosition++;

}

if (temp == nullptr) { // If position is greater than the size of the list, insert at the end

insertAtTail(data);

} else {

node->next = temp->next; // Set the next pointer of the new node to the next node of temp

temp->next = node; // Set the next pointer of temp to the new node

}

}

  

// Function to delete the first node of the linked list

void deleteAtHead() {

if (head == nullptr) { // Check if the list is empty

std::cout << "List is empty." << std::endl;

return;

}

Node* temp = head; // Create a temporary pointer to store the head

head = head->next; // Update the head to point to the next node

delete temp; // Delete the old head

}

  

// Function to delete the last node of the linked list

void deleteAtTail() {

if (head == nullptr) { // Check if the list is empty

std::cout << "List is empty." << std::endl;

return;

}

if (head->next == nullptr) { // Check if there is only one node in the list

delete head; // Delete the head

head = nullptr; // Set the head to nullptr

return;

}

Node* temp = head; // Create a temporary pointer to traverse the list

while (temp->next->next != nullptr) {

temp = temp->next; // Move to the next node

}

delete temp->next; // Delete the last node

temp->next = nullptr; // Set the next pointer of the second last node to nullptr

}

  

// Function to delete a node with the given data from the linked list

void deleteNode(int data) {

if (head == nullptr) { // Check if the list is empty

std::cout << "List is empty." << std::endl;

return;

}

if (head->data == data) { // Check if the first node contains the data

deleteAtHead();

return;

}

Node* temp = head; // Create a temporary pointer to traverse the list

while (temp->next != nullptr && temp->next->data != data) {

temp = temp->next; // Move to the next node

}

if (temp->next == nullptr) { // If data is not found in the list

std::cout << "Data not found." << std::endl;

return;

}

Node* nodeToDelete = temp->next; // Store the node to be deleted

temp->next = temp->next->next; // Set the next pointer of temp to the next node of the node to be deleted

delete nodeToDelete; // Delete the node

}

};

  

#endif // STRUCT_H
```
# References


###### Information
- date: 2024.09.21
- time: 12:39