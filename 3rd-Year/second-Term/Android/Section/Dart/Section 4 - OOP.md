# Abstract vs Interface, Concrete
## Abstract Class

- **Definition**: An abstract class is like a blueprint for other classes. It can contain both method declarations (with or without implementations) and fields. It cannot be instantiated on its own.
- **Example**: 

```dart
abstract class Shape {
  void draw(); // Abstract method declaration
  void calculateArea() {
    print('Calculating area...'); // Concrete method
  }
}
```
## Interface

- **Definition**: An interface defines a contract for what methods a class must implement, without providing any implementation itself. In Dart, interfaces are achieved using abstract classes with only abstract method declarations.
- **Example**: 

```dart
abstract class Comparable {
  int compareTo(Object other); // Abstract method declaration
}
```
## Concrete Class

- **Definition**: A concrete class is a regular class that can be instantiated directly. It provides implementations for all its methods, including those inherited from abstract classes or interfaces.
- **Example**: 

```dart
class Rectangle extends Shape {
  @override
  void draw() {
    print('Drawing a rectangle...'); // Method implementation
  }
}
```


# Mixins

- **Definition**: 
	- Mixins are a way to `reuse` code in multiple classes `without` using `inheritance`. 
	- They allow you to add functionality to a class without subclassing. 
	- Mixins are created using the `with` keyword in Dart.
- **Example**: 

```dart
// Mixin providing logging functionality
mixin LoggerMixin {
  void log(String message) {
    print('[Log]: $message');
  }
}

// Mixin providing formatting functionality
mixin FormatterMixin {
  String format(String text) {
    return '[Formatted]: $text';
  }
}

// Class using both mixins
class MyClass with LoggerMixin, FormatterMixin {
  void doSomething() {
    String result = format('Hello, world!');
    log(result);
  }
}

void main() {
  MyClass myClass = MyClass();
  myClass.doSomething(); // Output: [Log]: [Formatted]: Hello, world!
}
```

# Conditions in Dart

- **Definition**: 
	- Conditions in Dart are used to make decisions in your code based on the evaluation of expressions. 
	- Dart supports several types of conditions, including `if`, `else`, `else if`, and `switch` statements.
### `if` Statement

- **Usage**: The `if` statement is used to execute a block of code if a specified condition is true.
- **Example**: 

```dart
int x = 10;
if (x > 5) {
  print('x is greater than 5');
}
```
### `else` Statement

- **Usage**: The `else` statement is used to execute a block of code if the `if` condition evaluates to false.
- **Example**: 

```dart
int x = 3;
if (x > 5) {
  print('x is greater than 5');
} else {
  print('x is not greater than 5');
}
```
### `else if` Statement

- **Usage**: The `else if` statement is used to specify a new condition if the first condition is false.
- **Example**: 

```dart
int x = 3;
if (x > 5) {
  print('x is greater than 5');
} else if (x == 5) {
  print('x is equal to 5');
} else {
  print('x is less than 5');
}
```
### Ternary Operator

- **Usage**: 
	- The ternary operator (`condition ? expr1 : expr2`) is a concise way to express a conditional expression. 
	- It evaluates `condition`. If `condition` is true, `expr1` is evaluated and returned; otherwise, `expr2` is evaluated and returned.
- **Example**: 

```dart
int x = 10;
String message = x > 5 ? 'x is greater than 5' : 'x is not greater than 5';
print(message);
```
### `switch` Statement

- **Usage**: The `switch` statement is used to perform different actions based on different conditions.
- **Example**: 

```dart
String grade = 'A';
switch (grade) {
  case 'A':
    print('Excellent!');
    break;
  case 'B':
    print('Good job!');
    break;
  default:
    print('Keep it up!');
}
```
# Loops

- **Definition**: 
	- Loops are used to repeatedly execute a block of code as long as a specified condition is true. 
	- Dart supports several types of loops, including `for`, `while`, `do-while`, and `forEach` loops.
### `for` Loop

- **Usage**: The `for` loop is used to iterate over a range of values or elements in a collection.
- **Example**: 

```dart
for (int i = 0; i < 5; i++) {
  print('Index $i');
}
```
### `while` Loop

- **Usage**: The `while` loop is used to execute a block of code as long as a specified condition is true.
- **Example**: 

```dart
int i = 0;
while (i < 5) {
  print('Index $i');
  i++;
}
```
### `do-while` Loop

- **Usage**: The `do-while` loop is similar to the `while` loop, but the condition is evaluated after the block of code is executed, ensuring that the block is executed at least once.
- **Example**: 

```dart
int i = 0;
do {
  print('Index $i');
  i++;
} while (i < 5);
```

### `forEach` Loop

- **Usage**: The `forEach` loop is used to iterate over the elements of a collection, such as a list.
- **Example**: 

```dart
List<int> numbers = [1, 2, 3, 4, 5];
numbers.forEach((number) {
  print('Number: $number');
});
```
# Collections

- **Definition**: 
	- Collections are used to `store multiple values` in a single variable. 
	- Dart supports several types of collections, including `List` and `Map`.
### List

- **Definition**: 
	- A list is an `ordered` collection of objects, where each object can be accessed by its `index`. 
	- Lists in Dart are zero-indexed.
- **Example**: 

```dart
List<int> numbers = [1, 2, 3, 4, 5];
print(numbers[0]); // Output: 1

// Additional methods:
numbers.add(6); // Adds an element to the end of the list.
numbers.addAll([7, 8]); // Adds all elements from another list to the end of this list.
numbers.insert(0, 0); // Inserts an element at the specified index.
numbers.remove(3); // Removes the first occurrence of the specified value.
numbers.removeAt(1); // Removes the element at the specified index.
print(numbers); // Output: [0, 2, 4, 5, 6, 7, 8]
```

### Map

- **Definition**: 
	- A map is a collection of `key-value pairs`, where each key is unique and maps to a corresponding value. `Keys` and `values` can be of `any data type`.
- **Example**: 

```dart
Map<String, int> scores = {
  'John': 90,
  'Alice': 85,
  'Bob': 95,
};
print(scores['Alice']); // Output: 85

// Additional methods:
print(scores.entries); // Prints all key-value pairs.
print(scores.keys); // Prints all keys.
print(scores.values); // Prints all values.
scores['Charlie'] = 88; // Inserts a new key-value pair.
scores.remove('Alice'); // Removes the entry with the specified key.
print(scores.isEmpty); // Checks if the map is empty.
print(scores.isNotEmpty); // Checks if the map is not empty.
print(scores.containsKey('Bob')); // Checks if the map contains a key.
```
# Stack and Heap

- **Definition**: In Dart, memory is divided into two main areas: the `stack` and the `heap`.
### Stack

- **Definition**: 
	- The stack is a special region of memory that stores primitive data types and method invocation frames. 
	- It follows a Last-In-First-Out (LIFO) approach.
- **Example (Primitive Variables)**: 

```dart
void main() {
  int x = 10; // Variable 'x' is stored on the stack.
}
```

- **Primitive Variables**: Primitive variables hold `simple`, `single` values directly in memory.
### Heap

- **Definition**: 
	- The heap is a region of memory that stores objects (instances of classes) and arrays. 
	- It follows a dynamic allocation approach.
- **Example (Reference Variables)**: 

```dart
void main() {
  List<int> numbers = [1, 2, 3]; // List object is stored on the heap.
}
```

- **Reference Variables**: Reference variables hold references (memory addresses) to objects stored in the heap.
# `is` and `as` Keywords in Dart

## `is` Keyword

- **Usage**: 
  - The `is` keyword is used to check if an object is an instance of a particular type at runtime.
  - It returns `true` if the object is an instance of the specified type, otherwise `false`.

- **Example**:

```dart
void main() {
  String text = 'Hello';
  
  // Checking if 'text' is a String.
  if (text is String) {
    print('Text is a String');
  } else {
    print('Text is not a String');
  }
}
```

## `as` Keyword

- **Usage**: 
  - The `as` keyword is used for type casting or type conversion in Dart.
  - It attempts to cast an object to a specified type. If successful, it returns the object with the specified type; otherwise, it returns `null`.

- **Example**:

```dart
void main() {
  dynamic value = 10; // Dynamic variable
  
  // Casting 'value' to an int.
  int? number = value as int?;
  if (number != null) {
    print('Number: $number');
  } else {
    print('Value cannot be cast to an int');
  }
}
```

