# Strings and Hashing

## Strings
A string is a sequence of character. It is immutable
```java
String s = "Hello";
s = s + " World";// creates a NEW String object
```

## String methods
Some important methods are:

- length() : Returns total number of characters
```java
String s = "Jatin";
System.out.println(s.length()); // 5
```

- charAt(index) : Returns the character at a given index
```java
String s = "Jatin";
System.out.println(s.charAt(1)); // 'a'
```

- toLowerCase() : Converts the entire string to lowercase
```java
String s = "HELLO";
System.out.println(s.toLowerCase()); // hello
```

- toUpperCase() : Converts the entire string to uppercase
```java
String s = "hello";
System.out.println(s.toUpperCase()); // HELLO
```

- trim() : Removes spaces from the beginning and end.
```java
String s = "  Jatin  ";
System.out.println(s.trim()); // Jatin
```

- contains() : Checks if a substring exists inside the string.
```java
String s = "Hello Jatin";
System.out.println(s.contains("Jatin")); // true
```

- startsWith() : Checks if string begins with given value.
```java
String s = "programming";
System.out.println(s.startsWith("pro")); // true
```

- endsWith() : Checks if string ends with given value.
```java
String s = "notes.pdf";
System.out.println(s.endsWith(".pdf")); // true
```

- indexOf() : Returns the first index of a character or substring.
```java
String s = "banana";
System.out.println(s.indexOf("a")); // 1
```

- lastIndexOf() : Returns the last index of a character/substring.
```java
String s = "banana";
System.out.println(s.lastIndexOf("a")); // 5
```

- substring(start, end) : Extracts part of the string.
```java
String s = "JatinTasoria";
System.out.println(s.substring(0, 5)); // Jatin
```

- replace(old, new) : Replaces characters or substrings.
```java
String s = "Hello World";
System.out.println(s.replace("World", "Jatin")); // Hello Jatin
```

- equals() : Checks if two strings have EXACT same value (case-sensitive).
```java
System.out.println("Jatin".equals("jatin")); // false
```

- equalsIgnoreCase() : Compares strings ignoring case.
```java
System.out.println("Jatin".equalsIgnoreCase("jAtIn")); // true
```
---

## `--` vs `equals()`
```java
String a = "Java";
String b = new String("Java");

a == b        // false
a.equals(b)  // true
```

---

## Hashing
It is a technique to store and retrieve data from key-value pair.

### Importance of Hashing
- Reduces time complexity from O(n) to O(1) (average case)
- Used in frequency counting, duplicates, lookups

---

## HashMap

**Operations**
- Insertion : put()
- Retrieve : get()
- Check Key Exists : containsKey()
- Check Value Exists : containsValue()
- Delete Entry : remove()
- Safe Get : getOrDefault() 
- Number of Entries : size()
- Check Empty Map : isEmpty()
- Remove All Entries : clear()
- Get All Keys : keySet()
- Get All Values : values()

```java
HashMap<Integer, Integer> map = new HashMap<>();
map.put(5, 1);
map.put(5, map.getOrDefault(5, 0) + 1);
map.containsKey(5);
map.get(5);
```