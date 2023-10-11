---
title: "Linear Search: Searching Search Algorithm in JavaScript"
seoTitle: "Linear Search: Searching Search Algorithm in JavaScript"
seoDescription: "Linear search, also known as sequential search, is one of the simplest and most straightforward search algorithms. In this blog post, we'll explore the basi"
datePublished: Tue Oct 10 2023 10:35:57 GMT+0000 (Coordinated Universal Time)
cuid: clnk6s7nj000v09l6bjrc1tjh
slug: linear-search-searching-search-algorithm-in-javascript
tags: javascript, algorithm, linearsearch, searching-algorithms

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1697027072848/cdab3ac0-fab6-48e6-ae57-bbd0fe58a1cb.png align="center")

Linear search, also known as sequential search, is one of the simplest and most straightforward search algorithms. In this blog post, we'll explore the basics of linear search and implement it in JavaScript. Let's dive in!

### Linear Search Overview

Linear search is a straightforward algorithm that iterates through each element in a list until it finds the target value or reaches the end of the list. It is a basic search algorithm and is often the first algorithm taught to beginners.

In the Linear Search Algorithm, 

* Every element is considered as a potential match for the key and checked for the same.
    
* If any element is found equal to the key, the search is successful and the index of that element is returned.
    
* If no element is found equal to the key, the search yields “No match found”.
    

**For example:** Consider the array **arr\[\] = {3, 15, 8, 1, 38, -2, 7}** and **key** = 1

![Linear Search - Algorithm - TO THE INNOVATION](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRbpGamaUfroXxsjdCL5WrAziEf3NJFSWggUZK6ArvQ7u4J9F593e6D-_-7ntoH2br_ULw&usqp=CAU align="left")

### JavaScript Implementation

Let's look at a simple JavaScript implementation of the linear search algorithm:

### **Let me break it down step by step:**

1. Initialize an arrow function called `linearSearch` with parameters `arr` the array of integers, `n`given Array length, `target` targeted value
    
    ```javascript
    const linearSearch = (arr, n, target) => {}
    ```
    
2. Loop through each element in the array
    
    ```javascript
    const linearSearch = (arr, n, target) => {
      // Loop through each element in the array
      for (let i = 0; i < n; i++) {}
    }
    ```
    
3. Check if the current element is equal to the target If found, return the index of the target.
    
    ```javascript
    // const linearSearch = (arr, n, target) => {
    //     for (let i = 0; i < n; i++) {
                if (arr[i] === target) {
                  return i;
                }    
    //     }
    // }
    ```
    
4. If the target is not found in the entire array, return -1.
    
    ```javascript
    // const linearSearch = (arr, n, target) => {
    //     for (let i = 0; i < n; i++) {
    //          if (arr[i] === target) {
    //            return i;
    //          }    
    //     }
           return -1;
    // }
    ```
    
5. The complete implementation of the Linear search algorithm in JavaScript.
    

```javascript
// Given array to be searched
var arr = [64, 25, 12, 22, 11];

// Size of the array
var n = 5;

// Linear search algorithm function
const linearSearch = (arr, n, target) => {
  // Loop through each element in the array
  for (let i = 0; i < n; i++) {
    // Check if the current element is equal to the target
    if (arr[i] === target) {
      // If found, return the index of the target
      return i;
    }
  }
  
  // If the target is not found in the entire array, return -1
  return -1;
};

// Example: Search for the target value 225 in the array
console.log(linearSearch(arr, n, 225));
```

In this code snippet:

* `arr` is the array to be searched.
    
* `n` is the size of the array.
    
* `linearSearch` is a function that takes the array, its size, and a target value as parameters.
    

### How Linear Search Works

1. **Initialization**: The function starts at the beginning of the array (`i = 0`).
    
2. **Comparison**: It compares the current element with the target value.
    
3. **Condition Check**: If the current element is equal to the target, the function returns the index.
    
4. **Iteration**: If the target is not found, the function moves to the next element in the array and repeats the process until the end of the array is reached.
    
5. **Result**: If the target is not found in the entire array, the function returns -1.
    

**Advantages of Linear Search:**

* Linear search can be used irrespective of whether the array is sorted or not. It can be used on arrays of any data type.
    
* Does not require any additional memory.
    
* It is a well-suited algorithm for small datasets.
    

**Drawbacks of Linear Search:**

* Linear search has a time complexity of O(N), which in turn makes it slow for large datasets.
    
* Not suitable for large arrays.
    

**When to use Linear Search?**

* When we are dealing with a small dataset.
    
* When you are searching for a dataset stored in contiguous memory.
    

### Conclusion

Linear search is a fundamental algorithm that provides a basic understanding of how searching works. While it may not be the most efficient for large datasets, its simplicity makes it a great starting point for learning about algorithms.