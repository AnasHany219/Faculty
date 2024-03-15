# Named parameters
- Named parameters allow you to specify parameters explicitly by name when calling the constructor, which can improve code readability and make it more flexible.

```dart
class Person {
  // Named constructor with named parameters
  Person.insert({String? name, int? age, String? address, String? pen, String? type, String? email}) {
    // Here, you can initialize the attributes based on the provided parameters
  }
}

void main() {
  // Creating an instance of Person using the named constructor
  Person p = Person.insert(
    age: 30,
    name: 'Anas',
    pen: '555',
    type: 'male'
  );
}
```
# **Constructor**
- Constructors in Dart are special methods used for initializing objects of a class. 
- There are mainly two types of constructors: **parameterized** and **default** constructors.
### Parameterized Constructor:
- A parameterized constructor is a constructor that allows you to pass arguments when creating an instance of a class. 
- It initializes the object's properties with the values provided as parameters. Here's an example:

```dart
class Person {
  String name;
  int age;
  
  // Parameterized constructor
  Person(this.name, this.age);
}

void main() {
  // Creating an instance of Person using the parameterized constructor
  Person person = Person('John', 25);
}
```
### Default Constructor:
- A default constructor is a constructor that doesn't take any parameters. 
- It's created automatically by Dart if you don't define any constructors in your class. 
- It initializes the object's properties with default values. Here's an example:

```dart
class Person {
  String name;
  int age;
  
  // Default constructor
  Person() {
    name = 'Unknown';
    age = 0;
  }
}

void main() {
  // Creating an instance of Person using the default constructor
  Person person = Person();
}
```

- You can define both a parameterized constructor and a default constructor in the same class. Here's an example:

```dart
class Person {
  String name;
  int age;
  
  // Parameterized constructor
  Person(this.name, this.age);
  
  // Default constructor
  Person.defaultConstructor() {
    name = 'Unknown';
    age = 0;
  }
}

void main() {
  // Creating an instance of Person using the parameterized constructor
  Person person1 = Person('John', 25);
  
  // Creating an instance of Person using the default constructor
  Person person2 = Person.defaultConstructor();
}
```

# Inheritance
- Inheritance is a fundamental concept in object-oriented programming where a class (subclass or derived class) can inherit properties and behaviors (methods) from another class (superclass or base class). 
- In Dart, inheritance is achieved using the `extends` keyword. Let's demonstrate inheritance with an example involving `Person`, `Student`, and `Doctor` classes:

```dart
// Base class: Person
class Person {
  String name;
  int age;

  Person(this.name, this.age);
}

// Derived class 1: Student (inherits from Person)
class Student extends Person {
  String major;
  Student(String name, int age, this.major) : super(name, age);
}

// Derived class 2: Doctor (inherits from Person)
class Doctor extends Person {
  String specialty;
  Doctor(String name, int age, this.specialty) : super(name, age);
}

void main() {
  // Creating a student
  Student student = Student('John', 20, 'Computer Science');

  print('---');

  // Creating a doctor
  Doctor doctor = Doctor('Emily', 30, 'Cardiology');
}
```

Explanation:
- `Person` is the base class with properties `name` and `age`.
- `Student` and `Doctor` are derived classes that inherit from `Person` using the `extends` keyword.
- Each derived class adds its own properties (`major` for `Student` and `specialty` for `Doctor`).
- When an instance of `Student` or `Doctor` is created, it can access both the inherited properties/methods from `Person` and its own properties/methods specific to the subclass.

Inheritance allows you to create a hierarchy of classes, promoting code reuse and structuring your code in a more logical and organized manner.