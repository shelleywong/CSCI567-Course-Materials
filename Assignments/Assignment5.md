# Assignment 5 - REST API

## In this assignment your app needs to:

* **Have a simple UI**
  * Your UI should be user-friendly. Every feature should have a purpose, and it should be clear to users how they can interact with each feature.
* **Retrieve data from a REST API**
  * You must successfully make at least one HTTP GET request using the [Dart http package](https://pub.dev/packages/http) to fetch data.
    * The data returned by your chosen REST API should contain at least one object that is composed of at least three fields that can be effectively displayed or used.
  * To receive full credit for this assignment, use a different REST API from the one demonstrated in class.
    * Feel free to use a free and public API (you do not need to use an API Key for this assignment).
* **Display data received from a REST API in the View**
  * Present the data received from the REST API in a clear and user-friendly manner within the view (so that users can see a representation of the state of the resource in the user interface).
    * You are not required to display the entire response, but you must showcase at least one object and at least three different fields from the object, utilizing widgets to effectively display the values (e.g. using Text, ListTile, or Card) or using the values in a meaningful way (e.g. launching a URL with a GestureDetector or button)
    * The data should not be presented in its raw transferred state (e.g. if you receive JSON data, the data should not be displayed in JSON format). Instead, use appropriate widgets to provide a clear and visually appealing representation.

Also make sure that you:
  * Submit the assignment correctly
    * Use a branch called `assignment5`
    * Submit to your CINS467 GitLab repo

As long as your app does the tasks described above and is submitted correctly, you will get credit for this assignment.

The goal of Assignment 5 is to give you experience working with a [REST API](https://www.redhat.com/en/topics/api/what-is-a-rest-api). REST is one of the most widely used approaches for building web-based APIs, and it is useful for you to be familiar with how to interact with a REST API from the client side. Sending and/or receiving data from an internet-baseds source (such as a REST API) is one option for meeting the Final Project requirement that your project needs to leverage the fact it is on a device with internet connectivity.

> Note: Some APIs will not work on web by default (they require CORS support to be enabled). For this assignment, you may want to submit with an Android APK (which does not run into the CORS support issue) or find an API that works on web without additional configurations necessary.

## Getting Graded

> After completing Option 1 or Option 2, remember to submit your code to the `assignment5` branch!

### Option 1 - Android APK

Create a new APK for this assignment by running the `flutter clean` command, and then running the `flutter build apk` command. For more detailed instructions on creating and locating an APK, refer back to the instructions in [Assignment 1](https://github.com/shelleywong/CINS467-Course-Materials/blob/main/Assignments/Assignment1.md#getting-graded).

When you have your APK, move it to the root directory of your GIT repo that you were given to turn in assignments for this class. You must only have **one** APK in your root directory (remember, each assignment should be submitted to a unique branch, so you can overwrite any previous APKs). Do not use Android Studio or VSCode to manage your VCS/Repo as it may screw up the repo. So for this assignment you should have a directory that looks like the following:

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

### Now submit your code to the **assignment5** branch:

```bash
git checkout -b assignment5  #create branch and switch to it
git add -A  #add all
git commit -m "Assignment 5 Submission"  #Commit changes to branch
git push origin assignment5  #Push code up to assignment5 branch on remote
```

Make sure your branch is exactly named `assignment5` matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.

If you plan on making multiple updates to the code on this branch, you can include the `--set-upstream` option when you push the code (i.e. `git push --set-upstream origin assignment5`) -- this adds an upstream (tracking) reference so that, any time you push or pull from this branch in the future, you can simply use `git push` or `git pull`, without specifying the remote and branch.

If you would like to merge your `assignment5` branch with your `main` branch, you can run the following commands:
```bash
git checkout main  #switch to the main branch
git merge assignment5  #join the development history from the assignment5 branch with the current (main) branch
git push origin main  #push the assignment5 history up to the main branch on the remote
```
