# Assignment 6 - Firebase

## In this assignment your app needs to do the following:

* **Use a Form**
  * Needs to be some way for the user to provide text input and submit their input.
  * Must include at least two separate input fields for users. Make sure that each input field is clearly labeled and configured to indicate the required type of input -- note that your app will need to store at least two different data types (e.g., String, int, bool, double, List).
  * This can be implemented with either an [EditableText](https://api.flutter.dev/flutter/widgets/EditableText-class.html) field (such as [TextField](https://api.flutter.dev/flutter/material/TextField-class.html)) or an actual [Flutter Form](https://api.flutter.dev/flutter/widgets/Form-class.html) using the [TextFormField](https://api.flutter.dev/flutter/material/TextFormField-class.html), which wraps TextField in a FormField.
* **Store a Persistent state on Firebase**
  * You must store at least two different data types (e.g. string, number, boolean, map, array)
  * You must set up a project on [Firebase](https://firebase.google.com/)
  * You will need to use the [cloud_firestore](https://pub.dev/packages/cloud_firestore) and [firebase_core](https://pub.dev/packages/firebase_core) plugins
* **Form updates Firebase**
  * When the form receives user input, it must update data that is stored in the Firestore database.
* **View updates based on the changed state**
  * When the data in your Firebase Database changes, the corresponding user interface (view that the user sees) must also update to reflect that change. For example, you could update the view by clearing the form and displaying the stored data elsewhere on the page, or by redirecting the user to a different page where the data is displayed.
  * The updates to the state and view should be tested with at least two different types of inputs (you will likely need to use operations to convert the data, e.g. from the form to storage, and/or from storage to what is displayed to the user).

Also make sure that you:
  * Submit the assignment correctly
    * Use a branch called `assignment6`
    * Submit to your CINS467 GitLab repo

As long as your app does the tasks described above and is submitted correctly, you will get credit for this assignment.

The goal of Assignment 6 is similar to the goal of Assignment 4, but this assignment is specifically aimed at giving you experience working with Firebase Cloud Storage. Cloud Storage is more reliable and more scalable than other persistent storage options, and it expands the capabilities of your app, allowing for features like in-app collaboration and syncing across multiple devices.

## Getting Graded

> After completing Option 1 or Option 2, remember to submit your code to the `assignment6` branch!

### Option 1 - Android APK

Create a new APK for this assignment by running the `flutter clean` command, and then running the `flutter build apk` command. For more detailed instructions on creating and locating an APK, refer back to the instructions in [Assignment 1](https://github.com/shelleywong/CINS467-Course-Materials/blob/main/Assignments/Assignment1.md#getting-graded).

When you have your APK, move it to the root directory of your GIT repo that you were given to turn in assignments for this class. You must only have **one** APK in your root directory (remember, each assignment should be submitted to a unique branch, so you can overwrite any previous APKs).

For this assignment you should have a directory that looks like the following:

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
In your web.md file, you should have a web URL for your assignment hosted online. This will be the same web URL as any previous GitLab Pages submissions. Remember, if you are doing web submissions for Assignments 3-7, you must make sure that each assignment still meets the requirements of the previous assignments. (You will always only have one GitLab Pages website).

### Submitting to your remote CINS467 git repo

I recommend that you use git commands in a command line terminal to record changes to your project and push your updates to a remote repo. I recommend **not** using VSCode, GitHub Desktop, or Android Studio to manage your version control -- several students who have tried using these in the past have ended up screwing up their repos. Any issues you run into will be much easier to fix if you use git commands in a terminal.

### Now submit your code to the **assignment6** branch:

```bash
git checkout -b assignment6  #create branch and switch to it
git add -A  #add all
git commit -m "Assignment 6 Submission"  #Commit changes to branch
git push origin assignment6  #Push code up to assignment6 branch on remote
```

Make sure your branch is exactly named `assignment6` matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.

If you plan on making multiple updates to the code on this branch, you can include the `--set-upstream` option when you push the code (i.e. `git push --set-upstream origin assignment6`) -- this adds an upstream (tracking) reference so that, any time you push or pull from this branch in the future, you can simply use `git push` or `git pull`, without specifying the remote and branch.

If you would like to merge your `assignment6` branch with your `main` branch, you can run the following commands:
```bash
git checkout main  #switch to the main branch
git merge assignment6  #join the development history from the assignment6 branch with the current (main) branch
git push origin main  #push the assignment6 history up to the main branch on the remote
```
