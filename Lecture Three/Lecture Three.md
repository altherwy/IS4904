# All about Widgets

In this lesson, we will build a simple app to better explain widgets. We start with the simple code from [Lecture Two](https://github.com/altherwy/IS4904/blob/main/Lecture%20Two/Lecture%20Two.md)

```dart
import 'package:flutter/material.dart';
void main(){
  runApp(MyApp());
}
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // return a widget
  return MaterialApp(home: Text('Hello'),);
  }
}
```
## Scaffold
Scaffold is a widget structure to include other widgets. It has many useful named parameters, including:
- appBar: this parameter displays the bar of an app (usually at the top of the screen). 
- body: this parameter represent the body of the screen where other widgets are displayed. 

The following code displays a blank screen with a bar at the top

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('First App'),
        ),
        body: null,
      ),
    );
  }
}
```