# Assignment1 - Hello World

## In this assignment you will:

* Get your Flutter build environment setup
* Create your first app
* Create your first APK (Android Install Package)
  * Flutter supports iOS development but I'll only be requiring Android results in the class, since iOS development requires having an Apple computer still.


For this first assignment you are getting grade on if you succeed in turning in an Android APK that launches and successfully displays "CINS467 Hello World". This assignment is mostly to make sure you have the build environment setup and can successfully create and export an Android App for grading/install onto phones/devices.

## Getting Build Environment Setup

To get the build environment on your computer you should go to the [Flutter](https://flutter.io/docs/get-started/install) Download page and follow the directions there.

I recommend you develop using the [VScode](https://flutter.io/docs/get-started/editor) with Flutter and Dart plugins, which will be how I'll be developing in class. I still prefer using [Android Studio](https://flutter.io/docs/get-started/editor), which includes the IntelliJ IDE, Android SDK Tools, and Android Emulator all together. You'll also need to add the plugins for Flutter/Dart to Android Studio as directed in that getting started with Android Studio for Flutter link. But easier to demo the code on the projector with VScode, but both are equally good. I do recommend relying on the Flutter commandline directly for building your flutter exports as is more consistent than the built-in plugins for generating your submissions.

Use *flutter doctor -v* to make sure your setup is configured correctly. An example of flutter doctor running successfully on my computer is as follows:

```bash
~/$ flutter doctor -v                                               ✔
[✓] Flutter (Channel stable, 3.3.10, on macOS 11.7 20G817 darwin-x64, locale
    en-US)
    • Flutter version 3.3.10 on channel stable at
      /Users/bryandixon/development/flutter
    • Upstream repository https://github.com/flutter/flutter.git
    • Framework revision 135454af32 (13 days ago), 2022-12-15 07:36:55 -0800
    • Engine revision 3316dd8728
    • Dart version 2.18.6
    • DevTools version 2.15.0

[✓] Android toolchain - develop for Android devices (Android SDK version 33.0.0)
    • Android SDK at /Users/bryandixon/Library/Android/sdk
    • Platform android-33, build-tools 33.0.0
    • Java binary at: /Applications/Android
      Studio.app/Contents/jre/Contents/Home/bin/java
    • Java version OpenJDK Runtime Environment (build
      11.0.12+0-b1504.28-7817840)
    • All Android licenses accepted.

[✓] Xcode - develop for iOS and macOS (Xcode 13.2.1)
    • Xcode at /Applications/Xcode.app/Contents/Developer
    • Build 13C100
    • CocoaPods version 1.11.3

[✓] Chrome - develop for the web
    • Chrome at /Applications/Google Chrome.app/Contents/MacOS/Google Chrome

[✓] Android Studio (version 2021.2)
    • Android Studio at /Applications/Android Studio.app/Contents
    • Flutter plugin can be installed from:
      🔨 https://plugins.jetbrains.com/plugin/9212-flutter
    • Dart plugin can be installed from:
      🔨 https://plugins.jetbrains.com/plugin/6351-dart
    • Java version OpenJDK Runtime Environment (build
      11.0.12+0-b1504.28-7817840)

[✓] VS Code (version 1.74.0-insider)
    • VS Code at /Applications/Visual Studio Code - Insiders.app/Contents
    • Flutter extension version 3.56.0

[✓] Connected device (2 available)
    • macOS (desktop) • macos  • darwin-x64     • macOS 11.7 20G817 darwin-x64
    • Chrome (web)    • chrome • web-javascript • Google Chrome 108.0.5359.124

[✓] HTTP Host Availability
    • All required HTTP hosts are available

• No issues found!
```

## Creating Your First App

**Disclaimer:** *You should go through the steps yourself to create the Hello World app and not just import an existing Hello World app as you'll miss out on going through the steps of creating a new app.*

### Requirements:

* Your app should display "CINS467 Hello World"

### Walk-through

So to start create a "New Flutter Project", which you could do via the VScode or Android studio plugins; however, I would do it in the commandline where you want to host your project code. I would run this in the folder where the repo you'll be submitting to is cloned.

```bash
~/repos/CINS467-repo/$ flutter create AssignmentProject
```

You can name your project whatever you wish, and can use the same project for all of the assignment submissions. I opted to name it *AssignmentProject* for my example.

From here edit your main.dart to have a Text widget that says "CINS467 Hello World". The following would work; however, for the *home* component of *MaterialApp* I would **highly recommend** you wrap the Text widget in a *Scaffold/Column* so that the Text widget is centered and easier to see with your required text.

```Dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Hello World App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Text("Hello World"),
    );
  }
}

```
## Getting Graded

Remove the build folder and then explicitly build a new apk:

```bash
~/repos/CINS467-repo/AssignmentProject$ rm -rf build
~/repos/CINS467-repo/AssignmentProject$ flutter build apk
```

Once you find it move it to the root directory of your GIT repo that you created to turn in assignments for this class. The file should be in the build folder path here: *build/app/outputs/flutter-apk/app-release.apk*

If you don't have one go use the form on my website to request one. As we'll submit all the assignments for this class to separate branches. You can keep building on the same app for the future submissions as well, just adding the required new features to it.

```
    /
    ...app-release.apk
    ...AssignmentProject/
    ......android/
    ......ios/
    ......web/
    ......lib/
    ......pubspec.yaml
    ......(Rest of App Files)
```

Now submit your code to the **assignment1** branch:

```
git checkout -b assignment1 #create branch and switch to it
git add -A #add all
git commit -m "Assignment 1 Submission" #Commit changes to branch
git push --set-upstream origin assignment1 #Push code up to assignment1 branch on remote
```

Make sure your branch is exactly named assignment1 matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.
