# Assignment 6 - Firebase

The goal of Assignment 6 is similar to the goal of Assignment 4, but this assignment is specifically aimed at giving you experience working with Cloud Firestore (Firebase database) and internet-based persistent storage, which allows data to be persistent across devices. Databases and storage on the cloud are more reliable and more scalable than other persistent storage options, and it expands the capabilities of your app, allowing for features like in-app collaboration, sharing with other users, and syncing across multiple devices.

* [Requirements](#requirements)
* [Getting Graded](#getting-graded)
  * [Android APK](#android-apk)
  * [GitLab Pages Website](#gitlab-pages-website)
  * [Submitting your code](#submitting-your-code)
  * [Commit your code to the assignment6 branch](#commit-your-code-to-the-assignment6-branch)

## Requirements

In this assignment your app needs to do the following:

* **Use a Form**
  * Must include some way for the user to provide text input and a clear way to submit their input.
  * Must include at least two separate input fields for users.
    * Make sure that each input field is clearly labeled and configured to indicate the required type of input.
    * Your form should be able to handle at least two different data types (such as String, int, bool, double).
    * Implement at least one input field with either an [EditableText](https://api.flutter.dev/flutter/widgets/EditableText-class.html) field (such as [TextField](https://api.flutter.dev/flutter/material/TextField-class.html)) or an actual [Flutter Form](https://api.flutter.dev/flutter/widgets/Form-class.html) using the [TextFormField](https://api.flutter.dev/flutter/material/TextFormField-class.html), which wraps TextField in a FormField.
    * For additional input fields, you may use another TextField or a different type of form input field, such as a [DropdownButtonFormField](https://api.flutter.dev/flutter/material/DropdownButtonFormField-class.html) or a [RadioListTile](https://api.flutter.dev/flutter/material/RadioListTile-class.html).
    * If you are interested in using a type of input field not mentioned here, first check with the instructor to confirm -- for this assignment, you must use at least two input fields that are **not** standard buttons (like ElevatedButton, TextButton, OutlineButton, IconButton, or FloatingActionButton).
* **Store a Persistent state on Firebase**
  * You must store at least two different data types (e.g. string, number, boolean)
  * You must set up a project on [Firebase](https://firebase.google.com/)
  * You will need to use the [cloud_firestore](https://pub.dev/packages/cloud_firestore) and [firebase_core](https://pub.dev/packages/firebase_core) plugins
  * The data must persist across devices, and it must be clear to the user that the data persists. This means that the data needs to be displayed or used in the app in some way after the form is submitted, and when the app is opened on a different device (or in a different browser for web apps), the user interface should still provide clear visual cues that the data was successfully stored in internet-based storage.
* **Have the Form update the state and the View update based on the changed state**
  * After the user submits the form, it should be clear that the form was submitted. There are different ways to achieve this -- some options include but are not limited to displaying a "success" message, clearing the form fields, and navigating the user to a different page.
  * The user input from the form must be used to create or update data that is stored in the Firestore database.
  * When the data in storage changes, the corresponding user interface (view that the user sees) must also update to reflect that change. For example, after the form is submitted, the stored data can be displayed somewhere on the same page (outside of the form) or on a different page. if the stored data is a user preference, instead of displaying text on the page, you might update some other feature (such as a color, theme, language, unit, etc).
  * The updates to the state and view should be tested with at least two different types of inputs (you will likely need to use operations to convert the data, e.g. from the form to storage, and/or from storage to what is displayed to the user).<br>

Also make sure that you:
  * Submit the assignment correctly
    * Use a branch called `assignment6`
    * Submit to your CSCI567 GitLab repo
      * You may submit your app as either an Android app or a web app. Your CSCI567 GitLab repo on the `assignment6` branch should contain (at minimum):
        * Android submission: the code for your app (the project directory) and the APK file that you created for your app
        * Web submission: the code for your app (the project directory), the `.gitlab-ci.yml` file that defines the CI/CD pipeline for your GitLab repo, and a file called `web.md` that contains the URL to your project hosted online through GitLab Pages

As long as your app does the tasks described above and is submitted correctly, you will get credit for this assignment.


## Getting Graded

You may submit Assignment 6 as either an Android APK (Option 1) OR a GitLab Pages Website (Option 2) -- you do not need to submit both. After completing Option 1 or Option 2, remember to add, commit, and push your code to the `assignment6` branch to complete your submission!

### Android APK

Create a new APK for this assignment by running the `flutter clean` command, and then running the `flutter build apk` command. For more detailed instructions on creating and locating an APK, refer back to the instructions in [Assignment 1](https://github.com/shelleywong/CSCI567-Course-Materials/blob/main/Assignments/Assignment1.md#create-your-first-apk).

When you have your APK, move it to the root directory of your GIT repo that you were given to turn in assignments for this class. You must only have **one** APK in your root directory (remember, each assignment should be submitted to a unique branch, so you can overwrite any previous APKs).

For this assignment you should have a directory that looks like the following:

```
/
    README.md
    app-release.apk
    AssignmentProject/
        android/
        lib/
        web/
        pubspec.yaml
        (Rest of the AssignmentProject app/project files and folders)
```

### GitLab Pages Website

To submit via web, make sure you have a `.gitlab-ci.yml` file on the current branch and have updated the pipeline for the current assignment. You should also have a file called `web.md` that contains a web URL for your assignment hosted online. This will be the same web URL as any previous GitLab Pages submissions -- if you are doing web submissions for Assignments 3-7, you must make sure that each assignment still meets the requirements of the previous assignments. You will always only have one GitLab Pages website, so doing this ensures that your deployment will meet the requirements of each assignment (regardless of when the assignment actually gets graded).

```
/
    .gitlab-ci.yml
    README.md
    web.md
    AssignmentProject/
        android/
        lib/
        web/
        pubspec.yaml
        (Rest of the AssignmentProject app/project files and folders)
```

> Note: the `.gitlab-ci.yml` file is a hidden file, so you will not see it if you run the `ls` command without any options. You can see the .gitlab-ci.yml file if you list hidden files in long format using `ls -al`

### Submitting your code

Your code should be submitted to your CSCI567 repo (in the CSUC-CSCI567 GitLab group). You should use git commands in a command line terminal to record changes to your project and push your updates to a remote repo.

> Note: I recommend **not** using VSCode, GitHub Desktop, or Android Studio to manage your version control -- several students who have tried using these in the past have ended up screwing up their repos. Any issues you run into will be much easier to fix if you consistently use git commands in a terminal.

### Commit your code to the assignment6 branch

```bash
git checkout -b assignment6  #create branch and switch to it
git status #show the working tree status to confirm what changes have been made
git add -A  #add all (if you want to add all changes listed when you run 'git status')
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
