# rich_text_controller

An extended text editing controller that supports different inline styles for custom regex

## Getting Started
Add `rich_text_controller` to your package's pubspec.yaml file:

```dart
dependencies:
  pagarme_flutter_card_hash: [latest version]
```
Import it
```dart
import'rich_text_controller/rich_text_controller.dart';
```
## Demo
![](lib/demo.gif)

## Usage
```dart
import 'package:flutter/material.dart';  
import 'rich_text_controller/rich_text_controller.dart';  
  
void main() => runApp(MyApp());  
  
class MyApp extends StatelessWidget {  
  @override  
  Widget build(BuildContext context) {  
    return MaterialApp(  
      title: 'RichText Controller Demo',  
      theme: ThemeData(  
        primarySwatch: Colors.blue,  
      ),  
      home: RichTextControllerDemo(),  
    );  
  }  
}  
  
class RichTextControllerDemo extends StatefulWidget {
  @override
  _RichTextControllerDemoState createState() => _RichTextControllerDemoState();
}

class _RichTextControllerDemoState extends State<RichTextControllerDemo> {

// Add a controller
RichTextController _controller;

  @override
  void initState() {
      // initialize with your custom regex patterns and styles
      _controller = RichTextController({
           //
          //* Returns every Hashtag with red color
          //
          RegExp(r"\B#[a-zA-Z0-9]+\b"):TextStyle(color:Colors.red),
         // add as many expressions as you need!
      });
    super.initState();
  }
}
```