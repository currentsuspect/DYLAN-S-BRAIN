### **Chapter 3: Language Structures for OOP**

#### **1. Classes and Objects**

**Definition:**
- **Class:** A blueprint for creating objects. It defines a data structure that contains both data and methods that operate on that data.
- **Object:** An instance of a class. It represents a specific entity with its own data and methods defined by the class.

**Key Components:**
- **Attributes:** Variables defined within a class to hold data.
- **Methods:** Functions defined within a class to manipulate the data or perform actions.

**Purpose:**
- **Encapsulation:** Classes bundle data and methods together.
- **Instantiation:** Objects are created from classes, enabling the use of defined functionalities.

**Example:**
```cpp
class Car {
public:
    string brand;
    int year;

    void start() {
        cout << "Car started" << endl;
    }
};

int main() {
    Car myCar;  // Creating an object of Car
    myCar.brand = "Toyota";
    myCar.year = 2021;
    myCar.start();
}
```

**Real-World Application:**
- **Software Applications:** Classes and objects model real-world entities and their behaviors, such as users, products, or transactions.

---

#### **2. Methods and Attributes**

**Methods:**
- **Definition:** Functions defined inside a class that operate on the object's data.
- **Types:**
  - **Instance Methods:** Operate on individual instances of a class.
  - **Static Methods:** Belong to the class itself rather than instances and can be called without creating an object.

**Attributes:**
- **Definition:** Variables defined inside a class that hold data specific to each object.
- **Types:**
  - **Instance Attributes:** Unique to each instance of the class.
  - **Static Attributes:** Shared across all instances of the class.

**Example:**
```cpp
class Rectangle {
public:
    int width, height;

    int getArea() {
        return width * height;
    }

    static int getDefaultWidth() {
        return 10;  // Static method example
    }
};

int main() {
    Rectangle rect;
    rect.width = 5;
    rect.height = 10;
    cout << "Area: " << rect.getArea() << endl;
    cout << "Default Width: " << Rectangle::getDefaultWidth() << endl;
}
```

**Real-World Application:**
- **Banking Systems:** Attributes might include account number and balance, while methods might include deposit and withdraw functions.

---

#### **3. Access Specifiers**

**Definition:**
Access specifiers determine the visibility of class members. They control how and where the members can be accessed.

**Types:**
- **Public:** Members are accessible from outside the class.
- **Private:** Members are only accessible from within the class.
- **Protected:** Members are accessible within the class and its derived classes.

**Purpose:**
- **Encapsulation:** Control access to data and methods to enforce the principles of encapsulation.

**Example:**
```cpp
class Person {
private:
    string name;
public:
    void setName(string n) {
        name = n;
    }
    string getName() {
        return name;
    }
};
```

**Real-World Application:**
- **User Profiles:** Personal details can be protected (private), while profile operations can be exposed (public).

---

#### **4. Static Members**

**Definition:**
Static members belong to the class itself rather than to any particular object. They are shared among all instances of the class.

**Key Components:**
- **Static Variables:** Shared among all instances. Initialized only once.
- **Static Methods:** Can be called without creating an instance of the class.

**Example:**
```cpp
class Counter {
public:
    static int count;  // Static variable

    static void increment() {  // Static method
        count++;
    }
};

int Counter::count = 0;  // Initialization

int main() {
    Counter::increment();
    cout << "Count: " << Counter::count << endl;
}
```

**Real-World Application:**
- **Configuration Settings:** Static variables can be used for settings that apply to all instances of a class.

---

**Discussion Points:**
1. What are the benefits of using static members in a class?
2. How do access specifiers contribute to the security and integrity of a class?
3. In what scenarios might you prefer using static methods over instance methods?

Let me know if you have questions or if you’d like to proceed to the next chapter!