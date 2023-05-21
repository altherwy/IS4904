# Navigation
In Flutter, your app may contain multiple screens. To navigate between them, you can use the *Navigator* widget. The *Navigator* widget manages a stack of *Route* objects. In Flutter, screens are refereed to as *routes*. To navigate to a new route, *Navigator.push* is used. To go back to the previous route, *Navigator.pop* is used.

## Navigator.push
The *Navigator.push* function takes a *BuildContext* and a *Route* as parameters.
- The *BuildContext* is used to find the *Navigator* widget. 
- The *Route* is used to specify the route to navigate to. 

The *Route* can be created using the *MaterialPageRoute* class. The *MaterialPageRoute* class takes a *builder* function as a parameter, which takes a *BuildContext* as a parameter and returns a *Widget*. The *Widget* returned by the *builder* function is the screen that will be displayed when the user navigates to the route. For example,
```dart
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => SecondRoute()),
);
```
## Navigator.pop
The *Navigator.pop* function takes a *BuildContext* as a parameter. The *BuildContext* is used to find the *Navigator* widget. The *Navigator.pop* function removes the current route from the stack of routes and navigates to the previous route. For example,
```dart
Navigator.pop(context);
```

