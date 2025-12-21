# OOPs (Object Oriented Programming)
Java is an Object Oriented language, which means everything revolves around **cLasses & objects**.

## Why Object-Oriented Programming?
Before OOP, programs were written using a procedural approach which became hard to manage as applications grew.

OOP helps us:

- Organize code better
- Reuse code
- Model real-world entities
- Make programs scalable and maintainable

---

## Core Concepts of OOP
Java OOP is based on these pillars:
- Class
- Object
- Method
- Constructor
- this keyword
- static keyword
  
> (Encapsulation, Inheritance, Polymorphism will come later)

---

## Class
A class is a blueprint to create an objects.
```java
class Student {
    String name;
    int age;
}
```

---

## Object
An object is an instance of a class.
An entity that holds data(attributes) and can perform actions(methods).
```java
Student s1 = new Student();
s1.name = "Jatin";
s1.age = 21;

System.out.println(s1.name);
System.out.println(s1.age);
```

---

## Methods
Methods define the behavior of a class.

- Method without return value
```java
void greet() {
    System.out.println("Hello!");
}
```
- Method with parameters
```java
void printName(String name) {
    System.out.println(name);
}
```
- Method with return value
```java
int add(int a, int b) {
    return a + b;
}
```

---

## Constructor
A special method to initialize objects.

- Default Constructor
```java
class Student {
    Student() {
        System.out.println("Student object created");
    }
}
```
- Parameterized Constructor
```java
class Student {
    String name;
    int age;

    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

---

## `this` Keyword
Refers to current object.

>Without `this`, Java cannot differentiate between local and instance variables.

---