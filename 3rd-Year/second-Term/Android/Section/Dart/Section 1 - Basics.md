# 💡 Variable Declarations

```dart
void main() {
  // Variables
  String name = "Anas"; // Stores the name "Anas" as a string.
  int age = 21; // Stores the age 21 as an integer.
  double salary = 0.0; // Stores the salary as a double value, initialized with 0.0.
  // The type of 'gender' is inferred as String from the assigned value "male".
  var gender = 'male';
  // 'birthYear' is declared with a dynamic type, allowing its type to change during runtime.
  dynamic birthYear = 2003;
  bool isEmployee = false;
  
  print(name);
  print(age);
  print(salary);
  print(gender);
  print(birthYear);
  print(isEmployee);
}
```

# String

## substring()

```dart
  String s1 = "flutter"; 
  // Prints the substring from index 0 to 2 (exclusive), which is "flu".
  print(s1.substring(0, 3));
  // Prints the substring from index 3 to 6 (exclusive), which is "tte".
  print(s1.substring(3, 7));
```
## indexOf()

```dart
  String s1 = 'a flutter a dart'; 
  // Prints the index of the first occurrence of 'f' in 's1', which is 2.
  print(s1.indexOf('f'));
  // Prints the index of the first occurrence of 't' in 's1', which is 4.
  print(s1.indexOf('t'));
  // Prints the index of the first occurrence of 'a' in 's1' after index 2, which is 10.
  print(s1.indexOf('a', 2));
```
## Lower/Upper()

```dart
  String s1 = 'A Flutter, A Dart';
  print(s1.toUpperCase()); // Converts 's1' to uppercase -> A FLUTTER, A DART
  print(s1.toLowerCase()); // Converts 's1' to lowercase -> a flutter, a dart
```
## Contains()

```dart
  String s1 = 'A Flutter, A Dart'; 
  // Checks if the substring 'dart' is present in 's1' (case-sensitive). Prints false.
  print(s1.contains('dart'));
  // Checks if the substring 'Flutter' is present in 's1' (case-sensitive). Prints true.
  print(s1.contains('Flutter'));
```
## starts/endsWith()

```dart
  String s1 = 'A Flutter, A Dart';
  // Checks if 's1' starts with the character 'a'. Prints false because it's case-sensitive.
  print(s1.startsWith('a'));
  // Checks if 's1' starts with the character 'A'. Prints true.
  print(s1.startsWith('A'));
  // Checks if 's1' starts with the substring 'A Flutter'. Prints true.
  print(s1.startsWith('A Flutter'));
  // Checks if 's1' ends with the substring 'art'. Prints true.
  print(s1.endsWith('art'));
```
## Concatenate

```dart
  String s1 = 'A Flutter,'; 
  String s2 = 'A Dart'; 
  // Concatenates 's1' and 's2' and prints the result ('A Flutter,A Dart').
  print(s1 + s2);
  // Concatenates 's1', a space, and 's2' and prints the result ('A Flutter, A Dart').
  print(s1 + ' ' + s2);
```
## Split()

 ```dart
  String s1 = 'A Flutter A Dart'; 
  // Splits at each occurrence of space (' ').
  print(s1.split(' '));  // [A, Flutter, A, Dart]
```
## Padding

```dart
  String s1 = 'A Flutter A Dart';
  // Left-pads 's1' with '-' characters to make its length 17 and prints the result.
  print(s1.padLeft(17, '-'));   // -A Flutter A Dart
  // Right-pads 's1' with '-' characters to make its length 17 and prints the result.
  print(s1.padRight(17, '-'));  // A Flutter A Dart-
```
## Trim()

```dart
  String s1 = 'A Flutter            A Dart';  
  // Removes leading and trailing whitespace from 's1' and prints the result.
  print(s1.trim());
```
## Replace()

```dart
  String s1 = 'A Flutter A Dart'; 
  // Replaces all occurrences of 'A' with 'a' in 's1' and prints the result.
  print(s1.replaceAll('A', 'a'));
  // Replaces characters in 's1' starting from index 10 (inclusive) up to index 16 (exclusive) with the string 'Anas' and prints the result.
  print(s1.replaceRange(10, 16, 'Anas'));
```
