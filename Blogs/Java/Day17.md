# Generics

A concept where you can write a class, interface, or method that is compatible with different data types.
< T > type parameter (placeholder that gets replaced with a real type)
<String> type argument (specifies the type)

Before generics, Java used Object, which caused:

- Runtime ClassCastException
- No type safety
- Messy code

Generics solve this by:
- Compile-time type checking
- No casting
- Cleaner & safer code

---

## Generic Class
```java
class Box<T> {
    T value;

    void set(T value) {
        this.value = value;
    }

    T get() {
        return value;
    }
}
```
```java
Box<Integer> b = new Box<>();
b.set(10);
System.out.println(b.get());
```

---

## Generic Method
```java
class Printer {
    static <T> void print(T value) {
        System.out.println(value);
    }
}
```
```java
Printer.print("Hello");
Printer.print(100);
Printer.print(3.14);
```

---

## Generics with Collections
You’ve already used this — now you understand why.
```java
ArrayList<String> names = new ArrayList<>();
names.add("Jatin");
// names.add(10); ❌ compile-time error
```

---

## Bounded Type Parameters
Upper Bound (extends)
```java
class Calculator<T extends Number> {
    T num;

    Calculator(T num) {
        this.num = num;
    }

    double square() {
        return num.doubleValue() * num.doubleValue();
    }
}
```

Allows Number and its subclasses

---

## Wildcards
```java
void printList(List<?> list) {
    for(Object o : list) {
        System.out.println(o);
    }
}
```
<?> → unknown type
Useful in APIs

---

## Generics Rules (Interview Gold)

- Cannot use primitives (int, Integer)
- Type erasure happens at runtime
- Static methods need their own <T>
- Generics improve readability & safety
