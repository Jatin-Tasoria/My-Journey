# 🚀Java fundamentals (Variables, Data Types, Input/Output)

The goal for today is to get comfortable with building block of java programming.
Before writing any code it is necessary to understand hw java handles data, how we print output and how we take input from user.
---


## 📌Java program structure(```class```,```main```method)
Every java program starts with a class and main() method.
It looks like this:
```java
public class Main {
    public static void main(String[] args){
        //your code here
    }
}
```
---

## 🌟Variables
In java or any other programming language, a variable is a reusable  container for a value.
Types of Variables:
- Primitive: Simple values stored in memory.
- Reference: Stores memory addresses of objects

| Primitive |Reference  |
|-----------|-----------|
| int       | string    |
| double    | array     |
| char      | object    |
| boolean   |

### ⚙️Creating a variable
The name of the variable should be meaningful.
There are two steps to create a variable.
- Declaration
- Assignment

```java
int age = 21;
double currency =19.99;
char fLetter = 'J';
boolean is_sunny = true;

String myName ="Jatin";
```
---

## Naming conventions
In java, we follow camelCasing naming convention.
It implies:
- First letter of first word is lower case
- Every new word that follows must be capital. 
 
For example:- isStudent, myFirstName..
---

## Printing output
To print an output in a console, we use:
```java
System.out.print("myName");
```
Output: Jatin.
---

## User input
To take input in java we will use Scanner object which can be imported from a package name 
java.util.Scanner;
This can be written as:
```java
Scanner sc = new Scanner(System.in);
int number = sc.nextInt();
String name = sc.nextLine();

sc.close();
```
---

## Operators
Operators in Java are special symbols used to perform operations on variables and values. They help us calculate, compare, and make decisions in programs.

For Day 2, we focus only on the most important and frequently used operators:
Arithmetic Operators and Relational Operators.

**1. Arithmetic operators**
   
Used to perform basic mathematics

| Operator | Meaning        | Example |
|----------|----------------|---------|
| +        | Addition       | a + b   |
| -        | Subtraction    | a - b   |
| *        | Multiplication | a * b   |
| /        | Division       | a / b   |
| %        | Modulus        | a % b   |

**2. Relational operators**
   
Used to compare two values.

| Operator | Meaning               | Example |
|----------|-----------------------|---------|
| >        | Greater than          | a > b   |
| <        | Less than             | a < b   |
| >=       | Greater than or equal | a >= b  |
| <=       | Less than or equal    | a <= b  |
| ==       | Equal to              | a == b  |
| !=       | Not equal to          | a != b  |

---

# What I practiced

```java
Scanner sc = new Scanner(System.in);

// Taking input
System.out.print("Enter your name: ");
String name = sc.nextLine();

System.out.print("Enter your age: ");
int age = sc.nextInt();

System.out.print("Enter two numbers: ");
int a = sc.nextInt();
int b = sc.nextInt();

// Arithmetic operations
int sum = a + b;
int product = a * b;

// Relational check
boolean isAdult = age > 18;

// Output
System.out.println("\n----- OUTPUT -----");
System.out.println("Hello " + name);
System.out.println("Sum of numbers = " + sum);
System.out.println("Product of numbers = " + product);

if (isAdult) {
    System.out.println("You are an adult.");
} else {
    System.out.println("You are not an adult.");
    
sc.close();    }                                            
 ```

Sample output:
 ```
 ----- OUTPUT -----
Hello Jatin
Sum of numbers = 5
Product of numbers = 6
You are an adult.
```
---