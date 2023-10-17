---
title: "Understand Time and Space Complexities: Beginner's Guide"
seoTitle: "Understand Time and Space Complexities: Beginner's Guide with Ibrahim"
seoDescription: "Understand Time and Space Complexities: Beginner's Guide with Ibrahim sifat
Welcome, understanding the concepts of time and space complexities"
datePublished: Tue Oct 17 2023 10:11:42 GMT+0000 (Coordinated Universal Time)
cuid: clnu5zzvt000e0cl257p8cn0h
slug: understand-time-and-space-complexities-beginners-guide
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/ft0-Xu4nTvA/upload/6d445bb2e829d32827a0e513aa24023c.jpeg
tags: time-complexity, big-o-notation, space-complexity

---

Welcome, understanding the concepts of time and space complexities is akin to having a map that guides you through the vast landscape of programming. In this beginner-friendly guide, we'll break down these concepts with simple examples to make your coding adventures smoother.

**Keep In Mind for this Lectures:**

**<mark>Time Complexity is not counting Execution time.</mark>**

1. **Avoid Constants**
    
2. **Avoid Small Values**
    

## **1\. Why Time Complexity?**

Imagine you're searching for a book in a library. How long will it take, and does the time taken depend on the number of books? Time complexity answers these questions for your code.

### **1.1 Examples of Time Complexity**

#### **Example 1: Linear Time Complexity (O(n))**

```javascript
function linearSearch(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) {
      return i; // Book found at position i
    }
  }
  return -1; // Book not found
}
```

**Time Complexity Analysis:**

* The time complexity is denoted as O(n), where `n` is the number of books in the library.
    
* The wizard's effort grows linearly with the number of books.
    
* As the library size increases, the time taken for the quest increases at the same rate.
    

#### **Example 2: Logarithmic Time Complexity (O(log n))**

```javascript
function findPageWithBookmark(bookPages, targetPage) {
  let low = 0;                         // Start from the first page
  let high = bookPages.length - 1;     // End at the last page

  while (low <= high) {
    let mid = Math.floor((low + high) / 2);

    if (bookPages[mid] === targetPage) {
      return `Found the target page ${targetPage} at position ${mid}.`;
    } else if (bookPages[mid] < targetPage) {
      low = mid + 1;   // Search in the right half
    } else {
      high = mid - 1;  // Search in the left half
    }
  }

  return `The target page ${targetPage} is not in this book.`;
}

// Example Usage:
const bookPages = [1, 5, 13, 22, 36, 47, 55, 61, 74, 89];
const targetPage = 36;

const result = findPageWithBookmark(bookPages, targetPage);
console.log(result);
```

**Time Complexity:**

* Time complexity tells us how the time required for our spell grows as the size of the book (or array of pages) increases.
    
    In our binary search spell:
    
    * **Best Case:** O(1) - If you find the target page on the first try, you're done!
        
    * **Worst Case:** O(log n) - In the worst case, you keep dividing the search space in half until you find the page or determine it's not in the book. The log n term comes from the fact that you're repeatedly dividing the search space in half.
        

This binary search algorithm showcases logarithmic time complexity (`O(log n)`) due to the halving of the search space in each iteration, making it an efficient approach for sorted arrays.

### **1.2 How to Calculate Time Complexity**

Understanding time complexity involves unraveling how the number of operations grows with input size.

#### **Example: Linear Search (O(n))**

```javascript
function linearSearch(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) {
      return i; // Found the target at index i
    }
  }
  return -1; // Target not found in the array
}
```

### **Analysis:**

* **Basic Operation:** The basic operation here is the comparison (`arr[i] === target`) inside the loop.
    
* **Input Size:** Let `n` be the size of the array (`arr`).
    
* **Iterations:** The loop runs `n` times, where `n` is the size of the array.
    
* **Worst-Case Scenario:** The worst-case scenario is when the target is not present in the array, and the loop runs `n` times.
    
* **Time Complexity:**
    
    * **Best Case:** O(1) - Target is found on the first comparison.
        
    * **Worst Case:** O(n) - Target is found after the maximum number of comparisons (linear growth).
        

In `findMagicalBookWithAnalysis`, the time complexity is `O(n)` because the number of operations is directly linked to the number of books (`n`).

## **2\. Space Complexity:**

If time complexity is about the speed of your search, space complexity is like the magical backpack you carry—how much stuff can you fit inside?

### **2.1 Space Complexity Examples**

#### **Example 1: Constant Space Complexity (O(1))**

```javascript
function castSimpleSpell() {
  const spellIngredient1 = "Phoenix Feather";
  const spellIngredient2 = "Dragon Scale";
  const magicResult = spellIngredient1 + spellIngredient2;
  return magicResult; // Simple magic, constant space!
}
```

In this magical incantation, we have a few variables:

* `spellIngredient1`: This variable holds the value "Phoenix Feather."(`O(1)`)
    
* `spellIngredient2`: This variable holds the value "Dragon Scale."(`O(1)`)
    
* `magicResult`: This variable holds the result of combining `spellIngredient1` and `spellIngredient2`.(`O(1)`)
    

(`O(1)`)+(`O(1)`)+(`O(1)`)=(`O(1)`)

In `castSimpleSpell`, the amount of space used remains constant, regardless of the complexity of the spell (`O(1)`).

#### **Example 2: Linear Space Complexity (O(n))**

```javascript
function packMagicalItems(numberOfItems) {
  const magicalBackpack = new Array(numberOfItems);
  for (let i = 0; i < numberOfItems; i++) {
    magicalBackpack[i] = "Magical Item " + i;
  }
  return magicalBackpack; // A backpack full of magical items!
}
```

* The `new Array(numberOfItems)` dynamically allocates memory to create an array with a length of `numberOfItems`.
    

* The space complexity is O(n) because the space required scales linearly with the size of the input (`numberOfItems`).
    

### **2.2 How to Calculate Space Complexity**

Understanding space complexity involves analyzing how memory requirements grow with input size.

#### **Example: Constant Space Complexity (O(1))**

```javascript
function constantSpaceExampleWithAnalysis() {
  const a = 5;
  const b = 10;
  const result = a + b;
  return result;
}
```

`constantSpaceExampleWithAnalysis` has a space complexity of O(1) because it uses a fixed amount of space.

### **Points to Note:**

* **Fixed Number of Variables:**
    
    * The function uses three variables: `a`, `b`, and `result`.
        
* **Memory Consumption Unaffected by Input Size:**
    
    * The amount of memory needed to store these variables doesn't depend on the size of any input because there's no input.
        
* **No Dynamic Memory Allocation:**
    
    * The variables `a`, `b`, and `result` are simple primitives (numbers) and do not involve dynamic memory allocation.
        
* **No Iterative Structures:**
    
    * The function does not use loops or arrays. It's a straightforward sequence of variable assignments and an addition operation.
        
* **Constant Size Variables:**
    
    * The number of variables used in the function remains constant, regardless of the size or complexity of the function.
        
* **No Relationship with Input Size:**
    
    * Since there's no input parameter, the memory usage doesn't change based on any input size. The function produces the same result regardless.
        
* **Constant Space Complexity (O(1)):**
    
    * The space complexity is O(1) because the amount of memory required is constant and doesn't grow with the size or complexity of the function.
        

## **3\. Problems for Practice - Time and Space Complexity**

### **Example 1: Magical Factorial (Easy)**

```javascript
function performMagicalFactorialSpell(number) {
  if (number === 0 || number === 1) {
    return 1;
  }
  return number * performMagicalFactorialSpell(number - 1);
}
```

### **Example 2: Reverse the Spell (Easy)**

```javascript
function reverseMagicalSpell(spell) {
  return spell.split("").reverse().join("");
}
```

### **Example 3: Sort the Magical Potions (Medium)**

```javascript
function sortMagicalPotions(potions) {
  return potions.sort();
}
```

1. In this recursive spell,
    
    1. Time complexity of `O(n)` .
        
    2. Space complexity of `O(n)`.
        
2. `reverseMagicalSpell` reverses a magical spell in place, having a
    
    1. Time complexity of `O(n)` .
        
    2. Space complexity of `O(1)`.
        
3. `sortMagicalPotions` uses a sorting spell,
    
    1. Time complexity of `O(n)` .
        
    2. Space complexity of `O(1)`.
        

## 4\. Understanding Asymptotic Analysis and Notations

### Asymptotic Analysis:

Asymptotic analysis helps us understand the efficiency of an algorithm as the input size approaches infinity. It focuses on the growth rate of the algorithm's performance.

**Key Concepts:**

* **Infinite Input Size:** Asymptotic analysis considers the behavior of an algorithm as the input size becomes infinitely large.
    
* **Dominant Terms:** It identifies the most significant terms affecting the algorithm's performance.
    

**Example:**

Consider a simple summation algorithm:

```javascript
function sumUpToN(n) {
  let sum = 0;
  for (let i = 1; i <= n; i++) {
    sum += i;
  }
  return sum;
}
```

### Analysis:

* **Basic Operation:** The basic operation is the addition (`sum += i`) inside the loop.
    
* **Iterations:** The loop runs `n` times, where `n` is the input size.
    
* **Asymptotic Behavior:** As `n` becomes very large, the dominating term is `n`, and the efficiency is expressed as O(n).
    

## Asymptotic Notations:

Asymptotic notations provide a concise way to describe the growth rate of an algorithm's time or space complexity.

### Big O Notation (O):

* **Definition:** Represents the upper bound on the growth rate of an algorithm.
    
* **Example:**
    
    * `O(n^2)`: Quadratic growth.
        
    * `O(n)`: Linear growth.
        
    * `O(1)`: Constant growth.
        

### Omega Notation (Ω):

* **Definition:** Represents the lower bound on the growth rate of an algorithm.
    
* **Example:**
    
    * `Ω(n^2)`: At least quadratic growth.
        
    * `Ω(n)`: At least linear growth.
        
    * `Ω(1)`: At least constant growth.
        

### Theta Notation (Θ):

* **Definition:** Represents both upper and lower bounds, providing a tight bound on the growth rate.
    
* **Example:**
    
    * `Θ(n^2)`: Exactly quadratic growth.
        
    * `Θ(n)`: Exactly linear growth.
        
    * `Θ(1)`: Exactly constant growth.
        

### Examples:

#### Big O Notation (O):

* **Example:**
    
    ```javascript
    function findMax(arr) {
      let max = arr[0];
      for (let i = 1; i < arr.length; i++) {
        if (arr[i] > max) {
          max = arr[i];
        }
      }
      return max;
    }
    ```
    
    * **Analysis:**
        
        * Basic operation: Comparison inside the loop.
            
        * Time complexity: O(n) because the algorithm grows linearly with the input size.
            

#### Omega Notation (Ω):

* **Example:**
    
    ```javascript
    function linearSearch(arr, target) {
      for (let i = 0; i < arr.length; i++) {
        if (arr[i] === target) {
          return i;
        }
      }
      return -1;
    }
    ```
    
    * **Analysis:**
        
        * Basic operation: Comparison inside the loop.
            
        * Time complexity: Ω(1) in the best case (target found on the first comparison).
            

#### Theta Notation (Θ):

* **Example:**
    
    ```javascript
    function simpleSum(n) {
      return (n * (n + 1)) / 2;
    }
    ```
    
    * **Analysis:**
        
        * Basic operation: Arithmetic operations.
            
        * Time complexity: Θ(1) because the algorithm has constant time complexity.
            

### Conclusion:

Asymptotic analysis and notations provide powerful tools for understanding and expressing the efficiency of algorithms. Big O, Omega, and Theta notations offer clear and concise language for describing how algorithms scale with input size. Remember, it's about identifying the dominant term and expressing it in a way that captures the essential behavior of the algorithm.

**Thanks for reading ❤**

Say Hello [Linkedin](https://www.linkedin.com/in/ibrahim-sifat/) | [Twitter](https://twitter.com/Ibrahimsifat0)