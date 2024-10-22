Here’s a comprehensive markdown note on Java OOPs concepts with more detailed explanations of each topic:

# Java Object-Oriented Programming (OOPs) Concepts

## 1. **Basic Principles of OOP**

### 1.1 **Object**

- An object is an instance of a class.
- It has two main characteristics:

  1. **State** (attributes, represented by variables)
  2. **Behavior** (actions, represented by methods)

- **Example**:

  ```java
  class Car {
      String color;
      int speed;

      void accelerate() {
          speed += 10;
      }
  }

  public class Main {
      public static void main(String[] args) {
          Car myCar = new Car(); // Creating an object
          myCar.color = "Red";
          myCar.accelerate();
      }
  }
  ```

### 1.2 **Class**

- A class is a blueprint or template for creating objects.
- It defines properties (variables) and methods (functions) that the objects created from it will have.

- **Example**:

  ```java
  class Animal {
      String name;
      int age;

      void eat() {
          System.out.println(name + " is eating");
      }
  }

  public class Main {
      public static void main(String[] args) {
          Animal dog = new Animal(); // Creating an object
          dog.name = "Rover";
          dog.eat();
      }
  }
  ```

---

## 2. **Core OOP Principles**

### 2.1 **Encapsulation**

- Encapsulation is the practice of wrapping data (variables) and methods into a single unit (class) and restricting access to them.
- Use **private** access modifiers to make variables hidden and provide public **getter** and **setter** methods to access and modify them.

- **Example**:

  ```java
  class Person {
      private String name;
      private int age;

      // Getter for name
      public String getName() {
          return name;
      }

      // Setter for name
      public void setName(String name) {
          this.name = name;
      }
  }

  public class Main {
      public static void main(String[] args) {
          Person p = new Person();
          p.setName("John");
          System.out.println(p.getName());
      }
  }
  ```

### 2.2 **Inheritance**

- Inheritance allows a class (child) to inherit properties and methods from another class (parent).
- This helps promote code reusability and a hierarchical relationship between classes.

- **Types of Inheritance**:

  1. **Single Inheritance**: One child inherits from one parent.
  2. **Multilevel Inheritance**: A child inherits from a parent, which itself inherits from another class.
  3. **Hierarchical Inheritance**: Multiple child classes inherit from the same parent class.

- **Example**:

  ```java
  class Animal {
      void sound() {
          System.out.println("Animal makes a sound");
      }
  }

  class Dog extends Animal {
      @Override
      void sound() {
          System.out.println("Dog barks");
      }
  }

  public class Main {
      public static void main(String[] args) {
          Dog dog = new Dog();
          dog.sound(); // Calls overridden method in Dog class
      }
  }
  ```

### 2.3 **Polymorphism**

- Polymorphism allows one method or object to take many forms.
- **Two Types**:
  1. **Compile-Time (Static) Polymorphism**: Achieved through method overloading.
  2. **Run-Time (Dynamic) Polymorphism**: Achieved through method overriding.

#### Method Overloading (Compile-Time Polymorphism)

- Method overloading allows multiple methods in the same class to have the same name but different parameters.

- **Example**:

  ```java
  class MathOperation {
      int add(int a, int b) {
          return a + b;
      }

      int add(int a, int b, int c) {
          return a + b + c;
      }
  }

  public class Main {
      public static void main(String[] args) {
          MathOperation operation = new MathOperation();
          System.out.println(operation.add(2, 3));
          System.out.println(operation.add(2, 3, 4));
      }
  }
  ```

#### Method Overriding (Run-Time Polymorphism)

- Method overriding allows a child class to provide a specific implementation of a method already defined in its parent class.

- **Example**:

  ```java
  class Animal {
      void sound() {
          System.out.println("Animal makes a sound");
      }
  }

  class Cat extends Animal {
      @Override
      void sound() {
          System.out.println("Cat meows");
      }
  }

  public class Main {
      public static void main(String[] args) {
          Animal animal = new Cat(); // Run-time polymorphism
          animal.sound(); // Calls the overridden method in Cat class
      }
  }
  ```

### 2.4 **Abstraction**

- Abstraction is the concept of hiding implementation details and exposing only the essential functionality.
- In Java, abstraction can be achieved using **abstract classes** and **interfaces**.

#### Abstract Class

- Abstract classes can have both abstract (no implementation) and concrete (with implementation) methods.

- **Example**:

  ```java
  abstract class Vehicle {
      abstract void start(); // Abstract method

      void fuel() {
          System.out.println("Fueling the vehicle");
      }
  }

  class Car extends Vehicle {
      @Override
      void start() {
          System.out.println("Car is starting");
      }
  }

  public class Main {
      public static void main(String[] args) {
          Vehicle myCar = new Car();
          myCar.start();
          myCar.fuel();
      }
  }
  ```

#### Interface

- An interface is a contract that defines abstract methods that a class must implement.

- **Example**:

  ```java
  interface Animal {
      void sound();
  }

  class Dog implements Animal {
      @Override
      public void sound() {
          System.out.println("Dog barks");
      }
  }

  public class Main {
      public static void main(String[] args) {
          Animal dog = new Dog();
          dog.sound();
      }
  }
  ```

---

## 3. **Other Important Java OOP Concepts**

### 3.1 **Constructors**

- A constructor is a special method used to initialize objects.
- It has the same name as the class and no return type.

#### Default Constructor

- If no constructor is defined, Java provides a default constructor with no arguments.

- **Example**:

  ```java
  class Person {
      String name;

      Person() { // Default constructor
          name = "John";
      }
  }

  public class Main {
      public static void main(String[] args) {
          Person p = new Person();
          System.out.println(p.name); // Output: John
      }
  }
  ```

#### Parameterized Constructor

- A constructor that accepts parameters to initialize object attributes.

- **Example**:

  ```java
  class Person {
      String name;

      Person(String name) { // Parameterized constructor
          this.name = name;
      }
  }

  public class Main {
      public static void main(String[] args) {
          Person p = new Person("Alice");
          System.out.println(p.name); // Output: Alice
      }
  }
  ```

### 3.2 **`this` Keyword**

- The `this` keyword refers to the current class instance.
- It can be used to avoid confusion between instance variables and parameters with the same name.

- **Example**:

  ```java
  class Person {
      String name;

      Person(String name) {
          this.name = name; // Refers to the instance variable
      }
  }
  ```

### 3.3 **`super` Keyword**

- The `super` keyword is used to refer to the immediate parent class object.
- It is commonly used to call parent class methods or constructors.

- **Example**:

  ```java
  class Animal {
      Animal() {
          System.out.println("Animal constructor");
      }
  }

  class Dog extends Animal {
      Dog() {
          super(); // Calls the parent class constructor
          System.out.println("Dog constructor");
      }
  }

  public class Main {
      public static void main(String[] args) {
          Dog dog = new Dog(); // Output: Animal constructor, Dog constructor
      }
  }
  ```

---

## 4. **Access Modifiers in Java**

- **Private**: Accessible only within the class.
- **Default (Package-private)**: Accessible within the same package.
- **Protected**: Accessible within the same package and by subclasses.
- **Public**: Accessible from anywhere.

---

## 5. **Best Practices in OOP**

1. **Encapsulation**: Always encapsulate your class properties and provide access via public getter/setter methods.
2. **Inheritance**: Use inheritance to reuse code, but avoid deep inheritance chains that make your code complex.
3. **Polymorphism**: Use polymorphism to write flexible and extensible code.
4. **Abstraction**: Focus on what an object should do rather than how it does it, using interfaces or abstract classes.

## 6. **Static Keyword in Java**

### 6.1 **Static Variables**

- Static variables belong to the **class** rather than any specific instance.
- They are shared by all objects of that class and only one copy exists.

- **Example**:

  ```java
  class Employee {
      static int companyCode = 1001; // Static variable
      String name;

      Employee(String name) {
          this.name = name;
      }
  }

  public class Main {
      public static void main(String[] args) {
          Employee emp1 = new Employee("John");
          Employee emp2 = new Employee("Alice");

          System.out.println(Employee.companyCode); // Shared among objects
      }
  }
  ```

### 6.2 **Static Methods**

- Static methods belong to the class rather than an object of the class.
- They can be called without creating an object and can only access static variables or methods.

- **Example**:

  ```java
  class MathUtil {
      static int add(int a, int b) { // Static method
          return a + b;
      }
  }

  public class Main {
      public static void main(String[] args) {
          int sum = MathUtil.add(5, 3); // Called without object
          System.out.println(sum); // Output: 8
      }
  }
  ```

### 6.3 **Static Block**

- Static blocks are used to initialize static variables.
- They are executed when the class is loaded, before the main method.

- **Example**:

  ```java
  class Test {
      static int data;

      // Static block
      static {
          data = 50; // Initialize static variable
          System.out.println("Static block executed");
      }

      public static void main(String[] args) {
          System.out.println("Main method executed");
          System.out.println("Data: " + data); // Output: Data: 50
      }
  }
  ```

---

## 7. **Final Keyword in Java**

### 7.1 **Final Variables**

- A variable declared as **final** cannot be modified once assigned.

- **Example**:

  ```java
  class Constants {
      final int MAX_SPEED = 120; // Constant
  }

  public class Main {
      public static void main(String[] args) {
          Constants obj = new Constants();
          System.out.println(obj.MAX_SPEED);
      }
  }
  ```

### 7.2 **Final Methods**

- A method declared as **final** cannot be overridden by subclasses.

- **Example**:

  ```java
  class Vehicle {
      final void start() {
          System.out.println("Vehicle is starting");
      }
  }

  class Car extends Vehicle {
      // Cannot override start() method here
  }
  ```

### 7.3 **Final Classes**

- A class declared as **final** cannot be extended (i.e., no subclass can be created).

- **Example**:

  ```java
  final class MathOperation {
      // Class cannot be inherited
  }

  // This would cause an error:
  // class AdvancedMath extends MathOperation { }
  ```

---

## 8. **Constructor Overloading**

- Constructor overloading allows a class to have more than one constructor, each with a different parameter list.
- This provides flexibility in object creation.

- **Example**:

  ```java
  class Car {
      String color;
      int speed;

      // Default constructor
      Car() {
          this.color = "White";
          this.speed = 120;
      }

      // Parameterized constructor
      Car(String color, int speed) {
          this.color = color;
          this.speed = speed;
      }
  }

  public class Main {
      public static void main(String[] args) {
          Car car1 = new Car(); // Default constructor
          Car car2 = new Car("Red", 150); // Parameterized constructor

          System.out.println(car1.color + ", " + car1.speed); // Output: White, 120
          System.out.println(car2.color + ", " + car2.speed); // Output: Red, 150
      }
  }
  ```

---

## 9. **Object Class in Java**

- The **`Object`** class is the parent class of all classes in Java.
- Every class in Java implicitly inherits from the `Object` class, providing methods like `equals()`, `hashCode()`, `toString()`, and more.

### 9.1 **Common Methods of the Object Class**

- **`toString()`**: Returns the string representation of the object.
- **`equals()`**: Compares two objects for equality.
- **`hashCode()`**: Returns a unique integer (hash code) for the object.
- **`clone()`**: Creates a shallow copy of the object.
- **`finalize()`**: Called by the garbage collector before the object is destroyed.

- **Example**:

  ```java
  class Employee {
      String name;

      Employee(String name) {
          this.name = name;
      }

      @Override
      public String toString() {
          return "Employee name: " + name;
      }
  }

  public class Main {
      public static void main(String[] args) {
          Employee emp = new Employee("John");
          System.out.println(emp.toString()); // Output: Employee name: John
      }
  }
  ```

---

## 10. **Garbage Collection in Java**

- Java has automatic garbage collection, meaning the **JVM** automatically removes objects that are no longer in use to free up memory.

### 10.1 **`finalize()` Method**

- The `finalize()` method is invoked just before an object is garbage collected, giving the object one last opportunity to clean up resources.
- **Note**: It is not guaranteed when or if `finalize()` will be called.

- **Example**:

  ```java
  class Employee {
      @Override
      protected void finalize() throws Throwable {
          System.out.println("Employee object is being garbage collected");
      }
  }

  public class Main {
      public static void main(String[] args) {
          Employee emp = new Employee();
          emp = null; // Eligible for garbage collection
          System.gc(); // Request JVM to run garbage collector
      }
  }
  ```

---

## 11. **Association, Aggregation, and Composition**

### 11.1 **Association**

- **Association** is a relationship between two separate classes, allowing one object to communicate with another.
- **Types**:
  1. **One-to-One**
  2. **One-to-Many**
  3. **Many-to-One**
  4. **Many-to-Many**

### 11.2 **Aggregation**

- **Aggregation** represents a "has-a" relationship where one class contains a reference to another class.
- It is a **weak** association, meaning the contained object can exist independently of the container.

- **Example**:

  ```java
  class Department {
      String name;

      Department(String name) {
          this.name = name;
      }
  }

  class Employee {
      String name;
      Department department; // Aggregation

      Employee(String name, Department department) {
          this.name = name;
          this.department = department;
      }
  }

  public class Main {
      public static void main(String[] args) {
          Department dept = new Department("HR");
          Employee emp = new Employee("John", dept);
          System.out.println(emp.name + " works in " + emp.department.name);
      }
  }
  ```

### 11.3 **Composition**

- **Composition** is a stronger form of aggregation where the contained object **cannot exist independently** of the container.
- If the container is destroyed, the contained objects are also destroyed.

- **Example**:

  ```java
  class Engine {
      Engine() {
          System.out.println("Engine created");
      }
  }

  class Car {
      private Engine engine; // Composition

      Car() {
          engine = new Engine(); // Car creates the engine
      }
  }

  public class Main {
      public static void main(String[] args) {
          Car car = new Car(); // Creates car and engine together
      }
  }
  ```

---

## 12. **Interfaces vs Abstract Classes**

### 12.1 **Abstract Classes**

- Can have both **abstract** and **concrete** methods.
- Can contain **fields** and **constructors**.
- Supports **multiple levels** of inheritance.

### 12.2 **Interfaces**

- Can only have **abstract methods** (until Java 8, which allows default and static methods).
- Cannot have fields or constructors.
- A class can **implement multiple interfaces** but can only **extend one class**.

- **Example**:

  ```java
  interface Movable {
      void move();
  }

  class Car implements Movable {
      @Override
      public void move() {
          System.out.println("Car is moving");
      }
  }

  public class Main {
      public static void main(String[] args) {
          Movable car = new Car();
          car.move();
      }
  }
  ```

---

## 13. **Singleton Design Pattern**

- The **Singleton pattern** ensures that only **one instance** of a class is created, and it provides a global point of access to this instance.

- **Example**:

  ```java
  class Singleton {
    private static Singleton instance;

    // Private constructor prevents instantiation from other classes
    private Singleton() {}

    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
  }

   public class Main {
    public static void main(String[] args) {
        Singleton singleton = Singleton.getInstance();
    }
  }
  ```
