# Nullability in Dart

Dart introduced null safety as an optional setting in Dart 2.12, and it is required in Dart 3. With null safety, values can’t be null unless you say they can be. This makes it easier to avoid null reference errors and improve code reliability.

## Nullable and Non-nullable Types

With null safety, all types default to non-nullable. For example, if you have a variable of type `String`, it always contains a string. To allow a variable of type `String` to accept any string or the value `null`, add a question mark (`?`) after the type name. This changes the type of variable to a nullable type. For example, a variable of type `String?` can contain a string or it can be `null`.

```dart
String? carName; // initialized to null by default
int? marks = 36; // initialized to non-null
marks = null; // can be re-assigned to null
```
## Null-aware Operators

Null-aware operators are used to handle nullable values more efficiently and safely.

### Null-coalescing Operators (?? and ??=)

The null-coalescing operator (`??`) allows you to provide a default value when an expression is `null`,

```dart
String? name;
String fullName = name ?? 'John Doe'; // returns 'John Doe' if name is null
```
or, you can use ??= to update the same variable,
```dart
int? fontSize;
fontSize ??= 12;
```

### Null Assertion Operator (!)

If you’re sure an expression with a nullable type doesn’t equal `null`, you can use the null assertion operator (`!`) to make Dart treat it as non-nullable. By adding `!` after the expression, you assert two conditions to Dart about the expression:

1. Its value doesn’t equal `null`.
2. Dart can assign the value to a non-nullable variable.

If the expression does equal `null`, Dart throws an exception at run-time. This makes the `!` operator unsafe. Don’t use it unless you have no doubt the expression can’t equal `null`.

```dart
String? name = 'John';
String fullName = name! + ' Doe'; // throws an exception if name is null
```



### Conditional Property Access (?.)

The conditional property access operator (`?.`) allows you to access properties and methods of an object only if that object is not `null`. If the object is `null`, the entire expression evaluates to `null`.

```dart
int? age;
print(age?.isNegative); // do not crash when age is null, instead it returns null
```
### Late Keyword

The `late` keyword is used to declare variables that will be initialized later in the code. These variables are called non-nullable variables as they are initialized after the declaration². Once a non-nullable variable is declared with the `late` keyword, it cannot be null at runtime.

Here is an example of using the `late` keyword:

```dart
late String name;

void main() {
  name = 'John Doe';
  print(name); // Output: John Doe
}
```

In the above example, the variable `name` is declared with the `late` keyword. It is initialized later in the `main()` function. When we print the value of `name`, it outputs "John Doe" because it has been assigned a value³.

The `late` keyword is useful when you don't know the initial value of a variable, but you assure Dart that you will initialize it before using it³. It helps prevent null reference errors and improves code reliability.

## Conclusion

Null safety in Dart makes it easier to write reliable code by preventing null reference errors. By using nullable and non-nullable types, null assertion operators, and null-aware operators, you can handle nullable values more efficiently and safely.

Happy coding! 🚀
