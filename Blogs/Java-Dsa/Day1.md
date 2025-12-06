# 🧭 Introduction to Java

Java is one of the most popular programming language in the World.

It was developed in **early 1990s** by **James Gosling and team** at Sun Microsystems.

Its initial name was **GreenTalk** based on the team name that Gosling was part of.
Later it was changed to **Oak** inspired by an OAK tree outside of Gosling Office.

But due to copyright it was later renamed as JAVA.

---

## 🤔How does java code run?

Java follows the Write Once, Run Anywhere (WORA) principle.

Java converts the program in Bytecode making it machine independent.
To actually run this Bytecode you need a Java Development Kit (JDK).

```mermaid
flowchart TD
    A[program.java] --> B[Java Compiler (JAVAC)]
    B --> C[ByteCode (.class)]
    C --> D[Java Virtual Machine (JVM)]
 ```

---

## 🌟Features Of Java

### 1️⃣ Simple

Java is designed to be easy to learn. Its syntax is clean and similar to C/C++, but without complex concepts like pointers and multiple inheritance.

### 2️⃣ Object-Oriented

Everything in Java revolves around objects. Concepts like classes, objects, inheritance, and polymorphism help structure programs clearly.

### 3️⃣ Platform Independent

Java code is compiled into Bytecode, which can run on any system with a JVM.
This is known as the Write Once, Run Anywhere (WORA) principle.

### 4️⃣ Dynamic

Java supports dynamic loading of classes, meaning code can be linked at runtime—making applications more flexible.

### 5️⃣ Robust

Java handles errors effectively through exception handling and provides automatic memory management with Garbage Collection, reducing crashes.

### 6️⃣ Multithreaded

Java supports multiple threads of execution at the same time, helping build responsive and fast applications like games or servers.

### 7️⃣ High Performance

Even though Java is platform independent, its performance is boosted by the Just-In-Time (JIT) compiler, which converts bytecode to machine code efficiently.

### 8️⃣ Distributed

Java makes it easy to build distributed and networked applications using features like RMI and APIs such as Java Networking.

---


## 🏗️ JDK vs JRE vs JVM

Understanding the difference between JDK, JRE, and JVM is essential for learning how Java works internally.

### 🔹 JVM (Java Virtual Machine)

JVM is the engine that runs Java bytecode.
It is a virtual machine responsible for:

- Converting bytecode → machine code

- Managing memory

- Running garbage collection

- Ensuring security

📌 Without JVM, Java programs cannot run.
📌 JVM is platform-dependent (Windows JVM, Linux JVM, etc.), but bytecode is platform-independent.

--- 

### 🔹 JRE (Java Runtime Environment)

JRE = JVM + Libraries + Runtime Files

It provides everything required to run Java programs but cannot be used to develop them.

A JRE contains:

- JVM

- Core Java class libraries

- Supporting files

📌 Install JRE if you only want to run Java applications.

---

### 🔹 JDK (Java Development Kit)

JDK = JRE + Development Tools

It is the full kit required to develop, compile, and run Java programs.

JDK includes:

- JRE
- Javac compiler
- Debugger
- Documentation tools
- Development utilities

📌 Install JDK if you want to write and compile Java programs.

---

## 🛠️Installation of java

To setup Java on your machine you need two things:
- **JDK**
- **An IDE** (VS code, IntelliJ IDEA)

📌 I am using IntelliJ

  
[![Install Java](https://img.shields.io/badge/Install_Java-blue?style=for-the-badge)](https://www.oracle.com/java/technologies/downloads/)
[![Install IntelliJ](https://img.shields.io/badge/Install_IntelliJ-red?style=for-the-badge)](https://www.jetbrains.com/idea/download/)
