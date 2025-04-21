---
Title: Data Structures & Algorithm Lab 1
Status: true
marker: 
tags: 
Date: 20-07-2024
Time: 13:12
---
# Data Structures & Algorithm Lab 1
###### Details
Roll Number : K057
Name : Tejas Kamal Sahoo
Branch : Btech Cyber Security
Year : 2nd
Semester : 2
Date & Time : 20-07-2024 13:21


# Experiment 1
### Aime
To study Array

## Problems
### Question 1
Write a program to find minimum element from an array
### Answer 1

```cpp
#include <iostream>

#include <stdio.h>
// Function prototype
int minimum(int* arr, int size);
int main() {
    // Inputting the size of the array
    int size;
    std::cout << "Enter the size of the array: ";
    std::cin >> size;
    
    // Inputting the elements of the array
    int arr[size];
    std::cout << "Enter the elements of the array: ";
    for (int i = 0; i < size; i++) {
        std::cin >> arr[i];
    }

    // Displaying the elements of the array
    std::cout << "The array elements are: ";

    for (int i = 0; i < size; i++) {

        std::cout << arr[i] << " ";

    }

  

    // Finding the minimum element in the array

    int min = minimum(arr, size);

    std::cout << "\nThe minimum element in the array is: " << min << std::endl;

  

    return 0;

}

  

// Function definition

int minimum(int* arr, int size) {

    int min = arr[0];

    for (int i = 1; i < size; i++) {

        if (arr[i] < min) {

            min = arr[i];

        }

    }

    return min;

}
```

### Output 1
![[Pasted image 20240720132849.png]]

### Question 2 
Write a program to find mean of the array elements. Then find the count of the elements which are lesser, greater, and equal to the mean.
#### Answer 2
```cpp
#include <iostream>
#include <stdio.h>
// Function prototype
int average(int* arr, int size);
void countElements(int* arr, int size);
int main() {
    // Inputting the size of the array
    int size;
    std::cout << "Enter the size of the array: ";
    std::cin >> size;
    // Inputting the elements of the array
    int arr[size];
    std::cout << "Enter the elements of the array: ";
    for (int i = 0; i < size; i++) {
        std::cin >> arr[i];
    }
    // Displaying the elements of the array

    std::cout << "The array elements are: ";
    for (int i = 0; i < size; i++) {
        std::cout << arr[i] << " ";
    }
    // Finding the mean element in the array
    int mean= average(arr, size);
    std::cout << "\nThe minimum element in the array is: " << mean << std::endl;
    // Finding the number of elements lesser, greater and equal to the mean
    countElements(arr, size);
    return 0;
} 
int average(int* arr, int size) {
    int sum = 0;
    for (int i = 0; i < size; i++) {
        sum += arr[i];
    }
    return sum / size;
}

void countElements(int* arr, int size) {
    // Calculate the mean
    int mean = average(arr, size);

    // Initialize counters

    int lesserCount = 0;

    int greaterCount = 0;

    int equalCount = 0;

  

    // Count elements

    for (int i = 0; i < size; i++) {

        if (arr[i] < mean) {

            lesserCount++;

        } else if (arr[i] > mean) {

            greaterCount++;

        } else {

            equalCount++;

        }
    // Display the counts

    std::cout << "Number of elements lesser than the mean: " << lesserCount << std::endl;

    std::cout << "Number of elements greater than the mean: " << greaterCount << std::endl;

    std::cout << "Number of elements equal to the mean: " << equalCount << std::endl;

}
```

##### Output 2:
![[Pasted image 20240720153129.png]]

#### Question 3
Write a program to find count of zeros, even and odd elements from an array and display these numbers separately

```cpp
//Write a program to find count of zeros, even and odd elements from an array and display these numbers separately.

#include <iostream>

using namespace std;
void countElements(int arr[], int size, int& countZeros, int& countEven, int& countOdd) {

    for (int i = 0; i < size; i++) {

        if (arr[i] == 0) {

            countZeros++;

        } else if (arr[i] % 2 == 0) {

            countEven++;

        } else {

            countOdd++;

        }

    }

}

void displayCounts(int countZeros, int countEven, int countOdd) {

    cout << "Number of zeros: " << countZeros << endl;

    cout << "Number of even elements: " << countEven << endl;

    cout << "Number of odd elements: " << countOdd << endl;

}

  

int main() {

    int arr[10];

    int size;

  

    cout << "Enter the size of the array (up to 10): ";

    cin >> size;

  

    cout << "Enter the elements of the array: ";

    for (int i = 0; i < size; i++) {

        cin >> arr[i];

    }

  

    int countZeros = 0;

    int countEven = 0;

    int countOdd = 0;

  

    countElements(arr, size, countZeros, countEven, countOdd);

    displayCounts(countZeros, countEven, countOdd);

  

    return 0;

}
```
##### Answer 3
![[Pasted image 20240720153940.png]]

### Question 4 
Write a program to reverse an array.
##### Code 
```cpp
#include <iostream>

using namespace std;

  

int main() {

    int size;

    cout << "Enter the size of the array: ";

    cin >> size;

  

    int arr[size];

    cout << "Enter the elements of the array: ";

    for (int i = 0; i < size; i++) {

        cin >> arr[i];

    }

  

    cout << "Original array: ";

    for (int i = 0; i < size; i++) {

        cout << arr[i] << " ";

    }

  

    // Flip the array

    for (int i = 0; i < size / 2; i++) {

        int temp = arr[i];

        arr[i] = arr[size - 1 - i];

        arr[size - 1 - i] = temp;

    }

  

    cout << "\nFlipped array: ";

    for (int i = 0; i < size; i++) {

        cout << arr[i] << " ";

    }

  

    return 0;

}
```

#### Output
![[Pasted image 20240720171538.png]]

### Question 5
Write a program to insert an element in an array and then traverse the modified array
#### Code
```cpp
#include <iostream>

  

void inputArray(int arr[], int size) {

    std::cout << "Enter the elements of the array: ";

    for (int i = 0; i < size; i++) {

        std::cin >> arr[i];

    }

}

  

void outputArray(int arr[], int size) {

    std::cout << "Modified array: ";

    for (int i = 0; i < size; i++) {

        std::cout << arr[i] << " ";

    }

    std::cout << std::endl;

}

  

void insertElement(int arr[],

  

int& size, int element, int position) {

    if (position < 0 || position > size) {

        std::cout << "Invalid position!" << std::endl;

        return;

    }

  

    for (int i = size - 1; i >= position; i--) {

        arr[i + 1] = arr[i];

    }

  

    arr[position] = element;

    size++;

}

  

int main() {

    int size;

    std::cout << "Enter the size of the array: ";

    std::cin >> size;

  

    int arr[100];

  

    inputArray(arr, size);

  

    int element, position;

    std::cout << "Enter the element to insert: ";

    std::cin >> element;

    std::cout << "Enter the position to insert at: ";

    std::cin >> position;

  

    insertElement(arr, size, element, position);

  

    outputArray(arr, size);

  

    return 0;

}
```
#### Output
![[Pasted image 20240720171838.png]]

### Question 6
#### Code
```cpp
#include <iostream>

  

// Function declarations

void deleteElement(int arr[], int &size, int index);

void traverseArray(const int arr[], int size);

  

int main() {

    const int MAX_SIZE = 100;

    int arr[MAX_SIZE];

    int size;

  

    std::cout << "Enter the size of the array: ";

    std::cin >> size;

  

    std::cout << "Enter the elements of the array: ";

    for (int i = 0; i < size; i++) {

        std::cin >> arr[i];

    }

  

    int index;

    std::cout << "Enter the index of the element to delete: ";

    std::cin >> index;

  

    deleteElement(arr, size, index);

    traverseArray(arr, size);

  

    return 0;

}

  

// Function to delete an element from the array

void deleteElement(int arr[], int &size, int index) {

    if (index < 0 || index >= size) {

        std::cout << "Invalid index" << std::endl;

        return;

    }

    for (int i = index; i < size - 1; i++) {

        arr[i] = arr[i + 1];

    }

    // Decrease the size of the array

    size--;

}

  

// Function to traverse the modified array

void traverseArray(const int arr[], int size) {

    std::cout << "Modified Array: ";

    for (int i = 0; i < size; i++) {

        std::cout << arr[i] << " ";

    }

    std::cout << std::endl;

}
```
#### Output
![[Pasted image 20240720172207.png]]
