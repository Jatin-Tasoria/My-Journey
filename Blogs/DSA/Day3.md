# Searching
Searching is one of the most fundamental operations in Data Structure.Today’s goal is to master the two most important searching techniques: Linear Search and Binary Search, and solve essential interview questions based on them.

## Linear Search
It is the most simplest searching algorithm. As the name implies it goes from one element to another in linear ordering.

Q. Finding element in an array and printing its index value.
```java
public static void main(String[] args){
    int[] num ={34, 45, 64, 22, 53};
    int target = 64;
    int ans = linearSearch(num, target);
    System.out.println(ans);
}

static int linearSearch(int[] arr, int target){
    if(arr.length < 1)
        return -1;
    else
        for (int i = 0; i < arr.length; i++)
            if (arr[i] == target)
                return i;
    return -1;
}
```
Output: 2

Q. For ndimensional arrays
```java
public static void main(String[] args){
    int[][] num ={{34, 45, 64, 22, 53},
                {654, 54,25,87}
    };
    int target = 25;
    int[] ans = linearSearch(num, target);
    System.out.println(Arrays.toString(ans));
}

static int[] linearSearch(int[][] arr, int target){
    if(arr.length < 1 )
        return new int[]{-1,-1};
    else
        for (int i = 0; i < arr.length; i++)
            for (int j = 0; j < arr[i].length; j++)
                if (arr[i][j] == target)
                    return new int[] {i,j};
    return new int[]{-1,-1};
}
```

**Time complexity**
- Best case : O(1)
- Worst case: O(N)

## Binary Search
Binary search is faster and one of the most asked interview questions.
It works only on sorted arrays.

### Working
Works on **Divide & Conquer** approach
1. Takes a middle element.
2. If element>target, search left side of element.
3. If element< target, search right side of element.

Q.
```java
public static void main(String[] args){
    int[] num = {1,2,3,4,5,6,7};
    int target =1;
    int ans = search(num,target);
    System.out.println(ans);
}

static int search(int[] arr, int target) {
    int low = 0, high = arr.length - 1;

    while (low <= high) {
        int mid = low + (high - low) / 2;

        if (arr[mid] == target)
            return mid;
        else if 
            (arr[mid] < target) low = mid + 1;
        else 
            high = mid - 1;
    }
    return -1;
}
```

**Time complexity**
- Best case : O(1)
- Worst case: O(logN)

## Comparison
| Feature         | Linear Search | Binary Search       |
| --------------- | ------------- | ------------------- |
| Works on?       | Any array     | Sorted array only   |
| Time Complexity | **O(n)**      | **O(log n)**        |
| Approach        | Sequential    | Divide & Conquer    |
| Use-case        | Small arrays  | Large sorted arrays |
