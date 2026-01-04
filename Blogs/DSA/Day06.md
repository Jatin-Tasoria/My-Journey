# Quick Sort & Two Pointer Technique

## Quick Sort
Based n Divide and Conquer approach.

**Steps**:
- Choose a pivot element
- Partition the array so that:
  - Elements smaller than pivot go to the left
  - Elements greater than pivot go to the right
- Recursively apply Quick Sort on left and right subarrays

**Choosing Pivot element**
- First element
- Last element
- Random element

**Time Complexity**
- Best : O(n log n)
- Worst : O(n²)

**Example**
```java
static void quickSort(int[] arr, int low, int high) {
    if (low < high) {
        int p = partition(arr, low, high);
        quickSort(arr, low, p - 1);
        quickSort(arr, p + 1, high);
    }
}
```

---

## Merge Vs Quick Sort
| Feature         | Merge Sort   | Quick Sort     |
| --------------- | ------------ | -------------- |
| Time Complexity | O(n log n)   | O(n log n) avg |
| Worst Case      | O(n log n)   | O(n²)          |
| Space           | Extra space  | In-place       |
| Stability       | Stable       | Not stable     |
| Preferred For   | Linked Lists | Arrays         |

---

## Lomuto Partition Algorithm
This is the core of all Quick sort.

**Logic**
- Pivot : Last Element
- Maintain index `i` for smaller element
- Traverse from `low` to `high - 1`
- If `arr[j] < pivot` -> swap with `i`

**Example**
```java
static int partition(int[] arr, int low, int high) {
    int pivot = arr[high]; // last element
    int i = low - 1;

    for (int j = low; j < high; j++) {
        if (arr[j] < pivot) {
            i++;
            int temp = arr[i];
            arr[i] = arr[j];
            arr[j] = temp;
        }
    }

    // place pivot at correct position
    int temp = arr[i + 1];
    arr[i + 1] = arr[high];
    arr[high] = temp;

    return i + 1;
}
```

---

## Two Pointer Technique
Uses two indices to traverse an array efficiently instead of loops.

### Common Patterns
- One pointer at start and one pointer at end
- Move pointer based n condition

**Example**
Reverse of an array
```java
static void reverseArray(int[] arr) {
    int left = 0, right = arr.length - 1;

    while (left < right) {
        int temp = arr[left];
        arr[left] = arr[right];
        arr[right] = temp;

        left++;
        right--;
    }
}
```

---