# 🚀Day 3 - Conditional statements, escape sequences, type casting, logical operators
Today was all about decision making, type casting  in java.

## Conditional statements
Java give multiple ways to implement conditions depending upon complexity of code.

1. If statement
   Used when we need to specify a single condition.
```java
if(number > 0 ){
    System.out.print("Positive number")
}
```

2. If-else statement
   Used when we need two possible outcomes.
```java
if(age >=18){
    System.out.println("Adult")
} else{
    System.out.println("Child")
}
```

3. else-if ladder
   Used when we have multiple conditions
```java
if (marks >= 90) {
    System.out.println("A Grade");
} else if (marks >= 75) {
    System.out.println("B Grade");
} else if (marks >= 50) {
    System.out.println("C Grade");
} else {
    System.out.println("Fail");
}
```

4. nested if
   An if statement inside another if
```java
if (age >= 18) {
    if (isCitizen) {
        System.out.println("Eligible to vote");
    }
}
```

5. Switch case
   Useful to check one variable against multiple conditions. I will be using Enhanced switch
```java
switch(day){
    case "monday", "tuesday", "wednesday", "thursday", "friday" ->
        System.out.println("It is a weekday");
    case "saturday", "sunday" -> System.out.println("It is a weekend");

    default -> System.out.println("It is not a day");
}
```

> You might be wondering what is the difference between traditional Switch vs Enhanced Switch. There is a comparison table provided at the end of this document.(Available after Java14.)

6. Ternary operator
   It is a short form of if-else statement, used when you want to return a value based on a condition.

   Syntax:

   condition ? value_if_true : value_if_false
```java
int age = 20;
String result = (age >= 18) ? "Adult" : "Child";
```

---

## Escape Sequences
These are special sequences that are used inside strings. They begins with backslash "\".

| Escape sequence | Meaning         | Example           |
|-----------------|-----------------|-------------------|
| \n              | New Line        | "Hello\nWorld"    |
| \t              | Tab space       | "Hello\tWorld"    |
| \"              | Double quote    | "Hello\"World\""  |
| \'              | Single quote    | "Hello\'World\'"  |
| \\\             | BAckslash       | "C:\\Folder\\file"|
| \r              | Carriage Return | Move cursor to start of line |
| \b              | Backspace       | Deleted previous character   |
| \f              | Form feed       | Page Break(rarely used)      |

---

## Type casting
Converting one data types to another.

There are two types of casting:
- Implicit(Widening):
  - Java automatically converts smaller types to larger types.
  - These follows a specific order i.e.
```java
byte > short > int > long > float > double
```
- Explicit(Narrowing):
  - Manually converts larger to smaller.
```java
double x = 9.8;
int y = (int) x;  // loses decimal
```

---

## Logical operator
Allow us to check or modify more than one condition.

| Operator | Meaning |
|----------|---------|
| &&       | AND     |
| ∥        | OR      |
| !        | NOT     |

```java
if(age >= 18 && hasID){
    System.out.println("Entry allowed");
}
```

---

## Difference between Traditional Switch and Enhanced Switch

| Features         | Traditional | Enhanced |
|------------------|-------------|----------|
| Requires break   | Yes         | No       |
| Fall-through     | Possible    | No       |
| Arrow syntax     | No          | Yes      |
| Return Value     | No          | Yes      |
| Uses yield       | No          | Yes      |
| Multi case label | No          | Yes      |