# Mastering arrays basics
Arrays are the backbone of data structures & algorithms

## Array Indexes
To access the individual elements of an array, we can use indexes. Index always starts with 0.
```java
int[] arr ={1,2,3,4,5};
System.out.println(arr[0]);
```
Output : 1

## Updating values
To update individual element we must first know its index value.
```java
int[3] = 10;
System.ut.println(arr[3]);
```
Output : 10

## Traversing in array
Traversal is the starting point of array related operations
```java
int[] arr = {3, 5, 7, 9};

for(int i = 0; i < arr.length; i++) {
    System.out.print(arr[i] + " ");
}
```

## Problems Practiced
- Find the maximum element in an array
- Find the minimum element
- Find the second largest element
- Count how many elements are even and odd
- Reverse an array