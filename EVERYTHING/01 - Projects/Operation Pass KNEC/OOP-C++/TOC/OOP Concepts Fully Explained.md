### 2. OOP Concepts Fully Explained

**1. Encapsulation**

**Definition:**
Encapsulation is the concept of bundling the data (attributes) and methods (functions) that operate on the data into a single unit or class. It also involves restricting direct access to some of the object’s components, which is often done using access specifiers like `private`, `protected`, and `public`.

**Key Points:**
- **Data Hiding:** Encapsulation hides the internal state of the object from the outside world. This is achieved by making attributes `private` and providing `public` methods to access and modify them.
- **Access Modifiers:**
  - **`private`:** Members declared as private are accessible only within the class itself.
  - **`protected`:** Members declared as protected are accessible within the class and by derived classes.
  - **`public`:** Members declared as public are accessible from any part of the program.
- **Getter and Setter Methods:** These methods provide controlled access to the private attributes. They allow reading (getter) and updating (setter) the values of private attributes while encapsulating the logic for data validation or manipulation.

**Example:**
```cpp
class BankAccount {
private:
    double balance; // Private attribute

public:
    // Constructor
    BankAccount(double initial_balance) : balance(initial_balance) {}

    // Getter method
    double getBalance() const {
        return balance;
    }

    // Setter method
    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        }
    }
};
```
In this example, `balance` is a private attribute and cannot be accessed directly from outside the class. The `deposit` and `withdraw` methods control how `balance` is modified, ensuring that operations are valid.

**Real-World Application:**
- **Banking Systems:** Encapsulation is used to protect sensitive data like account balances and transaction history, only allowing controlled access and modification.

---

**2. Inheritance**

**Definition:**
Inheritance is a mechanism that allows one class (the derived class) to inherit attributes and methods from another class (the base class). It promotes code reuse and establishes a hierarchical relationship between classes.

**Key Points:**
- **Base Class (Parent Class):** The class whose properties and methods are inherited.
- **Derived Class (Child Class):** The class that inherits properties and methods from the base class.
- **Access Specifiers for Inheritance:**
  - **`public`:** Public members of the base class become public members of the derived class.
  - **`protected`:** Protected members of the base class become protected members of the derived class.
  - **`private`:** Private members of the base class are not accessible in the derived class, but they can be accessed through protected or public methods if provided.
- **Constructor and Destructor Inheritance:** Constructors and destructors are not inherited, but they can be called explicitly in the derived class.

**Example:**
```cpp
class Vehicle {
public:
    void start() {
        // Start vehicle
    }
};

class Car : public Vehicle {
public:
    void honk() {
        // Honk horn
    }
};
```
Here, `Car` inherits the `start` method from `Vehicle`. The `Car` class can use `start` and also has its own method, `honk`.

**Real-World Application:**
- **Vehicle Hierarchy:** A base class `Vehicle` might be inherited by classes such as `Car`, `Truck`, and `Motorcycle`, each adding specific features or overriding base methods.

---

**3. Polymorphism**

**Definition:**
Polymorphism allows objects of different classes to be treated as objects of a common base class. It enables methods to perform different operations based on the object’s actual derived class. Polymorphism can be categorized into two types: compile-time and run-time.

**Compile-Time Polymorphism (Method Overloading):**
- **Method Overloading:** Involves defining multiple methods with the same name but different parameters in the same class. The correct method is selected based on the method signature at compile-time.

**Example:**
```cpp
class Printer {
public:
    void print(int i) {
        // Print integer
    }

    void print(double d) {
        // Print double
    }
};
```
Here, the `print` method is overloaded with different parameter types.

**Run-Time Polymorphism (Inheritance and Virtual Functions):**
- **Virtual Functions:** Functions declared with the `virtual` keyword in a base class can be overridden in derived classes. The appropriate function is called based on the object’s actual type at runtime.

**Example:**
```cpp
class Shape {
public:
    virtual void draw() {
        // Default drawing
    }
};

class Circle : public Shape {
public:
    void draw() override {
        // Draw circle
    }
};

class Square : public Shape {
public:
    void draw() override {
        // Draw square
    }
};
```
In this example, the `draw` method is overridden in both `Circle` and `Square` classes. When `draw` is called on a `Shape` pointer pointing to a `Circle` object, the `Circle`'s `draw` method is executed.

**Real-World Application:**
- **User Interfaces:** Polymorphism is used to handle different types of user interface elements (e.g., buttons, text fields) through a common interface or base class.

---

**4. Abstraction**

**Definition:**
Abstraction involves hiding the complex implementation details and showing only the essential features of an object. It allows focusing on interactions at a higher level without worrying about the internal workings.

**Key Points:**
- **Abstract Classes:** Classes that cannot be instantiated and are used to define common characteristics and behaviors for derived classes. They often contain pure virtual functions, which must be implemented by derived classes.
- **Interfaces:** In some languages, interfaces define methods without implementations and are used to enforce certain behaviors across different classes.

**Example:**
```cpp
class AbstractShape {
public:
    virtual void draw() = 0; // Pure virtual function
};
```
Here, `AbstractShape` cannot be instantiated and requires derived classes to implement the `draw` method.

**Real-World Application:**
- **Abstract Interfaces:** In systems design, abstract classes or interfaces define a common protocol for different implementations, such as different types of payment gateways in an e-commerce application.

---
