# Assignment 3 - Simple UI

## In this assignment your app needs to do the following:

* **Have Three Buttons**
  * The buttons must not all look the same - try using different types of buttons and updating the style (color, font, size, etc). By default, Flutter adds some style to the buttons, but you must specify at least three button properties in each of your buttons.
  * Each button should also have a handler (e.g. onPressed), so that when you click the button, it changes what you see in your app.
* **Have Two Text Widgets**
  * Each Text widget must contain data (the text to display) and use at least two additional properties to style the text (something other than the default).
* **Make Updates When Each Button Is Pressed**
  * In at least one case, the contents of a Text widget must update when a button is pressed. The other buttons may update a Text widget or another aspect of your web app.
  * The buttons should give some indication of what they do when pressed (i.e. through text and/or icons)

As long as your app does those tasks you will get credit for this assignment.

The goal of Assignment 3 is to give you experience creating a simple UI (user interface) with Flutter. Have fun! This is a great time to start thinking about how you want your final project to look, or just play around and learn what different Flutter features can do.

## Getting Graded

### Option 1 - Android APK

Create a new APK for this assignment. If you do not remember how to create an APK, refer back to the instructions in [Assignment 1](https://github.com/shelleywong/CINS467-Course-Materials/blob/main/Assignments/Assignment1.md#getting-graded).

When you have your APK move it to the root directory of your GIT repo that you were given to turn in assignments for this class. You must only have **one** APK in your root directory (remember, each assignment should be submitted to a unique branch, so you can overwrite any previous APKs). Do not use Android Studio or VSCode to manage your VCS/Repo as it may screw up the repo. So for this assignment you should have a directory that looks like the following:

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

### (Alternatively) Option 2 - Web URL

```
    /
    ...web.md
    ...AssignmentProject/
    ......android/
    ......ios/
    ......lib/
    ......web/
    ......pubspec.yaml
    ......(Rest of firebase App Files)
```
In your web.md file you should have a web URL for your assignment hosted online.

### Now submit your code to the **assignment3** branch:

```
git checkout -b assignment3 #create branch and switch to it
git add -A #add all
git commit -m "Assignment 3 Submission" #Commit changes to branch
git push --set-upstream origin assignment3 #Push code up to assignment2 branch on remote
```

Make sure your branch is exactly named `assignment3` matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.
