---
title: Insertion Sort
publish: true
categories:
  - "[[Computer Science]]"
  - "[[Programming]]"
  - "[[Sorting Algorithms]]"
---

# Insertion Sort

This sorting is similar to sorting playing cards in hand.

- We can think there are 2 sides, left we have sorted elements and right unsorted.
- We pick an element from unsorted list and compare it against sorted list
- When we encounter any elements greater than comparing element from unsorted list, we switch the elements
- We stop switching when we are at the end of the sorted list, making the element picked from unsorted list smallest
- Or, when we encounter a smaller number from the sorted list compared to the element

```cpp
// Unsorted list
From j=2 to Array.length
	key = A[j] // Element from unsorted list
	i = j-1 // Start from last element of sorted array; Assuming it will be greatest
	while i > 0 && A[i] > key
		A[i + 1] = A[i]
		i = i -1
	A[i + 1] = key
```

Some years back I was mocked for calling `NULL` as nothing meaning, the pointer is not pointing to anything, and I was mocked.

Insertion sort in non-increasing (Decreasing) order elements

```cpp
From j=2 to A.lenght
	key = A[j]
	i = j -1
	while i > 0 && A[i] < key
		A[i + 1] = A[i]
		i = i -1
	A[i + 1] = key
```

_Problem_: Write pseduo code for linear search of value `v` where its one of the element of the array at index `i` or `NIL` otherwise. And prove the algorithm using <u>LOOP INVARIANT</u>

_Problem_: Add 2 n-bit binary array A & B. The sum of 2 integers should be stored in binary form an (n+1)-element array C. State problem formally and write _pseudocode_
