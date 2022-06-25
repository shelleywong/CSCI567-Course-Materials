# Assignment1 - Hello World

## In this assignment you will:

* Get your Flutter build environment setup
* Create your first app
* Create your first APK (Android Install Package)
  * Flutter supports iOS development but I'll only be requiring Android results in the class, since iOS development requires having an Apple computer still.


For this first assignment you are getting grade on if you succeed in turning in an Android APK that launches and successfully displays "CINS467 Hello World". This assignment is mostly to make sure you have the build environment setup and can successfully create and export an Android App for grading/install onto phones/devices.

## Getting Build Environment Setup

To get the build environment on your computer you should go to the [Flutter](https://flutter.io/docs/get-started/install) Download page and follow the directions there.

I highly recommend you develop using the [Android Studio](https://flutter.io/docs/get-started/editor) as well, which includes the IntelliJ IDE, Android SDK Tools, and Android Emulator all together. This will make everything easier and how I will be demoing development in Flutter in class. You'll also need to add the plugins for Flutter/Dart to Android Studio as directed in that getting started with Android Studio for Flutter link.

Use *flutter doctor -v* to make sure your setup is configured correctly.

## Creating Your First App

**Disclaimer:** *You should go through the steps yourself to create the Hello World app and not just import an existing Hello World app as you'll miss out on going through the steps of creating a new app.*

### Requirements:

* Your app should display "CINS467 Hello World"

### Walk-through

So to start create a "New Flutter Project", which should launch a dialog that looks like the following:

![flutter project app](https://github.com/CSUChico-CSCI567/CSCI567-Course-Materials/raw/master/Assignments/Images/new_flutter_project.png)

Select that you want to create a Flutter Application, and then fill in the configuration form that looks like the following with the details in the following screenshot but with your name and correct paths.

![flutter config](https://github.com/CSUChico-CSCI567/CSCI567-Course-Materials/raw/master/Assignments/Images/new_flutter_config.png)

From here edit your main.dart to have a Text widget that says "CSCI567 Hello World". The following would work; however, for the *home* component of *MaterialApp* I would **highly recommend** you wrap the Text widget in a *Scaffold/Column* so that the Text widget is centered and easier to see with your required text.

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

Flutter automatically creates an APK as you can see in the screenshot below:

![apk location](https://github.com/CSUChico-CSCI567/CSCI567-Course-Materials/raw/master/Assignments/Images/apk_flutter_location.png "APK location in Flutter")

Once you find it move it to the root directory of your GIT repo that you created to turn in assignments for this class. If you don't have one go use the form on my website to request one. As we'll submit all the assignments for this class to separate branches.

```
    /
    ...helloworld_<your_name>.apk
    ...Assignment1/
    ......android/
    ......ios/
    ......lib/
    ......pubspec.yaml
    ......(Rest of Hello World App Files)
```

You should also name all your submissions as shown, replacing \<your name\> with your actual name.

Now submit your code to the **assignment1** branch:

```
git checkout -b assignment1 #create branch and switch to it
git add -A #add all
git commit -m "Assignment 1 Submission" #Commit changes to branch
git push --set-upstream origin assignment1 #Push code up to assignment1 branch on remote
```

Make sure your branch is exactly named assignment1 matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.
