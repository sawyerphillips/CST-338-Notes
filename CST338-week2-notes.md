# CST 338 - Week 2 Notes

## Generics

### What it is
Generics are a Java feature that lets classes, methods, and collections work with different data types while still keeping type safety.

### What it does
It allows you to specify what type of data can be stored or used (such as `String` or `Integer`), preventing the wrong data type from being added.

### Why it's useful
- Prevents type errors.
- Makes code reusable.
- Eliminates unnecessary casting.

---

## Shallow Copy

### What it is
A shallow copy creates a new object but shares references to the original object's inner objects or arrays.

### What it does
If a shared object changes, both the original and the copied object will see that change.

### Why it's useful
- Faster to create than a deep copy.
- Uses less memory.
- Good when shared data is acceptable.

---

## Deep Copy

### What it is
A deep copy creates a completely new object along with new copies of all inner objects and arrays.

### What it does
Changes made to the copied object do not affect the original object.

### Why it's useful
- Prevents accidental changes.
- Makes objects completely independent.
- Safer when working with complex data.

---

## `toString()`

### What it is
A method that tells Java how an object should be displayed as text.

### What it does
Returns a custom string representation of an object instead of the default memory address.

### Why it's useful
- Makes output easier to read.
- Helps with debugging.
- Lets you control exactly what information is displayed.

---

## `@Override`

### What it is
An annotation that tells Java you're replacing a method inherited from a parent class.

### What it does
Checks that the method actually overrides an existing parent method. If it doesn't, Java produces an error.

### Why it's useful
- Prevents mistakes.
- Makes code easier to understand.
- Ensures the correct method is being overridden.

---

## Inheritance

### What it is
A way for one class (child) to inherit fields and methods from another class (parent).

### What it does
Allows subclasses to reuse existing code while adding or changing functionality.

### Why it's useful
- Reduces duplicate code.
- Makes programs easier to organize.
- Allows classes to share common behavior.

### Important Terms
- **Superclass:** Parent or base class.
- **Subclass:** Child or derived class.

---

## `this`

### What it is
A keyword that refers to the current object.

### What it does
Accesses the current object's variables and methods, especially when variable names are the same as parameter names.

### Why it's useful
- Removes ambiguity.
- Makes constructors easier to write.
- Clearly identifies instance variables.

---

## Creating a Subclass

### What it is
The process of making a new class inherit from another class using `extends`.

### What it does
Allows the subclass to use the parent class's methods and variables.

### Why it's useful
- Saves time by reusing code.
- Makes programs easier to expand.
- Keeps related classes organized.

**Remember:**
- Use `extends`.
- Constructors are not inherited.
- Use `super()` to call the parent constructor.
- `super()` must be the first line in the constructor.

---

## HashMap

### What it is
A collection that stores data as key-value pairs.

### What it does
Each key maps to one value, allowing quick storage and retrieval of information.

### Why it's useful
- Very fast lookups.
- Organizes related data.
- Great for storing paired information.

### Useful Methods
- `keySet()` - Returns all keys.
- `containsKey()` - Checks if a key exists.
- `containsValue()` - Checks if a value exists.
- `remove()` - Removes a key-value pair.
- `size()` - Returns the number of entries.

---

## Polymorphism

### What it is
The ability for one parent type to represent many different child objects.

### What it does
Allows the same method call to behave differently depending on the object's actual type.

### Why it's useful
- Makes code more flexible.
- Reduces duplicate code.
- Makes programs easier to maintain and expand.

---

## `final`

### What it is
A keyword that prevents something from being changed.

### What it does
- **Method:** Cannot be overridden.
- **Class:** Cannot be extended.
- **Variable:** Cannot be reassigned.

### Why it's useful
- Protects important code.
- Prevents accidental changes.
- Improves program reliability.

---

## Abstract Classes

### What it is
A class that cannot be instantiated directly and is meant to be extended.

### What it does
Provides common fields and methods for subclasses while allowing unfinished methods that child classes must implement.

### Why it's useful
- Creates a shared foundation.
- Reduces duplicate code.
- Forces subclasses to follow a common design.

---

## Static Variables

### What it is
A variable that belongs to the class instead of individual objects.

### What it does
Only one copy exists, and every object shares it.

### Why it's useful
- Saves memory.
- Keeps shared information consistent.
- Useful for counters, constants, and shared settings.

---

## Wrapper Classes

### What it is
Classes that convert primitive data types into objects.

### What it does
Allows primitive values like `int` and `double` to be used where Java requires objects.

### Why it's useful
- Works with collections like `ArrayList`.
- Provides useful built-in methods.
- Makes primitives compatible with Java's object-oriented features.

### Common Wrapper Classes
- `int` → `Integer`
- `double` → `Double`
- `boolean` → `Boolean`
- `char` → `Character`