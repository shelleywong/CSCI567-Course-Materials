# Final Project - Overview

## Details for this project:

* [Final Project Overview](#overview)
* [Final Project Options](#options)
* [Final Project Concept](#idea)
* [Final Project Full Proposal](#proposal)
* [Final Project Submission](#submission)
* [Final Project Presentation](#presentation)
* [Final Project and Group Feedback](#feedback)
* [Final Project Grading](#grading)

This project will occupy several weeks of your time this semester. You should plan on spending significantly more time on this project compared to the other assignments in the course. The early assignments and lectures will hopefully give you the rudimentary tools you need to get started creating a Flutter Application for this project.

> Important Note: Do NOT use your CINS467 project as a submission for another class. Do NOT submit a project from another class as your final project for CINS467. In certain cases, students are allowed to start from an existing project from another class and expand on it; however, you must make clear which components were completed for which class and get approval from any instructors involved. Without explicit permission, submitting the same work for credit in more than one course is a violation of academic integrity.


## <a name="overview">Final Project Overview</a>

The primary purpose of this project is to give you the opportunity to create a working Flutter Application. An additional goal is to give you a reason to make use of some of the software development tools discussed in this course (GIT, Issue Tracking, CI/CD, testing, etc). There are a few different classifications of projects (which will be discussed in a later section) -- this will hopefully provide you with flexibility and freedom to pursue something you or your partner has an interest in, whether it be a new app idea or contributing to an open source project. I am hopeful that you all will find this project fun and exciting, and I look forward to seeing your results at the end of this semester!<br>

If you need web and/or database backends for your project, I will have Google Cloud Education Credits available for every student that can go towards hosting on Google's Cloud services. The free tier provides adequate service for the scope of many CINS 467 projects; however, costs for some APIs and services (e.g. related to Google Maps) can go up quickly. If you use Google Cloud Education Credits as the billing account for your project, you should not need to add a credit card to your account, and you should be able to avoid getting any surprise charges. If you are nearing the credit limit or have reached the limit, let me know -- I can send message to the Google Cloud Education Programs Team and request additional credits for the specific accounts that are in need of additional funds.<br>

I highly recommend you work with Firebase on their free tier as the backend for your projects. The generous [No-cost Spark Plan](https://firebase.google.com/pricing) provides enough features to meet most students' needs for their final projects. You can use products in the free tier without counting against your education credits.<br>

More info on Google Cloud education credits: [Get and redeem education credits](https://cloud.google.com/billing/docs/how-to/edu-grants)

### Project Requirements

Grading for the final project will be based on the following criteria. Your final project must:

1. Be a **dynamic app that provides an interactive user experience and helps demonstrate your understanding of client-side web/mobile app development**.
    * Each final project will be different, but general features I will be looking for include effective interaction with a backend (which often include using async operations), handling user events (like clicks/taps, keyboard events, and user form submissions), and responsiveness (real-time updates that do not require reloading the page and a display/layout that updates automatically based on changes). I expect most final projects to provide a personalized user experience, meaning that the app's content, interface, or features should adapt to user interactions and inputs, as well as things like individual preferences, historical usage, user uploads, and location.
    * In contrast, a "static" app or website would deliver the same content to every user and only change if the underlying code is updated or reloaded. If you have an idea for an app that is mostly static, you should think of ways to make it more dynamic, or consider pursuing a different idea for your CINS 467 final project.
2. Leverage the fact it is on a device with internet connectivity
    * You must send and/or receive data from an internet-based source such as the Firebase database (Cloud Firestore) or an API.
    * **Completing this requirement shows that your client-side code is successfully communicating with a web server to retrieve and/or send data, interacting with a database to provide services to your users**.
    * This requirement will be weighted based on complexity and usefulness.
      * At minimum, your app should receive and display data from Cloud Firestore or an API. Note that not all APIs meet this criteria -- confirm if the API has an endpoint that you can interact with (e.g. a URL that you can make HTTP requests to).
      * There are various ways that you can meet this requirement at a more intermediate/advanced level. Some options include but are not limited to: allowing users to create unique, personalized data and send it to the backend (with results displayed that change based on input), connecting data to specific users and displaying it such that the data is clearly connected to specific users, only allowing the current user to view and edit their own data (through profiles and user accounts), allowing users to manipulate data after it has been created and then display, filter, sort, search, and use that data in a meaningful way.
3. Use the camera and/or location services on the device
    * If you are planning on using the camera, remember that the gallery or the ability to access files is not the same as using the camera.
    * If you are planning on using location services, remember that using a map is not the same as using location services on the device.
    * **Completing this requirement shows that your app is successfully interacting with the device hardware**. Recall that interacting with sensitive hardware components generally requires privacy and security measures -- if your app includes these features, the user is usually prompted for permission to grant access.
    * This requirement will be weighted based on complexity and usefulness.
      * At minimum, your app should capture a photo using the camera or get the location of the device and display the image or location in the app.
      * There are different ways that you can meet this requirement at a more intermediate/advanced level. Some options include but are not limited to: using the image in a meaningful way after it has been captured (e.g. storing the images and connecting them to specific users/documents, creating digital stories or collages from multiple photos, providing ways to process or edit photos), or using the location in a meaningful way after it has been accessed (e.g. using the GPS coordinates to provide location-based suggestions, connecting users to other nearby users, triggering actions or notifications when entering or leaving specific areas, tracking outdoor activities, planning routes).
4. Be interesting or useful
    * **Does not have to be a completely original idea, but should be unique in some way** -- should not just be implementing a tutorial or copying an example you have found online or generated with AI.
    * If you use any tutorials (particularly anything that is not an official Flutter tutorial), you must include a reference (at minimum, include a link). You should also go beyond the tutorial and include changes that make sense for your app. Your final project should not match something I can find on the internet. Please refer to the academic honesty policy in the syllabus or ask me if you have questions about this.
    * You are encouraged to use libraries, packages, and plugins to help enhance the functionality of your app; however, make sure these tools are not providing the core functionality of your app. Understanding how to interact with libraries is important, but the core logic of your app should be developed by you (and your partner, if working in a team).
5. **Be usable and accessible** -- aim to create an app that provides a quality experience to all users.
    * Accessibility can be very complex, especially when considering the unique needs of users with disabilities, but there are several features that I would expect in even the most basic apps, such as clear and consistent navigation across all app views, sufficient contrast between text and background colors so that text is readable, a responsive layout that works well across different screen sizes and orientations, forms that have clear labels/instructions and are easy to fill out, and alt text or other types of labels for images and icons.
6. Be submitted in a functional format that is usable by others. The app should work without crashing. You may submit your project as either an Android mobile app or a web app:
    * **For Android apps, submit a production-ready APK (release version) that can be installed on an Android device**. The APK should be usable without additional setup, and I should not need to use 'flutter run' to test your app locally. It may be helpful to test the release version of your app (in addition to the debug version) to ensure it functions as intended (some features work in debug mode but not in release mode).
    * **For web apps, submit the URL to a hosted, production-ready version of your web app.** The web app should be fully functional and accessible from any modern browser (not just accessible through localhost). There are several free and relatively simple options available that will work for most final projects in this class, including the examples covered in class using GitLab Pages or nginx.<br>


**Other important things that will be considered**:
* Part of the way you can demonstrate your web and mobile app development skills is by **using git version control effectively** (this includes commits, branches, merges, resolving conflicts, etc). Regular git commits (with meaningful commit messages) help document your development process, provide context about any changes made to the codebase, and make it easier to debug (or revert back to a previous stable state of the code). If you are working on a team, regular git commits make it easier to integrate changes, address bugs early, and make sure everyone is on the same page. Using git effectively helps improve the quality of your code and ensure the integrity of your project. When your final project is graded, your git commit history may be referenced to provide insight into your learning and development process. You should aim for your git repo to show a history of work (not just one big commit at the end). If you are working with a partner, the commit history should clearly indicate which changes were made by each team member. Ensure that both partners are regularly committing their individual contributions to the repository.
* You are encouraged to incorporate **basic security practices**, such as input validation, using HTTPS for network communications, using Firebase Authentication (or similar) that leverages industry standards like OAuth 2.0 and OpenID Connect, taking precautions related to user privacy (only collect relevant data (don't collect personal info if it's not needed), provide options to manage data, use consent mechanisms, restrict access to certain parts of the app or data based on user roles and permissions), etc.
* **Make sure your project aligns with the learning goals of a frontend-focused web and mobile app development course**. Just because an app idea includes a web or mobile interface does not mean it will result in a successful final project.
  * If your project idea requires extensive work in areas outside the primary focus of this course (such as training a machine learning model, developing complex hardware integrations, designing a new protocol for secure user authentication), then the idea might be more appropriate to pursue in a different course, for a senior project, or as a personal project. These projects can be valuable learning experiences, but they may not do a good job of allowing you to demonstrate the main skills and concepts we aim to develop here, such as UI/UX design, client-server communication, data handling, and other web and mobile-specific development practices.
  * If your project idea is for an app that is mostly static or only meant to be used by one person (such as a basic portfolio website or an app that just displays hard-coded or randomly generated information and does not store any data), it may not provide enough scope to demonstrate a wide range of skills in app development. Any app idea you have is worth creating (the experience can be beneficial to you while also being something that you can put on your resume); however, this type of app might be more appropriate to pursue for a personal project.
  * If your idea falls into either of these realms, consider adapting or expanding on your idea so it can better showcase client-side web/mobile app development (both what you have learned in class and how you have gone beyond the class examples), or think about choosing a different project that will allow you to demonstrate your skills in building a functional, dynamic, user-friendly, and responsive web or mobile application.


## <a name="options">Final Project Options</a>

For this project there are two different options for the type of project you can pursue. If you have general questions about either of these project options please ask.

* **New Project**
  * With this option, you will create and work on a project you/your partner come up with. If working with a partner, you will want to make sure you both are doing enough for it to be a good project, while at the same time making sure you are not trying to do too much. This is where the project proposal will be extremely important and helpful.
  * If you choose this option, you should try to get me your project proposal before it is due, so I can work with you to ensure the project has a good scope of work and give you the opportunity to resubmit if needed.


* **Open Source Project**
  * This option will require you to find an existing open source project that you/your partner will contribute to. Your project proposal will need to make sure that it indicates what contributions you will be making. For this project, you will also want to clone the open source project into a repo for your group to use for the CINS 467 Final Project. You may push your revisions up to the original open source project after the semester.
  * If you choose this option, you should figure out how and what you will be contributing to the project early on, so I can make sure your deliverables will actually be a significant contribution to the open source project. You will need to contribute significantly to the open source project to be successful on this kind of project.


Once you've decided on which kind of project you will be doing, you should begin brainstorming what you expect to get done this semester and then move onto putting together the project Concept and Proposal submissions.


## <a name="idea">Final Project Concept</a>

The goal of the **Final Project Concept** submission is for you to provide a description that gives a basic idea for your project. You should get your Concept approved before completing the Full Proposal. Your final Project Concept submission should include the initial parts of the proposal:

* **Project Title**
  * Your project proposal should be titled with what you expect to call your app.
* **Project Members**
  * You should make sure that you identify all members of the project team right below the project title.
  * You may work in a pair (group of 2) or as an individual for the project.
* **Project Description**
  * This should describe what your project is and what you expect it to accomplish. This description has some similarities to an elevator pitch -- it should explain the concept of your project in a way that any listener could understand it in a short period of time. Explain who your app is for and what it offers.
  * This description should include an overview of what you expect to accomplish, including **how you will address the program requirements**. In particular, make sure to highlight how you expect your app to use (1) internet connectivity (sending/receiving data from an internet-based source such as Cloud Firestore or an API) and (2) either location services or the camera (how your app will interact with the device hardware). Refer to the [Project Requirements](#project-requirements) for more details.


If you are completing the project as a pair, the quality and complexity of the project proposed should be slightly higher than that of an individual project; however, it does not need to be twice as complex, since working successfully in a group provides its own challenges.


Submit the **Final Project Concept** to Canvas as a **PDF** document. If you are working as a **pair**, only one member of the group needs to submit the PDF document to Canvas (the document should include the first and last name of both group members). It is fine if both members submit the PDF, just make sure the submissions match (I will only grade one submission per pair). **Make sure your group has communicated how the Final Project Concept will be submitted**.


## <a name="proposal">Final Project Full Proposal</a>

Your **Final Project Full Proposal** must contain the Final Project Concept (what your project is, who is working on the project, a general idea of what you will accomplish by the end of the semester), as well as some additional components (described below). The Project Title, Project Members, and Project Description should match or be similar to the *Final Project Concept* that you previously submitted -- if your concept got feedback that required any changes, you can address the feedback in your Final Project Full Proposal submission. As such, your Final Project Full Proposal should have the following sections:

* **Project Title**
  * Your project proposal should be titled with what you expect to call your app.
* **Project Members**
  * You should make sure that you identify all members of the project team right below the project title.
* **Project Description**
  * Use what you submitted for Final Project Concept, with any changes as needed or requested.
* **Project Implementation Details**
  * Let me know if you are building for Android or Web. You are not required to do both but you are welcome to target more than one platform. If you want to target iOS or desktop, you must also build for either Android or Web. If you are using any packages, remember to check if the package supports your chosen platform.
  * Describe what types of data you plan on sending and/or receiving from an internet-based source such as the Firebase database (Cloud Firestore) or an API. If you are using a database, what data will your app utilize and store (e.g. user info, user history, favorites, scores/records, events, camera photos, etc)? If you are using an API, what types of data and services will your app retrieve, display, and interact with? If you are using an API, it is also recommended that you store and process select pieces of data from the API (e.g. storing favorites or recently viewed items, so they are easier to access).
    * You do not need to create a database design diagram; you just need to indicate the collections of data you plan to use and provide a general idea of the fields that will be included in documents from these collections.
    * You may not be sure about all the specifics, and your data may change as you begin building your app -- that's fine. I just want to see that you have an idea of what types of data you are going to store and how that data is going to be used in your app. (Reminder: extensive research and planning at this stage can make your actual development go much more smoothly!)
* **Project UIs**
  * In this section, you should briefly describe or show prototype sketches/diagrams of what the expected UI for your app will look like at the end of the semester. This should include all of the Views you plan on creating. This component of the proposal is similar to a website wireframe, a visual guide that represents the skeletal framework of a website.
  * It is fine if your views (the number of views or what is displayed in the views) is different at the end of the semester. As you develop your project, you may realize that something else will work better. You do not need to resubmit your proposal if the updates do not significantly change the overall idea of your project -- I just want you to have an idea of your general UI layout before you start building.
  * Your Project UIs may be hand drawn or completed with a wireframing tool of your choice. It is ok if this component does not look professional, but I expect you to have given some thought to how people will interact with your site (page layout, interface elements, navigation).
* **Diagram Screen Relationships**
  * Taking the UI design/interaction process a bit farther, this section should show in a transition graph how the different screens relate to each other and transitions from one activity to another. How does everything work together?
  * Completing this section should help you design the UI in the previous stage. To be effective, each state in the diagram should connect to a specific UI from the previous section.
* **Project Deliverables**
  * This is the most important section of the proposal -- this is where you will actually create a list of expected contributions, features, developments, etc that you expect to have working by the end of the semester.
  * As your proposal will contribute to your project grade, more detail vs less detail here is important.
  * You should include separate **lists** for **expected deliverables** and **bonus deliverables**. Part of your grade will be based on the amount of progress you have made toward completing your expected deliverables (you may get bonus points for going beyond that).
  * These deliverables need to be clearly stated and specific enough so that when I read the proposal, it is clear to me what you will be doing on the project and what features your project will provide. If this is not clear, you will need to further explain your project deliverables to me before I will sign off on your project. You will lose points off your proposal significantly if I need to do this.
  * If I feel your project is not significant enough, I will ask you to complete more of your deliverables or add more to the project. Alternatively, if I feel that your project is taking on too much, I will propose a subset of your deliverables that you should make sure to get working first. The fact that you may need to modify the scope of your project proposal is the reason why I want you to start thinking about and submit your proposal as early as possible. Remember that I will need time to adequately read through and think about your projects.
* **Project Organization and Timeline**
  * This section breaks down how you expect to organize and manage the development of the project among your team (or just for yourself). What is the general plan? Are different members going to be assigned different components? Figure out what each individual's job/tasks will be, so everyone knows what they are doing when they start working on the project.
  * Think through the responsibilities for each group member at this stage. Depending on your project and the number of people working on the project, it would potentially be worthwhile to have someone focus on test completeness/soundness for all the functionality of your app. This would be very useful for tying your project into a CI/CD framework. CI/CD will be discussed in class and is an important component of most real world applications.
  * **You must create a timeline for each member of the group.**
    * Everyone's timeline may be a little different, but you might include steps for getting aspects of your project set up, working, developed, etc.
    * For each individual team member, set milestones that you want to complete by a given time (be realistic about the time you think you will need, but it is ok if you do not follow your timeline exactly)
    * Make sure to include time to test each component and confirm that everything is working as expected.
    * You must set at least 6-8 milestones per developer (you can create more milestones, too, if you think it makes sense). This equals out to about 1 milestone per week -- aim to make progress on your final project EVERY week for the last portion of the semester. Remember that you will need to regularly submit project progress updates. Do NOT leave everything until the last week or so!

Submit the **Final Project Full Proposal** to Canvas as a **PDF** document. If you are working as a **pair**, only one member of the group needs to submit the PDF document to Canvas (the document should include the first and last name of both group members). It is fine if both members submit the PDF, just make sure the submissions match (I will only grade one submission per pair). **Make sure your group has communicated how the Final Project Full Proposal will be submitted**.

If you want faster feedback, send me an email before the submission deadline to let me know. If you submit the proposal with a significant amount of time before the deadline, it will allow me to give you feedback without any grade penalty.

## <a name="submission">Final Project Submission</a>

You may create a new repo for your final project or use the CINS467 repo that is part of the csuchico-cins467 group. If you are working with a partner, you will need to create a new repo. **If you create a new repo**, it may be private or public, as long as it does not contain your submissions for Assignments 0-7. **If your repo is private** and it is not the one that was generated for you for this class, you should add me as a collaborator so I can see your project. At the end of the semester, you will submit information about your final project repo so I know where to look for it. For the final submission, make sure you put the compiled APK file into the root path of your git repo so I can easily install and test your project. To make sure you are creating a fresh APK, you can clear the build cache using the `flutter clean` command (or, alternatively, use the standard Linux command to remove all files in the build/ directory using `rm -rf build`) -- do this command before running the `flutter build apk` command. If you have an iOS or desktop version of your project, I will not be testing it.

If you are working as an individual and especially if you are working in a group, you should plan on making regular commits to your Final Project repo. This is a good way for me to see that you made regular progress on your project (I recommend making at least one commit for each milestone in your timeline). Failure to use the repo for code collaboration will generally not result in any direct grading impact; however, if there is a group work dispute I will use the commit history to gain insight into who contributed what. One of the key reasons for having you work in pairs for this project is to provide you the opportunity to collaborate on a project with version control -- a necessary skill when you enter the workforce. I also hope you will leverage CI/CD & testing in your projects, and GitHub and GitLab are a great resource in that regard.

## <a name="presentation">Final Project Presentation</a>

Each group (individual or pair) will present their project to the class. Presentations should be no more than 8 minutes. (I allocate 10 minutes per presentation to allow for transition time and questions from the audience). Plan on showing your app to the class and walking through how it works. You do not need to have a slide show, but you may include one if you think it would be helpful.

In your Final Project Presentations, you should plan on including the following:

* An introduction
  - let us know your name(s)!
* An overview of your project/app
  - What is your project?
  - What was your basic mission or design challenge in creating this project? What problem were you trying to solve, or what need or interest were you trying to address?
  - It may be useful to ask a question to the audience to engage them and bring them into your conversation, so they share your passion or pain.
* A demonstration of your app
  - Show your app to the class and walk through how it works!
  - How would a new user navigate your app and use its features?
  - Step through everything -- even if some components are not complete, your presentation can help me when I am grading and testing your final submission
  - Highlight anything about your approach that is different from other similar projects
* Discuss your challenges
  - Describe any technical hurdles you ran into
  - Explain what you still have to get working
* Discuss what you found cool/exciting/interesting about your project :grinning:

## <a name="feedback">Final Project and Group Feedback</a>

At the end of the semester, you will be given access to a Final Project Submission/Feedback Form. Completing this form will give me important information about the project, including details about where your project is hosted and/or where your code (and APK) is stored. The survey will also ask for feedback regarding your experience in the course and working on the project. This includes discussing the challenges you faced, expanding on why some deliverables did not get completed, exploring what you learned along the way, and providing some insight that could help future CINS 467 students. If you worked in a group, you will also be asked to evaluate how well the group worked together and how much you felt each teammate contributed.

The questions on Project Completion and Learning Feedback are especially important for helping me assess your work in this class, so give as much detail as possible in this section.

Failure to complete this survey will result in the loss of the group evaluation credit (if working in pairs) and a deduction or loss of the final project grade (for anyone).

## <a name="grading">Final Project Grading</a>

Your overall grade in the class includes several components related to the Final Project. The assessment for these components will be focused on the following:

* Project Concept and Proposal
  - Have you included all the requested components of the concept and proposal?
  - Are your descriptions and explanations clear, specific, and detailed?
  - Have you put thought into your deliverables and how you will complete them?
  - I am seeking well-organized details that clearly indicate thoughtful consideration of each component.

* Project Presentation and Presentation Feedback
  - Have you given a Presentation for your Final Project?
  - Does the presentation include all the requested components?
  - After watching your presentation, the audience should have a clear understanding of what your project is and how it works, and they should know a little about your experience working on the project (e.g. any technical hurdles, challenges, successes)
  - Have you attended presentations other than your own and completed the presentation feedback forms?
  - In the presentation feedback forms, you should make it obvious to me that you were listening and paying attention to the presentations (I am interested in seeing your thoughts on the project itself)
  - You will need to fill out feedback forms for at least 80% of the presentations to receive full credit for the presentation feedback portion of the grade

* Lecture Attendance, Lab Help Session Attendance, and Project Progress Updates
  - Lecture Attendance will be tracked through PollEverywhere polls. To be sure your participation is registered, make sure to use an account tied to your csuchico email. You should respond to at least 80% of PollEverywhere polls during class lectures to receive full credit for this portion of the grade.
  - Lab Help Session Attendance will be tracked through a sign-in sheet. This is time for you to make incremental progress on your project (and communicate with your partner, if you are working in a pair). To receive full credit for this component, you should attend at least 80% of lab help sessions.
  - A Project Progress Update Form will be available midway through the semester. Each member of the group needs to submit at least 6 updates (roughly 1 per week at the end of the semester). In the form, you will give a brief update about what you (as an individual) have been working on, any technical hurdles or challenges you have run into, and any goals or priorities you have for the next session. These evaluations are another way you can show me that you are making incremental progress on your project.

* Final Project
  * Does your project meet the [Project Requirements](#project-requirements)?
  * Have you completed (or made significant progress on) your deliverables?
    * This is why it is important that you make sure to have a good grasp on what your project is and what you expect to be able to turn in at the end of the semester.
    * The more detail you include in your deliverables, the more I will be able to see that you have met your deliverables.
    * I will also weight the difficulty of your deliverables, based on your survey at the end of the semester, my experience with aspects of your app, and the difficulty of your app overall. I try to ensure you expand your deliverables during the proposal stage; however, I have had students turn in such rudimentary projects at the end that I had to lower the weight of their end product.
  * Quality and usability of your app
    * I will use your app to test the deliverables -- how easy it is to use your app as well as how it looks will play into this aspect of your grade.
    * This is one reason you should make sure to spend some significant time planning your UIs for the proposal -- not only will it give you a clearer picture of what you want your app to look like, but it will also improve this aspect of your app overall. Additionally, you need to focus on how you can use Material Design's guidelines, components, and tools to ensure your app is usable and well designed.
  * Does your app run without crashing?
    * If your app force-closes during execution, I will not be able to give full credit for your app even if it is otherwise amazing.
  * Fails to work:
    * Android: Did you submit a working and up-to-date APK? I will likely be testing your apps on a Google Pixel 5. Student code that fails to install or work correctly on Android 14 will potentially lose points here.
    * Web: Is your website hosted and accessible? If your project is not hosted at the URL you provide for the project, I will follow up; however, failure to resolve hosting within 24 hours will lose points here.
    * Both: If I cannot get the code to run or should your main deliverables not work, you will need to meet with me to demo your project. If you fail to do this, I will have to go off of what was presented. If you failed to present as well, you will not get any of the final project submission credit.
  * Did you complete and submit the Project Submission/Feedback Form?
    * Every individual MUST submit a Project Submission/Feedback Form -- this is NOT a group assignment.
    * Completing this form is an easy way for you to provide me with accurate details about your project and feedback on your partner (if applicable).
    * Most importantly, completing this form will provide me with some insight into what you learned while working on the project. By discussing your challenges and what you learned along the way in trying to get your project working, you can help me assess your work and see your progress, regardless of whether or not you were able to complete all your deliverables.
  * Your Contribution (for groups)
    * If you did not contribute your portion of the overall app development, you will lost credit for your project grade. This will come from team evaluations and analysis of your physical code contributions on GitHub and/or GitLab.
