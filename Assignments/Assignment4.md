# Assignment 4 - Persistent Data on Client

## In this assignment your app needs to:

* **Use a Form**
  * Needs to be some way for the user to provide text input and submit their input.
  * Must include at least two separate input fields for users. Make sure that each input field is clearly labeled and configured to indicate the required type of input. Your form should be able to handle at least two different data types (such as String, int, bool, double).
  * Implement at least one input field with either an [EditableText](https://api.flutter.dev/flutter/widgets/EditableText-class.html) field (such as [TextField](https://api.flutter.dev/flutter/material/TextField-class.html)) or an actual [Flutter Form](https://api.flutter.dev/flutter/widgets/Form-class.html) using the [TextFormField](https://api.flutter.dev/flutter/material/TextFormField-class.html), which wraps TextField in a FormField.
  * For additional input fields, you may use another TextField or a different type of form input field, such as a [DropdownButtonFormField](https://api.flutter.dev/flutter/material/DropdownButtonFormField-class.html) or a [RadioListTile](https://api.flutter.dev/flutter/material/RadioListTile-class.html). If you are interested in using a type of input field not mentioned here, first check with the instructor to confirm -- for this assignment, you must use at least two input fields that are **not** standard buttons (like ElevatedButton, TextButton, OutlineButton, IconButton, or FloatingActionButton).
* **Store a Persistent State in the SQLite DB, local filesystem, or platform-specific persistent storage on the phone or web**
  * You must store at least two different data types (e.g. String, int, bool, double)
  * You must successfully use one of the following plugins:
    * [shared_preferences](https://pub.dev/packages/shared_preferences)
    * [path_provider](https://pub.dev/packages/path_provider)
    * [sqflite](https://pub.dev/packages/sqflite)
* **Have the Form update the state**
  * When the form receives user input, it must update data that is stored in a persistent state.
* **Have the View update based on the changed state**
  * When the data in storage changes, the corresponding user interface (view that the user sees) must also update to reflect that change. For example, you could update the view by clearing the form and displaying the stored data elsewhere on the page, or by redirecting the user to a different page where the data is displayed.
  * The updates to the state and view should be tested with at least two different types of inputs (you will likely need to use operations to convert the data, e.g. from the form to storage, and/or from storage to what is displayed to the user).


Also make sure that you:
  * Submit the assignment correctly
    * Use a branch called `assignment4`
    * Submit to your CINS467 GitLab repo
      * You may submit your app as either an Android app or a web app. Your CINS467 GitLab repo on the `assignment4` branch should contain (at minimum):
        * Android submission: the code for your app (the project directory) and the APK file that you created for your app
        * Web submission: the code for your app (the project directory), the `.gitlab-ci.yml` file that defines the CI/CD pipeline for your GitLab repo, and a file called `web.md` that contains the URL to your project hosted online through GitLab Pages

As long as your app does the tasks described above and is submitted correctly, you will get credit for this assignment.

The goal of Assignment 4 is to give you experience working with user input, dealing with persistent storage, and handling interactions with the data so that any changes in storage are also reflected in the view that the user sees. Understanding how these components interact is important any time you are developing a responsive and dynamic web or mobile application. Regardless of the framework, it is important to be able to display information that aligns with the current state of the application's data.

## Getting Graded

> After completing Option 1 or Option 2, remember to submit your code to the `assignment4` branch!

### Option 1 - Android APK

Create a new APK for this assignment by running the `flutter clean` command, and then running the `flutter build apk` command. For more detailed instructions on creating and locating an APK, refer back to the instructions in [Assignment 1](https://github.com/shelleywong/CINS467-Course-Materials/blob/main/Assignments/Assignment1.md#getting-graded).

When you have your APK, move it to the root directory of your GIT repo that you were given to turn in assignments for this class. You must only have **one** APK in your root directory (remember, each assignment should be submitted to a unique branch, so you can overwrite any previous APKs).

For this assignment you should have a directory that looks like the following:

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

### (Alternatively) Option 2 - Web URL

```
    /
    ....README.md
    ....web.md
    ....AssignmentProject/
    ........android/
    ........lib/
    ........web/
    ........pubspec.yaml
    ........(Rest of the AssignmentProject app/project files and folders)
```

> Note: the `.gitlab-ci.yml` file is a hidden file, so you will not see it if you run the `ls` command without any options. You can see the .gitlab-ci.yml file if you list hidden files in long format using `ls -al`

In your web.md file, you should have a web URL for your assignment hosted online. This will be the same web URL as any previous GitLab Pages submissions. Remember, if you are doing web submissions for Assignments 3-7, you must make sure that each assignment still meets the requirements of the previous assignments. You will always only have one GitLab Pages website, so doing this ensures that your deployment will meet the requirements of each assignment (regardless of when the assignment actually gets graded).

### Submitting to your remote CINS467 git repo

I recommend that you use git commands in a command line terminal to record changes to your project and push your updates to a remote repo. I recommend **not** using VSCode, GitHub Desktop, or Android Studio to manage your version control -- several students who have tried using these in the past have ended up screwing up their repos. Any issues you run into will be much easier to fix if you use git commands in a terminal.

### Now submit your code to the **assignment4** branch:

```bash
git checkout -b assignment4  #create branch and switch to it
git status #show the working tree status to confirm what changes have been made
git add -A  #add all (if you want to add all changes listed when you run 'git status')
git commit -m "Assignment 4 Submission"  #Commit changes to branch
git push origin assignment4  #Push code up to assignment4 branch on remote
```

Make sure your branch is exactly named `assignment4` matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.

If you plan on making multiple updates to the code on this branch, you can include the `--set-upstream` option when you push the code (i.e. `git push --set-upstream origin assignment4`) -- this adds an upstream (tracking) reference so that, any time you push or pull from this branch in the future, you can simply use `git push` or `git pull`, without specifying the remote and branch.

If you would like to merge your `assignment4` branch with your `main` branch, you can run the following commands:
```bash
git checkout main  #switch to the main branch
git merge assignment4  #join the development history from the assignment4 branch with the current (main) branch
git push origin main  #push the assignment4 history up to the main branch on the remote
```
