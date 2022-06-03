# Assignment 6 - Camera or Location

## In this assignment your app needs to do the following:

* Have a simple UI
* Do one of the following:
  * Launch the camera to get a photo
    * Photo should then be added to the simple UI
    * There is no need to store more than one instance of an image, but it would be recommended that you render a list of all the images taken in your UI.
  * Use location services on the device
    * Current location should be updated in the simple UI as it changes. Can be kept as a string representation of the location.
    * It isn't required to put the location on a map, but if you plan to use location in your project this would be a good stretch goal to attempt here.

As long as your app does those tasks you will get credit for this assignment.

## Getting Graded

When you have your APK move it to the root directory of your GIT repo that you were given to turn in assignments for this class. Do not use Android Studio to manage your VCS/Repo as it may screw up the repo. So for this assignment you should have a directory that looks like the following:

```
    /
    ...features_<your_name>.apk
    ...Assignment6/
    ......android/
    ......ios/
    ......lib/
    ......pubspec.yaml
    ......(Rest of features App Files)
```

You should also name all your submissions as shown, replacing \<your name\> with your actual name.

Now submit your code to the **assignment6** branch:

```
git checkout -b assignment6 #create branch and switch to it
git add -A #add all
git commit -m "Assignment 6 Submission" #Commit changes to branch
git push --set-upstream origin assignment6 #Push code up to assignment5 branch on remote
```

Make sure your branch is exactly named **assignment6** matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.
