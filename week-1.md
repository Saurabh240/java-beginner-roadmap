---

# **Week 1 – Java Basics & IDE Setup (Detailed Guide)**

---

## **Day 1: Java Installation, IDE Setup, Hello World, Variables, Data Types**

### 🎯 Objective

* Understand how Java works
* Install Java & IDE
* Write your **first Java program**
* Learn **variables and data types**

---

## 1️⃣ What is Java & How It Runs?

Java is:

* **Object-Oriented**
* **Platform Independent** (Write Once, Run Anywhere)

### Java Execution Flow

```
.java (source code)
   ↓ compile (javac)
.class (bytecode)
   ↓ JVM
Machine Code (runs on OS)
```

---

## 2️⃣ JDK Installation

### What is JDK?

* **JDK (Java Development Kit)** = JRE + Compiler + Tools
* Needed to **write & run Java programs**

### Steps:

1. Download **Java 17 or Java 21 (LTS)**

   * Oracle JDK or OpenJDK
2. Install it
3. Verify installation:

```bash
java -version
javac -version
```

### Environment Variables (Concept)

* `JAVA_HOME` → Path of JDK
* `PATH` → Allows running `java` from anywhere

---

## 3️⃣ IDE Setup (IntelliJ IDEA / Eclipse)

### Why IDE?

* Auto-complete
* Error highlighting
* Debugging

### IntelliJ Steps:

1. Create **New Project**
2. Select **Java**
3. Choose JDK
4. Create class

---

## 4️⃣ Structure of a Java Program

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### Breakdown:

| Part                 | Meaning          |
| -------------------- | ---------------- |
| `class`              | Blueprint        |
| `main()`             | Entry point      |
| `public static`      | JVM-accessible   |
| `System.out.println` | Print to console |

⚠️ **Program execution always starts from `main()`**

---

## 5️⃣ Variables & Data Types

### What is a Variable?

A **container** that stores data in memory.

```java
int age = 25;
```

### Primitive Data Types

| Type    | Size    | Example                     |
| ------- | ------- | --------------------------- |
| int     | 4 bytes | `int a = 10;`               |
| float   | 4 bytes | `float f = 10.5f;`          |
| double  | 8 bytes | `double d = 10.5;`          |
| char    | 2 bytes | `char c = 'A';`             |
| boolean | 1 bit   | `boolean isJavaFun = true;` |

### Non-Primitive

```java
String name = "Java";
```

---

## 6️⃣ Type Casting

### Implicit (Widening)

```java
int a = 10;
double b = a; // OK
```

### Explicit (Narrowing)

```java
double x = 10.5;
int y = (int) x; // 10
```

---

## ✅ Practice Solutions (Day 1)

### Print name, age, height

```java
public class Info {
    public static void main(String[] args) {
        String name = "Rahul";
        int age = 25;
        double height = 5.9;

        System.out.println(name);
        System.out.println(age);
        System.out.println(height);
    }
}
```

---

### Convert int ↔ double

```java
int a = 10;
double b = a;

double x = 12.7;
int y = (int) x;
```

---

## **Day 2: Operators & Conditional Statements**

---

## 1️⃣ Operators

### Arithmetic

```java
+  -  *  /  %
```

### Relational

```java
> < >= <= == !=
```

### Logical

```java
&&  ||  !
```

### Assignment

```java
=  +=  -=
```

---

## 2️⃣ If-Else

```java
if (a > b) {
    System.out.println("a is greater");
} else {
    System.out.println("b is greater");
}
```

### Else-if Ladder

```java
if (marks >= 90) {
    System.out.println("A");
} else if (marks >= 75) {
    System.out.println("B");
} else {
    System.out.println("C");
}
```

---

## 3️⃣ Switch Statement

```java
int day = 2;

switch (day) {
    case 1: System.out.println("Sunday"); break;
    case 2: System.out.println("Monday"); break;
    default: System.out.println("Invalid");
}
```

⚠️ `break` prevents fall-through

---

## ✅ Practice Solutions (Day 2)

### Even or Odd

```java
int num = 7;

if (num % 2 == 0)
    System.out.println("Even");
else
    System.out.println("Odd");
```

---

### Day of Week

```java
int day = 5;

switch (day) {
    case 1: System.out.println("Monday"); break;
    case 2: System.out.println("Tuesday"); break;
    case 3: System.out.println("Wednesday"); break;
    case 4: System.out.println("Thursday"); break;
    case 5: System.out.println("Friday"); break;
    default: System.out.println("Invalid");
}
```

---

## **Day 3: Loops**

---

## 1️⃣ For Loop

```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

### Best when iterations are known

---

## 2️⃣ While Loop

```java
int i = 1;
while (i <= 5) {
    System.out.println(i);
    i++;
}
```

---

## 3️⃣ Do-While Loop

```java
int i = 1;
do {
    System.out.println(i);
    i++;
} while (i <= 5);
```

✔ Executes **at least once**

---

## ✅ Practice Solutions (Day 3)

### Print 1–10

```java
for (int i = 1; i <= 10; i++) {
    System.out.println(i);
}
```

---

### Sum of First N Numbers

```java
int n = 10, sum = 0;

for (int i = 1; i <= n; i++) {
    sum += i;
}

System.out.println(sum);
```

---

## **Day 4: Arrays**

---

## 1️⃣ 1D Array

```java
int[] arr = {10, 20, 30};
System.out.println(arr[0]);
```

---

## 2️⃣ 2D Array

```java
int[][] matrix = {
    {1, 2},
    {3, 4}
};

System.out.println(matrix[1][0]); // 3
```

---

## ✅ Practice Solutions (Day 4)

### Max & Min

```java
int[] arr = {5, 3, 9, 1};
int max = arr[0], min = arr[0];

for (int num : arr) {
    if (num > max) max = num;
    if (num < min) min = num;
}
```

---

### Reverse Array

```java
for (int i = arr.length - 1; i >= 0; i--) {
    System.out.println(arr[i]);
}
```

---

## **Day 5: Strings**

---

## Common String Methods

```java
String s = "Hello World";
```

| Method           | Output |
| ---------------- | ------ |
| `length()`       | 11     |
| `charAt(1)`      | e      |
| `indexOf("W")`   | 6      |
| `substring(0,5)` | Hello  |

---

## ✅ Practice Solutions (Day 5)

### Reverse String

```java
String s = "Java";
String rev = "";

for (int i = s.length() - 1; i >= 0; i--) {
    rev += s.charAt(i);
}
```

---

### Palindrome

```java
String s = "madam";
String rev = "";

for (int i = s.length() - 1; i >= 0; i--) {
    rev += s.charAt(i);
}

System.out.println(s.equals(rev));
```

---

## **Day 6: Methods & Recursion**

---

## 1️⃣ Method Syntax

```java
public static int add(int a, int b) {
    return a + b;
}
```

---

## 2️⃣ Recursion

Function calling itself.

### Factorial

```java
static int factorial(int n) {
    if (n == 0) return 1;
    return n * factorial(n - 1);
}
```

---

### Fibonacci

```java
static int fib(int n) {
    if (n <= 1) return n;
    return fib(n - 1) + fib(n - 2);
}
```

---

## **Day 7: Full Practice – Solutions**

### Prime Numbers (1–50)

```java
for (int i = 2; i <= 50; i++) {
    boolean prime = true;
    for (int j = 2; j <= i / 2; j++) {
        if (i % j == 0) {
            prime = false;
            break;
        }
    }
    if (prime) System.out.println(i);
}
```

---

### Reverse Number

```java
int num = 123, rev = 0;

while (num != 0) {
    rev = rev * 10 + num % 10;
    num /= 10;
}
```

---

### Largest Element

```java
int[] arr = {2, 8, 1, 9};
int max = arr[0];

for (int x : arr)
    if (x > max) max = x;
```

---

### Sum of Even Numbers (1–100)

```java
int sum = 0;
for (int i = 2; i <= 100; i += 2)
    sum += i;
```

---

### Number Palindrome

```java
int num = 121, rev = 0, temp = num;

while (temp != 0) {
    rev = rev * 10 + temp % 10;
    temp /= 10;
}

System.out.println(num == rev);
```
