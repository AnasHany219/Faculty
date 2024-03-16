# Classes and Object

```dart
/* Simple Hello, World! program */
void main(){
    // Create Object 
    Student s1 = Student(); // Creates an instance of the Student class.
    s1.name = 'Anas'; // Sets the name attribute of the s1 object to 'Anas'.
    s1.age = 20; // Sets the age attribute of the s1 object to 20.
   
    // Prints the name and age attributes of the s1 object.
    print(s1.name);
    print(s1.age);
    
    // Calls the registration and printReport methods of the s1 object and prints the returned values.
    String regist = s1.registration('Flutter');
    String report = s1.printReport('Anas');
    
    print(regist);
    print(report);
}

// Create Class
class Student{
    // Class Attributes
    late String name; // Declares a string attribute 'name' for the Student class.
    late int age; // Declares an integer attribute 'age' for the Student class.
    
    // Class Methods
    String registration(String courseName){
        return 'Anas'; // Returns a string indicating registration confirmation.
    }
    String printReport(String stdName){
        return 'Reprot'; // Returns a string indicating a report.
    }
}
```

[[Section 3 - OOP]]