# PolyMorphism & toString()

## toString()
Method inherited from the Object class.
Used to return a string representation of an object.
By default, it returns a hash code as a unique identifier.
It can be overridden to provide meaningful details.

Example (without toString()): 
```java
public class Car {

    String make;
    String model;

    Car(String make, String model){
        this.make =make;
        this.model = model;
    }
}
```
Usage:
```java
Car car =new Car("Dodge", "HellCat");
    System.out.println(car);
```
Output:
```
Car@6acbcfc0
```

Example:
```java
public class Car {
    String make;
    String model;

    Car(String make, String model){
        this.make =make;
        this.model = model;
    }
    @Override
    public String toString(){
        return this.make +" "+ this.model;
    }
}
```
Usage:
```java
Car car =new Car("Dodge", "HellCat");
    System.out.println(car);
```
Output:
```
Dodge HellCat
```

---

## PolyMorphism
It is the third pillar in Object Oriented Programming.
Refers to `Same Method name, different behavior`.
Meaning:
- Poly → Many
- Morph → Forms
In simple words, one interface can have multiple implementations.

### Types
| Type                      | Achieved By        | Decision Time |
| ------------------------- | ------------------ | ------------- |
| Compile-time Polymorphism | Method Overloading | Compile time  |
| Runtime Polymorphism      | Method Overriding  | Runtime       |

### Compile-Time Polymorphism (Method Overloading)
Method Overloading happens when:
- Method name is same
- Parameter list is different
- Return type alone cannot differentiate methods

Key Points
- Decided at compile time
- Faster execution
- No inheritance required

```java
class Calculator {

    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

### Runtime Polymorphism (Method Overriding)
Method Overriding occurs when:
- A child class provides its own implementation
- Method signature remains the same
- Happens through inheritance

Example:
```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}
```
Usage:
```java
Animal a = new Dog();
a.sound();
```
Output:
```
Dog barks
```

>Even though reference is of Animal, Dog’s method is called.
>This is called Dynamic Method Dispatch.
---

## Dynamic Method Dispatch
Dynamic Method Dispatch means:
- Method call is resolved at runtime, not compile time.

Java checks:
- Which object is created (new Dog())
- Calls that object's overridden method
 
This is the core of runtime polymorphism.

---

## `@Override` Annotation (Very Important)
The `@Override` annotation ensures:
- Method is actually overriding
- No spelling or signature mistakes
- Compiler gives error if something is wrong

Example:
```java
@Override
void sound() {
    System.out.println("Dog barks");
}
```

---