# Wrapper Class
Allows *Primitive Values* (int, char, double, boolean) to be used as objects

## Primitive Vs Wrapper
| Primitive | Wrapper Class |
| --------- | ------------- |
| int       | Integer       |
| double    | Double        |
| char      | Character     |
| boolean   | Boolean       |
| byte      | Byte          |
| short     | Short         |
| long      | Long          |
| float     | Float         |

---

## Need of Wrapper Class
- Collection works only for objects
- Enable NULL values
- Provide utility values
- Support object-based APIs

---

## Creating Wrapper Class
- Old Way (Deprecated) 
```java
Integer a = new Integer(10);
```
- New Way
```java
Integer a = Integer.valueOf(10);
```

---

## AutoBoxing & Unboxing
**AutoBoxing** (Primitive to Object)
```java
int x = 10;
Integer y = x;
```
**Unboxing** (Objects to Primitive)
```java
Integer y = 10;
int x = y;
```

---

## Useful Wrapper Class Methods
**Integer**
```java
Integer.parseInt("123");   // 123
Integer.max(10, 20);       // 20
Integer.MIN_VALUE;
Integer.MAX_VALUE;
```
**Double**
```java
Double.parseDouble("3.14");
```
**Character**
```java
Character.isDigit('5');    // true
Character.isLetter('A');   // true
```
**Boolean**
```java
Boolean.parseBoolean("true");
```

---

# Common Pitfalls
Comparing wrapper objects using `==`
```java
Integer a = 100;
Integer b = 100;

System.out.println(a == b);      // true (cache)
System.out.println(a.equals(b)); // true

Integer a = 200;
Integer b = 200;

System.out.println(a == b);      // false
```

>Always use .equals()

---