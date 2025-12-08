# 🧠Introduction to DSA
I focused on three foundational topics: what DSA is, why it’s important, time complexity, and basic array operations.

## What is Data Structure?

A Data Structure is a way to store data so that it can be used effectively.


## What is an algorithm?
An algorithm is a step by step method to solve a problem.

Example: steps to make tea,steps to find largest number.

---

## What is DSA & Why do we need it?
DSA combines both the above mentioned terms.
- Data Structure
- Algorithm

It helps us write:
- Faster code.
- Efficient memory usage
- Scalable applications
- Better problem solving.

It is essential for interviews, backend, competitive programming, and system design foundations.

---

## Time Complexity
Time complexity tells us how the running time of a program grows with input size.

### Big O Notation
Simplified analysis of an algorithm's efficiency.
Describes worst case scenario of an algorithm

**General Rules**
1. Ignore Constants: 5n -> O(n)
2. Certain terms "dominates" others: 
   O(1) < O(logn) < O(n) < O(nlogn) < O(n²)  < O(2ⁿ) < O(n!)
   i.e ignore low-order terms

### Three Most common time complexities

1. O(1) : Constant time
    Takes the same time regardless of input size.
    Eg:
    ```java
    int x = arr[0];
    ```

2. O(n) : Linear time
    Time grows proportional with input size.
    Eg:
    ```java
    for(int i = 0; i < n; i++) { }
    ```

3. O(n²) : Quadratic time
    Nested loops, slow for large inputs.
    Eg:
    ```java
    for(int i = 0; i < n; i++)
    for(int j = 0; j < n; j++) { }
    ```
---

## Arrays - The first Data Structure

### What is an array?
An array is a linear data structure that stores elements of same data types at contiguous memory location.

**Declaration**
```java
int[] arr = new int[5];
// or
int[] arr = {1, 2, 3, 4, 5};
```

**Input**
Inputting values in an array can be a tedious task, but we can simplify it by using an for loop.

```java
for(int i=0; i< arr.length; i++){
    //your code
}    
```

### Example code
```java
Scanner sc = new Scanner(System.in);
System.out.print("Enter size of array: ");
int n = sc.nextInt();
int[] arr = new int[n];
System.out.print("Enter elements of array: ");
for(int i =0; i<arr.length; i++){
    arr[i] = sc.nextInt();
}

for(int i =0; i<arr.length; i++){
    System.out.print(arr[i]+ " ");
}
```

### Sample Output
```
Enter size of array: 5
Enter elements of array: 35 63 234 66 12
35 63 234 66 12 
```