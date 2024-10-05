Here’s a Java cheat sheet for both **beginners** and **intermediate** programmers, covering essential concepts, syntax, and common usage patterns. 

---

## **1. Basics of Java**

### **Hello World Program**
```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### **Variables & Data Types**
```java
int number = 10;          // Integer
double price = 10.99;     // Floating point number
char letter = 'A';        // Single character
boolean isJavaFun = true; // Boolean
String text = "Hello";    // String
```

### **Basic Input & Output**
```java
import java.util.Scanner;

Scanner sc = new Scanner(System.in);
int age = sc.nextInt();       // Input an integer
String name = sc.nextLine();  // Input a string
```

---

## **2. Operators**

### **Arithmetic Operators**
```java
int a = 10, b = 20;
System.out.println(a + b);  // Addition: 30
System.out.println(b - a);  // Subtraction: 10
System.out.println(a * b);  // Multiplication: 200
System.out.println(b / a);  // Division: 2
System.out.println(b % a);  // Modulus: 0
```

### **Comparison & Logical Operators**
```java
System.out.println(a > b);    // false
System.out.println(a == b);   // false
System.out.println(a != b);   // true

boolean c = (a < b && a != 0);  // Logical AND
boolean d = (a < b || a == 0);  // Logical OR
```

---

## **3. Control Flow**

### **Conditional Statements**
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

#### **For Loop**
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);  // Outputs 0 to 4
}
```

#### **While Loop**
```java
int i = 0;
while (i < 5) {
    System.out.println(i);
    i++;
}
```

#### **Do-While Loop**
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
```java
int[] numbers = {1, 2, 3, 4, 5};  // Array initialization
System.out.println(numbers[0]);    // Access first element
```

### **Iterating Through Arrays**
```java
for (int num : numbers) {
    System.out.println(num);   // Enhanced for loop
}
```

### **String Operations**
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
```java
class Animal {
    void eat() {
        System.out.println("This animal eats");
    }
}

class Dog extends Animal {
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
#### **ArrayList**
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
```java
import java.util.HashMap;

HashMap<String, Integer> map = new HashMap<>();
map.put("Apple", 1);
map.put("Banana", 2);

System.out.println(map.get("Apple"));  // Output: 1
```

---

## **8. Threads**
### **Creating a Thread**
```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        t1.start();
    }
}
```

### **Runnable Interface**
```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread using Runnable");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread t1 = new Thread(new MyRunnable());
        t1.start();
    }
}
```

---

This cheat sheet covers key topics for both beginners and intermediate Java programmers, from basic syntax to advanced OOP and threading concepts.
