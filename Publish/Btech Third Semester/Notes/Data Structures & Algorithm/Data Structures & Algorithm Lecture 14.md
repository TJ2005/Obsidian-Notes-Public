---
Title: Data Structures & Algorithm Lecture 14
Status: 
marker:
  - "[[Data Structures & Algorithm]]"
  - "[[Classification]]"
  - "[[Sorting Algorithms]]"
  - "[[Selection Sort]]"
  - "[[Insertion Sort]]"
tags:
  - BTech
Date: 2024.09.13
Time: 09:31
---
Continued From [[Data Structures & Algorithm Lecture 13]]
# Classification of Algorithms
Classifying algorithms helps in understanding their efficiency, scalability, and suitability for different types of problems. It allows for easier comparison, selection, and optimization by grouping algorithms with similar characteristics, such as sorting, searching, or graph traversal. This classification aids in identifying the best approach for a specific problem, ensuring optimal use of resources like time and memory, and helps match algorithms to fields like machine learning or cryptography for targeted solutions.
## Classifications
- Computational Complexity
	- Time Complexity
- Computational complexity of swaps
- Memory Usage
	- Space Complexity
- Recursion
- Stability
## Sorting Algorithms
- Bubble Sort
- Selection Sort 
- Insertion Sort
- Shell Sort
- Heap Sort
- Quick Sort
- Bucket Sort
- Merge Sort
- Radix Sort

# Selection Sort
The concept here is to select the minimum or maximum element and swap it to a position that it belongs to. For minimum it will be the last position.
```cpp
selectionSort(array,siez){
	repeat(size-1)times;
	set the first unsorted element as the minim
	for each of the unsorted elements
		if element<currentMinimum
			set element as new minimum;
			
	swap minimum with first unsorted position
	end selection sort
}
```

```cpp
void selectionSort(array,size){
	int min,max,f=0,r=0;
	for(int i = 0; i<size; i++){
		// Repeating for size-1 times
		min = array[1];
		// Setting the first element as the first
		for(i<f=0){
			if(i=)
		}
		
	}
}
```

### Maximizer
```cpp
void sort(int a,int size){
	for(i=SIZE-1;i>0,i--){
		int m=0;
		for(j=1;j<=i;j++){
			if(a[j]>a[m]){
				m=j;
			}
			swap(a,i,m)
		}
	}
}
```
### Minimizer
```cpp
void sort(int a,int size){
	for(i=0;i<size;i--){
		int m=0;
	}
}
```
# Insertion Sort
Insertion Sort keeps making the left of the array is always sorted and right side of the array is sorted. It sorts the value seen so far and repeatedly insert unseen values in the arrays into the left sorted array.

The insertion sort algorithm is the sort unknowingly used by most card players.

```cpp
#include <iostream>
using namespace std;

void insertionSort(int array[], int size) {
    for (int i = 1; i < size; i++) {
        int key = array[i];  // Element to be inserted
        int j = i - 1;

        // Move elements of array[0..i-1], that are greater than key,
        // to one position ahead of their current position
        while (j >= 0 && array[j] > key) {
            array[j + 1] = array[j];
            j--;
        }

        array[j + 1] = key;  // Place the key in its correct position
    }
}

int main() {
    int array[] = {12, 11, 13, 5, 6};
    int size = sizeof(array) / sizeof(array[0]);

    insertionSort(array, size);

    cout << "Sorted array: \n";
    for (int i = 0; i < size; i++) {
        cout << array[i] << " ";
    }

    return 0;
}
```

# References


###### Information
- date: 2024.09.13
- time: 09:31