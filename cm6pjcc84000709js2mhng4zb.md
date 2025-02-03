---
title: "Day 3 | Ultimate Guide to Sorting Algorithms: A Beginner-to-Advanced Journey in Bangla"
seoTitle: "Sorting Algorithms: Beginner to Advanced Guide in Bangla with Ibrahim "
seoDescription: "Master sorting from basics to advanced: techniques, applications, and algorithm analysis in bangla with Ibrahim Sifat"
datePublished: Mon Feb 03 2025 21:00:46 GMT+0000 (Coordinated Universal Time)
cuid: cm6pjcc84000709js2mhng4zb
slug: day-3-ultimate-guide-to-sorting-algorithms-a-beginner-to-advanced-journey-in-bangla
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1735971808266/e424b833-156e-4ed8-b73a-f83e3a914997.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1735971868750/1e75555a-d4a5-4fce-ae48-a4eed83a991c.png
tags: sorting, dsa, sorting-algorithms

---

## সর্টিং কি? (What is Sorting?)

সর্টিং হলো একটি প্রক্রিয়া যেখানে আমরা কিছু এলিমেন্ট (elements) কে একটা নির্দিষ্ট ক্রম অনুযায়ী সাজাই। এটা হতে পারে ছোট থেকে বড় (ascending order) বা বড় থেকে ছোট (descending order)।

### দৈনন্দিন জীবনে সর্টিং (Real-life Examples):

1. **লাইব্রেরির বই সাজানো:**
    
    * আপনি কি লক্ষ্য করেছেন লাইব্রেরিতে বইগুলো কিভাবে সাজানো থাকে?
        
    * বইগুলো থাকে subject অনুযায়ী, তারপর writer's name অনুযায়ী alphabetically সাজানো
        
    * এটাই সর্টিং এর একটা বাস্তব উদাহরণ
        
2. **তাস খেলার কার্ড সাজানো:**
    
    * Suit অনুযায়ী (♠️, ♣️, ♥️, ♦️)
        
    * প্রতিটি suit এর ভিতরে A থেকে K পর্যন্ত
        

### কম্পিউটার সায়েন্সে সর্টিং এর ব্যবহার:

1. **ডাটাবেজ অ্যাপ্লিকেশন:**
    
    ```sql
    SELECT * FROM students ORDER BY roll_number;
    ```
    
    * ছাত্রদের রোল নাম্বার অনুযায়ী সাজানো
        
    * মার্কস অনুযায়ী র‍্যাংকিং করা
        
2. **সার্চ ইঞ্জিন:**
    
    * Google search results রেলেভেন্স অনুযায়ী সাজিয়ে দেখায়
        
    * YouTube videos view count বা upload date অনুযায়ী সর্ট করে
        

## বেসিক টার্মিনোলজি (Key Terminology):

1. **Array কি?**
    
    ```python
    numbers = [5, 2, 8, 1, 9]  # Unsorted array
    ```
    
    * Array হলো একই ধরনের ডাটার একটা ordered collection
        
    * প্রতিটা এলিমেন্ট এর একটা নির্দিষ্ট position থাকে (index)
        
2. **Element Comparison:**
    
    ```python
    if numbers[0] > numbers[1]:  # Comparing 5 and 2
        # 5 is greater than 2
    ```
    
    * দুইটা এলিমেন্ট এর মধ্যে তুলনা করা
        
    * কোনটা বড়/ছোট বের করা
        
3. **Swapping:**
    
    ```python
    # Before: [5, 2]
    temp = numbers[0]      # temp = 5
    numbers[0] = numbers[1]  # numbers[0] = 2
    numbers[1] = temp      # numbers[1] = 5
    # After: [2, 5]
    ```
    
    * দুইটা এলিমেন্ট এর position exchange করা
        

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735546646491/2a627e33-c766-42bb-b564-09d4421578e9.png align="center")

# 1.2 Learning Through Visuals

## ভিজ্যুয়াল ডেমোনস্ট্রেশন (Visual Demonstration)

উপরের ছবিতে আমরা দেখতে পাচ্ছি:

1. **অসর্টেড অ্যারে (Unsorted Array):**
    
    * প্রথম লাইনে দেখানো হয়েছে একটি অসর্টেড অ্যারে: \[5, 2, 8, 1, 9\]
        
    * প্রতিটি এলিমেন্ট এর নিচে তার ইনডেক্স (0 থেকে 4) দেখানো হয়েছে
        
2. **সর্টেড অ্যারে (Sorted Array):**
    
    * দ্বিতীয় লাইনে দেখানো হয়েছে সর্টেড অ্যারে: \[1, 2, 5, 8, 9\]
        
    * ছোট থেকে বড় ক্রমে সাজানো (ascending order)
        
3. **মেমরি লেআউট (Memory Layout):**
    
    * কম্পিউটারের মেমরিতে অ্যারে কিভাবে স্টোর হয় তা দেখানো হয়েছে
        
    * প্রতিটি এলিমেন্ট এর মেমরি অ্যাড্রেস (0x1000 থেকে শুরু)
        
4. **স্বাপিং অপারেশন (Swapping Operation):**
    
    * দুইটি এলিমেন্ট কিভাবে পজিশন exchange করে তা দেখানো হয়েছে
        
    * 5 এবং 2 এর মধ্যে স্বাপিং প্রক্রিয়া
        

## ইন্টারেক্টিভ এক্সারসাইজ (Interactive Exercise)

আসুন একটি ছোট এক্সারসাইজ করি:

নিচের অ্যারেকে ascending order এ সাজান:

```python
numbers = [7, 3, 6, 1, 4]
```

**ধাপ-১:** সবচেয়ে ছোট নাম্বার খুঁজুন

* 1 হচ্ছে সবচেয়ে ছোট
    

**ধাপ-২:** এটিকে প্রথম পজিশনে আনুন

```python
# After first swap
numbers = [1, 3, 6, 7, 4]
```

**ধাপ-৩:** বাকি নাম্বারগুলোর মধ্যে সবচেয়ে ছোট নাম্বার খুঁজুন

* 3 ইতিমধ্যে সঠিক পজিশনে আছে
    

এভাবে ধাপে ধাপে সর্টিং করতে থাকুন।

I'll create a detailed explanation of Bubble Sort with visual aids.

# 2.1 Bubble Sort: Conceptual Understanding

বাবল সর্ট (Bubble Sort) হচ্ছে সবচেয়ে সহজ সর্টিং অ্যালগরিদমগুলোর মধ্যে একটি। আসুন এটা বুঝি একটি মজার উদাহরণের মাধ্যমে।

## বাবল সর্ট কিভাবে কাজ করে? (How Bubble Sort Works)

### পানির বাবল অ্যানালজি (Water Bubble Analogy):

পানির মধ্যে যেমন হালকা বাবলগুলো উপরে উঠে আসে আর ভারী জিনিসগুলো নিচে চলে যায়, বাবল সর্টও ঠিক একইভাবে কাজ করে:

1. **বড় সংখ্যাগুলো (Heavy Numbers):**
    
    * বড় সংখ্যাগুলো পানির নিচে ডুবে যাওয়া ভারী বাবলের মতো
        
    * প্রতি পাসে এগুলো ধীরে ধীরে ডান দিকে (অ্যারের শেষের দিকে) সরে যায়
        
2. **ছোট সংখ্যাগুলো (Light Numbers):**
    
    * ছোট সংখ্যাগুলো পানির উপরে ভাসমান হালকা বাবলের মতো
        
    * প্রতি পাসে এগুলো বাম দিকে (অ্যারের শুরুর দিকে) সরে আসে
        

### বাবল সর্টের স্টেপ-বাই-স্টেপ প্রসেস:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735547006194/0638a02f-ccd3-44ac-95b0-b9969df3b9f5.png align="center")

### প্রথম পাস (First Pass)

1. **স্টেপ ১.১:**
    
    * তুলনা: `[5, 3]` ⟶ 5 &gt; 3
        
    * স্বাপিং করবে: `[3, 5, 8, 4, 2]`
        
2. **স্টেপ ১.২:**
    
    * তুলনা: `[5, 8]` ⟶ 5 &lt; 8
        
    * স্বাপিং নেই: `[3, 5, 8, 4, 2]`
        
3. **স্টেপ ১.৩:**
    
    * তুলনা: `[8, 4]` ⟶ 8 &gt; 4
        
    * স্বাপিং করবে: `[3, 5, 4, 8, 2]`
        
4. **স্টেপ ১.৪:**
    
    * তুলনা: `[8, 2]` ⟶ 8 &gt; 2
        
    * স্বাপিং করবে: `[3, 5, 4, 2, 8]`
        

### দ্বিতীয় পাস (Second Pass)

5. **স্টেপ ২.১:**
    
    * তুলনা: `[3, 5]` ⟶ 3 &lt; 5
        
    * স্বাপিং নেই: `[3, 5, 4, 2, 8]`
        
6. **স্টেপ ২.২:**
    
    * তুলনা: `[5, 4]` ⟶ 5 &gt; 4
        
    * স্বাপিং করবে: `[3, 4, 5, 2, 8]`
        
7. **স্টেপ ২.৩:**
    
    * তুলনা: `[5, 2]` ⟶ 5 &gt; 2
        
    * স্বাপিং করবে: `[3, 4, 2, 5, 8]`
        

### তৃতীয় পাস (Third Pass)

8. **স্টেপ ৩.১:**
    
    * তুলনা: `[3, 4]` ⟶ 3 &lt; 4
        
    * স্বাপিং নেই: `[3, 4, 2, 5, 8]`
        
9. **স্টেপ ৩.২:**
    
    * তুলনা: `[4, 2]` ⟶ 4 &gt; 2
        
    * স্বাপিং করবে: `[3, 2, 4, 5, 8]`
        

### চতুর্থ পাস (Fourth Pass)

10. **স্টেপ ৪.১:**
    
    * তুলনা: `[3, 2]` ⟶ 3 &gt; 2
        
    * স্বাপিং করবে: `[2, 3, 4, 5, 8]`
        

### চূড়ান্ত ফলাফল (Final Result)

* সর্টেড অ্যারে: `[2, 3, 4, 5, 8]`
    

### সুবিধা ও অসুবিধা (Pros and Cons):

**সুবিধা:**

* খুব সহজ ইমপ্লিমেন্টেশন
    
* স্থিতিশীল (stable) সর্টিং অ্যালগরিদম
    
* ছোট অ্যারের জন্য ভালো পারফরম্যান্স
    

**অসুবিধা:**

* বড় অ্যারের জন্য ধীর (O(n²) টাইম কমপ্লেক্সিটি)
    
* প্রতিটি এলিমেন্টের জন্য অনেক swap করতে হয়
    

# 2.2 Implementation and Optimization (Detailed Breakdown)

## 1\. বেসিক ইমপ্লিমেন্টেশন বিশ্লেষণ

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735549406100/f2674309-2c63-42e4-95c3-d0c2fecfb0b2.png align="center")

## 2\. Code অ্যানালাইসিস

```java
procedure bubbleSort(array)
    n = length(array)
    swapped = false
    
    // বাইরের লুপ: n-1 বার চলবে
    for i from 0 to n-1
        swapped = false
        
        // ভিতরের লুপ: পাশাপাশি এলিমেন্ট কম্পেয়ার করে
        for j from 0 to n-1-i
            // পাশাপাশি দুইটা এলিমেন্ট কম্পেয়ার
            if array[j] > array[j+1]
                // স্বাপিং লজিক
                temp = array[j]
                array[j] = array[j+1]
                array[j+1] = temp
                swapped = true
        
        // Early Termination Check
        if not swapped
            break
            
    return array
```

### Explanation:

1. **ইনিশিয়ালাইজেশন:**
    
    ```java
    n = length(array)
    swapped = false
    ```
    
    * `n` স্টোর করে অ্যারের সাইজ
        
    * `swapped` ট্র্যাক করে কোন স্বাপিং হয়েছে কিনা
        
2. **বাইরের লুপ:**
    
    ```java
    for i from 0 to n-1
    ```
    
    * প্রতি পাসে একটি করে বড় এলিমেন্ট সঠিক পজিশনে যায়
        
    * `n-1` পাস প্রয়োজন (সর্বোচ্চ)
        
3. **ভিতরের লুপ:**
    
    ```java
    for j from 0 to n-1-i
    ```
    
    * পাশাপাশি এলিমেন্ট কম্পেয়ার করে
        
    * প্রতি পাসে শেষের `i` সংখ্যক এলিমেন্ট সর্টেড থাকে
        
4. **কম্পেয়ারিসন ও স্বাপিং:**
    
    ```java
    if array[j] > array[j+1]
        temp = array[j]
        array[j] = array[j+1]
        array[j+1] = temp
    ```
    
    * পাশাপাশি এলিমেন্ট তুলনা করে
        
    * বড় এলিমেন্টকে ডানে সরায়
        

## 3\. অপ্টিমাইজেশন টেকনিক

### Early Termination:

```python
swapped = false
for i from 0 to n-1
    if not swapped
        break
```

**কিভাবে কাজ করে:**

* যদি কোন পাসে স্বাপিং না হয়, অ্যারে সর্টেড
    
* অতিরিক্ত পাস এড়িয়ে যায়
    

### বাইডাইরেকশনাল বাবল সর্ট:

```python
while left < right
    # Forward pass
    for i from left to right
        compare and swap if needed
    right -= 1
    
    # Backward pass
    for i from right to left
        compare and swap if needed
    left += 1
```

**উন্নত বৈশিষ্ট্য:**

* দুই দিক থেকে সর্টিং করে
    
* টার্টল (ছোট) এবং রেবিট (বড়) এলিমেন্ট দ্রুত সরে
    

## 4\. মেমরি ব্যবহার বিশ্লেষণ

### স্ট্যাক মেমরি:

* লুপ ভ্যারিয়েবল (`i`, `j`)
    
* স্বাপিং এর জন্য `temp` ভ্যারিয়েবল
    
* `swapped` ফ্ল্যাগ
    

### হিপ মেমরি:

* শুধু ইনপুট অ্যারে
    
* কোন অতিরিক্ত অ্যারে প্রয়োজন নেই
    

## 5\. কমপ্লেক্সিটি অ্যানালাইসিস

### টাইম কমপ্লেক্সিটি ব্রেকডাউন:

1. **বেস্ট কেস - O(n):**
    
    ```java
    [1, 2, 3, 4, 5]  # Already sorted
    ```
    
    * একটি পাস
        
    * n-1 কম্পেয়ারিসন
        
    * কোন স্বাপিং নেই
        
2. **ওয়ার্স্ট কেস - O(n²):**
    
    ```java
    [5, 4, 3, 2, 1]  # Reverse sorted
    ```
    
    * n(n-1)/2 কম্পেয়ারিসন
        
    * n(n-1)/2 স্বাপিং
        
3. **অ্যাভারেজ কেস - O(n²):**
    
    ```java
    [3, 1, 4, 5, 2]  # Random order
    ```
    
    * n(n-1)/4 স্বাপিং (অ্যাভারেজ)
        

# 3.1 Selection Sort সিলেকশন সর্ট

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735558619483/40802cb7-51d4-4367-932f-2d8d1a479cd5.png align="center")

## Basic Concept

সিলেকশন সর্ট একটি সরল কিন্তু কার্যকর সর্টিং অ্যালগরিদম। এর নাম থেকেই বোঝা যায় এটি "সিলেকশন" বা নির্বাচনের মাধ্যমে কাজ করে।

### কীভাবে কাজ করে:

1. **মিনিমাম এলিমেন্ট খোঁজা:**
    
    ```python
    array = [7, 3, 5, 2, 4]
    # প্রথম পাস:
    minimum = 2  # সবচেয়ে ছোট নাম্বার খুঁজে পাওয়া গেল
    ```
    
2. **সর্টেড পোর্শন তৈরি:**
    
    ```python
    # 2 কে প্রথম পজিশনে আনা
    [2 | 3, 5, 7, 4]  # | এর বাম পাশে সর্টেড অংশ
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735558744795/6cb2e51a-5c7f-4fd2-afa3-65787356d1a5.png align="center")

### 1\. তাস খেলার কার্ড সাজানোর উদাহরণ:

ধরুন আপনার হাতে ৫টি কার্ড আছে: \[7, 3, 5, 2, 4\]

**প্রথম ধাপ:**

* আপনি সব কার্ড দেখে সবচেয়ে ছোট কার্ডটি খুঁজবেন
    
* এখানে 2 হলো সবচেয়ে ছোট
    
* 2 কে প্রথম পজিশনে নিয়ে আসবেন
    

```python
[2 | 7, 3, 5, 4]  # 2 এখন সঠিক জায়গায়
```

**দ্বিতীয় ধাপ:**

* বাকি কার্ড \[7, 3, 5, 4\] থেকে আবার সবচেয়ে ছোট খুঁজবেন
    
* 3 এখন সবচেয়ে ছোট
    
* 3 কে দ্বিতীয় পজিশনে আনবেন
    

```python
[2, 3 | 7, 5, 4]  # 3 এখন সঠিক জায়গায়
```

### 2\. লাইব্রেরি বই সাজানোর উদাহরণ:

ধরুন আপনি শেল্ফে বই সাজাচ্ছেন:

1. প্রথমে সব বই দেখে সবচেয়ে পাতলা বইটি বের করেন
    
2. সেটি প্রথমে রাখেন
    
3. বাকি বই থেকে আবার সবচেয়ে পাতলা বইটি খুঁজেন
    
4. এভাবে ক্রমানুসারে সাজিয়ে যান
    

### 3\. কেন এটি সিলেকশন সর্ট:

1. **নির্বাচন প্রক্রিয়া:**
    
    * প্রতিবার অনসর্টেড অংশ থেকে সবচেয়ে ছোট এলিমেন্ট নির্বাচন করি
        
    * এটি যেন একজন ক্রেতা দোকানে সবচেয়ে সস্তা জিনিস খুঁজে কেনার মতো
        
2. **স্থির সিদ্ধান্ত:**
    
    * একবার মিনিমাম পাওয়া গেলে সেটি নিশ্চিতভাবে সঠিক জায়গায় যায়
        
    * আর পরিবর্তন করা লাগে না
        
3. **ধাপে ধাপে সর্টেড অংশ বাড়ে:**
    
    ```python
    [7, 3, 5, 2, 4]  # শুরুতে
    [2 | 7, 3, 5, 4] # একটি সর্টেড
    [2, 3 | 7, 5, 4] # দুইটি সর্টেড
    [2, 3, 4 | 7, 5] # তিনটি সর্টেড
    ```
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735560524977/094ed0c5-674b-4510-8c5e-7f863e949d12.png align="center")

আবার, আমরা যখন তাস খেলি, তখন কিভাবে কার্ডগুলো সাজাই সেটা দিয়ে শুরু করি। ধরুন আপনার হাতে ৫টা কার্ড আছে:

`[7, 2, 5, 4, 1]`

এখন আপনি কি করবেন?

1. **প্রথম ধাপ:** সবচেয়ে ছোট নাম্বারটা খুঁজবেন (এখানে 1)
    
2. **দ্বিতীয় ধাপ:** সেটাকে বাম পাশে নিয়ে আসবেন
    
3. **তৃতীয় ধাপ:** বাকি নাম্বারগুলো থেকে আবার সবচেয়ে ছোট খুঁজবেন
    

### কিভাবে কাজ করে:

ধরুন আপনি বইয়ের তাক গুছাচ্ছেন। প্রথমে সব বই দেখে সবচেয়ে পাতলা বইটা বের করলেন। এটাকে প্রথমে রাখলেন। এরপর বাকি বইগুলো থেকে আবার সবচেয়ে পাতলা বইটা খুঁজলেন। এভাবে একটা একটা করে সব বই সাজিয়ে ফেললেন।

সিলেকশন সর্টও ঠিক একইভাবে কাজ করে:

1. **খোঁজার পদ্ধতি:**
    
    ```python
    [7, 2, 5, 4, 1]  # প্রথমে সব দেখব
    # 1 সবচেয়ে ছোট
    [1 | 7, 2, 5, 4]  # 1 কে প্রথমে আনলাম
    ```
    
2. **আবার খোঁজা:**
    
    ```python
    [1 | 7, 2, 5, 4]  # এখন এই অংশ থেকে খুঁজব
    # 2 সবচেয়ে ছোট
    [1, 2 | 7, 5, 4]  # 2 কে দ্বিতীয় পজিশনে আনলাম
    ```
    

### কোড:

```python
numbers = [7, 2, 5, 4, 1]

# সবগুলো নাম্বার একবার করে দেখব
for i in range(len(numbers)):
    
    # সবচেয়ে ছোট নাম্বারের পজিশন মনে রাখব
    smallest_position = i
    
    # বাকি নাম্বারগুলো চেক করব
    for j in range(i+1, len(numbers)):
        if numbers[j] < numbers[smallest_position]:
            smallest_position = j
    
    # ছোট নাম্বারটা সামনে নিয়ে আসব
    numbers[i], numbers[smallest_position] = numbers[smallest_position], numbers[i]
```

### কেন সিলেকশন সর্ট :

1. **সহজ বোঝা যায়:**
    
    * প্রতিবার শুধু সবচেয়ে ছোট জিনিসটা খুঁজতে হয়
        
    * যেভাবে আমরা স্বাভাবিকভাবে জিনিস সাজাই, ঠিক সেভাবেই কাজ করে
        
2. **কম জায়গা লাগে:**
    
    * আলাদা কোন জায়গা লাগে না
        
    * যেখানে আছে সেখানেই সাজানো হয়
        
3. **নিশ্চিত সাজানো:**
    
    * একবার কোন নাম্বার সঠিক জায়গায় গেলে আর নড়ে না
        
    * ধীরে ধীরে সামনের দিক থেকে সব ঠিক হতে থাকে
        

## কীভাবে বাবল সর্ট থেকে আলাদা

1. **স্বাপিং(Swaping) ফ্রিকোয়েন্সি:**
    
    * বাবল সর্ট: প্রতি তুলনায় swap করতে পারে
        
    * সিলেকশন সর্ট: প্রতি পাসে শুধু একবার swap করে
        
2. **মেমরি অ্যাক্সেস:**
    
    ```python
    # বাবল সর্ট: প্রতি তুলনায় swap 
    if arr[j] > arr[j+1]:
        swap(arr[j], arr[j+1])  # অনেক swap 
    
    # সিলেকশন সর্ট: পাস প্রতি একবার swap 
    min_idx = find_minimum(arr, i)
    swap(arr[i], arr[min_idx])  # কম swap
    ```
    

## কেন সিলেকশন সর্ট ব্যবহার করব?

1. **সহজ ইমপ্লিমেন্টেশন:**
    
    * স্ট্রেইটফরওয়ার্ড লজিক
        
    * সহজে ডিবাগ করা যায়
        
2. **কম মেমরি** swap **:**
    
    * n সাইজের অ্যারের জন্য সর্বোচ্চ n-1 স্বাপ
        
    * মেমরি-কনস্ট্রেইনড সিস্টেমে ভালো
        

## 4\. ইনসার্শন সর্ট | রিমার লাইব্রেরি গল্প

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735576320809/912a238a-b77a-4cb7-b524-9892c12bad37.png align="center")

রিমা নতুন লাইব্রেরি সহকারী। আজ তার প্রথম দিন। লাইব্রেরিয়ান তাকে একটা কাজ দিলেন - পাঁচটা বই সাজাতে হবে নম্বর অনুযায়ী (ছোট থেকে বড়)।

বইগুলোর নম্বর: `[5, 2, 8, 1, 4]`

#### রিমা কিভাবে কাজ করল:

**প্রথম বই:**

```python
[5]     # প্রথম বইটা হাতে নিল
```

রিমা ভাবল: "প্রথম বই তো সাজানোই আছে!"

**দ্বিতীয় বই:**

```python
[5 | 2]     # 2 নম্বর বইটা হাতে নিল
[2, 5]      # 2 ছোট, তাই 5 এর আগে রাখল
```

রিমা ভাবল: "2 ছোট, তাই 5 এর আগে রাখব"

**তৃতীয় বই:**

```python
[2, 5 | 8]   # 8 নম্বর বইটা হাতে নিল
[2, 5, 8]    # 8 বড়, তাই শেষে রাখল
```

রিমা ভাবল: "8 বড়, ঠিক আছে শেষেই থাকবে"

**চতুর্থ বই:**

```python
[2, 5, 8 | 1]    # 1 নম্বর বইটা হাতে নিল
[1, 2, 5, 8]     # 1 সবার ছোট, প্রথমে রাখল
```

রিমা ভাবল: "1 তো সবার ছোট! একদম প্রথমে রাখতে হবে"

**শেষ বই:**

```python
[1, 2, 5, 8 | 4]   # 4 নম্বর বইটা হাতে নিল
[1, 2, 4, 5, 8]    # 2 আর 5 এর মাঝে রাখল
```

রিমা ভাবল: "4 হচ্ছে 2 এর বড় কিন্তু 5 এর ছোট, তাই মাঝে রাখব"

### এই গল্প থেকে কি শিখলাম?

1. **একটা একটা করে নেওয়া:**
    
    * রিমা যেমন একটা একটা বই নিল
        
    * কম্পিউটারও তাই করে
        
2. **তুলনা করে সঠিক জায়গায় রাখা:**
    
    * রিমা প্রতিটা বই আগের বইগুলোর সাথে তুলনা করে রাখল
        
    * ঠিক যেমন আমরা তাস খেলার সময় করি
        
3. **ধৈর্য ধরে কাজ করা:**
    
    * রিমা ধীরে ধীরে সব বই সাজাল
        
    * একসাথে সব করার চেষ্টা করেনি
        

### কখন ব্যবহার করব?

1. **অল্প জিনিস সাজাতে:**
    
    * ৫০টার কম জিনিস
        
    * যেমন: ক্লাসের খাতা সাজানো
        
2. **প্রায় সাজানো জিনিস:**
    
    * যেমন: আগের দিনের সাজানো বই
        
    * শুধু কয়েকটা জায়গা বদলাতে হবে
        
3. **নতুন জিনিস যোগ করতে:**
    
    * যেমন: নতুন বই লাইব্রেরিতে যোগ করা
        
    * লাইভ ডেটা সাজানো
        

## Cycle Sort:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735964030629/3e0309b6-22fc-4192-816c-b78d33393cd1.png align="center")

আমরা এর আগে Bubble Sort, Selection Sort এবং Insertion Sort এ দেখেছি যে প্রতিবার দুইটি element compare করে swap করতে হয়। কিন্তু আজকের algorithm টি একটু অন্যরকম - এটি প্রতিটি element কে শুধুমাত্র একবারই তার সঠিক জায়গায় রাখে!

2. **Problem Introduction**: চলুন প্রথমে Cycle Sort এর মূল concept টা বুঝি।
    

<mark>Main Goal: প্রতিটি element কে minimum write operation ব্যবহার করে সঠিক position এ বসানো।</mark>

### Key Features:

• Minimum Memory Writes: প্রতিটি element কে শুধুমাত্র একবার write করা হয়

• In-Place Sorting: Extra space লাগে না

• Time Complexity: O(n²) - worst, average, and best case

• Space Complexity: O(1)

• Not Stable: Same value elements এর original order maintain করে না

### কেন Cycle Sort শিখবো?

1\. Memory write operation কম হওয়ায় flash memory বা SSD তে efficient

2\. Real-time applications এ useful যেখানে memory write cost বেশি

3\. Theoretical understanding এর জন্য cycle concept খুবই important

### **Real-world Example or Analogy**: "চলুন একটা মজার গেম দিয়ে Cycle Sort বুঝি!

Musical Chair Sorting Game: ধরুন, ৫টি চেয়ারে ৫ জন student বসে আছে। প্রত্যেকের হাতে তাদের roll number লেখা card: \[3, 1, 5, 2, 4\]

### Game Rules:

1\. প্রথম student (roll 3) উঠে দেখবে তার correct position (3rd chair)

2\. 3rd chair এ যে আছে (roll 5) তাকে তার correct position এ যেতে হবে

3\. এভাবে একটা cycle create হয়: • 3 → 5 → 4 → 2 → 1 → 3

Let's visualize: Initial: \[3, 1, 5, 2, 4\] Step 1: \[1, 3, 5, 2, 4\] (3 finds its position) Step 2: \[1, 2, 5, 3, 4\] (5 moves) Step 3: \[1, 2, 3, 5, 4\] (4 moves) Final: \[1, 2, 3, 4, 5\]

Key Insight: প্রতিটি student একবারই move করে!

### চলুন Step-by-Step বুঝি:

**Step 1: Cycle Detection**

• array\[5, 4, 3, 2, 1\] নিয়ে শুরু করি

• First element: 5

• 5 এর correct position: 4 (কারণ 4টি element 5 থেকে ছোট)

• 5 কে position 4 এ রাখি: \[1, 4, 3, 2, 5\]

**Step 2: Continue Cycle**

• Now displaced element: 1

• 1 এর correct position: 0

• 1 কে position 0 এ রাখি: \[1, 4, 3, 2, 5\]

Step 3: Next Cycle

• New start: 4 (index 1)

• Process repeats

### Visualization for \[5, 4, 3, 2, 1\]:

Initial: \[5, 4, 3, 2, 1\]

Cycle 1: \[1, 4, 3, 2, 5\]

Cycle 2: \[1, 2, 3, 4, 5\]

### Memory Write Analysis:

• প্রতিটি element maximum একবার write হয়

• Total writes = n (best case) to n-1 (worst case)

• Compare this with Bubble Sort: O(n²) writes!"

### **Practical Tips and Extended Insights**: Advanced Tips:

Optimization Techniques:

• Write operation আরও কমানোর জন্য duplicate check করুন

• Small array তে overhead বেশি, large array তে better