# Lesson Two

# Creating your first program

In this lesson, we will build a simple Flutter application. ## Creating a new project We start by creating a new project as explained in [Lesson One](https://github.com/altherwy/IS4904/blob/main/Lecture%20One/Lecture%20One.md). Then, we delete everything in *main.dart*, which is found in [**ROOT->lib->main.dart**]. *ROOT* is the root folder of your app. By default, Android Studio will create a new project and displays the *main.dart* file. After deleting everything, add the following to *main.dart*,

```dart
void main(){
}
```

The *main* method is the starting point of any Flutter app.

## Creating a new Widget

A Flutter app is basically a collection of widgets displayed on the screen. The collection of widgets is referred to in the Flutter world as **Widget Tree**. In a Widget Tree, widgets can reside next to each other vertically and horizontally as well as inside each other. A simple example of a Widget is the **Text** widget,

```dart
Text('some text')
```

Some of the widgets, such as the **Text** widget, are built-in and can be invoked by,

```dart
import 'package:flutter/material.dart'
```

*material.dart* is a dart class that implements **Material Design** by Google. From their [official website](https://m3.material.io/get-started),

> Material Design is a design system built and supported by Google designers and developers. Material.io includes in-depth UX guidance and UI component implementations for Android, Flutter, and the Web.
> 

The *material.dart* contains the widgets we need to create beautiful Flutter app as well as define a new custom widget. In fact, you usually need to define at least one custom widget as a Flutter app is basically one giant custom widget that contains other, built-in and custom, widgets. ## Creating a custom Widget To create a custom widget, you have to *extends* (inherit) from either *StatelessWidget* or *StatefulWidget* widgets. Both widgets are included in the *material.dart* and the difference between them is that *Stateless* has a state that cannot be changed once the widget is created. On the other hand, *Stateful* widget can change its state after it was created. We further explain *states* in future lessons.

To build a custom *Stateless* widget,

```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // return a widget
    return MaterialApp(home: Text('Hello'),);
  }
}
```

We created a new *class*, which we named *MyApp* (you can write any other *valid* [class name](https://dart.dev/language/classes)). *MyApp* *extends* (inherits) from *StatelessWidget*. Inheriting from *StatelessWidget* requires *overriding* the *build* function. In layman terms, the build function *draw* the widget on the screen and its called whenever the class (*MyApp* in this case) is called.

- The *build* function accepts as an argument, an object with a *BuildContext* type. *BuildContext* is a class responsible for locating a widget in the widget tree. Remember from earlier that Flutter is composed of widgets refereed to as the **Widget Tree**. *BuildContext* job is to track the location of widgets in that tree. *BuildContext* is defined in *material.dart*.
- The *build* function returns a widget. In this example, it returns the *MaterialApp* widget. The *MaterialApp* is a base widget that contains all other widgets and it uses the *Material Design* explained earlier. In the *MaterialApp*, we pass a *Text* widget to the *name* parameter, which displays a text (*Hello* in this case) on the screen. We discuss *Text* widget in details in [Lecture Three](https://github.com/altherwy/IS4904/blob/main/Lecture%20Three/Lecture%20Three.md).

After creating the custom widget, we call this custom widget in the main,

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

*runApp* is a function in the *material.dart* to call the **root** widget in the app. In other words, the first widget in the widget tree.

After running the app (**Run-> Run ‘main.dart’**), the following screen should appear,

![https://github.com/altherwy/IS4904/blob/main/pics/Hello%20program.jpg?raw=true](https://github.com/altherwy/IS4904/blob/main/pics/Hello%20program.jpg?raw=true)

This concludes Lesson Two.

---
# Summary
This lesson discuss how to create a simple Flutter application by creating a new project. It explains how to create a **widget tree**, how to create a custom widget by extending *StatelessWidget*, and how to call the root widget in the app using *runApp*. 
# Tutorials

- Change the text in *Text* widget inside *MaterialApp* to your name.
- Change the color of the *Text* widget to **white**. (Hint: lookup TextStyle widget)
- Create a new custom widget that has a *Text* widget that displays the following phrase: 'Flutter uses Dart'
