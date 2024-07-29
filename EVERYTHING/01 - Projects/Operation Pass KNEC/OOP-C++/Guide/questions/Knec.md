
---

## **Mock Exam: Object-Oriented Programming with C++**

**Duration:** 3 Hours

**Instructions:**
- Answer all questions.
- Write your answers clearly and legibly.
- For multiple-choice questions, choose the most appropriate option.
- For short answer and essay questions, provide concise and detailed explanations.

---

### **Section A: Multiple-Choice Questions (20 marks)**

1. **Which of the following is a characteristic of Object-Oriented Programming?**
   a) Structured programming
   b) Function overloading
   c) Data encapsulation
   d) Sequential processing
?
   **Answer:** c) Data encapsulation



2. **What is the default access specifier for members of a class in C++?**
   a) Public
   b) Private
   c) Protected
   d) None
?
   **Answer:** b) Private



3. **Which keyword is used to define a constructor in C++?**
   a) `construct`
   b) `init`
   c) `constructor`
   d) `~`
?
   **Answer:** d) `~`



4. **What will be the output of the following code snippet?**
   ```cpp
   class Example {
   public:
       void display() {
           std::cout << "Example class";
       }
   };

   int main() {
       Example e;
       e.display();
       return 0;
   }
   ```
   a) `Example class`
   b) `Example`
   c) `class`
   d) Compilation Error
?
   **Answer:** a) `Example class`



5. **Which of the following is used for runtime polymorphism in C++?**
   a) Function Overloading
   b) Operator Overloading
   c) Virtual Functions
   d) Templates
?
   **Answer:** c) Virtual Functions



6. **In C++, which operator is used to access members of a class using a pointer to an object?**
   a) `.` (dot)
   b) `->` (arrow)
   c) `::` (scope resolution)
   d) `.` (dot) and `->` (arrow)
?
   **Answer:** b) `->` (arrow)



7. **What does RAII stand for in C++?**
   a) Resource Allocation Is Initialization
   b) Resource Acquisition Is Initialization
   c) Resource Application Is Initialization
   d) Resource Allocation Is Interface
?
   **Answer:** b) Resource Acquisition Is Initialization <!--SR:!2024-07-25,4,270-->



8. **Which of the following is NOT a feature of the C++ Standard Library?**
   a) Containers
   b) Algorithms
   c) Smart Pointers
   d) Memory Management
?
   **Answer:** d) Memory Management



9. **Which feature allows you to call a method on an object even if you don't know its exact type?**
   a) Templates
   b) Inheritance
   c) Polymorphism
   d) Encapsulation
?
   **Answer:** c) Polymorphism



10. **What is the output of the following code snippet?**
    ```cpp
    class Base {
    public:
        virtual void show() {
            std::cout << "Base class";
        }
    };

    class Derived : public Base {
    public:
        void show() override {
            std::cout << "Derived class";
        }
    };

    int main() {
        Base* b = new Derived();
        b->show();
        return 0;
    }
    ```
    a) `Base class`
    b) `Derived class`
    c) `Base classDerived class`
    d) Compilation Error
?
    **Answer:** b) `Derived class`

---

### **Section B: Short Answer Questions (30 marks)**

1. **Explain the concept of inheritance in C++ and provide an example.**
?
   **Answer:**  
   Inheritance is a mechanism in C++ where a new class (derived class) inherits properties and behavior (methods) from an existing class (base class). This promotes code reusability and hierarchical organization.
   **Example:**
   ```cpp
   class Base {
   public:
       void display() {
           std::cout << "Base class";
       }
   };

   class Derived : public Base {
   public:
       void show() {
           std::cout << "Derived class";
       }
   };

   int main() {
       Derived d;
       d.display(); // Calls base class method
       d.show();    // Calls derived class method
       return 0;
   }
   ```



2. **What are virtual functions in C++ and why are they used?**
?
   **Answer:**  
   Virtual functions are member functions in a base class that can be overridden in derived classes. They are declared using the `virtual` keyword. Virtual functions enable runtime polymorphism, allowing the program to call the appropriate function based on the actual object type rather than the type of the pointer or reference.

   **Example:**
   ```cpp
   class Base {
   public:
       virtual void speak() {
           std::cout << "Base class speak";
       }
   };

   class Derived : public Base {
   public:
       void speak() override {
           std::cout << "Derived class speak";
       }
   };

   int main() {
       Base* b = new Derived();
       b->speak(); // Output: Derived class speak
       return 0;
   }
   ```



3. **Define function overloading and provide a code example.**
?
   **Answer:**  
   Function overloading allows multiple functions to have the same name but differ in the number or type of parameters. This is resolved at compile time based on the function signature.

   **Example:**
   ```cpp
   class Print {
   public:
       void show(int i) {
           std::cout << "Integer: " << i << std::endl;
       }

       void show(double d) {
           std::cout << "Double: " << d << std::endl;
       }

       void show(const std::string& s) {
           std::cout << "String: " << s << std::endl;
       }
   };

   int main() {
       Print p;
       p.show(10);        // Calls show(int)
       p.show(3.14);      // Calls show(double)
       p.show("Hello");  // Calls show(string)
       return 0;
   }
   ```

4. **Discuss the purpose and use of constructors and destructors in C++.**
?
   **Answer:**  
   **Constructors:** Special member functions used to initialize objects of a class. They are called automatically when an object is created. They can be parameterized to initialize objects with specific values.
   **Destructors:** Special member functions called automatically when an object is destroyed. They are used to release resources allocated by the object (e.g., memory, file handles).

   **Example:**
   ```cpp
   class Resource {
   public:
       Resource() {
           std::cout << "Constructor called" << std::endl;
       }

       ~Resource() {
           std::cout << "Destructor called" << std::endl;
       }
   };

   int main() {
       Resource r; // Constructor is called here
       // Destructor will be called when r goes out of scope
       return 0;
   }
   ```



5. **What is operator overloading? Provide an example where operator overloading is useful.**
?
   **Answer:**  
   Operator overloading allows defining custom behavior for operators (like `+`, `-`, `*`, etc.) for user-defined types. It makes it possible to use operators with classes in a way that is intuitive and consistent with built-in types.

   **Example:**
   ```cpp
   class Complex {
   private:
       float real, imag;
   public:
       Complex(float r = 0, float i = 0) : real(r), imag(i) {}

       // Overload + operator
       Complex operator + (const Complex& other) {
           return Complex(real + other.real, imag + other.imag);
       }

       void display() const {
           std::cout << real << " + " << imag << "i" << std::endl;
       }
   };

   int main() {
       Complex c1(1, 2), c2(3, 4);
       Complex c3 = c1 + c2; // Uses overloaded + operator
       c3.display();        // Output: 4 + 6i
       return 0;
   }
   ```

---

### **Section C: Essay Questions (50 marks)**

1. **Discuss the principles of Object-Oriented Programming and their benefits. Provide code examples to illustrate your points.**
?
   **Answer:**
   **Principles of OOP:**
   - **Encapsulation:** Encapsulation is the bundling of data and methods that operate on the data within a single unit, the class. It helps in hiding the internal state and requiring all interaction to be performed through an object's methods.
     ```cpp
     class BankAccount {
     private:
         double balance;
     public:
         void deposit(double amount) {
             if (amount > 0) balance += amount;
         }
         void withdraw(double amount) {
             if (amount > 0 && amount <= balance) balance -= amount;
         }
         double getBalance() const {
             return balance;
         }
     };
     ```

   - **Inheritance:** Inheritance allows a new class (derived class) to inherit attributes and methods from an existing class (base class). It

 promotes code reusability and establishes a hierarchical relationship.
 ```cpp
     class Animal {
     public:
         void eat() { std::cout << "Animal eats"; }
     };

     class Dog : public Animal {
     public:
         void bark() { std::cout << "Dog barks"; }
     };
     ```
   - **Polymorphism:** Polymorphism enables a single interface to be used for different underlying forms (data types). It allows methods to perform different tasks based on the object that invokes them.
     ```cpp
     class Shape {
     public:
         virtual void draw() = 0; // Pure virtual function
     };

     class Circle : public Shape {
     public:
         void draw() override { std::cout << "Draw Circle"; }
     };

     class Square : public Shape {
     public:
         void draw() override { std::cout << "Draw Square"; }
     };
     ```

   - **Abstraction:** Abstraction involves hiding complex implementation details and showing only the necessary features of an object. It allows focusing on interactions at a higher level.
   **Benefits:**
   - Improved code maintainability and reusability.
   - Easier modeling of real-world systems.
   - Enhanced ability to manage and scale large software systems.



2. **Explain the concept of templates in C++ and demonstrate their application with an example.**
?
   **Answer:**
   **Concept:**
   Templates in C++ allow writing generic and reusable code. They enable the creation of functions and classes that work with any data type, avoiding code duplication.

   **Function Templates:**
   ```cpp
   template <typename T>
   T max(T a, T b) {
       return (a > b) ? a : b;
   }
   ```
   **Class Templates:**
   ```cpp
   template <typename T>
   class Stack {
   private:
       std::vector<T> elements;
   public:
       void push(const T& elem) { elements.push_back(elem); }
       T pop() {
           T elem = elements.back();
           elements.pop_back();
           return elem;
       }
   };
   ```
   **Real-World Example:**
   **Stack of Integers and Doubles:**
   ```cpp
   int main() {
       Stack<int> intStack;
       intStack.push(1);
       intStack.push(2);
       std::cout << intStack.pop() << std::endl; // Output: 2

       Stack<double> doubleStack;
       doubleStack.push(1.1);
       doubleStack.push(2.2);
       std::cout << doubleStack.pop() << std::endl; // Output: 2.2

       return 0;
   }
   ```

3. **Describe the concept of metaprogramming in C++ and provide an example of a template metaprogram.**
?
   **Answer:**
   **Concept:**
   Metaprogramming involves writing programs that generate or manipulate other programs (or themselves) at compile-time. In C++, template metaprogramming uses templates to perform computations and make decisions during compilation rather than at runtime.
   **Example - Compile-Time Factorial Calculation:**
   ```cpp
   template <int N>
   struct Factorial {
       static const int value = N * Factorial<N - 1>::value;
   };

   template <>
   struct Factorial<0> {
       static const int value = 1;
   };

   int main() {
       std::cout << "Factorial of 5: " << Factorial<5>::value << istd::endl; // Output: 120
       return 0;
   }
   ```
   **Benefits:**
   - Compile-time optimizations and error checking.
   - Reduction of runtime overhead.

---

**End of Exam**

**Instructions:**
- Ensure all questions are answered.
- Review your answers carefully before submission.

Feel free to ask for further clarifications or additional practice materials!

#ObjectOriented