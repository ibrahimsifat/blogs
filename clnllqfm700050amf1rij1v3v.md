---
title: "Binary Search: Learn Algorithm in JavaScript"
seoTitle: "Binary Search: Learn Algorithm in JavaScript with IbrahimSifat"
seoDescription: "Learning Algorithm: 2. Binary Search
Binary Search: Searching Algorithm in JavaScript"
datePublished: Wed Oct 11 2023 10:22:14 GMT+0000 (Coordinated Universal Time)
cuid: clnllqfm700050amf1rij1v3v
slug: binary-search-algorithm-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1697011659568/3458af47-b902-4361-aa75-d2c6cf62333a.webp
tags: algorithms, binary-search-algorithm, searching-algorithms

---

### Conditions for when to apply Binary Search in a Data Structure:

To apply the Binary Search algorithm:

* The data structure must be sorted.
    
* Access to any element of the data structure takes constant time.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697011870504/d527103f-e567-4710-8a9b-1f38abf504ec.png align="center")

* *Compare the middle element of the search space with the key.* 
    
* *If the key is found in the middle element, the process is terminated.*
    
* *If the key is not found in the middle element, choose which half will be used as the next search space.*
    
    * *If the key is smaller than the middle element, then the left side is used for the next search.*
        
    * *If the key is larger than the middle element, then the right side is used for the next search.*
        
* *This process is continued until the key is found or the total search space is exhausted.*
    

### The **Binary Search Algorithm** can be implemented in the following two ways

* Iterative Binary Search Algorithm
    
* Recursive Binary Search Algorithm
    

## **Iterative  Binary Search Algorithm:**

How does Iterative Binary Search work?

**First Step:** Calculate the mid and compare the mid element with the key. If the key is less than the mid element, move to the left and if it is greater than the mid then move search space to the right.

![Binary search algorithm and usage - LearningSolo](https://i0.wp.com/learningsolo.com/wp-content/uploads/2018/04/binarray1-1.gif?fit=469%2C182&ssl=1 align="left")

* *The key is less than the current mid-45. The search space moves to the left.*
    
* **I**f the key matches the value of the mid element, the element is found, and stop search.
    

### Let me break it down step by step:

1. Initialize a function called `binarySearch` with parameters `arr` the array of integers, `n`given Array length, `target` targeted value
    
    ```javascript
    const binarySearch = (arr, n, target) => {
    }
    ```
    
2. Initialize pointers for the start, end, and mid of the array
    
    ```javascript
      let start = 0;
      let end = n - 1;
      let mid;
    ```
    
3. Perform the binary search using a while loop with the condition: if the start position number is greater than or equal to the end position then the loop will stop.
    
    ```javascript
    while (start <= end) {}
    ```
    
4. Calculate the middle index of the current search space.
    
    ```javascript
    //  while (start <= end) {
        mid = start + Math.floor((end - start) / 2);
    // }    
    ```
    
    Let's break down this `mid calculation` formula step by step:
    
    1. **Calculate the Range:** `(end - start)` represents the total number of elements in the current search space. For example, if `start` is 0 and `end` is 5, the range is 5 (inclusive of both `start` and `end`).
        
    2. **Divide by 2:** `(end - start) / 2` calculates the half of the range, which gives the distance from `start` to the middle element. This division ensures that the result is an integer (the `floor` function takes the integer part of the division).
        
    3. **Add to Start:** Finally, `start + Math.floor((end - start) / 2)` add the calculated distance to the initial starting index (`start`). This gives the index of the middle element within the current search space.
        
5. Check if the middle element is equal to the target
    
    ```javascript
    // while (start <= end) {
       // mid = start + Math.floor((end - start) / 2);
    
        if (arr[mid] === target) {
          // If found, return the index of the target
          return mid;
    // }
    ```
    
6. If the middle element is greater than the target then update the end pointer
    
    ```javascript
    //  while (start <= end) {
        if (arr[mid] > target) {
          end = mid - 1;
        }
    // }
    ```
    
7. If the middle element is less than the target then update the start pointer
    
    ```javascript
    //     if (arr[mid] > target) {
    //          end = mid - 1;
    //      } 
            else {
              start = mid + 1;
            }
    ```
    
8. If the target is not found in the entire array, return -1 after the while loop end.
    
9. The complete implementation of the binary search algorithm in JavaScript.
    
    ```javascript
    const binarySearch2 = (arr, n, target) => {
      // Initialize pointers for the start, end, and mid of the array
      let start = 0;
      let end = n - 1;
      let mid;
    
      // Perform binary search using a while loop
      while (start <= end) {
        // Calculate the middle index of the current search space
        mid = start + Math.floor((end - start) / 2);
    
        // Check if the middle element is equal to the target
        if (arr[mid] === target) {
          // If found, return the index of the target
          return mid;
        }
    
        // If the middle element is greater than the target, update the end pointer
        if (arr[mid] > target) {
          end = mid - 1;
        } else {
          // If the middle element is less than the target, update the start pointer
          start = mid + 1;
        }
      }
    
      // If the target is not found in the entire array, return -1
      return -1;
    }
    ```
    
    ## **Recursive  Binary Search Algorithm:**
    
    1. Declares a function named `binarySearch` that takes an array `arr`, `start` and `end` indices of the search space, and a `target` value to search for.
        
        ```javascript
        const binarySearch = (arr, start, end, target) => { ... }
        ```
        
    2. Check if the search space is not empty. If it's empty (`end < start`), the function returns -1 (indicating that the target is not found).
        
        ```javascript
        if (end >= start) { ... }
        ```
        
    3. Calculates the middle index of the current search space
        
        ```javascript
        let mid = start + Math.floor((end - start) / 2)
        ```
        
    4. Check if the middle element is equal to the target. If so, the function returns the index (`mid`) where the target is found.
        
        ```javascript
        if (arr[mid] == target) { return mid; }
        ```
        
    5. **Recursive Calls:**
        
        * If the target is less than the middle element, it means the target is in the left half of the array.
            
            ```javascript
            if (arr[mid] > target) { return binarySearch2(arr, start, mid - 1, target); }
            ```
            
        * If the target is greater than the middle element, it means the target is in the right half of the array. The function makes a recursive call on the right subarray.
            
            ```javascript
            else { return binarySearch2(arr, mid + 1, end, target); }
            ```
            
    6. If the target is not found in the entire array, the function returns -1.
        
        ```javascript
        return -1;
        ```
        
    7. The complete implementation of the recursive binary search algorithm in JavaScript.
        
        ```javascript
        const binarySearch2 = (arr, start, end, target) => {
          // Check if the search space is not empty
          if (end >= start) {
            // Calculate the middle index
            let mid = start + Math.floor((end - start) / 2);
        
            // Check if the middle element is the target
            if (arr[mid] == target) {
              return mid;  // If found, return the index
            }
        
            // If the target is in the left half, recursively search the left subarray
            if (arr[mid] > target) {
              return binarySearch2(arr, start, mid - 1, target);
            } else {
              // If the target is in the right half, recursively search the right subarray
              return binarySearch2(arr, mid + 1, end, target);
            }
          }
        
          // If the target is not found in the entire array, return -1
          return -1;
        };
        ```
        
        ## **Advantages of Binary Search:**
        
        * Binary search is faster than linear search, making it particularly efficient for searching in large arrays.
            
        * Binary search outperforms other searching algorithms with similar time complexities, such as interpolation search or exponential search.
            
        * Binary search is well-suited for searching large datasets stored in external memory, like on a hard drive or in the cloud.
            
        * The algorithm's logarithmic time complexity ensures efficient searching by repeatedly halving the search space.