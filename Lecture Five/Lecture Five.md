# StatefulWidget
*StatefulWidget* is a widget that has a mutable state. It can be used to represent any object that can be changed over time.
### State and setState
*State* is a data structure that holds some information that may change over the lifetime of the widget. It is immutable, which means that the state cannot be changed directly by the widget. Instead, the widget must call the *setState* function to change the state. The *setState* function notifies the framework that the state has changed, and the framework will redraw the widget.
### Example
The following code shows how to create a *StatefulWidget* that displays a counter. The *StatefulWidget* is called *Counter* and the *State* is called *CounterState*. The *Counter* widget has a *createState* function that returns a *CounterState* object. The *CounterState* object has a *build* function that returns a *Text* widget that displays the current count.
```dart
class Counter extends StatefulWidget {
  const Counter({Key? key}) : super(key: key);

  @override
  State<Counter> createState() => _CounterState();

  class _CounterState extends State<Counter> {
    int _count = 0;

    @override
    Widget build(BuildContext context) {
      return Text('Count: $_count');
    }
  }

}
```
Now, in order to change the counter, we need to call the *setState* function. *setState* is provided by the *State* class. It takes a function as a parameter, which changes the current state of the widget. In other words, the *setState* function notifies the framework that the state has changed, and that the framework should redraw the widget (i.e., call the *build* function). 
The following code shows how to create a button that increments the counter by one when pressed.
```dart
class Counter extends StatefulWidget {
  const Counter({Key? key}) : super(key: key);

  @override
  State<Counter> createState() => _CounterState();

  class _CounterState extends State<Counter> {
    int _count = 0;
    void changeCount() {
      setState(() {
        _count++;
      });
    }
    @override
    Widget build(BuildContext context) {
      return Column(
        children: [
          Text('Count: $_count'),
          ElevatedButton(
            onPressed: changeCount,
            child: const Text('Increment'),
          ),
        ],
      );
    }
  }

}
```
# Exercises
- Create a *StatefulWidget* that displays an image. The image should be centered on the screen. The image should change to another image when the user presses a button. You need to add five different images in the *assets* folder. When the user reaches the last image, the image should change back to the first image.
- Reformat the code from the previous exercise to display the images in a random order. In other words, the images should be displayed in a random order every time the user presses the button.