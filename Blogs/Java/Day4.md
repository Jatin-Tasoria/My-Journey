# Random and Math class, loops and Control flow statements
Today was all about taking control of program flow using loops, enhancing logic with break/continue, and exploring powerful utility classes like Math and Random.

## Random Class
Used to get random numbers with more control.
```java
import java.util.Random;

Random r = new Random();
```
Eg:
```java
Random r = new Random();

int num = r.nextInt(10);  // 0 to 9
System.out.println(num);
```
- Other Methods
  - nextInt()
  - nextDouble()
  - nextBoolean()

---

## Math class
Provides useful Maths functions

| Operation   | Example          | Output |
|-------------|------------------|--------|
| Pie         | Math.PI          | 3.1415 |
| e           | Math.E           | 2.7182 |
| Power       | Math.pow(2,3)    | 8      |
| Square Root | Math.sqrt(25)    | 5      |
| Absolute    | Math.abs(-5)     | 5      |
| Maximum     | Math.max(10,20)  | 20     |
| Minimum     | Math.min(10,20)  | 10     |
| Round off   | Math.round(3.14) | 3      |
| Floor       | Math.floor(3.14) | 3      |
| Ceil        | Math.ceil(3.14)  | 4      |

---

## Looping statements
Loops helps us in running a block of code repeatedly

### Types of loops
- For loop
- While loop
- Do while loop
- Nested loop

1. **For loop**
   Used when we know the number of iterations
```java
for(int i = 1; i <= 5; i++) {
    System.out.print(i+" ");
}
```
Output : 1 2 3 4 5

2. **While loop**
   Used when we don't know the number of iterations.
   Runs until a condition is satisfied.
```java
int i = 1;
while(i <= 5) {
    System.out.print(i+" ");
    i++;
}
```
Output : 1 2 3 4 5

3. **Do while loop**
   Runs atleast once even if the condition is false.
```java
int i = 1;
do {
    System.out.print(i+" ");
    i++;
} while(i <= 5);
```
Output : 1 2 3 4 5

4. Nested loop
   A loop inside of a loop
```java
for(int i = 0; i < 4; i++) {
    for (int j = 0; j < i; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```

---

## Control flow statements
Controls the flow of looping statements

### Type
- break : break out of the loop (Stop)
```java
for(int i = 1; i <= 10; i++) {
    if(i == 5) break;  
    System.out.print(i+ " ");
}
```
Output : 1 2 3 4

- continue :Skip current iteration
```java
for(int i = 1; i <= 10; i++) {
    if(i == 5) continue;  
    System.out.print(i+" ");
}
```
Output : 1 2 3 4 6 7 8 9 10

---
