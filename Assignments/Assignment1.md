# Assignment1 - Hello World

## In this assignment you will:

* [Get Your Flutter Build Environment Setup](#get-your-flutter-build-environment-setup)
* [Create your first app](#create-your-first-app)
* [Create your first APK (Android Install Package)](#getting-graded)

> Note: I will only be requiring Android and web results in this class. Flutter supports development for Android, iOS, Linux, macOS, Windows, Google Fuchsia, and the web, so while we will not focus on developing iPhone apps in this class (since iOS development requires macOS), it should be relatively simple to create an iOS app from your existing Flutter app if you choose to do so in the future.


For this first assignment you are getting grade on if you succeed in turning in an Android APK that launches and successfully displays "CINS467 Hello World". This assignment is mostly to make sure you have the build environment setup and can successfully create and export an Android App for grading/install onto phones/devices.

## Get Your Flutter Build Environment Setup

To get the build environment on your computer you should go to the [Flutter Install](https://flutter.io/docs/get-started/install) page and follow the directions there for your operating system.

Make sure you:
* Choose Mobile (Windows) or Android (Mac) for your first type of app
* Confirm your system requirements meet the minimum requirements
* Configure a text editor (the Flutter team recommends using Visual Studio Code and the Flutter extension for VS Code)
* Install the Flutter SDK
  * Windows users: Make sure you do NOT install Flutter to a directory or path that contains special characters or spaces, or that requires elevated privileges
* Make sure the SDK has been added to PATH
* Run `flutter doctor` to check your environment and display a report
  * I recommend running this command with the -v tag for verbose output

After you run `flutter doctor -v`, you should see a report displayed to the terminal. Check the output carefully to determine if there is any additional software you need to install or tasks you need to perform. The instructions provided in this report should address your unique environment and the specific tasks that you need to complete; alternatively, you can go back to the installation instructions in the documentation and complete the following.

Make sure you:
* Can develop for Android
  * You may use your own Android device or the Android emulator (or both)
  * If you want to use the Android emulator: Download and install Android Studio (this is the easiest way I know of to work with the Android Virtual Device (AVD) Manager)
* Can develop for web (this should be setup by default)

Ideally, you will be able to run `flutter doctor -v` and have the report say, "No issues found!" However, there are some cases where having unresolved issues is fine for this class -- remember that XCode (iOS and macOS) is NOT required in CINS 467.

### Code Editing

I recommend you develop using the [VS Code](https://docs.flutter.dev/get-started/editor?tab=vscode) editor with Flutter and Dart plugins, as this is how I'll be developing during class. [Android Studio](https://docs.flutter.dev/get-started/editor?tab=androidstudio), which includes the IntelliJ IDE, Android SDK Tools, and Android Emulator all together, is also a good option for development. For Android Studio, you'll also need to add the plugins for Flutter/Dart as directed in that getting started with Android Studio for Flutter link. It is easier for me to demo the code on the projector with VS Code, but both are equally good.

I do recommend relying on the Flutter command line directly for building your flutter exports, as it is more consistent than the built-in plugins for generating your submissions.

### flutter doctor

Remember to use `flutter doctor -v` to make sure your setup is configured correctly. An example of flutter doctor running successfully on my computer is as follows:

```bash
~/$ flutter doctor -v
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

## Create Your First App

**Disclaimer:** *You should go through the steps yourself to create the Hello World app and not just import an existing Hello World app as you'll miss out on going through the steps of creating a new app.*

Remember, the final submission for Assignment 1 may seem simple, but before you can complete the assignment, you will need to do a lot of setup for Flutter and Android. Give yourself time to get everything set up!

### Requirements:

* Create an app that displays "CINS467 Hello World" in a Text widget
* Create an APK for your app
* Submit the assignment correctly
  * Use a branch called `assignment1`
  * Submit to your CINS467 GitLab repo

### Walk-through

Start by creating a "New Flutter Project". You can do this via the VScode or Android studio plugins; however, I would do it through the command line, in the file location where you want to host your project code (i.e. I would run this command in the folder where the repo to which you will be submitting is cloned).

```bash
~/repos/CINS467-repo/$ flutter create AssignmentProject
```

You can name your project whatever you wish, and you can use the same project for all of the assignment submissions. I opted to name it *AssignmentProject* for my example.

From here edit your main.dart to have a Text widget that says "CINS467 Hello World". The following works if you update the Text widget; however, for the *home* component of *MaterialApp* I would **highly recommend** you wrap the Text widget in a *Scaffold/Column* so that the Text widget is centered and easier to see with your required text.

```Dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        useMaterial3: true,
      ),
      home: const Text('Hello World'),
    );
  }
}

```
## Getting Graded

> APK stands for Android Package Kit - it is the file format that Android uses to distribute and install apps.

You will need to run the `flutter build apk` command to create a new APK. The command should overwrite any files that are currently in the `build/` directory; however, if you want to be sure you are creating a fresh APK, you can remove the build folder using either `flutter clean` or `rm` (you should not need to run both commands):

```bash
~/repos/CINS467-repo/AssignmentProject$ flutter clean
~/repos/CINS467-repo/AssignmentProject$ rm -rf build
```

Then explicitly build a new APK:

```bash
~/repos/CINS467-repo/AssignmentProject$ flutter build apk
```

Look for the `app-release.apk` file - it should be located in the build folder path here: `build/app/outputs/apk/release/`. Once you find this .apk file, copy or move it to the root directory of your GIT repo that you created to turn in assignments for this class.

If you don't have a CINS467 GitLab repo, go to Canvas to see the instructions for generating a Git Repo for this class.

You will submit all the assignments for this class to separate branches on your CINS467 repo. You can keep building on the same app for the future submissions as well, just adding the required new features to it, or you can build separate apps in the same directory.

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

```bash
git checkout -b assignment1 #create branch and switch to it
git add -A #add all
git commit -m "Assignment 1 Submission" #Commit changes to branch
git push origin assignment1 #Push code up to assignment1 branch on remote
```

Make sure your branch is exactly named `assignment1` matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.

If you plan on making multiple updates to the code on this branch, you can include the `--set-upstream` option when you push the code (i.e. `git push --set-upstream origin assignment1`) -- this adds an upstream (tracking) reference so that, any time you push or pull from this branch in the future, you can simply use `git push` or `git pull`, without specifying the remote and branch.

If you would like to merge your `assignment1` branch with your `main` branch, you can run the following commands:
```bash
git checkout main  #switch to the main branch
git merge assignment1  #join the development history from the assignment1 branch with the current (main) branch
git push origin main  #push the assignment1 history up to the main branch on the remote
```
