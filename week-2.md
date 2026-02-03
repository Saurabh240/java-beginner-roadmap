# **Week 2 – Object-Oriented Programming (OOP) + Core DSA**

---

## **Day 1: Classes, Objects, Constructors**

### 🎯 Objective

Understand **how Java models real-world entities** using classes and objects, and how constructors initialize data.

---

## 1️⃣ What is OOP?

OOP is about organizing code around **objects** instead of functions.

**Core idea:**

> *An object = data + behavior*

---

## 2️⃣ Class & Object

### Class

A **blueprint/template**.

```java
class Car {
    String model;
    int year;
}
```

### Object

A **real instance** created from a class.

```java
Car myCar = new Car();
myCar.model = "Toyota";
myCar.year = 2020;
```

### Memory Concept (Important)

* Class → No memory
* Object → Memory allocated on **Heap**

---

## 3️⃣ Constructors

### What is a Constructor?

* Special method
* Same name as class
* No return type
* Used to **initialize object data**

---

### Default Constructor

Provided automatically if none is defined.

```java
class Car {
    String model;
    int year;
}
```

---

### Parameterized Constructor

```java
class Car {
    String model;
    int year;

    Car(String m, int y) {
        model = m;
        year = y;
    }
}
```

Usage:

```java
Car c1 = new Car("Honda", 2022);
```

---

## ✅ Practice – Solution (Day 1)

### Student Class

```java
class Student {
    String name;
    int age;
    char grade;

    Student(String name, int age, char grade) {
        this.name = name;
        this.age = age;
        this.grade = grade;
    }

    void display() {
        System.out.println(name + " " + age + " " + grade);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student("Amit", 20, 'A');
        Student s2 = new Student("Neha", 21, 'B');

        s1.display();
        s2.display();
    }
}
```

---

## **Day 2: `this` Keyword, `static`, Method Overloading**

---

## 1️⃣ `this` Keyword

### Why needed?

To differentiate **instance variables** from **parameters**.

```java
class Student {
    String name;

    Student(String name) {
        this.name = name; // instance = parameter
    }
}
```

Without `this`, Java gets confused.

---

## 2️⃣ `static` Keyword

### Meaning

* Belongs to **class**, not object
* Shared across all objects

---

### Static Method Example

```java
class MathUtil {
    static int add(int a, int b) {
        return a + b;
    }
}

MathUtil.add(5, 10);
```

⚠️ Static method **cannot access non-static variables**

---

## 3️⃣ Method Overloading

### Definition

Same method name, **different parameter list**

```java
class Printer {
    void print(int a) {
        System.out.println(a);
    }

    void print(String a) {
        System.out.println(a);
    }
}
```

### Overloading Rules

* Parameter count OR type must differ
* Return type alone is NOT enough

---

## ✅ Practice – Solution (Day 2)

### Calculator with Overloading

```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}
```

---

## **Day 3: Inheritance & Method Overriding**

---

## 1️⃣ Inheritance (`extends`)

### Purpose

* Code reuse
* Parent → Child relationship

```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Bark");
    }
}
```

---

## 2️⃣ Method Overriding

### Rules

* Same method signature
* Happens at **runtime**
* Use `@Override` annotation

```java
@Override
void sound() {
    System.out.println("Bark");
}
```

---

## ✅ Practice – Solution (Day 3)

### Shape Example

```java
class Shape {
    double area() {
        return 0;
    }
}

class Circle extends Shape {
    double radius;

    Circle(double r) {
        radius = r;
    }

    @Override
    double area() {
        return Math.PI * radius * radius;
    }
}

class Rectangle extends Shape {
    double length, width;

    Rectangle(double l, double w) {
        length = l;
        width = w;
    }

    @Override
    double area() {
        return length * width;
    }
}
```

---

## **Day 4: Polymorphism, `instanceof`, Abstract Classes**

---

## 1️⃣ Runtime Polymorphism

```java
Animal a = new Dog();
a.sound(); // Dog's sound()
```

✔ Method call decided at **runtime**

---

## 2️⃣ `instanceof`

Checks object type at runtime.

```java
if (a instanceof Dog) {
    System.out.println("Its a Dog");
}
```

---

## 3️⃣ Abstract Class

### Definition

* Cannot create object
* Can have abstract & concrete methods

```java
abstract class Animal {
    abstract void sound();
}
```

---

## ✅ Practice – Solution (Day 4)

```java
abstract class Vehicle {
    abstract void start();
}

class Car extends Vehicle {
    void start() {
        System.out.println("Car starts with key");
    }
}

class Bike extends Vehicle {
    void start() {
        System.out.println("Bike starts with kick");
    }
}
```

---

## **Day 5: Interfaces vs Abstract Classes**

---

## 1️⃣ Interface

* 100% abstraction (Java 7)
* Supports **multiple inheritance**

```java
interface Drawable {
    void draw();
}
```

Implementation:

```java
class Circle implements Drawable {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}
```

---

## 2️⃣ Abstract Class vs Interface

| Feature     | Abstract Class      | Interface           |
| ----------- | ------------------- | ------------------- |
| Inheritance | Single              | Multiple            |
| Methods     | Abstract + Concrete | Abstract / default  |
| Variables   | Any                 | public static final |
| Constructor | Yes                 | No                  |

---

## ✅ Practice – Solution (Day 5)

```java
interface Payable {
    double calculateSalary();
}

class Employee implements Payable {
    public double calculateSalary() {
        return 50000;
    }
}
```

---

## **Day 6: Encapsulation & Access Modifiers**

---

## 1️⃣ Encapsulation

**Wrapping data + methods together**

```java
class Person {
    private String name;

    public void setName(String n) {
        name = n;
    }

    public String getName() {
        return name;
    }
}
```

✔ Prevents unauthorized access

---

## 2️⃣ Access Modifiers

| Modifier  | Same Class | Package | Subclass | World |
| --------- | ---------- | ------- | -------- | ----- |
| private   | ✔          | ✖       | ✖        | ✖     |
| default   | ✔          | ✔       | ✖        | ✖     |
| protected | ✔          | ✔       | ✔        | ✖     |
| public    | ✔          | ✔       | ✔        | ✔     |

---

## ✅ Practice – Solution (Day 6)

```java
class BankAccount {
    private double balance;

    public void deposit(double amount) {
        balance += amount;
    }

    public void withdraw(double amount) {
        if (amount <= balance)
            balance -= amount;
    }

    public double getBalance() {
        return balance;
    }
}
```

---

## **Day 7: Mini Project – Library Management System**

---

## 🎯 Goal

Apply **all OOP concepts** together.

---

## 1️⃣ Book Class

```java
class Book {
    private int id;
    private String title;
    private String author;

    public Book(int id, String title, String author) {
        this.id = id;
        this.title = title;
        this.author = author;
    }

    public String getTitle() {
        return title;
    }

    public void display() {
        System.out.println(id + " " + title + " " + author);
    }
}
```

---

## 2️⃣ Searchable Interface

```java
interface Searchable {
    void searchBook(String title);
}
```

---

## 3️⃣ Library Class

```java
import java.util.ArrayList;

class Library implements Searchable {
    private ArrayList<Book> books = new ArrayList<>();

    public void addBook(Book book) {
        books.add(book);
    }

    public void viewBooks() {
        for (Book b : books) {
            b.display();
        }
    }

    public void searchBook(String title) {
        for (Book b : books) {
            if (b.getTitle().equalsIgnoreCase(title)) {
                b.display();
                return;
            }
        }
        System.out.println("Book not found");
    }
}
```

---

## 4️⃣ Main Class

```java
public class Main {
    public static void main(String[] args) {
        Library lib = new Library();

        lib.addBook(new Book(1, "Java", "James"));
        lib.addBook(new Book(2, "Python", "Guido"));

        lib.viewBooks();
        lib.searchBook("Java");
    }
}
```


