# Assignment 3 - Persistent Data on Phone

## In this assignment your app needs to do the following:

* Have a Form
* Store a Persistent state in the SQLite DB on the phone
* Form updates the state
* View updates based on the changed state

As long as your app does those tasks you will get credit for this assignment.

## Getting Graded

When you have your APK move it to the root directory of your GIT repo that you were given to turn in assignments for this class. Do not use Android Studio to manage your VCS/Repo as it may screw up the repo. So for this assignment you should have a directory that looks like the following:

```
    /
    ...persistence_<your_name>.apk
    ...Assignment3/
    ......android/
    ......ios/
    ......lib/
    ......pubspec.yaml
    ......(Rest of persistence App Files)
```

You should also name all your submissions as shown, replacing \<your name\> with your actual name.

Now submit your code to the **assignment3** branch:

```
git checkout -b assignment3 #create branch and switch to it
git add -A #add all
git commit -m "Assignment 3 Submission" #Commit changes to branch
git push --set-upstream origin assignment3 #Push code up to assignment3 branch on remote
```

Make sure your branch is exactly named assignment2 matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.
