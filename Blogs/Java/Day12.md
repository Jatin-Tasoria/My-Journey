# Interfaces
A blueprint for a class that specifies a set of abstract methods that implementing
classes MUST define. 

Simply, Interface tells WHAT to do, not HOW to do.

## Why they exists
Java does not support multiple inheritance with classes
Interface supports multiple inheritance-like behavior.
- Avoid diamond problem
- Support multiple inheritance
- Loose coupling
- Used everywhere in frameworks

---

## Syntax and rules
```java
interface Animal(){
    void sound();
}
```

**Rules**
- Methods are *Public Abstract* by default
- Variables are *Public static final* by default
- No *Constructors*
- No object creation

---

## Interface vs Abstract class
| Feature              | Interface                    | Abstract Class |
| -------------------- | ---------------------------- | -------------- |
| Multiple inheritance | ✅ Yes                       | ❌ No           |
| Method body          | ❌ (Java 8+: default allowed) | ✅             |
| Constructors         | ❌                            | ✅             |
| Variables            | public static final          | Instance       |
| Keyword              | implements                   | extends        |

---

Example:

```java
public interface Predator {
    void hunt();
}

public interface Prey {
    void flee();
}

public class Rabbit implements Prey{
    @Override
    public void flee(){
        System.out.println("Rabbit is running");
    }
}

public class Hawk implements Predator{
    @Override
    public void hunt(){
        System.out.println("Hawk is catching the rabbit");
    }
}

public class Fish implements Prey,Predator{

    @Override
    public void flee(){
        System.out.println("Small fish is running from bigger fish");
    }

    @Override
    public void hunt(){
        System.out.println("Bigger fish is hunting smaller fish");
    }
}
```
Usage:
```java
public class Main {
    public static void main(String[] args){

        Rabbit rabbit =new Rabbit();
        Hawk hawk = new Hawk();
        Fish fish = new Fish();

        rabbit.flee();
        hawk.hunt();
        fish.flee();
        fish.hunt();
    }
}
```
Output:
```
Rabbit is running
Hawk is catching the rabbit
Small fish is running from bigger fish
Bigger fish is hunting smaller fish
```