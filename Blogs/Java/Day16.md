# Collection Framework

##  **Why Collections?**

Problems with arrays:

* Fixed size
* No ready-made methods
* Manual operations

```java
int[] arr = new int[5]; // fixed size
```

Collections solve this by providing:
✔ Dynamic size
✔ Built-in methods
✔ Better performance
✔ Cleaner code

---

## *Collections Framework Hierarchy

```
Iterable
 └── Collection
      ├── List
      │    ├── ArrayList
      │    └── LinkedList
      ├── Set
      │    ├── HashSet
      │    └── TreeSet
      └── Queue
Map (separate hierarchy)
 ├── HashMap
 ├── TreeMap
 └── LinkedHashMap
```

---

## List Interface

* Ordered
* Allows duplicates
* Index-based access

### ArrayList

```java
ArrayList<Integer> list = new ArrayList<>();

list.add(10);
list.add(20);
list.add(10);

System.out.println(list);   // [10, 20, 10]
```

### Common Methods

```java
list.get(0);
list.set(1, 50);
list.remove(0);
list.size();
list.contains(20);
```

---

## Set Interface

* No duplicates
* Unordered (mostly)

###  HashSet

```java
HashSet<Integer> set = new HashSet<>();

set.add(10);
set.add(20);
set.add(10);

System.out.println(set);   // [10, 20]
```

---

## Map Interface

* Key–Value pairs
* Keys are unique
* Values can repeat

###  HashMap

```java
HashMap<Integer, String> map = new HashMap<>();

map.put(1, "Jatin");
map.put(2, "Rahul");
map.put(1, "Amit");

System.out.println(map);
```

```java
map.get(2);        // Rahul
map.containsKey(1);
map.remove(1);
```

---

## iterating Collections

### for-each loop

```java
for(int x : list) {
    System.out.println(x);
}
```

### Iterator

```java
Iterator<Integer> it = list.iterator();
while(it.hasNext()) {
    System.out.println(it.next());
}
```

### Map iteration

```java
for(Map.Entry<Integer, String> e : map.entrySet()) {
    System.out.println(e.getKey() + " " + e.getValue());
}
```

---

## When to Use What?

| Need                 | Use               |
| -------------------- | ----------------- |
| Ordered + duplicates | ArrayList         |
| No duplicates        | HashSet           |
| Key–Value mapping    | HashMap           |
| Fast search          | HashSet / HashMap |

---