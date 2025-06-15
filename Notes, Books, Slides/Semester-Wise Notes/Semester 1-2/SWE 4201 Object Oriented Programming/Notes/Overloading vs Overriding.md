- [[#🔁 Method Overloading vs. Overriding in Java|🔁 Method Overloading vs. Overriding in Java]]
- [[#✨ 1. **Method Overloading**|✨ 1. **Method Overloading**]]
	- [[#✨ 1. **Method Overloading**#✅ Example:|✅ Example:]]
	- [[#✨ 1. **Method Overloading**#🧪 Usage:|🧪 Usage:]]
- [[#🔄 2. **Method Overriding**|🔄 2. **Method Overriding**]]
	- [[#🔄 2. **Method Overriding**#✅ Example:|✅ Example:]]
	- [[#🔄 2. **Method Overriding**#🧪 Usage:|🧪 Usage:]]
- [[#🧠 Key Notes & Tips|🧠 Key Notes & Tips]]
	- [[#🧠 Key Notes & Tips#🟢 Method Overloading:|🟢 Method Overloading:]]
	- [[#🧠 Key Notes & Tips#🟢 Method Overriding:|🟢 Method Overriding:]]
- [[#🧪 Common Mistakes to Avoid|🧪 Common Mistakes to Avoid]]
	- [[#🧪 Common Mistakes to Avoid#🚫 Mistaking Overriding for Overloading:|🚫 Mistaking Overriding for Overloading:]]
	- [[#🧪 Common Mistakes to Avoid#🚫 Wrong `@Override`:|🚫 Wrong `@Override`:]]
- [[#🧠 Use Cases in Real Life:|🧠 Use Cases in Real Life:]]

## 🔁 Method Overloading vs. Overriding in Java

|Feature|Method Overloading|Method Overriding|
|---|---|---|
|Defined in|Same class|Subclass (child class)|
|Purpose|Increase method flexibility|Customize inherited method behavior|
|Parameters|Must be different (type, number, order)|Must be the same|
|Return type|Can be different (if parameters differ)|Must be the same or covariant|
|Access modifier|Can be anything|Cannot reduce visibility (e.g., public → private)|
|`@Override` required|No|Optional but recommended|
|Compile-time / Runtime|Compile-time|Runtime|
|Inheritance needed|No|Yes|

## ✨ 1. **Method Overloading**

> **Same method name**, different **parameter list** within the same class.

### ✅ Example:

```java
public class Calculator {

    // Overloaded methods
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }

    public int add(int a, int b, int c) {
        return a + b + c;
    }

    public String add(String a, String b) {
        return a + b; // Concatenation
    }
}
```

### 🧪 Usage:

```java
Calculator calc = new Calculator();
System.out.println(calc.add(2, 3));           // 5
System.out.println(calc.add(2.5, 4.5));       // 7.0
System.out.println(calc.add(1, 2, 3));        // 6
System.out.println(calc.add("Hi ", "there")); // "Hi there"
```

✅ All versions of `add` coexist — the compiler picks one based on the arguments (**compile-time resolution**).

## 🔄 2. **Method Overriding**

> Subclass provides a specific implementation of a method already defined in its superclass or interface.

### ✅ Example:

```java
class Animal {
    public void sound() {
        System.out.println("Some generic animal sound");
    }
}

class Dog extends Animal {
    @Override
    public void sound() {
        System.out.println("Bark");
    }
}

class Cat extends Animal {
    @Override
    public void sound() {
        System.out.println("Meow");
    }
}
```

### 🧪 Usage:

```java
Animal myDog = new Dog();
Animal myCat = new Cat();

myDog.sound();  // Bark
myCat.sound();  // Meow
```

✅ Even though the reference is `Animal`, the method called is based on the **actual object at runtime** — this is **runtime polymorphism**.

## 🧠 Key Notes & Tips

### 🟢 Method Overloading:

- Happens **in the same class**.
    
- Can change:
    
    - Number of parameters
        
    - Types of parameters
        
    - Order of parameters
        
- Cannot overload only by return type.
    

### 🟢 Method Overriding:

- Requires **inheritance**.
    
- Must have:
    
    - **Same name**
        
    - **Same parameters**
        
    - **Same or covariant return type**
        
- Can’t throw **more checked exceptions** than the overridden method.
    
- Can **widen** access (e.g., protected → public) but not narrow it.

## 🧪 Common Mistakes to Avoid

### 🚫 Mistaking Overriding for Overloading:

```java
class A {
    public void display(int x) { }
}
class B extends A {
    public void display(double x) { }  // This is OVERLOADING, not overriding
}
```

### 🚫 Wrong `@Override`:

```java
class A {
    public void show(int x) { }
}
class B extends A {
    @Override
    public void show(double x) { }  // ❌ Compile error — no method to override
}
```

---

## 🧠 Use Cases in Real Life:

|Feature|When you'd use it|
|---|---|
|Overloading|To make a method flexible (like constructors, `print()`)|
|Overriding|To change or extend behavior (e.g., custom logic in child classes)|

