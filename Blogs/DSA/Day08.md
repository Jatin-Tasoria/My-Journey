# Prefix Sum & Sliding Window Technique

## Prefix Sum
It is a technique where we **pre-calculate cumulative sums** of an array so that the range sum queries become fast.
Instead of calculating sum every time, we store the previous results.

### Why Prefix Sum is Needed
Imagine an array:
```java
arr = [2, 4, 6, 8, 10]
```

Query:
- Sum from index 1 to 3
- Sum from index 0 to 4
- Sum from index 2 to 4

### Brute Force:
Loop every time → O(n) per query
10 queries → O(10n)

### Prefix Sum:
Precompute once → O(n)
Each query → O(1)

### How Prefix Array is Built
Prefix array stores sum from index 0 to i
```java
prefix[0] = arr[0]
prefix[1] = arr[0] + arr[1]
prefix[2] = arr[0] + arr[1] + arr[2]
```
Example:
```java
arr    = [2, 4, 6, 8]
prefix = [2, 6, 12, 20]
```

### Range Sum Formula (Very Important)
```java
sum(l, r) = prefix[r] - prefix[l - 1]
```
If l = 0, then:
```java
sum(0, r) = prefix[r]
```

### Problems where it can be used
- Range sum queries (multiple queries)
- Sum of subarrays
- Check if subarray sum equals K
- Difference array problems (advanced)

---

## Sliding WIndow Technique
Sliding Window is used when dealing with continuous subarrays or substrings.

Instead of recalculating everything, you:
- Add the new element entering the window
- Remove the element leaving the window

### Why it is powerful
Consider this problem:
Find the maximum sum of subarray of size K

**Brute Force:**
Nested loop → O(n²)

**Sliding Window:**
One loop → O(n)

### Types Of sSLiding Windows
1. Fixed Size Window
Windows size is constant (K)
Example
```java
arr = [2, 1, 5, 1, 3, 2]
K = 3
```
Steps:
- Calculate sum of first K elements
- Slide window:
  - Add next element
  - Remove first element of previous window

*Used in:*
- Max sum subarray of size K
- Average of subarrays of size K

2. Variable Size Window
Window size changes dynamically.

*Used when:*
- Condition involves ≤ K, ≥ K, or distinct elements

Example problems:
- Longest subarray with sum ≤ K
- Longest substring with at most K distinct characters

>Requires two pointers + condition checking.

3. Sliding Window on Strings (Very Important)

#### Why Strings are Harder
- You can’t use sum directly
- You must track frequency of characters

Solution:

Use HashMap or array of size 26 / 128

---

## Prefix Sum vs Sliding WIndow
| Technique      | When to Use                      |
| -------------- | -------------------------------- |
| Prefix Sum     | Static array, multiple queries   |
| Sliding Window | Continuous subarray or substring |
| Prefix Sum     | Query-based problems             |
| Sliding Window | Optimization-based problems      |
