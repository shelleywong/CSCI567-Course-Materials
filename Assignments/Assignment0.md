# Assignment 0 - GitLab README

## In this assignment you will:

* [Complete the preliminary setup](#preliminary-setup)
* [Generate a CSCI567 Course Repo](#generate-a-csci567-course-repo)
* [Add a README file on the main branch](#add-a-readme-file-on-the-main-branch)
* [Submit Assignment 0](#submit-assignment-0)

## Preliminary setup

Note: I recommend using native Flutter on Windows, macOS, or Linux, depending on your device. If you plan to develop with an Android virtual device emulator, you will need native Flutter (an emulator will either not work or be very slow inside a virtual machine, such as a VM hosted by VirtualBox, VMWare, or Docker).

* If you are using **macOS** or native **Linux**, you should be able to complete everything using the default terminal and the editor of your choice (I recommend VS Code or Android Studio).
* If you are using **Windows**, plan on completing your Flutter development in PowerShell, the Windows Command Prompt shell, and/or VS Code or Android Studio. You may need to use multiple terminals, as some commands may not work in all terminals.
  * PowerShell does not have git installed by default, so you will need to install and setup Git on PowerShell to complete the Git commands (including those that interact with GitLab).
  * Alternatively, you may want to use PowerShell for Flutter commands, and then install and setup Git Bash for Git commands.
  * Another potential option is to use WSL2 -- this will likely require a little extra setup and not work by default, and I would recommend only using this option if you put your CSCI567 repo in a place that is accessible from both a PowerShell/Command Prompt terminal and WSL2 (since some commands may not work in every terminal). If you are interested in this option and not sure where to start, I recommend asking for help on the cd Discord.<br>

> My instructions regarding SSH keys are based on the GitHub Docs regarding SSH: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh

> Note: If you already have an SSH key, you may reuse it for GitLab in some cases; however, if you have an SSH key in a VM instance or a WSL2 terminal but plan on using a different shell for Flutter development in this course, you will need to generate a new SSH key in the appropriate terminal. Ask the instructor if you are not sure what to do in your case.

Before you complete Assignment 0, check that you have completed the following steps (sign up for GitLab, install and set up git, set up your SSH key, set up Two-Factor Authentication in GitLab):

1. [Sign up for GitLab](https://about.gitlab.com/)
  * GitLab is free for personal projects. To sign up, you will need to select the option to start a free 30-day trial of GitLab Ultimate. Once the free trial is over, you should choose to go back to the Free tier -- the Free tier is all you need for personal project.
  * Unfortunately, despite GitLab's website saying "no credit card required" -- you may need to enter a credit card. GitLab started requiring new users to provide a valid credit or debit card in order to discourage and [reduce crypto mining abuse](https://about.gitlab.com/blog/2021/05/17/prevent-crypto-mining-abuse/). When you provide the card, it will not be charged but instead will be verified with a one-dollar authorization transaction. No charge will be made and no money will transfer.
  * Note that you must actually sign up for GitLab -- you will not be able to join the CSUC-CSCI567 group if you sign in to GitLab with credentials for another site (e.g. GitHub).
2. Confirm that you have git installed (if installed, `which git` will identify the location of git installed on your machine, while `git version` will display version information)
```
$ which git
$ git --version
```
  * If you do not have Git installed, [download and install Git for your operating system](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
3. Check your Git settings and confirm that you have set your name and email. Start by viewing your settings. If you see your name and email (e.g `user.name=Your Name` and `user.email=youremail@mail.com`), type `q` to exit and continue to the next step.
```
$ git config --list
```
  * If you do not see your name and email, set them using the following (make sure to use your real name and email in place of the John Doe example below):
```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```
  * You can confirm that your name and email have been set by running the `git config --list` command again.
4. Check for an existing SSH key
  * Note: you need to generate an SSH key for your local machine -- if you have previously generated an SSH key in a Linux Virtual Machine or ecc-linux, you will need to generate another one locally.
  * Note: If you already have an existing SSH key on your local machine, it is safe to reuse your existing SSH key, just make sure to keep your private key secure. If you already have a key, continue to step 6.
  * Open a terminal and enter the following command to see if existing SSH keys are present:
    * `ls -al ~/.ssh`
  * Examples of public ssh keys include `id_rsa.pub`, `id_ecdsa.pub`, and `id_ed25519.pub`. If you have a key already, you can skip the step to generate a new SSH key and upload your existing key to GitLab (if you complete the step to Generate a new SSH key and the SSH key is the same type as one you already have, it will overwrite your existing key)
5. Generate a new SSH key
  * Note: Ed25519 signatures are elliptical curve signatures, which are fast and very secure; however, some legacy systems do not support the Ed25519 algorithm, so if the ed25519 key is not working for you, create and use an RSA key.
  * Use the ssh-keygen command to generate an ssh key (below are options for generating an ed25519 key or an RSA key):
    * `ssh-keygen -t ed25519`
    * `ssh-keygen -t rsa -b 8192`
  * This will generate a public/private key pair. When you're prompted to "Enter a file in which to save the key", you should press Enter to accept the default file location (the `~/.ssh` folder). Do not give the key a name (the default name works best for our purposes).
  * At the next prompt, you may choose to type a secure passphrase (or leave empty for no passphrase).
    * If you include a passphrase, make sure it is one that you will easily remember, as you will need to type the passphrase every time you use a git command that interacts with GitLab (e.g. `push`, `pull`, `clone`).
    * If you do not include a passphrase, make sure you keep your computer secure (do not allow other people to use or easily access it).
6. Add an SSH key to your GitLab account
  * Copy the SSH public key to your clipboard
    * Windows: `clip < ~/.ssh/id_ed25519.pub`
    * Mac: `pbcopy < ~/.ssh/id_ed25519.pub`
    * If the `clip` or `pbcopy` command is not working, you can locate the hidden .ssh folder, open the file in your favorite text editor, and copy it to your clipboard, or use the `cat` command (e.g. `cat id_rsa.pub`) to display the key in the terminal and copy the key from there.
  * Go to GitLab, login (if you have not already), and add your SSH key to GitLab:
    * Click on your account (look for your name and username), select the `Edit Profile` option, and select `SSH Keys`. Alternatively, you can use the search bar ("Search or go to..."), enter "ssh keys", and go to Settings > SSH Keys.
    * Click the `Add new key` button, then paste your public key into the `Key` text box (it should begin with something like 'ssh-rsa' or 'ssh-ed25519')
    * Give your SSH key a title (I recommend using a title that indicates the laptop/computer/device to which it is connected)
    * Leave the Usage type as "Authentication & Signing"
    * Optionally, set an expiration date -- if you include an expiration date, make sure it is after the end of the semester for this class.
    * Click the `Add key` button to finish adding the SSH key. Now, you should see your key in the list of "Your SSH keys".
  * Enable Two-Factor Authentication
    * In order to use the CSCI567 course repo, you will need to increase your account's security by enabling two-factor authentication (2FA). Go to your account (gitlab.com/yourusername), click the `Edit profile` button, then select `Account` from the left sidebar. Make sure you **enable Two-factor authentication**.
      * For two-factor authentication, you can **Register a one-time password authenticator** (such as Duo Mobile, Authy, Google Authenticator, etc) or **Register a WebAuthn device** (a hardware device such as a YubiKey).
      * You should already have Duo Mobile for campus authentication -- if you set up Duo for GitLab, note that you may not get a notification (like you do when signing in to campus apps). You can look for a 6 digit passcode (hidden by default) in the app (note that the passcode will get refreshed frequently).

## Generate a CSCI567 Course Repo

For this course, you will complete all programming assignments (with the possible exception of your final project) in your private GitLab repo that is part of the CSUChico/CSCI567 group. The group is private -- you will only be able to access it after you have generated a CSCI567 repo and joined the group.

1. Go to the [Repo Generator](https://repo.bryandixon.phd/) page and select your course (CSCI 567)
2. Fill out the form with your First Name, Last Name, GitLab username, and the Course Token (provided during lecture).
  * If you are retaking CSCI 567, you may receive an error that you have already generated a repo. Email or talk to the instructor about getting your repo updated for the current semester (you will not submit the form again in this case).
  * Make sure you enter everything correctly -- if you enter a valid, existing GitLab username but it is not your GitLab username, a different person will receive the invite.
  * Click the button to Generate a GitLab Repo.
  * If you run into any issues with generating a GitLab repo in the CSUChico/CSUC-CSCI567 group, talk to the instructor!
3. After submitting the form, go to [gitlab.com/CSUChico/CSUC-CSCI567](https://gitlab.com/CSUChico/CSUC-CSCI567) and see if you have access to the CSUC-CSCI567 group. You should see a private repo generated for you. The repo will have a name in this format: `CSCI567-Semester-FirstName-LastName`.
4. If you click on the repo, you should see that it is empty. Now you should use the command line instructions to "Create a new repository". The steps described below are given in the empty repo -- the main difference is that you need to add some additional information to the README for Assignment 0.

## Add a README file on the main branch

Follow the Command line instructions provided in the empty repo to "Create a new repository" (make sure to include the information specified below in your README):

1. Clone your project (the url you should use is provided in the empty repo, or you can click the blue **Code** button and copy the URL to Clone with SSH):
```
git clone git@gitlab.com:CSUChico/CSUC-CSCI567/CSCI567-Semester-FirstName-LastName.git
```
  * Note: If this is your first time connecting to GitLab (or another server), you will get a message that looks something like this: "The authenticity of host '...' can't be established." This is normal. You should be asked if you are you sure you want to continue connecting, and you should type in 'yes'. This will add GitLab to your list of known hosts.
    * For more insight, you may be interested in reading this forum post on [SSH: The authenticity of host <host> can't be established](https://superuser.com/questions/421074/ssh-the-authenticity-of-host-host-cant-be-established)

2. Move into the repository that you've just cloned:
```
cd CSCI567-Semester-FirstName-LastName
```
3. Create a new branch called `main` and switch to that branch:
```
git switch --create main
```
  * This is a shortcut for creating a main branch (`git branch main`) and then moving to that branch (`git switch main`)
  * `switch` is a relatively new option; you could also create a new branch and switch to that branch with the following command: `git checkout -b main`
4. Create a new file called "README.md":
```
touch README.md
```
5. Open README.md with the editor of your choice (e.g. vim, VSCode)
6. Edit your README.md file to include the following information, using the style specified -- feel free to reference the [Markdown Style Guide](https://handbook.gitlab.com/docs/markdown-guide/) for more information. (Note that spacing matters when writing markdown)
  * Add your First and Last name as an `h2` heading
  * On a separate line, add the following text (use the current semester): "Private repo for CSCI 567 assignments: Fall 2025"
    * Give emphasis to the current semester (e.g. "Fall 2025") using (**bold** and/or _italics_)
  * Add a **horizontal line** below the current semester
  * Below the horizontal line, add an **ordered or unordered list** that contains the following two items: (1) "Chico State Username: " followed by the username you use to login to the Chico State Portal, and (2) "GitLab Username: " followed by the username you use to login to GitLab
7. After you have finished editing the README.md file, save your changes.
8. Check the working tree status (you should see that you are on the main branch and have README.md as an untracked file):
```
git status
```
9. Add the README.md file to the index, to prepare the content staged for the next commit:
```
git add README.md
```
10. Record the changes to the repository (make sure to include a short but descriptive message to describe what you are committing):
```
git commit -m "add README"
```
11. Update the remote repo on GitLab:
```
git push --set-upstream origin main
```
  * Note: you only need to include `--set-upstream` the first time you push to a branch -- the next time you push to the `main` branch, you can simply use `git push` or `git push origin main`
12. Now go to your CSCI567 repo on GitLab, reload the page, and confirm that you have added a README.md that contains the details specified above. It should look something like this:

![README example](/Assignments/Images/README_example.png)

  * If your code is one big block of text, look at  the [Markdown Style Guide](https://handbook.gitlab.com/docs/markdown-guide/) instructions more carefully, or ask the instructor about fixing your README.
  * If the README looks good, then you are done with Assignment 0!

## Submit Assignment 0

If you have completed the steps above, your Assignment 0 submission is complete. I will be looking for a README.md file (with the information specified above, formatted as described) in the `main` branch of your private CSCI567 repo, in the CSUC-CSCI567 group.<br>

Reminder: if you have completed the README.md file and it is in the correct location, this indicates that you have created a GitLab account (with Two Factor Authentication), generated a CSCI567 course repo, set up Git, created an SSH key, used Markdown to edit a README.md file, and practiced some basic Git commands.
