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

To put it all together, we start by solving the example in the exercise from the [previous lecture](https://github.com/altherwy/IS4904/blob/main/Lecture%20Five/Lecture%20Five.md),

```dart
// main.dart
import 'package:flutter/material.dart';
import 'my_app.dart';
void main() {
  runApp(const MyApp());
}
```
```dart
// my_app.dart
import 'package:flutter/material.dart';
import 'dice_roller.dart';
class MyApp extends StatelessWidget {
  const MyApp({super.key});
  @override
  Widget build(BuildContext context) {
    // return a widget
    return MaterialApp(
      home: Scaffold(
        body: Container(
          decoration: const BoxDecoration(
            gradient: LinearGradient(
              colors: [Colors.blueGrey, Colors.purple],
              begin: Alignment.topLeft,
              end: Alignment.bottomRight,
            ),
          ),
          child: const Center(
            child: DiceRoller(),
          ),
        ),
      ),
    );
  }
}
```
```dart
// dice_roller.dart
import 'package:flutter/material.dart';
import 'my_button.dart';
import 'dart:math';
class DiceRoller extends StatefulWidget {
  const DiceRoller({Key? key}) : super(key: key);
  @override
  State<DiceRoller> createState() => _DiceRollerState();
}
class _DiceRollerState extends State<DiceRoller> {
  var activeDiceImage = 'assets/images/dice-1.png';
  int rand = 1;


  void rollDice() {
    setState(() {
        rand = (rand+1)%6;
        activeDiceImage = 'assets/images/dice-${rand+1}.png';
    });
  }
  @override
  Widget build(BuildContext context) {
    return Column(
      mainAxisSize: MainAxisSize.min,
      children: [
        MyButton(activeDiceImage),
        const SizedBox(
          height: 10,
        ),
        TextButton(
          onPressed: rollDice,
          style: TextButton.styleFrom(
              padding: const EdgeInsets.symmetric(
                vertical: 10,
              ),
              foregroundColor: Colors.yellow,
              textStyle: const TextStyle(
                fontSize: 28,
              )),
          child: const Text(
            'Roll the dice',
          ),
        )
      ],
    );
  }
}
```
```dart
// my_button.dart
import 'package:flutter/material.dart';
class MyButton extends StatelessWidget {
  const MyButton(this.textValue,  {super.key});
  final String textValue;
  @override
  Widget build(BuildContext context) {
    return TextButton(
          onPressed: null,
          child: Image.asset(
            textValue,
            height: 200,
            width: 200,
          ),
        );
  }
}
```
We now add another route (i.e., page) to our app,
```dart
// second_route.dart
import 'package:flutter/material.dart';

class SecondRoute extends StatelessWidget {
  const SecondRoute({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: Container(
          decoration: const BoxDecoration(
            gradient: LinearGradient(
              colors: [Colors.blueGrey, Colors.purple],
              begin: Alignment.topLeft,
              end: Alignment.bottomRight,
            ),
          ),
          child: Center(
            child: Column(
              mainAxisSize: MainAxisSize.min,
              children: [
                TextButton(
                  onPressed: () {},
                  child: Image.asset('assets/images/dice-1.png'),
                ),
                const SizedBox(height: 20),
                ElevatedButton(
                  onPressed: () {
                    // we move to the previous page
                    Navigator.pop(context);
                  },
                  child: const Text('Go back to the previous page'),
                )
              ],
            ),
          ),
        ),
      ),
    );
  }
}

```
Now, we modify our *DiceRoller* widget to use the *Navigator* widget to navigate to the *SecondRoute* widget,
```dart
// dice_roller.dart
.
.
.
ElevatedButton(
          onPressed: () {
            Navigator.push(
              context,
              MaterialPageRoute(builder: (context) => const SecondRoute()),
            );
          },
          child: const Text('Go to the next page'),
        )
.
.
.
```
# Navigation with Hero Animation
We can use the *Hero* widget to animate the transition between two routes. The *Hero* widget takes a *tag* as a parameter. The *tag* is used to identify the *Hero* widget. The *Hero* widget is used to wrap a widget that is displayed in both the current and the next route. For example, we can modify the *MyButton* widget to use the *Hero* widget,
```dart
// my_button.dart
import 'package:flutter/material.dart';
class MyButton extends StatelessWidget {
  const MyButton(this.textValue,  {super.key});
  final String textValue;
  @override
  Widget build(BuildContext context) {
    return Hero(
      tag: 'dice',
      child: TextButton(
            onPressed: null,
            child: Image.asset(
              textValue,
              height: 200,
              width: 200,
            ),
          ),
    );
  }
}
```
# Exercise
- Modify the *SecondRoute* widget to display the image of the dice that was rolled in the *main* route. For example, if the main *route* shows a *dic-3* image, the *SecondRoute* widget should display the same image.
- Modify the *SecondRoute* widget to display the number of times the dice was rolled in the *main* route. For example, if the dice was rolled 5 times in the *main* route, the *SecondRoute* widget should display the number 5.