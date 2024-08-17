# Assignment 3 - Simple UI

## In this assignment your app needs to:

* **Have At Least Three Buttons**
  * Each button widget must include at least 3 properties:
    * child (the button's label - often an Icon or Text widget)
    * onPressed or other callback (something should happen when the button is tapped or otherwise activated)
      * Each button should have its own unique action.
      * The label for each button should provide an indication of what the button does when pressed.
    * style (an instance of the ButtonStyle class that is used to customize the button's appearance)
      * The buttons must not all look the same.
      * By default, Flutter adds some style to the buttons, but for this assignment, you need to update at least one aspect of the appearance of each button (e.g. background or foreground color, size or padding, shape, font, etc).
    * You are encouraged to play around with other button properties in addition to the ones specified above!
* **Have At Least Two Text Widgets**
  * Each Text widget must contain at least 2 properties:
    * data (the text to display)
    * style (an instance of the TextStyle class that is used to style the text)
      * by default, all text has some style, but for this assignment, you need to stylize the text in some way other than the default.
      * The text in each Text widget should have its own unique style.
      * The TextStyle class is used to format and paint text. **Use at least 2 TextStyle properties** to style the Text widget (notice that you can make changes to color, font, decoration, size, spacing, and more)
* **Make Updates When Each Button Is Pressed**
  * When each button is tapped, it should make a change that is visible in the app.
  * In at least one case, the contents of a Text widget must be updated when a button is pressed. The other buttons may update a Text widget or another aspect of your web app.
  * Remember that the label of each button (e.g. text or icon) should give some indication of what the button does when pressed

Also make sure that you:
* Submit the assignment correctly
  * Use a branch called `assignment3`
  * Submit to your CINS467 GitLab repo
    * You may submit your app as either an Android app or a web app. Your CINS467 GitLab repo on the `assignment3` branch should contain (at minimum):
      * Android submission: the code for your app (the project directory) and the APK file that you created for your app
      * Web submission: the code for your app (the project directory), the `.gitlab-ci.yml` file that defines the CI/CD pipeline for your GitLab repo, and a file called `web.md` that contains the URL to your project hosted online through GitLab Pages

As long as your app does the tasks described above and is submitted correctly, you will get credit for this assignment.

> Note: some aspects of style and layout can be deceptively tricky. Make sure to give yourself time to try out and test various features! Look for code examples and short videos in the official Flutter docs to help with understanding Flutter classes, properties, and methods.

The goal of Assignment 3 is to give you experience creating a simple UI (user interface) with Flutter. Have fun! This is a great time to start thinking about how you want your final project to look, or to just play around, learn about different Flutter features, and figure out how you can customize an app and make it look unique.

## Getting Graded

> After completing Option 1 or Option 2, remember to submit your code to the `assignment3` branch!

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

### Now submit your code to the **assignment3** branch:

```bash
git checkout -b assignment3  #create branch and switch to it
git status #show the working tree status to confirm what changes have been made
git add -A  #add all (if you want to add all changes listed when you run 'git status')
git commit -m "Assignment 3 Submission"  #Commit changes to branch
git push origin assignment3  #Push code up to assignment3 branch on remote
```

Make sure your branch is exactly named `assignment3` matching the case, spacing, etc as my grading script will only pull your submission if it matches exactly.

If you plan on making multiple updates to the code on this branch, you can include the `--set-upstream` option when you push the code (i.e. `git push --set-upstream origin assignment3`) -- this adds an upstream (tracking) reference so that, any time you push or pull from this branch in the future, you can simply use `git push` or `git pull`, without specifying the remote and branch.

If you would like to merge your `assignment3` branch with your `main` branch, you can run the following commands:
```bash
git checkout main  #switch to the main branch
git merge assignment3  #join the development history from the assignment3 branch with the current (main) branch
git push origin main  #push the assignment3 history up to the main branch on the remote
```
