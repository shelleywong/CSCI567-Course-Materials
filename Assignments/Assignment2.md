# Assignment 2 - Web Hello World

## In this assignment your app needs to:

* [Be a static web app, hosted using GitLab Pages](#gitlab-pages)
* [Display "CINS467 Hello World" in a Text widget](#web-app)

Also make sure that you:
* Submit the assignment correctly
  * Use a branch called `assignment2`
  * Submit to your CINS467 GitLab repo
    * Your CINS467 GitLab repo on the `assignment2` branch should contain (at minimum) the code for your app (the project directory), the `.gitlab-ci.yml` file that defines the CI/CD pipeline for your GitLab repo, and a file called `web.md` that contains the URL to your project hosted online through GitLab Pages

As long as your app does the tasks described above and is submitted correctly, you will get credit for this assignment.

The goal of Assignment 2 is for you to create a simple web application using Flutter, and to give you experience developing a multi-platform application from a single codebase. For future assignments, you will have the option to submit using either an Android APK or a web URL.

## GitLab Pages

[GitLab Pages](https://about.gitlab.com/stages-devops-lifecycle/pages/) is a simple way for you to host a website directly from your GitLab repository. GitLab Pages is similar to [GitHub Pages](https://pages.github.com/), with a slightly different setup -- among other things, GitLab Pages use pipelines to publish static websites, so you need a CI/CD pipeline setup in order to create a GitLab Pages website. Look for the lecture materials that provide a guide for creating a `.gitlab-ci.yml` file and a basic CI/CD pipeline (deploy stage only).

From your CINS467 GitLab repository, you should be able to see the pipeline running and access your GitLab Pages website:
* To see the pipeline for your project, go to the left sidebar and select `Build` > `Pipelines`
* To see your website, go to the left sidebar and select `Deploy` > `Pages`
  * Then click on the link provided under **Access pages** (it should include your repo name and end with `gitlab.io`)

## Web App

It is alright if your code for this assignment looks very similar to your code for Assignment 1. Just make sure that you are able to visit your GitLab Pages web app and your app displays the message, "CINS467 Hello World".

Note that if you set up the `.gitlab-ci.yml` file correctly, it will run the `flutter build web` command to generate a release build and complete the other commands necessary to upload your program to use with GitLab Pages.

## Getting Graded

Create a file called `web.md`. In your `web.md` file, you should add the web URL for your assignment hosted online through GitLab Pages. You can do a web hosted submission for all subsequent assignments as long as they continue to have the functionality of the earlier assignments. The `web.md` file should remain the same for all these submissions. You also can continue to use and build on the same project code as long as it is submitted to the correct branch.

When you have your project finished, submit it in the following format:

```
    /
    ...README.md
    ...web.md
    ...AssignmentProject/
    ......android/
    ......lib/
    ......web/
    ......pubspec.yaml
    ......(Rest of your App Files)
```

> Note: the `.gitlab-ci.yml` file is a hidden file, so you will not see it if you run the `ls` command without any options. You can list hidden files in long format using `ls -al`

If you are able to see your project hosted through GitLab Pages, you should be good for this assignment; just make sure you have submitted the code through the correct branch.

### Submitting to your remote CINS467 git repo

I recommend that you use git commands in a command line terminal to record changes to your project and push your updates to a remote repo. I recommend **not** using VSCode, GitHub Desktop, or Android Studio to manage your version control -- several students who have tried using these in the past have ended up screwing up their repos. Any issues you run into will be much easier to fix if you use git commands in a terminal.

### Now submit your code to the **assignment2** branch:

```bash
git checkout -b assignment2  #create branch and switch to it
git status #show the working tree status to confirm what changes have been made
git add -A  #add all (if you want to add all changes listed when you run 'git status')
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
