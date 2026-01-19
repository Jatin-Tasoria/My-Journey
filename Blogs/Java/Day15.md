# Aggregation & Composition

## Aggregation
Represents a *has-a* relationship between objects.
One object contains another object as part of its structure but the contained object/s
can exist independently.

```java
class Teacher {
    String name;

    Teacher(String name) {
        this.name = name;
    }
}

class Department {
    String deptName;
    Teacher teacher;   // HAS-A

    Department(String deptName, Teacher teacher) {
        this.deptName = deptName;
        this.teacher = teacher;
    }
}
```

---

## Composition
Represents a *part-of* relationship between objects.
Allows complex objects to be constructed from smaller objects.

```java
class Engine {
    void start() {
        System.out.println("Engine started");
    }
}

class Car {
    private Engine engine;   // Strong HAS-A

    Car() {
        engine = new Engine();  // created inside
    }

    void startCar() {
        engine.start();
    }
}
```

---

## Difference
| Feature          | Aggregation        | Composition |
| ---------------- | ------------------ | ----------- |
| Relationship     | HAS-A              | HAS-A       |
| Coupling         | Weak               | Strong      |
| Object lifecycle | Independent        | Dependent   |
| Example          | Department–Teacher | Car–Engine  |
