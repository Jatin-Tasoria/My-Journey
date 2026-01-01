# Abstraction
Process of hiding implementation details and showing only essential features.

## Abstract Class
An Abstract Class :
- Cannot be initiated
- Can contain *Abstract* methods (Implemented)
- Can contain *concrete* method (Inherited)

Example
```java
abstract class Shape {
    abstract void area();

    void display() {
        System.out.println("Calculating area");
    }
}
```

## Abstract Method
An abstract method:
- Has no body
- Must be implemented by child class
```java
abstract void area();
```

---

## Need of Abstract class
Without abstraction
- Code duplication 
- Tight coupling
- Difficult maintenance

With abstraction:
- Loose coupling
- Clean API
- Scalability

---

## Abstract vs Normal class
| Feature          | Abstract Class | Normal Class |
| ---------------- | -------------- | ------------ |
| Object creation  | ❌ No           | ✅ Yes        |
| Abstract methods | ✅ Yes          | ❌ No         |
| Concrete methods | ✅ Yes          | ✅ Yes        |
| Constructors     | ✅ Yes          | ✅ Yes        |

---

Example:
```java
public class Main {
    public static void main(String[] args){
        Rectangle rectangle = new Rectangle(2,5);
        Circle circle = new Circle(5);

        System.out.println(circle.area());
        System.out.println(rectangle.area());
    }
}
public abstract class Shape {

    abstract double area(); // abstract

    void display(){ //concrete
        System.out.println("This is a shape");
    }
}
public class Circle extends Shape{

    double radius;

    Circle(double radius){
        this.radius=radius;
    }
    @Override
    double area(){
        return Math.PI*radius*radius;
    }
}
public class Rectangle extends Shape{

    double len;
    double wid;

    Rectangle(double length,double width) {
        this.len = length;
        this.wid = width;
    }
    @Override
    double area(){
        return len*wid;
    };
}
```

---