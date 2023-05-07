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

Using *Scaffold* widget, the following code displays a blank screen with a bar at the top

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
![](https://github.com/altherwy/IS4904/blob/main/pics/Scaffold.jpg?raw=true)

## Text and TextStyle
*Text* widget is one of the popular widgets in *material.dart*. It displays a text on the screen,
```dart
Text('text here')
```
You can customize the text using *TextStyle* widget. For example, you can change the color of the text,

```dart
Text('text here', style:TextStyle(color:Colors.black))
```
## Column
In terms of visibility, widgets can either be **Visible**, **Non Visible**, or combination of both. *Text* is a visible widget, whereas, *Column* is an example of *non visible* widgets.

*Column* is a widget that organize other widgets in a vertical fashion. An important named parameter for *Column* is *children*. *children* value is a list of widgets. For example, to display multiple *Text* widgets in a vertical manner,

```dart
Column(children: [Text('First Text'), Text('Second Text'), Text('Third Text')])
```

## ElevatedButton
*ElevatedButton* is a button and it replaces the deprecated *RaisedButton*. To display an *ElevatedButton*

```dart
ElevatedButton( onPressed: ..., child: ...)
```
*ElevatedButton* should at least have two main named parameters: 
- **onPressed**: it accepts a function as a value, which is called when the button is **pressed**.
- **child**: it accepts a *text* or an *icon* to display on the button. 
---
The following is a simple example that displays what we have learned thus far in this lesson,

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // return a widget
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('First App'),
        ),
        body: Column(
          children: [
            Text('What is your name?'),
            ElevatedButton(onPressed: null, child: Text('submit'))
          ],
        ),
      ),
    );
  }
}
```
The above code displays the following,
![](https://github.com/altherwy/IS4904/blob/main/pics/widgets.jpg?raw=true)

This concludes this lesson. 
---
# Tutorial
- Reformat the last code to organize the widgets *horizontally* (Hint: lookup *Row*)
- Write the code to generate the following snapshot
![](https://github.com/altherwy/IS4904/blob/main/pics/Row%20and%20Column%20widgets.jpg?raw=true)

