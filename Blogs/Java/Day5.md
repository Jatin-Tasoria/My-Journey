# Strings and String methods & String builder

## String
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

## string builder
Q. Why we need it?
- It is mutable (can be changed without creating new objects)
- Super fast for:
  - loops
  - concatenations
  - dynamic string creation

```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" Jatin");
sb.append(" 👋");
System.out.println(sb); // Hello Jatin 👋
```

### Methods

- append() : Adds text at the end of the existing StringBuilder content.
```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" Jatin");
System.out.println(sb);   // Hello Jatin
```

- insert() : Inserts text at a specific index.
```java
StringBuilder sb = new StringBuilder("HelloJatin");
sb.insert(5, " ");
System.out.println(sb);   // Hello Jatin
```

- setCharAt(index , 'char') : Changes the character at a specific index
```java
StringBuilder sb = new StringBuilder("Jatin");
sb.setCharAt(0, 'K');
System.out.println(sb);   // Katin
```

- delete(start, end) : Removes characters from start to end
```java
StringBuilder sb = new StringBuilder("Hello123");
sb.delete(5, 8);
System.out.println(sb);   // Hello
```

- deleteCharAt(index) : Removes a single character at the given index
```java
StringBuilder sb = new StringBuilder("Hello!");
sb.deleteCharAt(5);
System.out.println(sb);   // Hello
```

- replace(start, end, newText) : Replaces characters from start to end with new text.
```java
StringBuilder sb = new StringBuilder("Hello Jatin");
sb.replace(6, 11, "Java");
System.out.println(sb);   // Hello Java
```

- reverse() : Reverses the entire sequence.
```java
StringBuilder sb = new StringBuilder("Jatin");
sb.reverse();
System.out.println(sb);   // nitaJ
```

- toString() : Converts the mutable StringBuilder into a normal immutable String.
```java
StringBuilder sb = new StringBuilder("Hello");
String str = sb.toString();
System.out.println(str);  // Hello
```