# Assignment1 - Hello World

## In this assignment you will:

* [Get Your Flutter Build Environment Setup](#get-your-flutter-build-environment-setup)
  * [Code Editing](#code-editing)
  * [flutter doctor](#flutter-doctor)
* [Create your first app](#create-your-first-app)
  * [Requirements](#requirements)
  * [Steps](#steps)
* [Create your first APK](#create-your-first-apk)
  * [Submitting your code](#submitting-your-code)
  * [Commit your code to the assignment1 branch](#commit-your-code-to-the-assignment1-branch)

> Note: I will only be requiring Android and web results in this class. Flutter supports development for Android, iOS, Linux, macOS, Windows, Google Fuchsia, and the web, so while we will not focus on developing iPhone apps in this class (since iOS development requires macOS), it should be relatively simple to create an iOS app from your existing Flutter app if you choose to do so in the future.


For this first assignment you are getting grade on if you succeed in turning in an Android APK that launches and successfully displays "CSCI567 Hello World". This assignment is mostly to make sure you have the build environment setup and can successfully create and export an Android App for grading/install onto phones/devices.

## Get Your Flutter Build Environment Setup

To get the build environment on your computer you should go to the [Flutter Install](https://flutter.io/docs/get-started/install) page and follow the directions there for your operating system. For more detailed instructions and installation hints, look for the lecture materials that introduce Flutter and go over Flutter setup (provided through Canvas).

Make sure you:
* Choose **Android** (Windows, Mac, or Linux) for your first type of app
* Confirm your system requirements meet the minimum requirements for hardware and software
* Configure a text editor (I will use Visual Studio Code and the Flutter extension for VS Code during class)
* Install the Flutter SDK
  * Flutter now provides instructions to use VS Code to install OR to download a provided installation bundle to get the latest stable release of the Flutter SDK -- I recommend downloading and installing yourself, without VS Code
  * Windows users:
    * Make sure you do NOT install Flutter to a directory or path that contains special characters or spaces, or that requires elevated privileges
  * All users:
    * Make sure the SDK has been added to the PATH environment variable
  * To enable these changes, make sure you close and reopen or restart any existing command prompts, terminal shells, or PowerShell instances.
* Run `flutter doctor` to check your environment and display a report
  * I recommend running this command with the -v tag for verbose output

After you run `flutter doctor -v`, you should see a report displayed to the terminal. Check the output carefully to determine if there is any additional software you need to install or tasks you need to perform. The instructions provided in this report should address your unique environment and the specific tasks that you need to complete; alternatively, you can go back to the installation instructions in the documentation and complete the following.

Make sure you:
* Can develop for Android
  * You may use your own Android device or the Android emulator (or both)
  * If you want to use the Android emulator: Download and install Android Studio (this is the easiest way I know of to work with the Android Virtual Device (AVD) Manager)
* Can develop for web (this should be setup by default)

You should be able to run `flutter doctor -v` and see a checkmark next to most categories (Flutter, Android Toolchain, Chrome, etc). If the report says, "No issues found!", then you are definitely good. You are also good if you have unresolved issues specifically related to developing desktop apps (Windows, macOS, or Linux) or iOS apps -- you do not need XCode (for iOS and macOS apps), Visual Studio (for Windows apps), or the Linux toolchain (for Linux apps) in CSCI 567, so if you see issues in these categories, do not worry about it -- continue with the next steps.

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

### Requirements

* Create an app that displays "CSCI567 Hello World" in a Text widget
* Create an APK for your app
* Submit the assignment correctly
  * Use a branch called `assignment1`
  * Submit to your CSCI567 GitLab repo
    * Your CSCI567 GitLab repo on the `assignment1` branch should contain (at minimum) the code for your app (the project directory) and the APK file that you created for your app

### Steps

Start by creating a New Flutter Project. You can do this via the VSCode or Android Studio plugins; however, I recommend doing this through the command line, in the file location where you want to host your project code (i.e. I would run this command in the folder where the repo to which you will be submitting is cloned). Use the `flutter create <DIRECTORY>` command:

```bash
~/repos/CSCI567-repo/$ flutter create my_assignment
```

In the example above, the project is named *my_assignment*, but you can name your project whatever you wish, as long as it meets the naming requirements (the name should consist of lowercase words separated by underscores, "like_this". Use only basic Latin letters and Arabic digits: [a-z0-9_], and ensure the name is a valid Dart identifier, i.e. it does not start with a digit and is not a reserved word). You can use the same project for all of the assignment submissions, or create new projects for each assignment.

From here, edit your main.dart to have a Text widget that says "CSCI567 Hello World". You can begin with the starter code (created by default when you use the `flutter create` command), or use something similar to the following (as long as you update the Text widget). If you start with the code below, I would **highly recommend** you update the *home* component of *MaterialApp* by using some [basic layout widgets](https://docs.flutter.dev/ui/widgets/basics) (such as Scaffold and Column) to wrap the Text widget. Layout widgets allow you to align/center the Text widget so it is easier to read and looks nicer.

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

For Assignment 1, you will need to submit an APK. Look for the lecture materials covering how to build an APK, or reference the instructions below.

## Create your first APK

For Assignment 1 grading, you must submit an Android APK (the Android install package), in addition to the files needed for your app to run.

> APK stands for Android Package Kit - it is the file format that Android uses to distribute and install apps.

You will need to run the `flutter build apk` command to create a new APK. The command should overwrite any files that are currently in the `build/` directory; however, if you want to be sure you are creating a fresh APK, you should first remove the build folder using either `flutter clean` or `rm` (you should not need to run both commands):

```bash
~/repos/CSCI567-repo/AssignmentProject$ flutter clean
~/repos/CSCI567-repo/AssignmentProject$ rm -rf build
```

Then explicitly build a new APK:

```bash
~/repos/CSCI567-repo/AssignmentProject$ flutter build apk
```

Look for the `app-release.apk` file - it should be located in the build folder path here: `build/app/outputs/apk/release/` (you can also use the `app-release.apk` file located here: `build/app/outputs/flutter-apk/`). Once you confirm that this .apk file has been created, copy or move it to the root directory of your GIT repo that you created to turn in assignments for this class. If you are in the root of your project (the same directory that contains the `pubspec.yaml` file), you can copy the `app-release.apk` file to the root of your GIT repo with the following command (if the parent directory of your project is the root of your GIT repo):

```bash
~/repos/CSCI567-repo/AssignmentProject$ cp build/app/outputs/apk/release/app-release.apk ..
```

Then move to the root of your GIT repo and confirm that your repo contains the apk file (it should also contain the README.md file and the project directory for your app):

```bash
~/repos/CSCI567-repo/AssignmentProject$ cd ..
~/repos/CSCI567-repo$ ls
README.md app-release.apk AssignmentProject
```

If you don't have a CSCI567 GitLab repo, go to Canvas to see the instructions for generating a Git Repo for this class.

You will submit all the assignments for this class to separate branches on your CSCI567 repo. You can keep building on the same app for the future submissions as well, just adding the required new features to it, or you can build separate apps in the same directory.

```
    /
    ....README.md
    ....app-release.apk
    ....AssignmentProject/
    ........android/
    ........lib/
    ........web/
    ........pubspec.yaml
    ........(Rest of the AssignmentProject app/project files and folders)
```

### Submitting your code

Your code should be submitted to your CSCI567 repo (in the CSUC-CSCI567 GitLab group). You should use git commands in a command line terminal to record changes to your project and push your updates to a remote repo.

> Note: I recommend **not** using VSCode, GitHub Desktop, or Android Studio to manage your version control -- several students who have tried using these in the past have ended up screwing up their repos. Any issues you run into will be much easier to fix if you consistently use git commands in a terminal.

### Commit your code to the assignment1 branch

It is important to ensure that your GitLab repository includes all the necessary files for your app to run, even if some of these files were generated automatically or were not directly edited by you. This includes configuration files, dependency files (like pubspec.yaml), and other project files required for your app to build and run on another machine. The following instructions use `git add -A` to make sure all changes in your working directory are staged for commit.<br>

There are some files and folders (like temporary build files, logs, or system-specific files) that you should **not** commit to your Git repository, and this is where the the `.gitignore` file (that was generated when you created a new Flutter project with `flutter create`) comes in. The provided `.gitignore` ignores all directories and files that we intentionally do not want to track for our Flutter project. When you use the `git add -A` command, it will stage all changes to tracked and untracked files and directories, **except** for those that are specified in the `.gitignore` file. (This is what we want -- any files or directories listed in `.gitignore` will not be added to the staging area or committed to the repository, but all others will be).<br>

Create a new branch and switch to it (this can be completed before you begin writing and updating the code):

```bash
git checkout -b assignment1  #create branch and switch to it
```

If you are unsure about what files are being ignored and included, you can check the status of your files with `git status` (note that patterns in the `.gitignore` file should be excluded):

```bash
git status #show the working tree status to confirm what changes have been made
```

Stage the changes in your working directory for the next commit, save your changes to your local repository (create a snapshot and add a message describing what you've done), and upload your local changes to your remote repository on GitLab:

```bash
git add -A  #add all (if you want to add all changes listed when you run 'git status')
git commit -m "Assignment 1 Submission"  #Commit changes to branch
git push origin assignment1  #Push code up to assignment1 branch on remote
```

Make sure your branch is exactly named `assignment1` matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.

If you plan on making multiple updates to the code on this branch, you can include the `--set-upstream` option when you push the code (i.e. `git push --set-upstream origin assignment1`) -- this adds an upstream (tracking) reference so that, any time you push or pull from this branch in the future, you can simply use `git push` or `git pull`, without specifying the remote and branch.

If you would like to merge your `assignment1` branch with your `main` branch, you can run the following commands:
```bash
git checkout main  #switch to the main branch
git merge assignment1  #join the development history from the assignment1 branch with the current (main) branch
git push origin main  #push the assignment1 history up to the main branch on the remote
```
