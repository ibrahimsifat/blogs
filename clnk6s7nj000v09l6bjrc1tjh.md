---
title: "Linear Search: Learn Algorithm with JavaScript"
seoTitle: "Linear Search: Learn Algorithm with JavaScript with Ibrahimsifat"
seoDescription: "Linear search, also known as sequential search, is one of the simplest and most straightforward search algorithms. In this blog post, we'll explore the basi"
datePublished: Tue Oct 10 2023 10:35:57 GMT+0000 (Coordinated Universal Time)
cuid: clnk6s7nj000v09l6bjrc1tjh
slug: linear-search-learn-algorithm-with-javascript
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
    // const linearSearch = (arr, n, target) => {
         for (let i = 0; i < n; i++) {}
    // }
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
    

### **Recursive Linear Search:**

Let's break down the Recursive Linear Search algorithm step by step:

1. Declares a function named `binaryLinearSearch` that takes an array `arr`, the size of the array `n`, and a `target` value to search for.
    
    ```javascript
    
    const binaryLinearSearch = (arr, n, target) => {
    //  if (n === 0) {
    //    return -1;
    //  } else if (arr[n - 1] === target) {
    //    return n - 1;
    //  }
    //  return binaryLinearSearch(arr, n - 1, target);
    };
    ```
    
2. Check if the array is empty (`n` is 0). If so, it means the target cannot be found, and the function returns -1.
    
    ```javascript
    
    // const binaryLinearSearch = (arr, n, target) => {
         if (n === 0) {
         return -1;
    //   } else if (arr[n - 1] === target) {
    //     return n - 1;
    //   }
    //   return binaryLinearSearch(arr, n - 1, target);
    // };
    ```
    
3. Check if the last element of the array is equal to the target. If it is, the function returns the index of the last element.
    
    ```javascript
    // const binaryLinearSearch = (arr, n, target) => {
    //   if (n === 0) {
    //     return -1;
    //   }
         else if (arr[n - 1] === target) {
           return n - 1;
         }
    //  return binaryLinearSearch(arr, n - 1, target);
    // };
    ```
    
4. If the last element is not the target, the function makes a recursive call on a smaller array by reducing the size (`n - 1`). This process repeats until the base case is reached.
    
    ```javascript
    // const binaryLinearSearch = (arr, n, target) => {
    //   if (n === 0) {
    //     return -1;
    //   }
    //   else if (arr[n - 1] === target) {
    //     return n - 1;
    //   }
        return binaryLinearSearch(arr, n - 1, target);
    // };
    ```
    

# It's Time to Improve Linear Search

Linear search is like flipping through a book page by page until you find what you're looking for. It goes through each element in order until it finds a match or reaches the end.

To make it a bit faster, we can use a trick called "Transposition." If we find the key element, we swap it with the element just before it. This makes future searches for the same element quicker because we move it closer to the beginning of the list.

Imagine you're looking for your favorite toy on a shelf. When you find it, you put it in front of the shelf, so next time you can grab it faster without going through all the toys again. That's what transposition does in a nutshell.

Let's dive in and learn through practical experience:

1. Defines a function named `LinearSearchTransposition` that takes an array `arr` and a `key` value to search for.
    
    ```javascript
    function LinearSearchTransposition(arr, key) { ... }
    ```
    
2. Initiates a loop that traverses through each element of the array.
    
    ```javascript
    for (i = 0; i < arr.length; i++) { ... }
    ```
    
3. Check if the `key` is the first element. If so, return the index immediately, as there is no previous element to swap with.
    
    ```javascript
    //   function LinearSearchTransposition(arr, key) {
    //      let i;
        
    //      for (i = 0; i < arr.length; i++) {
              if (key == arr[i]) {
                if (i == 0) return i;
        
    //          let temp = arr[i];
    //          arr[i] = arr[i - 1];
    //          arr[i - 1] = temp;
        
    //          return i;
    //        }
    //      }
        
    //      return -1;
    //    }
        
    //    console.log(LinearSearchTransposition([1, 23, 3, 4, 5, 6, 7, 8, 9, 10], 10));
            
    ```
    
4. Swaps the current element with its previous element. The temporary variable `temp` is used to facilitate the swap.
    
    ```javascript
    //   function LinearSearchTransposition(arr, key) {
    //      let i;
        
    //      for (i = 0; i < arr.length; i++) {
    //          if (key == arr[i]) {
    //            if (i == 0) return i;
        
                let temp = arr[i];
                arr[i] = arr[i - 1];
                arr[i - 1] = temp;
        
    //          return i;
    //        }
    //      }
        
    //      return -1;
    //    }
        
    //    console.log(LinearSearchTransposition([1, 23, 3, 4, 5, 6, 7, 8, 9, 10], 10));
            
    ```
    
    1. Alternatively, you can use a destructuring assignment for a more concise swap:
        
        ```javascript
        [(arr[i], arr[i - 1])] = [arr[i - 1], arr[i]];
        ```
        
5. Returns the index of the element where the key was found after the swap.
    
    ```javascript
    //   function LinearSearchTransposition(arr, key) {
    //      let i;
        
    //      for (i = 0; i < arr.length; i++) {
    //          if (key == arr[i]) {
    //            if (i == 0) return i;
        
    //          let temp = arr[i];
    //          arr[i] = arr[i - 1];
    //          arr[i - 1] = temp;
        
                return i;
    //        }
    //      }
        
    //      return -1;
    //    }
        
    //    console.log(LinearSearchTransposition([1, 23, 3, 4, 5, 6, 7, 8, 9, 10], 10));
            
    ```
    
6. If the key is not found in the entire array, the function `returns -1`.
    
    ```javascript
    //   function LinearSearchTransposition(arr, key) {
    //      let i;
        
    //      for (i = 0; i < arr.length; i++) {
    //          if (key == arr[i]) {
    //            if (i == 0) return i;
        
    //          let temp = arr[i];
    //          arr[i] = arr[i - 1];
    //          arr[i - 1] = temp;
        
    //          return i;
    //        }
    //      }
        
          return -1;
    //    }
        
    //    console.log(LinearSearchTransposition([1, 23, 3, 4, 5, 6, 7, 8, 9, 10], 10));
            
    ```
    
7. Invokes the function with an example array and key (10) and logs the result.
    
    ```javascript
    //   function LinearSearchTransposition(arr, key) {
    //      let i;
        
    //      for (i = 0; i < arr.length; i++) {
    //          if (key == arr[i]) {
    //            if (i == 0) return i;
        
    //          let temp = arr[i];
    //          arr[i] = arr[i - 1];
    //          arr[i - 1] = temp;
        
    //          return i;
    //        }
    //      }
        
    //    return -1;
    //    }
        
    console.log(LinearSearchTransposition([1, 23, 3, 4, 5, 6, 7, 8, 9, 10], 10));
            
    ```
    

### Front (or Head) Method in Linear Search

The Move to Front (or Head) method is a search optimization technique where, upon finding a key element, it is immediately moved to the front (index 0) of the array. This strategy is employed to reduce the time complexity of subsequent searches for the same key, making them constant time (O(1)).

Here's a breakdown using an example:

Consider the array `arr[] = {2, 5, 7, 1, 6, 4, 5, 8, 3, 7}`. Let's say we want to search for the key 4.

1. **Initial Search:**
    
    * The key 4 is found at index 5 after 6 comparisons.
        
    * Array before Move to Front: `{2, 5, 7, 1, 6, 4, 5, 8, 3, 7}`.
        
2. **Move to Front Operation:**
    
    * After the search, the key 4 is moved to the front of the array.
        
    * Array after Move to Front: `{4, 2, 5, 7, 1, 6, 5, 8, 3, 7}`.
        
3. **Subsequent Search:**
    
    * Now, if we search for the key 4 again, it is found at index 0.
        
    * Array continues to be `{4, 2, 5, 7, 1, 6, 5, 8, 3, 7}`.
        

By moving the found key to the front, the subsequent search for the same key becomes highly efficient, as the key is now at the beginning of the array. This approach optimizes the search process and reduces the search space, resulting in constant time complexity for repeated searches of the same key.

**Here's a JavaScript code example implementing the Move to Front algorithm:**

1. Declares a function named `linearSearchMoveToFront` that takes an array (`arr`) and a key (`key`) to search.
    
    ```javascript
    const linearSearchMoveToFront = (arr, key) => { ... }
    ```
    
2. Initiates a loop to traverse the array.
    
    ```javascript
    //    const linearSearchMoveToFront = (arr, key) => {
            for (let i = 0; i < arr.length; i++) {
    //        if (key === arr[i]) {
    //          let temp = arr[i];
    //          arr[i] = arr[0];
    //          arr[0] = temp;
    //          return i;
    //        }
            }
    //      return -1;
    //    };
    ```
    
3. Check if the current element in the array is equal to the key.
    
    ```javascript
    //    const linearSearchMoveToFront = (arr, key) => {
    //      for (let i = 0; i < arr.length; i++) {
              if (key === arr[i]) {
    //          let temp = arr[i];
    //          arr[i] = arr[0];
    //          arr[0] = temp;
    //          return i;
              }
    //      }
    //      return -1;
    //    };
    ```
    
4. If the key is found, swap the current element with the element at the 0-th index. This is the move-to-front operation.
    
    ```javascript
    //    const linearSearchMoveToFront = (arr, key) => {
    //      for (let i = 0; i < arr.length; i++) {
    //        if (key === arr[i]) {
                let temp = arr[i];
                arr[i] = arr[0];
                arr[0] = temp;
    //          return i;
    //        }
    //      }
    //      return -1;
    //    };
    ```
    
5. Returns the index where the key was found after the move-to-front operation.
    
    ```javascript
    //    const linearSearchMoveToFront = (arr, key) => {
    //      for (let i = 0; i < arr.length; i++) {
    //        if (key === arr[i]) {
    //          let temp = arr[i];
    //          arr[i] = arr[0];
    //          arr[0] = temp;
                return i;
    //        }
    //      }
    //      return -1;
    //    };
    ```
    
6. If the loop completes without finding the key, the function returns `-1` to indicate that the key is not present in the array.
    
    ```javascript
    //    const linearSearchMoveToFront = (arr, key) => {
    //      for (let i = 0; i < arr.length; i++) {
    //        if (key === arr[i]) {
    //          let temp = arr[i];
    //          arr[i] = arr[0];
    //          arr[0] = temp;
    //          return i;
    //        }
    //      }
            return -1;
    //    };
    ```
    

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