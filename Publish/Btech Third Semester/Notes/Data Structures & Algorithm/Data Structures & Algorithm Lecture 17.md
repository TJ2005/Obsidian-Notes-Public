---
Title: Data Structures & Algorithm Lecture 17
Status: 
marker:
  - "[[Divide and Conquer]]"
  - "[[Merge Sort]]"
  - "[[Algorithm]]"
tags:
  - BTech
Date: 2024.09.20
Time: 09:20
---
# Divide And Conquer
Just like the British conquered and enslaved us we can divide and conquer the data to have a more proper reign on it.

## Steps
- **Divide**: If the input size is too large divide it with a straightforward manner.
- **Recur**: Repeat the division until fine divisions
- **Merge:** After the division merge it and while merging perform the desired operation.

## Example Merge Sort
- Algorithm
	- **Divide**
	- **Recur:**: Recursive sort sequences $S_1$ and $S_2$ .
	- **Conquer:** While merging the perform sorting of the variables that are sorted. Resulting in a sorted merge.

## Merge Sort Procedure
```algorithm
If q-p > 1 do steps 2-5
Split s into 2 subsequences, a = {sp … sm-1 } and b = {sm … sq-1 }, where m = (q-p)/2. 
Sort a 4. Sort b 
Merge a and b back into s, preserving order
```

```cpp
void sort(int a[],int q)
{
	if(p>r)
		return;
	int m = (p+q)/2;
	sort(a,p,m);
	sort(a,m+1,q);
	merge(a,p,m,q);
}
```

```cpp
void merge(int a[],int q)
{
	
	int i,m,k,I,temp[max];
	I=low;
	i=low;
	m=mid+I;
	while((i<=mid)&&(m<=high))
	{
		if
	}
}
```


# References


###### Information
- date: 2024.09.20
- time: 09:20