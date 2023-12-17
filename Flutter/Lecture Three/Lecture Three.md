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
## Container
*Container* is a widget that allows you to encapsulate other widgets and customize their appearances. For example, you can add a gradient affect to a *Text* widget,,
```dart
Container(
  decoration: BoxDecoration(
    gradient: LinearGradient(
      colors: [Colors.red, Colors.blue],
    ),
  ),
  child: Text('text here'),
)
```
The *Container* widget in the code above contains two new widgets: *BoxDecoration* and *LinearGradient*. *BoxDecoration* is a widget that allows you to customize the appearance of the parent widget, *Container* in this case. One type of gradient effect in *BoxDecoration* is *LinearGradient*. *LinearGradient* is a widget that allows you to add a linear gradient effect.

## Center
*Center* is a widget that allows you to **center** other widgets. For example, to center a *Text* widget,

```dart
Center(child: Text('text here'))
```

## ElevatedButton
*ElevatedButton* is a button and it replaces the deprecated *RaisedButton*. To display an *ElevatedButton*

```dart
ElevatedButton( onPressed: ..., child: ...)
```
*ElevatedButton* should at least have two named parameters: 
- **onPressed**: it accepts a function as a value, which is called when the button is **pressed**.
- **child**: it accepts a *text* or an *icon* to display on the button. 
---
The following is a simple example that uses what we have learned thus far in this lesson,

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
          title: const Text(
            'First App',
            style: TextStyle(color: Colors.white),
          ),
        ),
        body: Container(
          decoration: const BoxDecoration(
            gradient: LinearGradient(
              colors: [Colors.blue, Colors.purple],
            ),
          ),
          child: Center(
            child: Column(
              children: const [
                Text(
                  'What is your name?',
                  style: TextStyle(
                    color: Colors.white,
                  ),
                ),
                ElevatedButton(
                    onPressed: null,
                    child: Text(
                      'submit',
                      style: TextStyle(
                        color: Colors.white,
                      ),
                    ))
              ],
            ),
          ),
        ),
      ),
    );
  }
}

```
The above code displays the following,

![https://github.com/altherwy/IS4904/blob/main/pics/widgets.jpg?raw=true](https://github.com/altherwy/IS4904/blob/main/pics/widgets.jpg?raw=true)


# Summary
This lesson covers different widgets such as the Scaffold widget for structuring other widgets, the Text widget for displaying text, the Column widget for organizing widgets vertically, and the ElevatedButton widget for creating buttons.To learn more about widgets, check out the official [widget catalog](https://docs.flutter.dev/ui/widgets).

---
# Exercises
- Reformat the last code to organize the widgets *horizontally* (Hint: lookup *Row*)
- Reformat the last code to change the background color of the *Scaffold* to **Red**.
- Reformat the last code to change the *AppBar* color to **Red**.
- Reformat the last code to change the start and end colors of the gradient effect (Hint: lookup *begin* and *end* in *LinearGradient*)
- Reformat the last code to create a new widget called *MyButton* that replaces the *ElevatedButton* widget in the code. However, it should accept the *text* as a parameter. Then, use the *MyButton* widget to create two buttons: *Submit* and *Cancel*.
- In Flutter, it is considered a good practice to split the classes into different **.dart** files. Thus, create a new file called *my_app.dart* and move the *MyApp* class to it. Then, import the *my_app.dart* file into the *main.dart* file and fix any errors.
- Write the code to generate the following snapshot

![https://github.com/altherwy/IS4904/blob/main/pics/Row%20and%20Column%20widgets.jpg?raw=true](https://github.com/altherwy/IS4904/blob/main/pics/Row%20and%20Column%20widgets.jpg?raw=true)
  
  ```dart