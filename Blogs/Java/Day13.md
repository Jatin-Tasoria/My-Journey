# Exception Handling

## What is Exception
An event that disrupts the normal flow of a program.

Common examples:
- Dividing the number by zero 
- Accessing invalid array syntax
- Mismatch input type

---

## Types of Exceptions
Java exceptions are mainly divided into **two types**

- Checked Exception
  - Checked at compile time 
  - Must be handled using `try-catch` or `throws`
  - Represent recoverable conditions

Examples: 
```
IOException
SQLException
FileNotFoundException
```

- Unchecked Exception
  - Occur at Runtime
  - Subclass of `RuntimeException`
  - Usually caused by programming mistakes

Example:
```
ArithmeticException
NullPointerException
ArrayIndexOutOfBoundsException
```

---

## Error vs Exceptions
- Error : Serious System issues
- Exception : Application-level issues

> Never try to handle errors

---

## try-catch block
Used to protect risky code from crashing the whole program
```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero");
}
```

### How it works
1. Code inside `try` runs
2. If exception occurs -> JVM jumps to `catch`
3. Program continues normally

## Multiple Catch blocks 
Used when multiple different exceptions occurs
```java
try {
    int[] arr = new int[3];
    System.out.println(arr[5]);
} catch (ArithmeticException e) {
    System.out.println("Math error");
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Invalid index access");
}
```

## finally Block
Always executes, whether an exception occurs or not.
```java
try {
    int x = 10 / 2;
} catch (Exception e) {
    System.out.println("Error occurred");
} finally {
    System.out.println("Program finished");
}
```

Real-World Usage:
- Closing files
- Closing database connections
- Releasing resources

## throw Keyword
Used to manually create and throw an exception.
```
int age = 16;

if (age < 18) {
    throw new ArithmeticException("Not eligible to vote");
}
```

## throws Keyword
Used to declare responsibility of exception handling.
```java
void readFile() throws IOException {
    // file reading logic
}

try {
    readFile();
} catch (IOException e) {
    System.out.println("File error");
}
```

> Caller method must handle it

## Custom Exceptions
Custom exceptions represent business logic errors.
```java
class InvalidAgeException extends Exception {
    InvalidAgeException(String message) {
        super(message);
    }
}

Using Custom Exception
int age = 15;

if (age < 18) {
    throw new InvalidAgeException("Age must be 18 or above");
}
```

---