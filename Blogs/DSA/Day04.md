# Sorting algorithms
Sorting might look like a basic concept, but it forms the backbone of many advanced algorithms and real-world applications.

## Bubble Sort
Repeatedly compare adjacent elements and swap them if they’re out of order.

**Steps**
1. Steps
2. Loop through the array
3. Compare adjacent elements
4. Swap if needed
5. Repeat until no swaps occur

```java
public static void main(String[] args){
    int[] arr = {1, 58, 785 ,56,44};
    bubble(arr);
    for (int n : arr){
        System.out.print(n+" ");
    }
}
static void bubble(int[] arr){
    for (int i = 0; i < arr.length -1; i++) {
        for (int j = 0; j < arr.length - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}
```

**Time Complexity**
- Best: O(n)
- Worst : O(n²)

## Insertion sort
Build the sorted array one element at a time by inserting each element at the correct position.
Almost like sorting cards in your hand.

**Steps**
1. Pick an element
2. Compare it backward with the sorted part
3. Shift elements
4. Insert it in the correct place

```java
public static void main(String[] args){
    int[] arr = {1, 58, 785 ,56,44};
    insertion(arr);
    for (int n : arr){
        System.out.print(n+" ");
    }
}
static void insertion(int[] arr){
    int n = arr.length;
    for (int i = 0; i < n - 1; i++) {
        int min = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[min]) {
                min = j;
            }
        }
        int temp = arr[min];
        arr[min] = arr[i];
        arr[i] = temp;
    }
}
```

**Time Complexity**
- Best: O(n)
- Worst : O(n²)

## Selection Sort
Find the minimum element from the unsorted part and place it at the beginning. No shifting, only swapping.

**Steps**
- Find the smallest element
- Swap it with the first unsorted element
- Move the boundary forward
- Repeat

```java
public static void main(String[] args){
    int[] arr = {1, 58, 785 ,56,44};
    selection(arr);
    for (int n : arr){
        System.out.print(n+" ");
    }
}
static void selection(int[] arr){
    for (int i = 0; i < arr.length -1; i++) {
        int smallest =i ;
        for (int j = i+1; j < arr.length; j++) {
            if(arr[smallest]>arr[j]){
                smallest = j;
            }
        }
        int temp =arr[smallest];
        arr[smallest] = arr[i];
        arr[i]=temp;
    }
}
```

**Time Complexity****

Best / Worst : O(n²)

## Comparison

| Algorithm      | Best Case | Worst Case | Stable? | Use Case                |
| -------------- | --------- | ---------- | ------- | ----------------------- |
| Bubble Sort    | O(n)      | O(n²)      | Yes     | Beginners, small arrays |
| Insertion Sort | O(n)      | O(n²)      | Yes     | Nearly sorted arrays    |
| Selection Sort | O(n²)     | O(n²)      | No      | Minimum swap cases      |
