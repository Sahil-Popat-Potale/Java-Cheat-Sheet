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

Moving into more advanced Java concepts will take us deeper into topics like concurrency, advanced collection frameworks, generics, memory management, JVM architecture, design patterns, and more. Here’s an exploration of some key advanced Java topics:

---

## **1. Generics**

### **Introduction**
Generics enable types (classes and interfaces) to be parameters when defining classes, interfaces, and methods. By using generics, you can write more flexible, reusable code. Generics provide compile-time type checking and eliminate the need for casting.

### **Generic Class Example**
A generic class uses a placeholder for the type, like `<T>`.
```java
class Box<T> {
    private T value;

    public void setValue(T value) {
        this.value = value;
    }

    public T getValue() {
        return value;
    }
}

public class Main {
    public static void main(String[] args) {
        Box<Integer> intBox = new Box<>();
        intBox.setValue(10);
        System.out.println(intBox.getValue());  // Output: 10

        Box<String> strBox = new Box<>();
        strBox.setValue("Hello");
        System.out.println(strBox.getValue());  // Output: Hello
    }
}
```

### **Bounded Type Parameters**
You can restrict the types that are allowed as parameters by using **bounded type parameters**.
```java
class NumberBox<T extends Number> {
    private T number;

    public void setNumber(T number) {
        this.number = number;
    }

    public T getNumber() {
        return number;
    }
}
```
In the above example, only `Number` types (like `Integer`, `Double`, etc.) can be used with `NumberBox`.

---

## **2. Collections Framework (Advanced)**

### **Concurrent Collections**
Java provides thread-safe collections in the `java.util.concurrent` package. These collections handle concurrent access by multiple threads more efficiently than traditional synchronized collections.

#### **ConcurrentHashMap**
A `ConcurrentHashMap` is similar to a regular `HashMap`, but it allows concurrent reads and writes without locking the entire map.
```java
import java.util.concurrent.ConcurrentHashMap;

ConcurrentHashMap<String, Integer> map = new ConcurrentHashMap<>();
map.put("One", 1);
map.put("Two", 2);

System.out.println(map.get("One"));  // Output: 1
```

### **NavigableSet and NavigableMap**
`NavigableSet` and `NavigableMap` are interfaces that extend `SortedSet` and `SortedMap` respectively, adding navigation methods to retrieve the closest matches for elements.

#### **TreeSet (NavigableSet Implementation)**
`TreeSet` is a class that implements `NavigableSet`. It stores elements in a sorted order.
```java
import java.util.TreeSet;

TreeSet<Integer> set = new TreeSet<>();
set.add(10);
set.add(20);
set.add(15);

System.out.println(set.lower(15));  // Output: 10 (lower element)
System.out.println(set.higher(15)); // Output: 20 (higher element)
```

#### **TreeMap (NavigableMap Implementation)**
`TreeMap` implements `NavigableMap`, sorting the keys in natural order.
```java
import java.util.TreeMap;

TreeMap<String, Integer> map = new TreeMap<>();
map.put("A", 1);
map.put("B", 2);
map.put("C", 3);

System.out.println(map.ceilingEntry("B")); // Output: B=2 (closest greater or equal entry)
System.out.println(map.floorEntry("A"));   // Output: A=1 (closest less or equal entry)
```

---

## **3. Memory Management and Garbage Collection**

### **JVM Memory Structure**
The JVM divides memory into two main areas: **Heap** and **Stack**.

- **Heap:** This is where all the objects are stored. The heap memory is shared by all threads.
- **Stack:** Each thread has its own stack, where it stores local variables, method calls, and references to objects in the heap.

### **Garbage Collection**
Garbage collection in Java is the process of automatically identifying and reclaiming memory that is no longer in use. The JVM provides different types of garbage collectors, such as:

- **Serial GC:** A single-threaded collector for smaller applications.
- **Parallel GC:** Uses multiple threads for parallel garbage collection, suitable for high-throughput applications.
- **G1 GC (Garbage-First):** A low-pause garbage collector designed for large heap sizes.

### **Finalize Method**
The `finalize()` method is called by the garbage collector before an object is removed from memory. However, its usage is discouraged in modern Java, and it's deprecated as of Java 9.
```java
@Override
protected void finalize() throws Throwable {
    System.out.println("Object is garbage collected");
}
```

### **Reference Types**
Java provides different levels of references to objects, which influence how the garbage collector treats them:
- **Strong Reference:** The default; the object is not eligible for garbage collection unless all references are removed.
- **Weak Reference:** An object referenced by a `WeakReference` will be collected if the JVM needs memory.
- **Soft Reference:** Similar to a weak reference, but the object will only be collected when the JVM is critically low on memory.
- **Phantom Reference:** Used to do cleanup actions before an object is removed from memory.

---

## **4. Java Concurrency (Multithreading)**

### **Thread Synchronization**
To prevent multiple threads from accessing shared resources simultaneously, synchronization is used. The `synchronized` keyword ensures that only one thread can access a critical section at a time.
```java
class Counter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public int getCount() {
        return count;
    }
}
```

### **Executor Framework**
The **Executor Framework** provides an abstraction layer for managing a pool of threads and running tasks asynchronously. You can submit tasks without worrying about thread management.
```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

ExecutorService executor = Executors.newFixedThreadPool(2);
executor.submit(() -> {
    System.out.println("Task 1");
});

executor.shutdown();
```

### **Future and Callable**
The `Callable` interface is similar to `Runnable`, but it returns a result and can throw an exception. The result can be retrieved using a `Future`.
```java
import java.util.concurrent.*;

Callable<Integer> task = () -> {
    return 123;
};

ExecutorService executor = Executors.newFixedThreadPool(1);
Future<Integer> future = executor.submit(task);

System.out.println(future.get());  // Output: 123
executor.shutdown();
```

---

## **5. Functional Programming in Java (Java 8 and beyond)**

### **Lambda Expressions**
Lambda expressions provide a way to write anonymous methods that can be passed around as parameters, making your code cleaner and more readable.
```java
List<String> names = Arrays.asList("John", "Jane", "Jack");

names.forEach(name -> System.out.println(name));  // Output: John Jane Jack
```

### **Streams API**
The **Streams API** allows you to process collections of data in a functional style (e.g., filter, map, reduce).
```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

int sum = numbers.stream()
    .filter(n -> n % 2 == 0)   // Filter even numbers
    .mapToInt(n -> n * n)      // Square them
    .sum();                    // Sum them up

System.out.println(sum);  // Output: 20
```

### **Optional Class**
The `Optional` class is used to represent a value that may or may not be present, which helps in avoiding `NullPointerException`.
```java
Optional<String> name = Optional.ofNullable(null);
System.out.println(name.orElse("Default"));  // Output: Default
```

---

## **6. Reflection**

### **What is Reflection?**
Reflection is a powerful feature that allows you to inspect and manipulate classes, methods, and fields at runtime. It’s used in frameworks like Spring and Hibernate for dependency injection and object creation.

### **Example**
```java
import java.lang.reflect.Method;

class Person {
    public void sayHello() {
        System.out.println("Hello!");
    }
}

public class Main {
    public static void main(String[] args) throws Exception {
        Class<?> personClass = Class.forName("Person");
        Object obj = personClass.newInstance();

        Method method = personClass.getMethod("sayHello");
        method.invoke(obj);  // Output: Hello!
    }
}
```

---

## **7. Java Design Patterns**

### **Singleton Pattern**
The Singleton pattern ensures that only one instance of a class is created during the application lifecycle.
```java
class Singleton {
    private static Singleton instance;

    private Singleton() {}  // Private constructor

    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

### **Factory Pattern**
The Factory pattern is used to create objects without exposing the creation logic to the client.
```java
interface Shape {
    void draw();
}

class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}

class Square implements Shape {
    public void draw() {
        System.out.println("Drawing Square");
    }
}

class ShapeFactory {
    public static Shape getShape(String shapeType) {
        if (shapeType.equalsIgnoreCase("CIRCLE")) {
            return new Circle();
        } else if (shapeType.equalsIgnoreCase("SQUARE"))

 {
            return new Square();
        }
        return null;
    }
}
```

---

These are just some of the advanced concepts in Java. Mastering these topics will take your skills to the next level, and they'll prepare you for enterprise-level development and deeper architectural decisions.
