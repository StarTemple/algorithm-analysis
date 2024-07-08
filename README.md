#### Assignment: Analyzing and Optimizing Algorithm Efficiency

#### Objective:
In this assignment, we analyze the time complexity of given algorithms, express their complexity using Big O notation, and propose optimizations to improve their efficiency.

#### Problem Statement:
We are given two algorithms to analyze and optimize:
1. Linear Search
2. Bubble Sort

#### Requirements:

1. **Algorithm 1: Linear Search**
   - **Description**: Find the index of the first occurrence of a target value in an unsorted array of integers. Return -1 if the target is not found.
   - **Time Complexity**: The time complexity of linear search is **O(n)**, where **n** is the number of elements in the array.
   - **Code**:
     ```python
     def linear_search(arr, target):
         for index, value in enumerate(arr):
             if value == target:
                 return index
         return -1

     # Sample Test Cases
     array = [10, 23, 45, 70, 11, 15]
     target = 70
     print(f"Index of {target}: {linear_search(array, target)}")  # Output: 3

     target = 11
     print(f"Index of {target}: {linear_search(array, target)}")  # Output: 4

     target = 99
     print(f"Index of {target}: {linear_search(array, target)}")  # Output: -1
     ```
   - **Optimization**: Linear search is already optimal for unsorted arrays as it checks each element once.

2. **Algorithm 2: Bubble Sort**
   - **Description**: Sort an array of integers in ascending order using the bubble sort algorithm.
   - **Time Complexity**: The time complexity of bubble sort is **O(n^2)** in the worst case, where **n** is the number of elements in the array.
   - **Code**:
     ```python
     def bubble_sort(arr):
         n = len(arr)
         for i in range(n):
             for j in range(0, n-i-1):
                 if arr[j] > arr[j+1]:
                     arr[j], arr[j+1] = arr[j+1], arr[j]
         return arr

     # Sample Test Cases
     array = [64, 34, 25, 12, 22, 11, 90]
     print(f"Sorted array: {bubble_sort(array)}")  # Output: [11, 12, 22, 25, 34, 64, 90]

     array = [5, 1, 4, 2, 8]
     print(f"Sorted array: {bubble_sort(array)}")  # Output: [1, 2, 4, 5, 8]
     ```
   - **Optimization**:
     - **Improved Bubble Sort**: Stop the algorithm if no elements were swapped during a pass, indicating the array is sorted.
     - **Optimized Code**:
       ```python
       def optimized_bubble_sort(arr):
           n = len(arr)
           for i in range(n):
               swapped = False
               for j in range(0, n-i-1):
                   if arr[j] > arr[j+1]:
                       arr[j], arr[j+1] = arr[j+1], arr[j]
                       swapped = True
               if not swapped:
                   break
           return arr

       # Sample Test Cases
       array = [64, 34, 25, 12, 22, 11, 90]
       print(f"Sorted array: {optimized_bubble_sort(array)}")  # Output: [11, 12, 22, 25, 34, 64, 90]

       array = [5, 1, 4, 2, 8]
       print(f"Sorted array: {optimized_bubble_sort(array)}")  # Output: [1, 2, 4, 5, 8]
       ```
