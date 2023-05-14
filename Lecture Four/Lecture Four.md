# Assets, Buttons, and Buttons style
## Assets
In Flutter, if you need to add an asset such as images, you first need to create a folder that contains those assets and then add the folder to the *pubspec.yaml* file. The *pubspec.yaml* file is a configuration file that contains information about the project such as the Flutter *SDK* version. To add an asset folder called *assets* to the *pubspec.yaml* file,
```yaml
flutter:
  assets:
    - assets/
```
The *assets* folder in this case is located in the root directory of the project. Now, to add an image to the code, use the *Image.asset* widget,
```dart
Image.asset('assets/images/image_name.jpg'),
```
Note that after the *pubspec.yaml* file is changed, you need to click on *Pub get* to update the project dependencies.
 
## Buttons
In Flutter, there are many types of button. [Lecture Three](https://github.com/altherwy/IS4904/blob/main/Lecture%20Three/Lecture%20Three.md) introduces one type of button called *ElevatedButton*. *ElevatedButton* is a button that has a shadow. The following code shows how to create a button using the *ElevatedButton* widget.
```dart
ElevatedButton(
  onPressed: null,
  child: Text(
    'Submit',
    style: const TextStyle(
      color: Colors.white,
    ),
  ),
);
```
Another type of button is called *TextButton*. *TextButton* with clickable text. The following code shows how to create a button using the *TextButton* widget.
```dart
TextButton(
  onPressed: null,
  child: Text(
    'Submit',
    style: const TextStyle(
      color: Colors.white,
    ),
  ),
);
```
Finally, *OutlinedButton* is a button that has a border without a shadow. The following code shows how to create a button using the *OutlinedButton* widget.
```dart
OutlinedButton(
  onPressed: null,
  child: Text(
    'Submit',
    style: const TextStyle(
      color: Colors.white,
    ),
  ),
);
```
The common named parameters between the three buttons are *onPressed* and *child*. The *onPressed* parameter is a function that is called when the button is clicked. The *child* parameter is a widget that is displayed inside the button. 

### onPressed
The *onPressed* parameter accepts a function that is called when the button is clicked. The function should be *void* and accept no parameters. The following code shows how to create a function that is called when the button is clicked.
```dart
void submit() {
  print('Submit button is clicked');
}
```
To call the *submit* function when the button is clicked, pass the *submit* function to the *onPressed* parameter,
```dart
ElevatedButton(
  onPressed: submit,
  child: Text(
    'Submit',
    style: const TextStyle(
      color: Colors.white,
    ),
  ),
);
```
Note that the *submit* function is passed to the *onPressed* parameter **without parentheses**. If the parentheses are added, the function will be called immediately when the button is created, which is not the desired behavior.

To override the style of the button, use the *style* parameter and the *.styleFrom* function. The following code shows how to change the background color of the button to *Colors.red*.
```dart
ElevatedButton(
  onPressed: submit,
  style: ElevatedButton.styleFrom(
    backgroundColor: Colors.red,
  ),
  child: Text(
    'Submit',
    style: const TextStyle(
      color: Colors.white,
    ),
  ),
);
```
Note that is is a common practice in Flutter to place the *child* parameter as the last parameter of a widget.
### Padding
In Flutter, the *Padding* is used to add padding to a widget. It accepts a widget of type *EdgeInsets*. The *EdgeInsets* class specify padding at four different locations: *top*, *bottom*, *left*, and *right*. The following code shows how to add a **uniform** padding to an *ElevatedButton* widget by using *EdgeInsets.all()*,
```dart
ElevatedButton(
  onPressed: submit,
  style: ElevatedButton.styleFrom(
    padding: const EdgeInsets.all(8.0),
    backgroundColor: Colors.red,
  ),
  child: Text(
    'Submit',
    style: const TextStyle(
      color: Colors.white,
    ),
  ),
);
```
An alternative way to add a padding is to use *SizedBox* widget. The *SizedBox* renders an empty box that has a *width* and/or *height*. The following code shows how to add a padding above an *ElevatedButton* widget by using *SizedBox*,
```dart
SizedBox(height: 8.0),
ElevatedButton(
  onPressed: submit,
  style: ElevatedButton.styleFrom(
    backgroundColor: Colors.red,
  ),
  child: Text(
    'Submit',
    style: const TextStyle(
      color: Colors.white,
    ),
  ),
);
```


# Tutorial
- Change the width and height of an image to 200 pixels both.
- Create an *OutlinedButton* widget that displays the text *Cancel*.
- Create a function called *cancel* that prints *Cancel button is clicked*, and pass it to the *onPressed* parameter of the *OutlinedButton* widget created in the previous step.
- Change the background color of the *OutlinedButton* widget to *Colors.purple*.
- Add a padding of 10 pixels to the *OutlinedButton* widget at the **top and bottom** only.
- Add a padding of 10 pixels to the *OutlinedButton* widget using *SizedBox* widget.

