- [[#1. **`public`**|1. **`public`**]]
- [[#2. **`private`**|2. **`private`**]]
- [[#3. **(default)** – _Package-private_|3. **(default)** – _Package-private_]]
- [[#4. **`protected`**|4. **`protected`**]]
- [[#✅ Summary of Access Modifiers|✅ Summary of Access Modifiers]]
- [[#`@Override` in Java|`@Override` in Java]]
- [[#Key Points:|Key Points:]]
- [[#Syntax:|Syntax:]]
- [[#Example 1: Overriding a Method from a Superclass|Example 1: Overriding a Method from a Superclass]]
- [[#Example 2: Without `@Override` (Still Works, But Risky)|Example 2: Without `@Override` (Still Works, But Risky)]]
- [[#Example 3: Overriding a Method from an Interface|Example 3: Overriding a Method from an Interface]]
- [[#When to Use `@Override`|When to Use `@Override`]]



Access modifiers in Java control the **visibility (accessibility)** of classes, methods, constructors, and variables from other parts of the code.

Java has **four** main access levels:

|Modifier|Class|Package|Subclass (in other pkg)|World|
|---|:-:|:-:|:-:|:-:|
|`public`|✔|✔|✔|✔|
|`protected`|✔|✔|✔|✖|
|(default)|✔|✔|✖|✖|
|`private`|✔|✖|✖|✖|

- ✅ = Accessible
- ✖ = Not Accessible
### 1. **`public`**

Accessible from **anywhere** in the program.

```java
public class MyClass {
    public int x = 10;

    public void show() {
        System.out.println("Public method");
    }
}
```

### 2. **`private`**

Accessible **only within the same class**.

```java
public class MyClass {
    private int x = 5;

    private void display() {
        System.out.println("Private method");
    }

    public void accessPrivate() {
        display(); // OK
    }
}
```

### 3. **(default)** – _Package-private_

If no modifier is specified. Accessible **only within the same package**.

```java
class MyPackageClass {
    void packageMethod() {
        System.out.println("Package-private method");
    }
}
```

### 4. **`protected`**

Accessible in the **same package** and in **subclasses in other packages**.

```java
package mypkg;
public class Parent {
    protected void greet() {
        System.out.println("Hello from protected method");
    }
}

package otherpkg;
import mypkg.Parent;

public class Child extends Parent {
    public void test() {
        greet(); // OK because Child is a subclass
    }
}
```

---

### ✅ Summary of Access Modifiers

|Modifier|Same Class|Same Package|Subclass|Other Classes|
|---|---|---|---|---|
|`public`|✔|✔|✔|✔|
|`protected`|✔|✔|✔|✖|
|(default)|✔|✔|✖|✖|
|`private`|✔|✖|✖|✖|

### `@Override` in Java

The `@Override` annotation in Java is used when a **subclass (child class)** provides a **specific implementation** of a method that is already defined in its **superclass (parent class)** or an **interface**.

### Key Points:

- It **ensures** that you're actually overriding a method from a superclass or interface.
    
- If the method signature doesn't match or the method doesn't exist in the parent class/interface, the compiler will throw an **error**.
    
- Improves **readability** and helps catch **bugs** early.
    
### Syntax:

```java
@Override
public void someMethod() {
    // new implementation
}
```

### Example 1: Overriding a Method from a Superclass

```java
class Animal {
    public void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Dog barks");
    }
}
```

**Explanation**:

- `Dog` overrides the `makeSound()` method of `Animal`.
    
- When called on a `Dog` object, the overridden version is executed.
    

### Example 2: Without `@Override` (Still Works, But Risky)

```java
class Cat extends Animal {
    public void makesound() { // Typo: method name doesn't match
        System.out.println("Cat meows");
    }
}
```

**Problem**: No error is shown, but the method is **not actually overriding** `makeSound()` because of the typo. The annotation `@Override` would have caught this error.

### Example 3: Overriding a Method from an Interface

```java
interface Shape {
    void draw();
}

class Circle implements Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }
}
```

**Explanation**:  
`Circle` provides a concrete implementation of `draw()` from the `Shape` interface using `@Override`.

### When to Use `@Override`

- Always use it when you're **intentionally overriding** a method.
    
- Helps the compiler check that the method exists in the superclass/interface.
    
- Prevents **silent bugs** due to typos or incorrect method signatures.
    



