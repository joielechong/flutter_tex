# Flutter TeX

A Flutter Package to render so many types of equations based on **LaTeX**, most commonly used are as followings:

- **Mathematics / Maths Equations** (Algebra, Calculus, Geometry, Geometry etc...)

- **Physics Equations**

- **Signal Processing Equations**

- **Chemistry Equations**

- **Statistics / Stats Equations**

- It also includes full **HTML** with **JavaScript** support.

Rendering of equations depends on [mini-mathjax](https://github.com/electricbookworks/mini-mathjax) a simplified version of [MathJax](https://github.com/mathjax/MathJax/) and [Katex](https://github.com/KaTeX/KaTeX) JavaScript libraries.

This package mainly depends on [webview_flutter](https://pub.dartlang.org/packages/webview_flutter) plugin.


#####  **Katex for fast render.**
#####  **MathJax for quality render.**
## Use this package as a library in your flutter Application

**1:** Add this to your package's pubspec.yaml file:

```yaml
dependencies:
  flutter_tex: ^3.0.0
```

**2:** You can install packages from the command line:

```bash
$ flutter packages get
```

Alternatively, your editor might support flutter packages get. Check the docs for your editor to learn more.


**3:** For **Android** Make sure to add this line `android:usesCleartextTraffic="true"` in your `<project-directory>/android/app/src/main/AndroidManifest.xml` under `application` like this.
```xml
<application
       android:usesCleartextTraffic="true">
</application>
```
and permissions
```xml
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    <uses-permission android:name="android.permission.WAKE_LOCK" />
```

For **iOS** add following code in your `<project-directory>/ios/Runner/Info.plist`
```plist

<key>NSAppTransportSecurity</key>
  
  <dict>
    <key>NSAllowsArbitraryLoads</key> <true/>
  </dict>

<key>io.flutter.embedded_views_preview</key> <true/> 
```

**4:** Now in your Dart code, you can use:

```dart
import 'package:flutter_tex/flutter_tex.dart'; 
```

**5:** Now you can use TeXHTML widget like this.
```dart
    TeXView(
          teXHTML: r"""$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$<br> """,
          renderingEngine: RenderingEngine.Katex,  // Katex for fast render and MathJax for quality render.
          onRenderFinished: (height) {
                print("Widget Height is : $height")
                },   
          onPageFinished: (string) {
                print("Page Loading finished");
              },
        )
```
[Complete working application Example](https://github.com/shahxadakram/flutter_tex/tree/master/example)


## To Do:
- ~~Speed Optimizations as it's a bit slow rendering speed. It takes 1-2 seconds to render after application loaded.~~ (Solved by adding Katex Support)
- Beta support for Flutter Web, Automatically calculation of TeXView Height in Flutter Web and much more to do for Flutter Web.

## Cautions:
- Please avoid using too many TeXViews in a single page, because this is based on [webview_flutter](https://pub.dartlang.org/packages/webview_flutter) a complete web browser. Which may cause to slow down your app.


# Screenshots

Screenshot# 01             |  Screenshot# 02
:-------------------------:|:-------------------------:
<img src="https://raw.githubusercontent.com/shah-xad/flutter_tex/master/screenshots/Screenshot_1.png"/> | <img src="https://raw.githubusercontent.com/shah-xad/flutter_tex/master/screenshots/Screenshot_2.png"/> 

[![Tweet Flutter_TeX](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=A%20Flutter%20Package%20to%20render%20Mathematics%2C%20Physics%20and%20Chemistry%20Equations%20based%20on%20LaTeX%20with%20full%20HTML%20support.&url=https://github.com/shahzadakram67/flutter_tex&via=shahzadakram67&hashtags=flutter,flutter_tex,latex,equations)
