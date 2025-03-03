# Assignment 7 - Camera or Location

The goal of Assignment 7 is to give you experience working with the camera or location services on a device. There are special installation and usage instructions for working with these features on a device (such as adding permissions). One requirement of your Final Project is that it needs to utilize the camera or location services on the device, so this assignment will help you prepare for the Final Project and complete the first steps necessary to work with hardware features (you should plan on expanding beyond the requirements of this assignment for the final project).

* [Requirements](#requirements)
* [Getting Graded](#getting-graded)
  * [Android APK](#android-apk)
  * [GitLab Pages Website](#gitlab-pages-website)
  * [Submitting your code](#submitting-your-code)
  * [Commit your code to the assignment7 branch](#commit-your-code-to-the-assignment7-branch)

## Requirements

In this assignment your app needs to do the following:

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
      * You may submit your app as either an Android app or a web app. Your CINS467 GitLab repo on the `assignment7` branch should contain (at minimum):
        * Android submission: the code for your app (the project directory) and the APK file that you created for your app
        * Web submission: the code for your app (the project directory), the `.gitlab-ci.yml` file that defines the CI/CD pipeline for your GitLab repo, and a file called `web.md` that contains the URL to your project hosted online through GitLab Pages

As long as your app does the tasks described above and is submitted correctly, you will get credit for this assignment.

> Note: Make sure you have read and addressed any setup or usage instructions to make sure the plugins will work for your deployment target (Android or Web). These instructions are usually provided in the Readme for the package in pub.dev.

## Getting Graded

You may submit Assignment 7 as either an Android APK (Option 1) OR a GitLab Pages Website (Option 2) -- you do not need to submit both. After completing Option 1 or Option 2, remember to add, commit, and push your code to the `assignment7` branch to complete your submission!

### Android APK

Create a new APK for this assignment by running the `flutter clean` command, and then running the `flutter build apk` command. For more detailed instructions on creating and locating an APK, refer back to the instructions in [Assignment 1](https://github.com/shelleywong/CINS467-Course-Materials/blob/main/Assignments/Assignment1.md#create-your-first-apk).

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

Your code should be submitted to your CINS467 repo (in the CSUC-CINS467 GitLab group). You should use git commands in a command line terminal to record changes to your project and push your updates to a remote repo.

> Note: I recommend **not** using VSCode, GitHub Desktop, or Android Studio to manage your version control -- several students who have tried using these in the past have ended up screwing up their repos. Any issues you run into will be much easier to fix if you consistently use git commands in a terminal.

### Commit your code to the assignment7 branch

```bash
git checkout -b assignment7  #create branch and switch to it
git status #show the working tree status to confirm what changes have been made
git add -A  #add all (if you want to add all changes listed when you run 'git status')
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
