---
title: "Strings and StringBuilder in Java: A Comprehensive Guide In Bangla"
seoTitle: "Java Strings vs StringBuilder Differences"
seoDescription: "Java's String is immutable and uses a string pool; StringBuilder is mutable, allowing efficient string handling and better memory management in bangla with "
datePublished: Sat Jan 04 2025 21:00:46 GMT+0000 (Coordinated Universal Time)
cuid: cm5io4s7m000509mkeyug4shc
slug: strings-and-stringbuilder-in-java-a-comprehensive-guide-in-bangla
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1735971468142/e0ea6c8b-eca2-4e5d-8dae-21a1c0be5709.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1735971476194/5fd6d663-b9b5-49c1-bb79-eb7e111d257e.png
tags: java, string, bangla, ibrahimsifat

---

কল্পনা করো তুমি "দারাজ" এ কাজ করছো। তোমার কাজ হচ্ছে প্রোডাক্টের নাম, প্রাইস, ডিসক্রিপশন ম্যানেজ করা। এখন দেখো - প্রোডাক্টের নাম "Samsung M33" কে তুমি যেভাবে স্টোর করছো, ঠিক একইভাবে Java-তেও String ব্যবহার করে টেক্সট স্টোর করা হয়।

## String: প্রথম পরিচয়

### 1\. স্ট্রিং কি আসলে?

```java
// একটা প্রোডাক্টের ইনফরমেশন স্টোর করছি
String productName = "Samsung M33";
String description = "Best gaming phone";
String price = "25000 TK";
```

এখানে `productName`, `description`, `price` - সবই String। কিন্তু এদের মধ্যে পার্থক্য কি?

* `productName`: শুধু টেক্সট + নাম্বার
    
* `description`: শুধু টেক্সট
    
* `price`: নাম্বার + টেক্সট
    

### 2\. রিয়েল লাইফ অ্যানালজি

মনে করো তুমি একটা চিঠি লিখছো। চিঠিটা একবার লিখে ফেললে কি আর rubber দিয়ে মুছে চেইঞ্জ করতে পারবে? না! ঠিক তেমনি String ও <mark>immutable (অপরিবর্তনীয়)।</mark>

```java
String letter = "Dear Friend";
letter.toUpperCase();  // নতুন String তৈরি হবে, আগেরটা চেইঞ্জ হবে না
System.out.println(letter);  // এখনো "Dear Friend" প্রিন্ট করবে
```

## String নিয়ে game খেলি

### 1\. স্ট্রিং তৈরি করার Options:

```java
// Option ১: সরাসরি ভ্যালু দেওয়া (String Literal)
String name1 = "Rakib";

// Option ২: নতুন object তৈরি করা
String name2 = new String("Rakib");

// এখন প্রশ্ন: name1 == name2 কি true নাকি false?
System.out.println(name1 == name2);  // false! কেন? পরে জানবো!
```

### 2\. স্ট্রিং ম্যানিপুলেশন:

```java
// ধরো তুমি ইউজার থেকে ইনপুট নিলে
String userInput = "    RaKiB123   ";

// এখন এই ইনপুট কে ক্লিন করার দরকার
String cleanName = userInput.trim()  // extra space বাদ
                          .toLowerCase()  // সব ছোট হাতের
                          .replace("123", "");  // নাম্বার বাদ

System.out.println(cleanName);  // "rakib" প্রিন্ট করবে
```

## Populear কিছু String Methods

### 1\. substring(): স্ট্রিং এর একটা অংশ নেওয়া

```java
String text = "Bangladesh";
System.out.println(text.substring(0, 6));  // "Bangla" প্রিন্ট করবে
```

### 2\. split(): স্ট্রিং কে ভাগ করা

```java
String fruits = "Apple,Banana,Orange";
String[] fruitArray = fruits.split(",");
// fruitArray = ["Apple", "Banana", "Orange"]
```

### 3\. charAt(): নির্দিষ্ট পজিশনের ক্যারেক্টার

```java
String name = "Rakib";
char firstLetter = name.charAt(0);  // 'R'
```

## Common Interview Questions

1\. **প্রশ্ন:** String Literal এবং new String() এর মধ্যে পার্থক্য কি?

```java
String s1 = "Hello";  // String Literal
String s2 = new String("Hello");  // new keyword
```

**উত্তর:** String Literal String Pool এ store হয়, new keyword নতুন memory location এ object create করে।

2\. **প্রশ্ন:** String Immutable কেন? **উত্তর:**

* Security: একবার create করলে change করা যায় না
    
* Thread Safety: Multiple thread একই String use করতে পারে
    
* Performance: String Pool optimization এর জন্য
    

## Quiz Time!

1\. নিচের কোড এর আউটপুট কি হবে?

```java
String s1 = "Hello";
String s2 = "Hel" + "lo";
System.out.println(s1 == s2);  // true নাকি false?
```

2\. কেন নিচের কোড ভুল?

```java
String str = "Hello";
if(str == "Hello") {
    System.out.println("Same!");
}
```

# স্ট্রিং ক্রিয়েশন এবং মেমরি ম্যানেজমেন্ট

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735966094393/68e5c992-9342-499d-b606-d1fac7974118.png align="center")

## 1\. String Literals

ধরো তুমি একটা লাইব্রেরিতে গেছো। সেখানে দুইটা বই আছে - "Programming Java"। এখন তুমি যদি দুইটা বই একই রাখতে চাও, লাইব্রেরিয়ান কি দুইটা আলাদা জায়গায় রাখবে? না! একটা জায়গায় রাখবে, কারণ দুইটা একই বই।

ঠিক একইভাবে Java-তে String Literal কাজ করে:

```java
// একই String দুইবার ডিক্লেয়ার করলাম
String book1 = "Programming Java";
String book2 = "Programming Java";

// এখন মজার ব্যাপার হলো
System.out.println(book1 == book2);  // true! কারণ দুইটা একই মেমরি লোকেশন
```

## 2\. String Creation with 'new' Keyword

এবার আরেকটা উদাহরণ দেখি। ধরো তুমি প্রিন্টার দিয়ে সেই "Programming Java" বইটা দুইবার প্রিন্ট করলে। এখন দুইটা কপি আলাদা জায়গায় থাকবে, তাই না?

```java
// new keyword ব্যবহার করে নতুন String object তৈরি
String book3 = new String("Programming Java");
String book4 = new String("Programming Java");

System.out.println(book3 == book4);  // false! কারণ দুইটা আলাদা মেমরি লোকেশন
```

## 3\. String Pool

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735966428310/b6e50617-273a-46d2-8e49-b161c56fc359.png align="center")

String Pool কে আমরা একটা ম্যাজিক পুকুর হিসেবে ভাবতে পারি। এই পুকুরে:

* একই String শুধু একবারই থাকতে পারে
    
* নতুন String literal তৈরি করলে Java আগে পুকুরে খুঁজে দেখে
    
* যদি পায়, সেটাই রিটার্ন করে
    
* না পেলে, নতুন করে তৈরি করে
    

```java
String s1 = "Hello";  // পুকুরে "Hello" তৈরি হলো
String s2 = "Hello";  // পুকুর থেকে আগের "Hello" পেয়ে গেলো
String s3 = new String("Hello");  // পুকুরের বাইরে নতুন "Hello" তৈরি হলো
```

## 4\. Memory Allocation

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735966819873/9cb36e5d-0748-4697-9cfc-9211bfde4f8c.png align="center")

### 1\. Memory Types in Java

### Stack Memory

* মূলত primitive types এবং object references স্টোর করে
    
* LIFO (Last In First Out) প্রিন্সিপালে কাজ করে
    
* Access speed বেশি fast
    
* Thread-safe (প্রত্যেক thread এর নিজস্ব stack থাকে)
    

### Heap Memory

* সব Object এবং Arrays এখানে স্টোর হয়
    
* Garbage Collection এখানে হয়
    
* Shared memory (সব thread শেয়ার করে)
    
* String Pool এখানেই থাকে
    

### 2\. Step by Step Memory Allocation Process

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735966841788/0a935b78-a843-4395-9d84-f4c803b104d4.png align="center")

### Step 1: Variable Declaration

```
Strnig name= "Rakib";
```

কি কি ঘটে:

1. **Stack Memory তে:**
    
    * `name` নামে একটি reference variable তৈরি হয়
        
    * এই variable 4 bytes জায়গা নেয় (32-bit system এ)
        
2. **Heap Memory তে:**
    
    * String Pool চেক করে "Rakib" আছে কিনা
        
    * না থাকলে নতুন String object তৈরি করে
        
    * Object এ char array হিসেবে "Rakib" store করে
        
3. **Reference Link:**
    
    * Stack এর `name` variable টি Heap এর String object কে point করে
        

## 5\. String Immutability: একবার লিখলেই চিরকাল!

### Immutability এর কারণ:

1. **সিকিউরিটি:**
    

```java
void login(String username, String password) {
    // password কেউ modify করতে পারবে না
    // কারণ String immutable
}
```

2. **Thread Safety:**
    

```java
// Multiple threads একই String ব্যবহার করতে পারে
// কোন thread এটা modify করতে পারবে না
public class SharedString {
    private String sharedText = "Hello";
}
```

3. **Caching:**
    

```java
String s1 = "Hello";  // String Pool এ store হয়
String s2 = "Hello";  // আগের value reuse করে
```

## Performance Implications

### Good প্র্যাক্টিস:

```java
// Good ✅
String name = "Rakib";  // String Pool ব্যবহার করে

// Bad ❌
String name = new String("Rakib");  // নতুন object তৈরি করে
```

### লুপে String Concatenation:

## Interview Questions

1. **প্রশ্ন:** String Pool কি? **উত্তর:** String Pool হল JVM এর Heap Memory তে একটি special memory space যেখানে String literals store করা হয়।
    
2. **প্রশ্ন:** `String s1 = new String("hello");` এই কোডে কয়টা object create হয়? **উত্তর:** ২টা:
    
    * একটা String Pool এ "hello"
        
    * আরেকটা Heap এ new String() দিয়ে
        

## Quiz

1. নিচের কোডের আউটপুট কি হবে?
    

```java
String s1 = "Hello";
String s2 = "Hel" + "lo";
String s3 = "Hel";
String s4 = s3 + "lo";

System.out.println(s1 == s2);  // true
System.out.println(s1 == s4);  // false
```

# String Comparison

ধরো তুমি Facebook এর প্রোফাইলে লগইন করতে চাচ্ছো। তোমার ইউজারনেম "rakib123" এবং পাসওয়ার্ড "pass123"। এখন Facebook কিভাবে চেক করবে যে তুমি সঠিক ইউজারনেম-পাসওয়ার্ড দিয়েছো? এখানেই String comparison এর ব্যবহার!

## 1 String Comparison Using == Operator

### Wrong Way ❌

```java
javaCopyString user1 = "rakib123";
String user2 = new String("rakib123");

if(user1 == user2) {
    System.out.println("Same user!");  // এটা execute হবে না!
} else {
    System.out.println("Different users!");  // এটা execute হবে
}
```

### কেন এটা ভুল?

মনে করো দুইটা আম আছে। একটা আম তোমার বাড়ির বাগানে, আরেকটা পাশের বাড়ির বাগানে। দুইটা আম দেখতে একই রকম। কিন্তু location আলাদা। `==` operator ঠিক এভাবেই location চেক করে, content না!

## 2 String Comparison Using .equals() Method

### Right Way ✅

```java
javaCopyString password1 = "pass123";
String password2 = new String("pass123");

if(password1.equals(password2)) {
    System.out.println("Correct password!");  // এটা execute হবে
} else {
    System.out.println("Wrong password!");
}
```

ধরেন আপনার দুইটা বন্ধু - রাকিব আর সাকিব। দুজনের নাম শুনতে প্রায় একই রকম, কিন্তু দুজন আলাদা। ঠিক তেমনি Java-তে String এর তুলনা করার সময়ও আমাদের বুঝতে হবে - দুটি String দেখতে একই হলেও তারা আসলে একই কিনা!

## 1\. == দিয়ে Comparison (মেমরি লোকেশন চেক)

মনে করেন আপনার দুটি বই আছে - দুটোই "Java Programming"। একটা আপনার ঘরে, আরেকটা আপনার দোকানে। দেখতে একই, কিন্তু জায়গা আলাদা।

```java
String book1 = "Java";  // ঘরের বই
String book2 = new String("Java");  // দোকানের বই

// == দিয়ে চেক করলে false আসবে, কারণ জায়গা আলাদা!
```

## 2\. equals() দিয়ে Comparison (কনটেন্ট চেক)

এবার ভাবুন, আপনি দুটো বইয়ের পাতা খুলে দেখছেন - লেখাগুলো হুবহু একই কিনা।

```java
// .equals() true রিটার্ন করবে, কারণ কনটেন্ট (Text) একই!
String name1 = "Rakib";
String name2 = new String("Rakib");
name1.equals(name2)  // true
```

## 3\. কেস সেনসিটিভ আর ইনসেনসিটিভ Comparison

ধরেন, আপনি ইমেইল চেক করছেন:

```java
// rakib@gmail.com আর RAKIB@GMAIL.COM আসলে একই ইমেইল
// equalsIgnoreCase() ব্যবহার করে ছোট-বড় হাতের তফাত ignore করা যায়
```

## 4\. String জোড়া লাগানো (Concatenation)

মনে করেন, আপনি নাম আর পদবী জুড়ে ফুল নাম বানাচ্ছেন:

```java
// সহজ পদ্ধতি (+ অপারেটর)
firstName + " " + lastName

// দ্রুত পদ্ধতি (StringBuilder)
StringBuilder দিয়ে একসাথে যোগ করা (লুপের জন্য ভালো)
```

## গুরুত্বপূর্ণ টিপস:

1. **সাধারণ** Comparison **জন্য:**
    
    * সবসময় `.equals()` ব্যবহার করুন
        
    * `==` ব্যবহার করবেন না
        
2. **ইমেইল/ইউজারনেম চেকের জন্য:**
    
    * `.equalsIgnoreCase()` ব্যবহার করুন
        
3. **অনেক String জোড়া(Concatination) দেওয়ার জন্য:**
    
    * StringBuilder ব্যবহার করুন
        
    * অপারেটর এড়িয়ে চলুন
        

## মনে রাখার বিষয়:

1. `==` শুধু মেমরি লোকেশন চেক করে
    
2. `.equals()` কনটেন্ট চেক করে
    
3. `.equalsIgnoreCase()` ছোট-বড় হাতের তফাত ইগনোর করে
    
4. অনেক String জোড়ার **(Concatination)** জন্য StringBuilder ব্যবহার করুন
    

চলুন String Methods এবং Manipulation নিয়ে মজার একটা ক্লাস শুরু করি! 🎯

# String Methods এবং Manipulation

কল্পনা করো তুমি Instagram এ একটা পোস্ট করতে চাও। পোস্টে:

* ক্যাপশন থাকবে
    
* হ্যাশট্যাগ থাকবে
    
* @mention থাকবে
    

এই সবকিছু ম্যানেজ করার জন্য String methods লাগবে। চলো দেখি কিভাবে করা যায়!

```java
String caption = "   Having fun at Cox's Bazar! @rakib #beach #travel #bangladesh   ";
```

## 1\. Essential String Methods

### Basic Methods Showcase:

```java
String text = "Bangladesh";

// 1. length(): স্ট্রিং এর লেংথ
System.out.println(text.length());  // 10

// 2. charAt(): নির্দিষ্ট পজিশনের ক্যারেক্টার
System.out.println(text.charAt(0));  // 'B'

// 2. substring(): স্ট্রিং এর একটা অংশ
System.out.println(text.substring(0, 6));  // "Bangla"
System.out.println(text.substring(6));     // "desh"

// Real-life Example:
String email = "rakib.ahmed@gmail.com";
String username = email.substring(0, email.indexOf("@"));  // "rakib.ahmed"
```

## 2\. String Transformation Methods

### Instagram Post Cleaner:

```java
String post = "   Having FUN at COX'S BAZAR!   ";

// 1. trim(): extra spaces বাদ দেয়
post = post.trim();  // "Having FUN at COX'S BAZAR!"

// 2. toLowerCase(): সব ছোট হাতের
post = post.toLowerCase();  // "having fun at cox's bazar!"

// 3. toUpperCase(): সব বড় হাতের
String hashtag = "#travel";
System.out.println(hashtag.toUpperCase());  // "#TRAVEL"
```

## 4\. String Searching Methods

### Social Media Mention Finder:

```java
String post = "Hello @rakib! Have you seen @karim's new post?";

// 1. indexOf(): প্রথম occurrence খুঁজে
int firstMention = post.indexOf("@");  // 6

// 2. lastIndexOf(): শেষ occurrence খুঁজে
int lastMention = post.lastIndexOf("@");  // 28

// 3. contains(): কোন টেক্সট আছে কিনা চেক
boolean hasMention = post.contains("@");  // true
```

## 4\. String Replacement Methods

### Censorship System:

```java
String comment = "This is a bad word post!";

// 1. replace(): সাধারণ replacement
comment = comment.replace("bad", "good");  // "This is a good word post!"

// 2. replaceAll(): regex সাপোর্ট করে
String text = "My phone: 017-1234-5678";
text = text.replaceAll("\\d", "*");  // "My phone: ***-****-****"
```

## 5\. String Splitting and Joining

### Hashtag Processor:

```java
String post = "#travel #beach #bangladesh";

// 1. split(): স্ট্রিং কে array তে ভাগ করে
String[] hashtags = post.split(" ");  // ["#travel", "#beach", "#bangladesh"]

// 2. String.join(): array কে স্ট্রিং এ জোড়া
String[] words = {"Cox's", "Bazar", "Beach"};
String location = String.join(" ", words);  // "Cox's Bazar Beach"
```

`substring()` কি mutable?

```java
String str = "Hello";
str.substring(0, 2);  // returns "He" but doesn't modify str
System.out.println(str);  // still prints "Hello"
```

# String Formatting এবং Output

## একটা মজার গল্প দিয়ে শুরু করি

ধরো তুমি একটা বইয়ের দোকানের ম্যানেজমেন্ট সিস্টেম বানাচ্ছো। প্রতিটা বইয়ের:

* নাম
    
* দাম
    
* রেটিং
    
* প্রকাশের তারিখ
    

এগুলো সুন্দর করে প্রিন্ট করতে হবে। চলো দেখি কিভাবে করা যায়!

## 1\. PrintStream Class এবং System.out

### Basic Output Methods:

```java
// 1. println(): নতুন লাইনে প্রিন্ট
System.out.println("Hello World!");

// 2. print(): একই লাইনে প্রিন্ট
System.out.print("Hello ");
System.out.print("World!");

// 3. printf(): formatted প্রিন্ট
System.out.printf("Price: %.2f TK%n", 299.99);
```

## 2\. Pretty Printing Techniques

### টেবিল ফরম্যাট:

```java
public class BookStore {
    public static void printBookTable(List<Book> books) {
        // Header
        System.out.println("╔═══════════════════════════════════════════════╗");
        System.out.println("║              Book Store Inventory             ║");
        System.out.println("╠═══════════════════╦═══════════╦═════════════╣");
        System.out.println("║       Name        ║   Price   ║   Rating    ║");
        System.out.println("╠═══════════════════╬═══════════╬═════════════╣");
        
        // Data Rows
        for (Book book : books) {
            System.out.printf("║ %-17s ║ %9.2f ║ %9.1f/5 ║%n",
                book.getName(), book.getPrice(), book.getRating());
        }
        
        // Footer
        System.out.println("╚═══════════════════╩═══════════╩═════════════╝");
    }
}
```

## 3\. Format Specifiers in Detail

### 1\. Numeric Format Specifiers:

```java
double price = 1234.5678;

// ১. Decimal Format
System.out.printf("Regular: %.2f%n", price);     // 1234.57
System.out.printf("Width: %10.2f%n", price);     //    1234.57
System.out.printf("Left: %-10.2f%n", price);     // 1234.57   
System.out.printf("Grouped: %,d%n", 1234567);    // 1,234,567

// ২. Scientific Notation
System.out.printf("Scientific: %e%n", price);    // 1.234568e+03

// ৩. General Format
System.out.printf("General: %g%n", price);       // 1234.57
```

### 2\. String Format Specifiers:

```java
String name = "Harry Potter";

// ১. Basic String Format
System.out.printf("Name: %s%n", name);           // Harry Potter

// ২. Width Specification
System.out.printf("'%20s'%n", name);             // '         Harry Potter'
System.out.printf("'%-20s'%n", name);            // 'Harry Potter         '

// ৩. Substring
System.out.printf("%.5s%n", name);               // Harry
```

### 3\. Date/Time Format Specifiers:

```java
LocalDateTime now = LocalDateTime.now();

// ১. Date Formats
System.out.printf("%tF%n", now);      // 2024-01-04
System.out.printf("%tD%n", now);      // 01/04/24

// ২. Time Formats
System.out.printf("%tT%n", now);      // 15:30:45
System.out.printf("%tr%n", now);      // 03:30:45 PM

// ৩. Custom Formats
System.out.printf("%tB %td, %tY%n", now, now, now);  // January 04, 2024
```

## 4\. Advanced Formatting Techniques

### 1\. Custom Number Formatting:

```java
public class PriceFormatter {
    public static String formatBDTPrice(double price) {
        NumberFormat formatter = NumberFormat.getCurrencyInstance(
            new Locale("bn", "BD"));
        return formatter.format(price);
    }
}

// Usage
double price = 12345.67;
System.out.println(PriceFormatter.formatBDTPrice(price));  // ৳12,345.67
```

## Interview Questions

1\. **প্রশ্ন:** `System.out.println()` এবং `System.out.printf()` এর মধ্যে পার্থক্য কি? **উত্তর:** `println()` সাধারণ টেক্সট প্রিন্ট করে, `printf()` formatted টেক্সট প্রিন্ট করে। `printf()` format specifiers ব্যবহার করে যেমন `%d`, `%f`, `%s` ইত্যাদি।

2\. **প্রশ্ন:** Format specifier এ precision কিভাবে কন্ট্রোল করা যায়? **উত্তর:** Format specifier এ `.` এর পরে নাম্বার দিয়ে। যেমন: `%.2f` দুই decimal place দেখাবে।

# StringBuilder: সহজ ভাষায় বোঝা যাক

কল্পনা করো তুমি একটা চ্যাট অ্যাপ বানাচ্ছো। ইউজার যখন মেসেজ টাইপ করে, তখন:

* প্রতিটা character টাইপ করার সাথে সাথে text change হয়
    
* Emoji add করতে পারে
    
* Text edit করতে পারে
    

এখন এই কাজগুলো String দিয়ে করলে performance issue হবে। কেন? চলো জানি!

## 1\. What is StringBuilder?

### String vs StringBuilder:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1735969542322/b50ae653-b023-414f-9120-cf0ef0fd8c34.png align="center")

```java
// String এ প্রতিবার নতুন অবজেক্ট তৈরি হয়
String text = "Hello";
text += " World";  // নতুন String object তৈরি হলো

// StringBuilder একই object modify করে
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");  // একই object modify হলো
```

## কেন StringBuilder ব্যবহার করব?

একটা মজার উদাহরণ দিয়ে বুঝি:

```java
public class StringVsStringBuilder {
    public static void main(String[] args) {
        // Test 1: Normal String
        long startTime = System.currentTimeMillis();
        
        String result = "";
        for(int i = 0; i < 10000; i++) {
            result += "Hello";  // প্রতিবার নতুন স্ট্রিং অবজেক্ট তৈরি হচ্ছে 😢
        }
        
        long endTime = System.currentTimeMillis();
        System.out.println("String Time: " + (endTime - startTime) + "ms");
        
        // Test 2: StringBuilder
        startTime = System.currentTimeMillis();
        
        StringBuilder sb = new StringBuilder();
        for(int i = 0; i < 10000; i++) {
            sb.append("Hello");  // একই অবজেক্ট মডিফাই হচ্ছে 😊
        }
        
        endTime = System.currentTimeMillis();
        System.out.println("StringBuilder Time: " + (endTime - startTime) + "ms");
    }
}
```

## 2\. StringBuilder এর সুবিধা

1. **মেমরি ব্যবহার কম:**
    
    * String: প্রতি মডিফিকেশনে নতুন object
        
    * StringBuilder: একই object মডিফাই করে
        
2. **Performance ভালো:**
    
    ```java
    // Bad Practice ❌
    String name = "";
    name += "Mr.";
    name += " ";
    name += "Rakib";
    
    // Good Practice ✅
    StringBuilder name = new StringBuilder();
    name.append("Mr.")
        .append(" ")
        .append("Rakib");
    ```
    
3. **Garbage Collection কম:**
    
    * String এ বেশি object তৈরি হয় = বেশি garbage collection
        
    * StringBuilder এ কম object = কম garbage collection
        

## কখন StringBuilder ব্যবহার করব?

1. **Loop এর ভিতরে String Concatenation:**
    

```java
// Example: CSV File Builder
StringBuilder csvBuilder = new StringBuilder();
for(User user : users) {
    csvBuilder.append(user.getName())
             .append(",")
             .append(user.getEmail())
             .append("\n");
}
```

2. **Dynamic String Building:**
    

```java
// Example: HTML Builder
StringBuilder htmlBuilder = new StringBuilder();
htmlBuilder.append("<html>")
          .append("<head>")
          .append("<title>").append(pageTitle).append("</title>")
          .append("</head>")
          .append("<body>")
          .append(content)
          .append("</body>")
          .append("</html>");
```

### Most Used Methods:

```java
StringBuilder sb = new StringBuilder("Hello");

// ১. append(): যোগ করা
sb.append(" World");           // "Hello World"
sb.append('!');               // "Hello World!"
sb.append(123);               // "Hello World!123"

// ২. insert(): মাঝখানে ঢোকানো
sb.insert(5, " Dear");        // "Hello Dear World!123"

// ৩. delete(): মুছে ফেলা
sb.delete(5, 10);            // "Hello World!123"

// ৪. reverse(): উল্টানো
sb.reverse();                // "321!dlroW olleH"

// ৫. replace(): বদলে ফেলা
sb.replace(0, 4, "Hi");      // "Hi!dlroW olleH"

// ৬. charAt() and setCharAt(): ক্যারেক্টার access/modify
char c = sb.charAt(0);       // 'H'
sb.setCharAt(0, 'h');       // "hi!dlroW olleH"
```

## 3\. Performance Comparison

চলো একটা performance test করি:

```java
public class PerformanceTest {
    public static void stringTest(int iterations) {
        String result = "";
        long start = System.currentTimeMillis();
        
        for(int i = 0; i < iterations; i++) {
            result += "a";
        }
        
        long end = System.currentTimeMillis();
        System.out.println("String Time: " + (end - start) + "ms");
    }
    
    public static void stringBuilderTest(int iterations) {
        StringBuilder result = new StringBuilder();
        long start = System.currentTimeMillis();
        
        for(int i = 0; i < iterations; i++) {
            result.append("a");
        }
        
        long end = System.currentTimeMillis();
        System.out.println("StringBuilder Time: " + (end - start) + "ms");
    }
    
    public static void main(String[] args) {
        int iterations = 100000;
        stringTest(iterations);
        stringBuilderTest(iterations);
    }
}
```

## 4\. When to Use StringBuilder

### Use StringBuilder When:

1. **লুপের ভিতরে String Concatenation:**
    

```java
// Bad Practice ❌
String result = "";
for(int i = 0; i < 1000; i++) {
    result += i;
}

// Good Practice ✅
StringBuilder result = new StringBuilder();
for(int i = 0; i < 1000; i++) {
    result.append(i);
}
```

2. **Multiple Modifications:**
    

```java
// Bad Practice ❌
String text = "Hello";
text = text + " World";
text = text + "!";
text = text.toUpperCase();

// Good Practice ✅
StringBuilder text = new StringBuilder("Hello");
text.append(" World")
    .append("!")
    .toString()
    .toUpperCase();
```

### Use String When:

1. **Simple Concatenation:**
    

```java
// এক্ষেত্রে String ভালো
String name = "Mr. " + firstName + " " + lastName;
```

2. **Immutability Required:**
    

```java
// Password যেখানে change হওয়া উচিত না
String password = "secure123";
```

## 5️⃣ Best Practices

### 1\. Initial Capacity Setting:

```java
// Bad Practice ❌
StringBuilder sb = new StringBuilder();

// Good Practice ✅
StringBuilder sb = new StringBuilder(1000);  // If you know approximate size
```

### 2\. Method Chaining:

```java
// Bad Practice ❌
StringBuilder sb = new StringBuilder();
sb.append("Hello");
sb.append(" ");
sb.append("World");

// Good Practice ✅
StringBuilder sb = new StringBuilder()
    .append("Hello")
    .append(" ")
    .append("World");
```

## 6\. Memory Efficiency

### Memory Usage Example:

```java
public class MemoryTest {
    public static void main(String[] args) {
        // Memory before test
        Runtime rt = Runtime.getRuntime();
        long startMemory = rt.totalMemory() - rt.freeMemory();
        
        // Test code here
        StringBuilder sb = new StringBuilder(1000000);
        for(int i = 0; i < 1000000; i++) {
            sb.append("a");
        }
        
        // Memory after test
        long endMemory = rt.totalMemory() - rt.freeMemory();
        System.out.println("Memory used: " + (endMemory - startMemory));
    }
}
```

## Interview Questions

১. **প্রশ্ন:** StringBuilder thread-safe না কেন? **উত্তর:** StringBuilder একই সময়ে multiple threads থেকে access করা safe না। Thread-safety লাগলে StringBuffer ব্যবহার করতে হবে।

২. **প্রশ্ন:** StringBuilder এর initial capacity কত? **উত্তর:** Default capacity 16 characters। তবে constructor এ custom capacity দেওয়া যায়।

## Memory Leaks in String

1. **String Interning এর ভুল ব্যবহার:**
    
    * অতিরিক্ত String.intern() ব্যবহার
        
    * String Pool-এ অনেক বেশি String জমা হওয়া
        
2. **Large String References:**
    
    * বড় String অবজেক্ট হোল্ড করে রাখা
        
    * Substring এর মাধ্যমে original String কে রেফারেন্স ধরে রাখা
        

### সমাধান:

* String Pool ক্লিয়ার করার জন্য System.gc() কল করা
    
* Substring এর পরিবর্তে new String() ব্যবহার করা
    
* WeakHashMap ব্যবহার করে String caching
    

আমাদের এই লম্বা জার্নিতে আমরা Java String নিয়ে অনেক আলোচনা করেছি। শুরু করেছিলাম সাধারণ String দিয়ে, তারপর ধীরে ধীরে জেনেছি String Pool, StringBuilder, এবং অন্যান্য অ্যাডভান্সড কনসেপ্টগুলো।

প্রথমে দেখেছি String এর মৌলিক Concept- কিভাবে এটা মেমোরিতে স্টোর হয়, কেন immutable, আর কিভাবে String Pool কাজ করে। এই বেসিক জ্ঞান আমাদেরকে বুঝতে সাহায্য করেছে যে কেন কখনো সাধারণ String ব্যবহার করব, আর কখন StringBuilder বা StringBuffer নিয়ে কাজ করব।

StringBuilder নিয়ে কাজ করার সময় দেখেছি কিভাবে এটা পারফরম্যান্স ইম্প্রুভ করে, বিশেষ করে লুপের মধ্যে String অপারেশন করার সময়। একটা সিঙ্গেল StringBuilder অবজেক্ট বারবার মডিফাই করে নতুন মেমোরি ওয়েস্ট করা থেকে বাঁচায়।

String ফরম্যাটিং এবং আউটপুট জেনারেশন নিয়ে কাজ করার সময় দেখেছি কিভাবে প্রফেশনাল-লুকিং আউটপুট তৈরি করা যায়। এটা খুবই গুরুত্বপূর্ণ যখন আমরা লগ ফাইল, রিপোর্ট বা ইউজার ইন্টারফেস তৈরি করি।

ট্রাবলশুটিং এবং কমন ইস্যুগুলো নিয়ে আলোচনা করে বুঝেছি কিভাবে মেমোরি লিক এড়ানো যায়, পারফরম্যান্স বটলনেক ফিক্স করা যায়, এবং ক্যারেক্টার এনকোডিং সমস্যার সমাধান করা যায়।

একজন ভালো Java ডেভেলপার হতে হলে String হ্যান্ডলিং এর উপর দক্ষতা থাকা খুবই জরুরি। কোড লেখার সময় সবসময় মনে রাখতে হবে পারফরম্যান্স এবং মেমোরি ব্যবহারের কথা। StringBuilder ব্যবহার করে লুপের ভিতরে স্ট্রিং ম্যানিপুলেশন, proper exception handling, এবং সঠিক ক্যারেক্টার এনকোডিং ব্যবহার - এই জিনিসগুলো মাথায় রেখে কোড লিখলে অনেক কমন সমস্যা এড়ানো যায়।

String programming এর জার্নি কখনোই শেষ হয় না। নতুন নতুন চ্যালেঞ্জ আসবে, নতুন সমাধান বের করতে হবে। তবে আশা করি এই আর্টিকেল পড়ার পর আপনারা Java String নিয়ে আরও আত্মবিশ্বাসী হয়েছেন। মনে রাখবেন, প্রোগ্রামিং শেখা একটা continuous journey - প্রতিদিন নতুন কিছু শিখার সুযোগ আছে।

Simple is better than complex, but complex is better than complicated. - এই quote টা String programming এর ক্ষেত্রে খুবই প্রযোজ্য। সহজ সমাধান খুঁজবেন, কিন্তু যেখানে প্রয়োজন সেখানে অ্যাডভান্সড টেকনিক ব্যবহার করতে ভয় পাবেন না।

Keep coding, keep learning!