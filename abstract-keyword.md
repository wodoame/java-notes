### **The `abstract` Keyword in Java**

The `abstract` keyword in Java is used to define classes and methods that are incomplete and need to be implemented by subclasses. This enables the design of flexible and reusable code by allowing developers to define abstract behavior in a parent class that must be specified in derived classes.

---

### **1. Abstract Classes**

An **abstract class** is a class that cannot be instantiated. It can contain both:

- **Abstract Methods** (methods without a body).
- **Concrete Methods** (methods with a body).

#### Syntax:
```java
abstract class ClassName {
    // Abstract method (no body)
    abstract void abstractMethod();

    // Concrete method
    void concreteMethod() {
        System.out.println("This is a concrete method.");
    }
}
```

#### Example:
```java
// Abstract class
abstract class Animal {
    // Abstract method
    abstract void makeSound();

    // Concrete method
    void sleep() {
        System.out.println("Sleeping...");
    }
}

// Subclass providing implementation for abstract methods
class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Woof! Woof!");
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog(); // Polymorphism
        myDog.makeSound(); // Woof! Woof!
        myDog.sleep();     // Sleeping...
    }
}
```

---

### **2. Abstract Methods**

An **abstract method** is declared without a body in an abstract class. Subclasses must provide an implementation for these methods.

#### Rules for Abstract Methods:
1. **No Method Body:** Abstract methods do not have a body.
2. **Mandatory Override:** Subclasses must implement all abstract methods of their parent abstract class.
3. **Access Modifiers:** Abstract methods can only be declared as `public` or `protected`.

#### Example:
```java
abstract class Shape {
    // Abstract method
    abstract double calculateArea();
}

// Subclass providing the implementation
class Circle extends Shape {
    private double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    @Override
    double calculateArea() {
        return Math.PI * radius * radius;
    }
}
```

---

### **3. Abstract Class vs Concrete Class**

| Feature                 | Abstract Class                      | Concrete Class                     |
|-------------------------|--------------------------------------|-------------------------------------|
| Instantiation           | Cannot be instantiated.             | Can be instantiated.               |
| Abstract Methods        | Can have abstract methods.          | Cannot have abstract methods.      |
| Concrete Methods        | Can have concrete methods.          | Can have concrete methods.         |

---

### **4. Key Points**

1. **Cannot Be Final:** An abstract class cannot be declared as `final` because it is meant to be extended.
2. **Constructors in Abstract Classes:** Abstract classes can have constructors, which can be used to initialize variables.
    ```java
    abstract class Vehicle {
        String type;

        Vehicle(String type) {
            this.type = type;
        }

        abstract void drive();
    }

    class Car extends Vehicle {
        Car(String type) {
            super(type);
        }

        @Override
        void drive() {
            System.out.println("Driving a " + type);
        }
    }
    ```
3. **Polymorphism:** Abstract classes support polymorphism.
    ```java
    Vehicle vehicle = new Car("SUV");
    vehicle.drive(); // Driving a SUV
    ```

---

### **5. Abstract Classes vs Interfaces**

| Feature                   | Abstract Class                                | Interface                                      |
|---------------------------|----------------------------------------------|-----------------------------------------------|
| Methods                   | Can have abstract and concrete methods.      | Abstract methods (until Java 8).             |
| Default Methods           | Not supported.                              | Supported (from Java 8).                     |
| Fields                    | Can have fields (not necessarily `final`).   | All fields are `public static final`.         |
| Multiple Inheritance      | Not supported.                              | Supported.                                    |

---

### **6. Practical Use Cases**

1. **Defining Common Behavior:** Use an abstract class when several related classes share some behavior but also have specialized behavior.
    ```java
    abstract class Animal {
        abstract void sound();
    }

    class Cat extends Animal {
        @Override
        void sound() {
            System.out.println("Meow");
        }
    }
    ```

2. **Base Class for Frameworks:** Abstract classes are often used as base classes in frameworks, where they define the skeleton of a process.

---

[abstract keyword in java - GeeksforGeeks](https://www.geeksforgeeks.org/abstract-keyword-in-java/)
