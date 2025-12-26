# Static, Encapsulation & Access Modifiers

## Static
A `static` variable makes a variable or a method belng to the `class` rather than any specific object.

```java
class Student {
    String name;
    static String college = "ABC College";

    Student(String name) {
        this.name = name;
    }

    public void display() {
        System.out.println(name + " - " + college);
    }
}
```
In the above code: 
- college is same for all objects

---

## Static vs Non-Static
| Feature       | static     | non-static |
| ------------- | ---------- | ---------- |
| Belongs to    | Class      | Object     |
| Memory        | One copy   | Per object |
| Access `this` | No         | Yes        |
| Called using  | Class name | Object     |

---

## Access Modifiers
These defines who can access the class, variables, methods, or constructor.
They are used to enforce encapsulation, control visibility and protect data.

### What do Access Modifiers do?
They answer questions like:
- Can this variable be accessed from outside the class?
- Can a subclass use this method?
- Is this member visible outside the package?

### Types
Java has 4 types of Access Modifiers

| Modifier                 | Same Class | Same Package | Subclass | Other Package |
| ------------------------ | ---------- | ------------ | -------- | ------------- |
| **public**               | ✅         | ✅           | ✅       | ✅            |
| **protected**            | ✅         | ✅           | ✅       | ❌             |
| **default** (no keyword) | ✅         | ✅           | ❌        | ❌             |
| **private**              | ✅         | ❌            | ❌        | ❌             |

1. private :
   - Most Restrictive
   - Accessible only inside the same class
```java
class Person{
    private int age;
}
```

2. default
   - Accessible only within same package
   - Used when modifier is written
```java
class Person{
    int age;
}
```

3. protected
   - Accessible within same package and in subclasses.
```java
class Person{
    protected int age;
}
```

4. public
   - Least restrictive
   - Accessible from anywhere
```java
class Person{
    public int age;
}
```

---

## Encapsulation
Encapsulation = Data Hiding + Controlled Access

**Without Encapsulation**
```java
class Student {
    public int marks;
}
```
- Anyone can assign invalid values
- No control or validation
- Not used in real projects

**With Encapsulation**
```java
class Student {
    private int marks;

    public void setMarks(int marks) {
        if (marks >= 0 && marks <= 100) {
            this.marks = marks;
        }
    }

    public int getMarks() {
        return marks;
    }
}
```
- Data is protected
- Validation is possible
- Industry standard approach

---

## Getter & Setter
Help protect object data and add rules for accessing or modifying them.
Getter : Methods that make a field **READABLE**.
Setter : Methods that make a field **WRITEABLE**.

```java
class BankAccount {
    private double balance;

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    public double getBalance() {
        return balance;
    }
}
```