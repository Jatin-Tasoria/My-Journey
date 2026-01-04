# Arrays
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

---

## Arraylist
Dynamic arrays without size specifications
syntax:
```java
import java.util.ArrayList;

ArrayList<datatype> name = new ArrayList<>();   
```

### Adding Elements
```java
names.add("Jatin");
names.add("Rahul");
names.add("Aditi");
```

### Access Elements
```java
System.out.println(names.get(0));  // Jatin
```

### Update Elements
```java
names.set(1, "Rohit");
```

### Remove Elements
```java
names.remove("Aditi");   // remove by value
names.remove(0);         // remove by index
```

### Check Size
```java
System.out.println(names.size());
```

### Iterating Over ArrayList
1. Normal for loop
```java
for(int i = 0; i < names.size(); i++){
    System.out.println(names.get(i));
}
```

2. Enhanced for loop
```java
for(String name : names){
    System.out.println(name);
}
```

3. Using Iterator
```java
Iterator<String> it = names.iterator();
while(it.hasNext()){
    System.out.println(it.next());
}
```

### Common Methods of ArrayList

| Method       | Description             |
| ------------ | ----------------------- |
| `add()`      | Add element             |
| `get()`      | Fetch element           |
| `set()`      | Update element          |
| `remove()`   | Delete element          |
| `size()`     | Number of elements      |
| `contains()` | Check if element exists |
| `isEmpty()`  | Check if list is empty  |
| `clear()`    | Remove all elements     |

## Difference
| Feature     | Array               | ArrayList                  |
| ----------- | ------------------- | -------------------------- |
| Size        | Fixed               | Dynamic (auto-grows)       |
| Type        | Primitive & Objects | Only Objects               |
| Methods     | Not many            | Tons of ready-made methods |
| Flexibility | Low                 | High                       |

## Example
```java 
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> nums = new ArrayList<>();

        nums.add(10);
        nums.add(20);
        nums.add(30);

        System.out.println("Numbers: " + nums);

        nums.remove(1);
        System.out.println("After removal: " + nums);

        nums.set(1, 100);
        System.out.println("Updated list: " + nums);
    }
}
```