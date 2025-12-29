# Inheritance 
A property of OOP that allows **child class** to inherit properties of **parent class**
Example
```java
public class Animal {
    boolean isAlive;

    Animal(){
        isAlive =true;
    }
    void eat(){
        System.out.println("The animal is eating");
    }
}
public class Dog extends Animal{
}
Dog dog =new Dog();
System.out.println(dog.isAlive);

dog.eat();
```

## Types Of Inheritance
- Single Level
```java
class A { }
class B extends A { }
```

- Multilevel
```java
class A { }
class B extends A { }
class C extends B { }
```

---

## `Super` Keyword
Refers to the parent class (subclass <- superclass)
Used in Constructor r Method overriding

- Access Parent variable
```java
super.variableName;
```
- Access Parent method
```java
super.method();
```
- Call Parent Constructor
```java
super();
```
* Example
```java
public class Person {
    String first;
    String last;

    Person(String first, String last){
        this.first =first;
        this.last =last;
    }

    void showName(){
        System.out.println(first +" "+ last);
    }
}
public class Student extends Person{
    double gpa;

    Student(String first, String last, Double gpa){
        super(first, last);
        this.gpa=gpa;
    }
}
Person person = new Person("Jatin", "Tasoria");
Student student = new Student("Harry", "Putter", 3.45);
person.showName();
student.showName();
```

---

## `Final` Keyword in Inheritance
| Usage          | Meaning              |
| -------------- | -------------------- |
| final variable | Value cannot change  |
| final method   | Cannot be overridden |
| final class    | Cannot be inherited  |

```java
final class A { }
// class B extends A ❌ not allowed
```

---

## Constructor Execution Order
Always remember:
>Parent constructor runs first, then child constructor
```java
class A {
    A() { System.out.println("A"); }
}

class B extends A {
    B() { System.out.println("B"); }
}
```
* Output:
```css
A
B
```

---

## Method Overriding
When a subclass provides its own implementation of a method that is already defined.
Allows Code reusability and give specific implementation

```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}
```
---