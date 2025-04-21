---
Title: Data Structure & Algorithm Lecture 16
Status: 
marker:
  - "[[Insertion Sort]]"
  - "[[Algorithm]]"
  - "[[Data Structures & Algorithm]]"
tags:
  - BTech
Date: 2024.09.18
Time: 14:09
---
# Insertion Sort of an Array of Five Integers

### Initial Array:
`[29, 10, 14, 37, 13]`

### Step-by-Step Process:

1. **Copy 10**
   - Compare 10 with 29.
   - Since 10 is less than 29, **shift 29** to the right.
   - Insert 10 at the start.
   - **Result:** `[10, 29, 14, 37, 13]`

2. **Copy 14**
   - Compare 14 with 29.
   - Since 14 is less than 29, **shift 29** to the right.
   - Insert 14 in the second position.
   - Compare 14 with 10. Since not less than it will break out of the loop
   - Run Loop till next element is shorter than current one
   - **Result:** `[10, 14, 29, 37, 13]`

3. **Copy 37**
   - Compare 37 with 29.
   - Since 37 is greater than 29, leave it in place.
   - **Result remains the same:** `[10, 14, 29, 37, 13]`

4. **Copy 13**
   - Compare 13 with 37, 29, and 14.
   - **Shift 37, 29, and 14** to the right.
   - Insert 13 in the second position.
   - **Result:** `[10, 13, 14, 29, 37]`

### Final Sorted Array:
`[10, 13, 14, 29, 37]`](<# Data Structure & Algorithm Lecture 16

## Insertion Function
```
insertionSort(array)
	mark first element as sorted
	for each unsorted element
		'hold' the element
		for j<-lastSortedIndex down to 0
			if current element j>X
				move soretd element to the right by I
			break loop and insert X here
	end insertionSort
```

```cpp
#include <iostream>  // Standard library for input/output operations
using namespace std;

/*
 * Function to perform insertion sort on an array
 * @param a[]: the array to be sorted
 * The array is passed as a parameter and sorted in place
 */
void insertionSort(int a[], int SIZE) {
    // Outer loop traverses the entire array starting from the second element (index 1)
    // The first element is already considered sorted as a dry run
    for (int i = 1; i < SIZE; i++) {
        int ai = a[i];  // 'Hold' the current element in a temporary variable (ai)
        int j;          // j will be used to find the correct position for ai

        // Inner loop that shifts elements to the right to create space for ai
        // The condition (j > 0) ensures we stay within bounds of the array
        // The condition (a[j-1] > ai) ensures we only move elements larger than ai
        for (j = i; j > 0 && a[j - 1] > ai; j--) {
            a[j] = a[j - 1];  // Move the element one position to the right
        }

        // After the inner loop ends, j is at the correct position for ai
        // Insert ai at its correct position in the sorted part of the array
        a[j] = ai;
    }
}

int main() {
    // Example array
    int a[] = {29, 10, 14, 37, 13};
    int size = sizeof(a) / sizeof(a[0]);  // Calculate the size of the array

    // Display the array before sorting
    cout << "Unsorted array: ";
    for (int i = 0; i < size; i++) {
        cout << a[i] << " ";
    }
    cout << endl;

    // Call the insertionSort function to sort the array
    insertionSort(a, size);

    // Display the array after sorting
    cout << "Sorted array: ";
    for (int i = 0; i < size; i++) {
        cout << a[i] << " ";
    }
    cout << endl;

    return 0;
}

```


# References


###### Information
- date: 2024.09.18
- time: 14:09>)