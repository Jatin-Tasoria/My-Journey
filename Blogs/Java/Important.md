# Scanner Pitfall
This **`Scanner` pitfall** is one of the **most common beginner bugs in Java**.

## The Problem: `nextInt()` + `nextLine()`

### Buggy Code

```java
Scanner sc = new Scanner(System.in);

System.out.print("Enter age: ");
int age = sc.nextInt();

System.out.print("Enter name: ");
String name = sc.nextLine();

System.out.println("Age: " + age);
System.out.println("Name: " + name);
```

### Expected Output

```
Enter age: 20
Enter name: Jatin
Age: 20
Name: Jatin
```

### Actual Output

```
Enter age: 20
Enter name:
Age: 20
Name:
```
>  **The name is skipped!**

---

## Why This Happens

### `nextInt()` behavior

- Reads **only the number**
- **Does NOT consume** the newline (`\n`) left when you press Enter

### `nextLine()` behavior

- Reads **everything until a newline**
- If a newline is already waiting → it reads **empty string**

---

### Input Buffer Reality

When you type:

```
20
```

Buffer contains:

```
20\n
```

- `nextInt()` → reads `20`
- `\n` is **still there**
- `nextLine()` → reads that leftover `\n` → returns `""`

---

## CORRECT FIX

### Solution 1: Consume the leftover newline

```java
int age = sc.nextInt();
sc.nextLine();   // clear buffer

String name = sc.nextLine();
```

> This is the **BEST and MOST USED fix**

---

## Solution 2: Use `nextLine()` everywhere

```java
int age = Integer.parseInt(sc.nextLine());
String name = sc.nextLine();
```

✔ Clean
✔ No buffer issues
✔ Professional approach

---

## WRONG Fixes (Avoid These)

❌ Reordering inputs
❌ Ignoring the issue
❌ Using `next()` instead of understanding the problem

---

##  Rule to Remember (EXAM + REAL LIFE)

> 🔑 **Whenever you use `nextInt()`, `nextDouble()`, etc.
> and then use `nextLine()`, ALWAYS consume the newline first.**

---

## 📌 Quick Memory Trick

```
nextInt() → leaves ENTER
nextLine() → reads ENTER
```

---