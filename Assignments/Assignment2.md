# Assignment 2 - Web Hello World

The Flutter framework allows you to build natively compiled, multi-platform applications from a single codebase. For Assignment 2, start with the same codebase that you created for Assignment 1. The difference is that this time, you will build the app for web.

* [Requirements](#requirements)
* [GitLab Pages](#gitlab-pages)
* [Getting Graded](#getting-graded)
  * [Submitting your code](#submitting-your-code)
  * [Commit your code to the assignment2 branch](#commit-your-code-to-the-assignment2-branch)

### Requirements

* Create a static web app that displays "CINS467 Hello World" in a Text widget
* Get your web app deployed and hosted using GitLab Pages
  * Create a `.gitlab-ci.yml` file with a basic CI/CD pipeline
* Submit the assignment correctly
  * Use a branch called `assignment2`
  * Submit to your CINS467 GitLab repo
    * Your CINS467 GitLab repo on the `assignment2` branch should contain (at minimum) the code for your app (the project directory), the `.gitlab-ci.yml` file that defines the CI/CD pipeline for your GitLab repo, and a file called `web.md` that contains the URL to your project hosted online through GitLab Pages


The goal of Assignment 2 is for you to create a simple web application using Flutter, and to give you experience developing a multi-platform application from a single codebase. For future assignments, you will have the option to submit using either an Android APK or a web URL.

## GitLab Pages

[GitLab Pages](https://about.gitlab.com/stages-devops-lifecycle/pages/) is a simple way for you to host a website directly from your GitLab repository. GitLab Pages is similar to [GitHub Pages](https://pages.github.com/), with a slightly different setup -- among other things, GitLab Pages use pipelines to publish static websites, so you need a CI/CD pipeline setup in order to create a GitLab Pages website.

To use GitLab CI/CD, you will start with a `.gitlab-ci.yml` file at the root of your project. It is a YAML file with its own custom syntax. This file is used to specify the stages, jobs, and scripts to be executed during your CI/CD pipeline, as well as define variables, dependencies between jobs, and specify when and how each job should be executed.

Your `.gitlab-ci.yml` file for Assignment 2 can be very simple (just need to build and deploy; we will review other stages later in class). Refer to the lecture materials that cover GitLab Pages (find these materials on Canvas), which provide a guide for creating a `.gitlab-ci.yml` file and a basic CI/CD pipeline. I recommend you start with the `.gitlab-ci.yml` example covered in class and make adjustments based on your project.<br>

Make sure your pipeline:
* Includes at least one stage (for building and deploying)
* Uses an up-to-date Docker image for Flutter (I use the one provided by [cirruslabs](https://github.com/cirruslabs/docker-images-flutter/pkgs/container/flutter))
* Includes a script with commands to move into the correct project directory, get all dependencies, build for web, and copy the build files to a directory called `public`
* Specifies the `public` directory for artifacts (GitLab Pages only considers files stored in the `public` directory)
* Optionally, you may also want to configure the pipeline to only run the job on a specific branch (in this case, you want the pipeline to run on the `assignment2` branch)<br>

After you add, commit, and push code to GitLab on a branch that contains a `.gitlab-ci.yml` file, you should be able to go to your CINS467 GitLab repository and see the pipeline running. If the pipeline succeeds, you should then be able to access your GitLab Pages website:
* To see the pipeline for your project, go to the left sidebar and select `Build` > `Pipelines`
  * The pipeline can take several minutes to run.
  * If the status is *Passed*, then your build succeeded.
  * If the status is *Failed*, you can try to identify the issue (if you hover over or click on certain components on the Pipelines page, you can see more details), or feel free to ask the instructor for help.
* To see your website, go to the left sidebar and select `Deploy` > `Pages`
  * Then click on the link provided under **Access pages** (it should include your repo name and end with `gitlab.io`)


## Getting Graded

Create a file called `web.md` in the root of your CINS467 repo. In your `web.md` file, you should add the web URL for your assignment hosted online through GitLab Pages.

You can do a web hosted submission for all subsequent assignments **as long as they continue to have the functionality of the earlier assignments** (this is very important -- there is only one GitLab Pages deployment per repo). The `web.md` file can remain exactly the same for all web submissions, or you can add a note that indicates which assignments are included in the web deployment. You also can continue to use and build on the same project code as long as it is submitted to the correct branch.

Note that GitLab Pages uses a cache for efficiency -- if you have a successful pipeline but then visit your website and it does not appear to have updated, you may be seeing a cached version of the website. Don't panic! Stay calm and either disable the cache or try visiting your website in a private/incognito browser. To disable the cache, go to the browser Developer Tools, click on the Network tab, and make sure the **Disable cache** box is checked.


When you have your project finished, submit it in the following format:

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

If you are able to see your project hosted through GitLab Pages, you should be good for this assignment; just make sure you have submitted the code through the correct branch and included all necessary files on the branch (the project directory, the `.gitlab-ci.yml` file, and the `web.md` file).

### Submitting your code

Your code should be submitted to your CINS467 repo (in the CSUC-CINS467 GitLab group). You should use git commands in a command line terminal to record changes to your project and push your updates to a remote repo.

> Note: I recommend **not** using VSCode, GitHub Desktop, or Android Studio to manage your version control -- several students who have tried using these in the past have ended up screwing up their repos. Any issues you run into will be much easier to fix if you consistently use git commands in a terminal.

### Commit your code to the assignment2 branch

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
