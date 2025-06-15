- [[#🧱 Object-Oriented Programming (OOP) in Java|🧱 Object-Oriented Programming (OOP) in Java]]
- [[#🔑 The Four Main Pillars:|🔑 The Four Main Pillars:]]
- [[#1. ✅ **Encapsulation**|1. ✅ **Encapsulation**]]
- [[#1. ✅ **Encapsulation**#🔧 Example:|🔧 Example:]]
- [[#2. ✅ **Abstraction**|2. ✅ **Abstraction**]]
- [[#2. ✅ **Abstraction**#🔧 Example using Abstract Class:|🔧 Example using Abstract Class:]]
- [[#3. ✅ **Inheritance**|3. ✅ **Inheritance**]]
- [[#3. ✅ **Inheritance**#🔧 Example:|🔧 Example:]]
- [[#4. ✅ **Polymorphism**|4. ✅ **Polymorphism**]]
- [[#4. ✅ **Polymorphism**#🔧 Example: Method Overloading (Compile-time)|🔧 Example: Method Overloading (Compile-time)]]
- [[#4. ✅ **Polymorphism**#🔧 Example: Method Overriding (Runtime)|🔧 Example: Method Overriding (Runtime)]]
- [[#📌 Summary Table|📌 Summary Table]]


### 🧱 Object-Oriented Programming (OOP) in Java

OOP is a programming paradigm based on the concept of "objects", which encapsulate data and behavior.

### 🔑 The Four Main Pillars:

1. **Encapsulation**
2. **Abstraction**
3. **Inheritance**
4. **Polymorphism**

---

## 1. ✅ **Encapsulation**

**Definition:** Wrapping data (variables) and code (methods) together in a single unit and restricting direct access to some of the object’s components.

- Achieved using:
    
    - `private` variables
    - `public` getters/setters
    - etc.

### 🔧 Example:

```java
public class Person {
    private String name;  // private = encapsulated
    private int age;

    // Getter
    public String getName() {
        return name;
    }

    // Setter
    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if(age >= 0) this.age = age;  // validation logic
    }
}
```

---

## 2. ✅ **Abstraction**

**Definition:** Hiding complex implementation details and showing only essential features. Abstraction is used to enforce certain methods, and disallow from creating objects of that class. 

- Achieved using:
    
    - **Abstract classes**
    - **Interfaces**

### 🔧 Example using Abstract Class:

```java

public abstract class Payment {
    public abstract void makePayment(double amount);
}

public class CreditCardPayment extends Payment {
    @Override
    public void makePayment(double amount) {
        System.out.println("Paid $" + amount + " using Credit Card.");
        // internal logic: validate card, connect to bank, etc.
    }
}

public class PayPalPayment extends Payment {
    @Override
    public void makePayment(double amount) {
        System.out.println("Paid $" + amount + " using PayPal.");
        // internal logic: authenticate PayPal account, etc.
    }
}

//abstraction is used
public class Checkout {
    public void processPayment(Payment paymentMethod, double amount) {
        paymentMethod.makePayment(amount);  // doesn't care *how* it works
    }
}


```

---

## 3. ✅ **Inheritance**

**Definition:** Mechanism by which one class (child/subclass) inherits the fields and methods of another class (parent/superclass).

- Promotes code reusability.

### 🔧 Example:

```java
class Vehicle {
    public void start() {
        System.out.println("Vehicle started");
    }
}

class Car extends Vehicle {
    public void honk() {
        System.out.println("Car horn");
    }
}
```

Usage:

```java
Car myCar = new Car();
myCar.start();  // Inherited method
myCar.honk();   // Own method
```

---

## 4. ✅ **Polymorphism**

**Definition:** The ability of one interface to be used for a general class of actions; behavior depends on the specific object type.

- **Compile-time Polymorphism/ Ad hoc Polymorphism / Early Binding:** Method Overloading
- **Runtime/ Dynamic Polymorphism/ Late Binding:** Method Overriding

### 🔧 Example: Method Overloading (Compile-time)

```java
class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }
}
```

### 🔧 Example: Method Overriding (Runtime)

```java
class Animal {
    public void speak() {
        System.out.println("Animal speaks");
    }
}

class Cat extends Animal {
    public void speak() {
        System.out.println("Meow");
    }
}
```

Usage:

```java
Animal myCat = new Cat();
myCat.speak();  // Outputs "Meow" (runtime polymorphism)
```

---

## 📌 Summary Table

|Pillar|Purpose|How to Implement|
|---|---|---|
|Encapsulation|Hide internal state, protect data|`private` fields, `public` getters/setters|
|Abstraction|Show only essential features|`abstract` classes, `interface`|
|Inheritance|Reuse code from parent class|`extends` keyword|
|Polymorphism|One interface, multiple behaviors|Overloading, Overriding|
