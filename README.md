## **1. Basics of Java**

### **Hello World Program**
The most basic program in Java simply prints "Hello, World!" to the console. Java programs consist of **classes** and **methods**. The `main` method is the entry point, and the `System.out.println` function is used to print text to the console.
```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### **Variables & Data Types**
Java supports multiple data types such as integers (`int`), floating-point numbers (`double`), characters (`char`), and booleans (`boolean`). Strings are represented by the `String` class.
```java
int number = 10;          // Integer
double price = 10.99;     // Floating point number
char letter = 'A';        // Single character
boolean isJavaFun = true; // Boolean
String text = "Hello";    // String
```

### **Basic Input & Output**
To take input from the user, Java uses the `Scanner` class, and you can output using `System.out`.
```java
import java.util.Scanner;

Scanner sc = new Scanner(System.in);  // Create a Scanner object
int age = sc.nextInt();               // Reads an integer
String name = sc.nextLine();          // Reads a string
```

---

## **2. Operators**

### **Arithmetic Operators**
Java supports basic arithmetic operators such as addition (`+`), subtraction (`-`), multiplication (`*`), division (`/`), and modulus (`%`).
```java
int a = 10, b = 20;
System.out.println(a + b);  // Addition: 30
System.out.println(b - a);  // Subtraction: 10
System.out.println(a * b);  // Multiplication: 200
System.out.println(b / a);  // Division: 2
System.out.println(b % a);  // Modulus (remainder): 0
```

### **Comparison & Logical Operators**
Java provides operators for comparing values (`>`, `<`, `==`, `!=`, etc.) and for logical operations (`&&`, `||`, `!`). These are used to control the flow of a program.
```java
System.out.println(a > b);    // false
System.out.println(a == b);   // false
System.out.println(a != b);   // true

boolean c = (a < b && a != 0);  // true (Logical AND)
boolean d = (a < b || a == 0);  // true (Logical OR)
```

---

## **3. Control Flow**

### **Conditional Statements**
Control flow allows you to execute certain blocks of code based on conditions. The `if-else` statement evaluates a boolean condition and executes code accordingly.
```java
if (a > b) {
    System.out.println("a is greater");
} else if (a == b) {
    System.out.println("a is equal to b");
} else {
    System.out.println("a is smaller");
}
```

### **Switch Case**
The `switch` statement allows you to choose between different cases based on the value of a variable.
```java
int day = 2;
switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    default:
        System.out.println("Other day");
        break;
}
```

### **Loops**
Loops are used to execute a block of code repeatedly.

#### **For Loop**
The `for` loop is used when you know in advance how many times a loop should run.
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);  // Outputs 0 to 4
}
```

#### **While Loop**
The `while` loop runs as long as a condition is true. It is often used when the number of iterations is unknown.
```java
int i = 0;
while (i < 5) {
    System.out.println(i);
    i++;
}
```

#### **Do-While Loop**
The `do-while` loop is similar to the `while` loop, except it guarantees at least one execution of the loop body.
```java
int i = 0;
do {
    System.out.println(i);
    i++;
} while (i < 5);
```

---

## **4. Arrays & Strings**

### **Array Declaration**
An array is a container object that holds a fixed number of values of a single type. The length of an array is established when the array is created.
```java
int[] numbers = {1, 2, 3, 4, 5};  // Array initialization
System.out.println(numbers[0]);    // Access first element
```

### **Iterating Through Arrays**
The enhanced for loop is used to iterate through all elements of an array.
```java
for (int num : numbers) {
    System.out.println(num);   // Outputs elements 1 to 5
}
```

### **String Operations**
Strings are immutable objects in Java. You can perform various operations on strings such as concatenation, comparison, and case conversion.
```java
String s1 = "Hello";
String s2 = "World";
System.out.println(s1.length());        // Get string length
System.out.println(s1.concat(s2));      // Concatenate strings
System.out.println(s1.equals(s2));      // Compare strings
System.out.println(s1.toUpperCase());   // Convert to uppercase
```

---

## **5. Object-Oriented Programming (OOP)**

### **Classes & Objects**
Java is an object-oriented language, meaning that you structure programs using **classes** and **objects**. A class is a blueprint for creating objects (instances).
```java
class Dog {
    String name;
    int age;

    void bark() {
        System.out.println(name + " says woof!");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog();   // Object creation
        myDog.name = "Buddy";    // Accessing object properties
        myDog.age = 5;
        myDog.bark();            // Calling methods
    }
}
```

### **Constructors**
A **constructor** is a special method that is called when an object is instantiated. It is used to initialize the object's properties.
```java
class Dog {
    String name;
    int age;

    // Constructor
    Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    void bark() {
        System.out.println(name + " says woof!");
    }
}
```

### **Inheritance**
Inheritance allows one class (child class) to inherit properties and methods from another class (parent class). This promotes code reuse.
```java
class Animal {
    void eat() {
        System.out.println("This animal eats");
    }
}

class Dog extends Animal {   // Dog inherits from Animal
    void bark() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.eat();   // Inherited method
        myDog.bark();  // Dog's own method
    }
}
```

### **Polymorphism**
Polymorphism allows one method to have different implementations depending on the object that is calling it. This is typically achieved through **method overriding**.
```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Cat extends Animal {
    void sound() {
        System.out.println("Cat meows");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myAnimal = new Cat();  // Upcasting
        myAnimal.sound();             // Output: Cat meows
    }
}
```

### **Encapsulation**
Encapsulation is the practice of keeping data (variables) and the methods that manipulate that data within the same class, while restricting access from outside the class using **private** access modifiers.
```java
class Person {
    private String name;  // Private variable

    // Getter
    public String getName() {
        return name;
    }

    // Setter
    public void setName(String newName) {
        this.name = newName;
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person();
        person.setName("John");
        System.out.println(person.getName());  // Output: John
    }
}
```

---

## **6. Exception Handling**
Java provides a robust mechanism to handle runtime errors using **exceptions**. You can use the `try-catch` block to catch and handle exceptions, ensuring that your program doesn't crash unexpectedly.
```java
try {
    int[] numbers = {1, 2, 3};
    System.out.println(numbers[10]);
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Index out of bounds!");
} finally {
    System.out.println("This block always executes");
}
```

---

## **7. Intermediate Java Concepts**

### **Abstract Classes**
An **abstract class** is a class that cannot be instantiated and is meant to be extended by other classes. It can contain both abstract methods (without a body) and concrete methods (with a body).
```java


abstract class Animal {
    abstract void sound();
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}
```

### **Interfaces**
An **interface** is a completely abstract class that defines methods that must be implemented by any class that implements the interface.
```java
interface Animal {
    void sound();  // Abstract method
}

class Dog implements Animal {
    public void sound() {
        System.out.println("Dog barks");
    }
}
```

### **Lambda Expressions (Java 8)**
A **lambda expression** is a concise way to represent a function that can be passed around and executed. It is primarily used for functional interfaces (interfaces with only one abstract method).
```java
interface MathOperation {
    int operation(int a, int b);
}

public class Main {
    public static void main(String[] args) {
        MathOperation addition = (a, b) -> a + b;
        System.out.println(addition.operation(5, 3));  // Output: 8
    }
}
```

### **Collections**
Collections provide a framework to store and manipulate groups of objects. Common collections include `ArrayList`, `HashMap`, and `HashSet`.

#### **ArrayList**
An `ArrayList` is a resizable array implementation that allows for dynamic addition and removal of elements.
```java
import java.util.ArrayList;

ArrayList<String> list = new ArrayList<>();
list.add("Apple");
list.add("Banana");

for (String fruit : list) {
    System.out.println(fruit);  // Output: Apple, Banana
}
```

#### **HashMap**
A `HashMap` is a collection that stores key-value pairs, allowing you to efficiently look up values based on their keys.
```java
import java.util.HashMap;

HashMap<String, Integer> map = new HashMap<>();
map.put("Apple", 1);
map.put("Banana", 2);

System.out.println(map.get("Apple"));  // Output: 1
```

---

## **8. Threads**
Java provides built-in support for multithreading, allowing your program to perform multiple tasks concurrently.

### **Creating a Thread**
You can create a thread by extending the `Thread` class and overriding its `run()` method.
```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start();  // Start the thread
    }
}
```

### **Runnable Interface**
Alternatively, you can create a thread by implementing the `Runnable` interface and passing it to a `Thread` object.
```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread using Runnable");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread t1 = new Thread(new MyRunnable());
        t1.start();  // Start the thread
    }
}
```

---

This cheat sheet now includes both a concise reference to Java syntax and a detailed explanation of core concepts, making it suitable for both beginners and intermediate programmers.
