# Assignment 2 - Web Hello World

## In this assignment your app needs to do the following:

* [Be hosted as a GitHub Pages](#github-pages)
* [Your web app should display "CINS467 Hello World"](#web-app)

As long as your app does these tasks, you will get credit for this assignment.

The goal of Assignment 2 is for you to create a simple web application using Flutter, and to give you experience developing a multi-platform application from a single codebase. For future assignments, you will have the option to submit using either an Android APK or a web URL.

## GitHub Pages

[GitHub Pages](https://pages.github.com/) is a simple way for you to host a website directly from your GitHub repository.

Make sure your CINS 467 GitHub repository settings are set up correctly for GitHub pages (from your repo, look for Settings => Pages).

## Web App

It is alright if your code for this assignment looks very similar to your code for Assignment 1. Just make sure that you are able to visit your GitHub Pages web app and your app displays the message, "CINS467 Hello World".

Remember that you will need to run the `flutter build web` command to generate a release build and update the base href (since you are deploying to a non-root URL). The `flutter build web` command populates a `build/web` directory with built files -- you will need to move the `build/web` files and folders into the root of your CINS 467 directory.

## Getting Graded

Create a file called `web.md`. In your `web.md` file you should have a web URL for your assignment hosted online. You can do a web hosted submission for all subsequent assignments as long as they continue to have the functionality of the earlier assignments. The `web.md` file should remain the same for all these submissions. You also can continue to use and build on the same project code as long as it is submitted to the correct branch.

When you have your project finished, submit it in the following format:

```
    /
    ...web.md
    ...AssignmentProject/
    ......android/
    ......ios/
    ......lib/
    ......web/
    ......pubspec.yaml
    ......(Rest of your App Files)
```

All flutter `build/web` files and folders should also be in the same directory as `web.md`.

### Now submit your code to the **assignment2** branch:

```bash
git checkout -b assignment2  #create branch and switch to it
git add -A  #add all
git commit -m "Assignment 2 Submission"  #Commit changes to branch
git push origin assignment2  #Push code up to assignment2 branch on remote
```

Make sure your branch is exactly named `assignment2` matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.

If you plan on making multiple updates to the code on this branch, you can include the `--set-upstream` option when you push the code (i.e. `git push --set-upstream origin assignment2`) -- this adds an upstream (tracking) reference so that, any time you push or pull from this branch in the future, you can simply use `git push` or `git pull`, without specifying the remote and branch.

If you would like to merge your `assignment2` branch with your `main` branch, you can run the following commands:
```bash
git checkout main  #switch to the main branch
git merge assignment2  #join the development history from the assignment2 branch with the current (main) branch
git push origin main  #push the assignment2 history up to the main branch on the remote
```
