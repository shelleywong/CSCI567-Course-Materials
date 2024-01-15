# Assignment 7 - Camera or Location

## In this assignment your app needs to do the following:

* **Have a simple UI**
  * Your UI should be user-friendly. Every feature should have a purpose, and it should be clear to users how they can interact with each feature.
* **Do one of the following:**
  * Launch the **camera** to get a photo
    * Photo should then be added to the simple UI (note that the photo needs to be rendered in the view, so it is visible in the app after users take the photo, click the checkmark, and close the camera).
    * Make sure you are launching the camera -- if you are only allowing users to pick a photo from the gallery, you will not be meeting the requirements for this project.
    * There is no need to store more than one instance of an image, but it is recommended that you render a list of all the images taken in your UI.
    * If you choose this option, I recommend using either the [image_picker](https://pub.dev/packages/image_picker) plugin (for Android apps) or the [camera](https://pub.dev/packages/camera) plugin (for Web and Android).
  * Use **location services** on the device
    * Current location should be updated and displayed in the simple UI as it changes. This can be kept as a string representation of the location.
    * It isn't required to put the location on a map, but if you plan to use location in your project, this would be a good stretch goal to attempt here.
    * If you choose this option, I recommend using the [geolocator](https://pub.dev/packages/geolocator) plugin.

Also make sure that you:
  * Submit the assignment correctly
    * Use a branch called `assignment7`
    * Submit to your CINS467 GitLab repo

As long as your app does the tasks described above and is submitted correctly, you will get credit for this assignment.

The goal of Assignment 7 is to give you experience working with the camera or location services on a device. There are special installation and usage instructions for working with these features on a device (such as adding permissions). Your Final Project needs to leverage the fact it is on a device with access to internet, camera, or location services, so this assignment will help you prepare for the Final Project.

## Getting Graded

> After completing Option 1 or Option 2, remember to submit your code to the `assignment7` branch!

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

### Now submit your code to the **assignment7** branch:

```bash
git checkout -b assignment7  #create branch and switch to it
git add -A  #add all
git commit -m "Assignment 7 Submission"  #Commit changes to branch
git push origin assignment7  #Push code up to assignment7 branch on remote
```

Make sure your branch is exactly named `assignment7` matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.

If you plan on making multiple updates to the code on this branch, you can include the `--set-upstream` option when you push the code (i.e. `git push --set-upstream origin assignment7`) -- this adds an upstream (tracking) reference so that, any time you push or pull from this branch in the future, you can simply use `git push` or `git pull`, without specifying the remote and branch.

If you would like to merge your `assignment7` branch with your `main` branch, you can run the following commands:
```bash
git checkout main  #switch to the main branch
git merge assignment7  #join the development history from the assignment7 branch with the current (main) branch
git push origin main  #push the assignment7 history up to the main branch on the remote
```
