# Arrays

>Covered in Dsa Day 2
[Day2-Dsa](../DSA/Day2.md)

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