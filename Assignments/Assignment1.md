#Assignment1 - Hello World

##In this assignment you will:

* Get your Android build environment setup
* Create your first app
* Create your first APK
* Getting Graded


For this first assignment you are getting grade on if you succeed in turning in an Android APK that launches and successfully displays "Hello World". This assignment is mostly to make sure you have the build environment setup and can successfully create and export an Android App for grading/install onto phones/devices.

##Getting Build Environment Setup

To get the build environment on your computer you should go to the Android SDK Download page and follow the directions there. The page defaults to the Android Studio bundle, which includes everything you need including the IntelliJ IDE, Android SDK Tools, and Android Emulator all together. It maybe possible to setup for development still using Eclipse; however, as this isn't documented anywhere I'm not going to use it for the class.

##Creating Your First App

**Disclaimer:** *You should go through the steps yourself to create the Hello World app and not just import an existing Hello World app as you'll miss out on going through the steps of creating a new app.*

###Requirements:

* Your app should display "Hello World"


So the following is going to be a walk through for accomplishing the requirements for this assignment's app. This is the only assignment where I'll be giving details beyond the requirements that I have for your app to accomplish. The benefit of this app is it'll hopefully give you the confidence and information to know how to get started on any future app you build for this class or in the future.

<img src="https://raw.githubusercontent.com/CSUChico-CSCI567/CSCI567-Course-Materials/master/Assignments/Images/StartScreen.png" alt="Start Screen for Android Studio" width="250")/>

* First step is to create a new project, which will open up this dialogue:

![New Project Screen 1](https://raw.githubusercontent.com/CSUChico-CSCI567/CSCI567-Course-Materials/master/Assignments/Images/NewProject1.png "New Project Screen 1 for Android Studio")

* You should name your project Hello World \<Your Name\>, as you can see in the dialogue above I've done the same for my name. This will make it easier for us to grade. Next you want to choose the target minimum SDK, you'll want to use the same as shown; however, we'll discuss what this means more later in the semester. Also do not enable any of the platforms other than Phone & Tablet:

![New Project Screen 2](https://raw.githubusercontent.com/CSUChico-CSCI567/CSCI567-Course-Materials/master/Assignments/Images/NewProject2.png "New Project Screen 2 for Android Studio")


* Next you'll want to create a blank activity:

![Select Activity Type](https://raw.githubusercontent.com/CSUChico-CSCI567/CSCI567-Course-Materials/master/Assignments/Images/NewProject3.png "New Project Screen 3 for Android Studio")

* Next, customize your blank activity with the following:

![Customize Activity](https://raw.githubusercontent.com/CSUChico-CSCI567/CSCI567-Course-Materials/master/Assignments/Images/NewProjectCustomize.png "Custom Activity Screen")

* Once that's finished you'll have a new project added to your workspace in Android Studio. The next step is to update the layout file. For this assignment what we'll be doing is programmatically putting a string into a TextView container. So you need to open up the layout xml file. This will be in the file "fragment_main.xml" by default. The following shows where the file is in the project directory:

![fragment_main](https://raw.githubusercontent.com/CSUChico-CSCI567/CSCI567-Course-Materials/master/Assignments/Images/fragmentmain.png "fragment_main")

Once we have that file open you'll want to give the TextView already there an id so we can reference it. I'm going to use textView1 for the moment, but in your future apps you will likely want to give it a more descriptive id value:

	<TextView
		android:layout_width="wrap_content"
		android:layout_height="wrap_content"
		android:id="@+id/textView1"
		android:text="@string/hello_world" />


Now that we have done that we open the MainActivity.java file found in the java files folder as shown here:

![MainActivityFragment](https://raw.githubusercontent.com/CSUChico-CSCI567/CSCI567-Course-Materials/master/Assignments/Images/mainactivityfragment.png "MainActivityFragment")

We now need to import the TextView class into the MainActivity.java file, so at the top of the program where the other imports are (you may have to click on the plus symbol on the left to expand the imports) you need to add the following import:

<pre>
	import android.widget.TextView;
</pre>

After adding the import statement, you'll want to replace the contents of the onCreateView method with the following code:

<pre>
	//Instantiate View object
	View rootView =  inflater.inflate(R.layout.fragment_main, container, false);
	//Initialize TextView Object to the textview we provided in our layout xml referencing the id we gave it
	TextView txt = (TextView) rootView.findViewById(R.id.textView1);
	//Replace the text in the textView with the following text.
	txt.setText("CSCI567 Hello World");
	//Return View described by fragment_main.xml file
	return rootView;
</pre>

These two lines will get the TextView from the layout and assign it to the the variable txt (super original I know...) We then make use of that TextView object and make use of the setText function to put text into the TextView field. Make sure you put the String "CSCI567 Hello World" into your textView as I'll be looking for this for grading purposes.

That should do it. You should now have a functional app that displays "CSCI567 Hello World" when you open it. You can test that it works by using the Android Virtual Device Emulator. To do that you need to first create a virtual device for the project to be run on. Go to your Android Studio menus and likely under the Tools tab you'll see the following options:




This'll launch the Android Virtual Device Manager. You'll want to select the option to create a new device, if you don't already have one. This'll launch the dialogue to create a new Android Virtual Device (AVD). In the select hardware dialogue select the Nexus 6 as this is the current generation Nexus device and would be the ideal phone to target:



Next choose the system image and for this I'd recommend the default, which should be Lollipop x86 (5.0.1). Depending you may have the option for version 5.0.2:


You'll now want to name and save the image, you can go with the defaults here; however, I would recommend saving a snapshot for faster startup and disabling host GPU as this will make the AVD start up faster and it's unlikely you'll have GPU intense applications for this course so this will save you time in the long run:


As you get to later assignments or your project you may want to insure your app scales and works on a multitude devices and resolutions. Now to actually make use of this device all you'll need to do is just click the green play button should say "Run 'app'" when you hover over it. This'll launch the AVD you just created with your project installed on it. It'll also usually launch the app once the AVD starts up. If it works than you're good to move onto the exporting and submitting for grading section of the assignment.

Creating an APK/Exporting your app for submission

Now the final step is you need to export an APK to submit for grading. To start go to the menu bar under Build to find the generate signed APK option:



You won't want to change anything on the first page of this dialogue so just click Next. On the next page you'll get the keystore creation/selection page. As you likely don't have an existing keystore you'll need to create one.



So click the "Create New..." option. This'll launch a dialogue to create a new keystore:



Make sure you choose a location you can remember and don't lose your keystore as this is how you sign your application package. It's also how the phone identifies an app of the same name as the same app to replace. If you change keystores it'll be like its a new app. You can name your keystore whatever you want. Also, choose a good password for your keystore and you should use the same organizational details except replacing my name with yours. Now that you have a keystore and key certificate when we return to the "Generate Signed APK Wizard" it'll have the details filled in for us. You should only need to remember your password to use this keystore/key going forward:



The next page will ask where you want to save your resultant APK file.



This is the file we will be using for grading. This is also a signed Android package, which can be installed on a phone if you allow "Unknown Sources" to be installed on your phone. This signed package is also what you push onto the Android App stores like Google Play or Amazon's Appstore.

Getting Graded

When you have your APK move it to a "Submissions" folder in the root directory of your GIT repo that you were given to turn in assignments for this class. You'll be putting all of the APK files for this class in this folder. The source code should be in a directory named the same as your app in the root directory. I recommend creating your projects in the git repo. Do not use Android Studio to manage your VCS/Repo as it may screw up the repo. So for this assignment you should have a directory that looks like the following:

    /
    ...Submissions/
    ......helloworld_<your name>.apk
    ...HelloWorld/
    ......app/
    ......(Rest of Hello World App Files)


You should also name all your submissions as shown.
