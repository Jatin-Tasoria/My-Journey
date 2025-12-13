# Recursion & Merge Sort

## Recursion
When a function calls itself again and again to solve a problem.
It requires two parts
1. **Base Case**
   The Stopping condition that prevents infinite calling.
2. **Recursive Case**
    The part where the function calls itself

### Call Stack
Every time the function calls itself a new frame is added to memory called **stack memory**
The function returns value only when reached Base Case.

>Common practice Question : Factorial of a number

---

## Merge Sort
Based on Divide and conquer approach.

Steps:
- Divide the array into two halves.
- Recursively sort the left half.
- Recursively sort the right half.
- Merge both sorted halves into one sorted array.

**Time Complexity**
- Best : O(n logn)
- Worst : O(n logn)

**Example**
```java
public class Main {
    public static void main(String[] args) {

        int[] arr = {8, 3, 4, 12, 5, 6};

        mergeSort(arr, 0, arr.length - 1);

        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
    static void mergeSort(int[] arr, int low, int high) {
        if (low < high) {
            int mid = low + (high - low) / 2;

            mergeSort(arr, low, mid); // Sort left half

            mergeSort(arr, mid + 1, high); // Sort right half

            merge(arr, low, mid, high); // Merge both halves
        }
    }

    // Function to merge two sorted halves
    public static void merge(int[] arr, int low, int mid, int high) {
        int n1 = mid - low + 1;
        int n2 = high - mid;

        // Temporary arrays
        int[] left = new int[n1];
        int[] right = new int[n2];

        // Copy data to temp arrays
        for (int i = 0; i < n1; i++) {
            left[i] = arr[low + i];
        }
        for (int j = 0; j < n2; j++) {
            right[j] = arr[mid + 1 + j];
        }

        int i = 0, j = 0, k = low;

        // Merge the temp arrays
        while (i < n1 && j < n2) {
            if (left[i] <= right[j]) {
                arr[k] = left[i];
                i++;
            } else {
                arr[k] = right[j];
                j++;
            }
            k++;
        }

        // Copy remaining elements of left[]
        while (i < n1) {
            arr[k] = left[i];
            i++;
            k++;
        }

        // Copy remaining elements of right[]
        while (j < n2) {
            arr[k] = right[j];
            j++;
            k++;
        }
    }
}
```