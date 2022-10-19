# Message Logger

## Learning Goals
- Demonstrate:
    - OOP through development of a Console Application
    - Unit testing of all methods
    - Iterative Flow Control to manage user interaction
    - Excellent communication
    - Professionalism/Teamwork
- Explore:
    - Adding additional features

## Project Description

The aim of this project is to develop a Console Application that will allow a user to log their thoughts as 'Messages' throughout the day.  These thoughts could be musings, simple poems, grocery lists... whatever they want!

While this idea is simple, it is actually the basis for many applications that you may be familiar with.  Apps like Twitter, Instagram, and Reddit are all based on the idea that a user wants to have a record of their thoughts and ideas.  When applications and programs are being developed, the design and creation process often begins with something basic - the Minimum Viable Product (MVP).  The MVP of any application is the smallest usable starting point that will be added to over time, until the final prouct is complete.  Similarly, this project will start small, then build upon previously written code.

This project will give you the opportunity to showcase all of the concepts we have learned this Mod.  There might be skills that we covered all the way back in week 1, so don't forget to go back and review those earlier lessons and labs!

We are going to work throught this project in small chunks, called **iterations**.  Completing each iteration will get you closer to building an application that will allow a user to: 

* Create a user profile
* log a Message
* List all Messages that have been logged.
* Query for Messages

This project will be completed in small groups of 2 or 3 students.  This is a great opportunity for you to practice collaboration and communication.

**Important Project Expectations**  
Completing this project gives you the opportunity to showcase what you have learned during this Module - and that is great!  But, completing the project (getting to the end of iteration 4) is not the only priority.  It is more important to work well as a group!  If a group does not finish the project, but they show good communication with each other and the instructors, that is a <u>success</u>

### Iteration 1 - Group Expectations and Project Setup
As a group, you will produce **one** project; this means that even though your code will live on one person's computer, you all have ownership of what is produced.  In order to set your group up for success, answer the following questions together.  Take notes during your discussion in a slack message with all group members.

**Group Expectations**
1. Who is going to be the 'Keeper of the Code'?  Whose computer is going to be used as the main workspace - this will be the person that we ask to share their screen during project check-ins.

2. How will you manage working collaboratively?  The 'Keeper of the Code' is not a solo worker - every group member should be contributing ideas and code to the project.  This means that there will be times when one group member is dictating to others, or might be sending code snippets through slack.  Remember that everyone shares ownership of the project and that during project checkins, we will ask everyone to discuss the code that is being written.  Plan to discuss your code together throughout the project!

** THIS IS IMPORTANT ** The 'Keeper of the Code' will NOT be coding on this project without the other group members present.

3. How will you manage disagreements? When there are two conflicting ideas, how will you determine a path forward?  On the job, you will experience times when there are multiple ideas presented to solve a common problem; it is important to practice discussing these options and agreeing as a group on the best option (which is often a combination of ideas!).

**Project Setup**
To get started on this project:

1. The 'Keeper of Code' will **fork and clone** this [starter repo]()
    * The starter repo has the project and test project set up already
2. Make sure that the Test Project references the Project

When you have completed the Group Expectations and Project Setup, send a link to your cloned repository, and a copy of the notes you took for the Group Expectations to all your instructors.


### Iteration 2 - Message

For this application, one of the most important parts is the messages themselves.  So, before we get to creating users, we are going to build some functionality around message logging.  

When completed, a user should be able to complete an interaction like this (feel free to add your own flair!):

![Possible Completed version of Iteration1](/Mod1/Images/Project/1MessageLogger.png)

To complete this interaction, your project will need a class `Message` that has two properties:
- string Content - the text of a message.
- DateTime CreatedAt - the time that the message was created.

Remember to test all Properties and Methods as you create them!


### Iteration 3 - User

Logging messages as a single user is great, but wouldn't it be nice to have multiple users logging messages? For this iteration, we will update our application so that multiple users (on the same computer) can log messages.  When completed, users should be able to complete an interaction like this:

![Possible Completed version of Iteration2](/Mod1/Images/Project/2MessageLogger.png)

<!-- To complete this interaction, your project will need to have another class `User` that has three properties:
- string Name
- string UserName
- List<Message> Messages

A `User` will also need a method that will add a message to their `Messages`. -->

To complete this interaction, you will need to add an additional class to your project.  Discuss with your group what this additional class should be, before writing additional code.  You may also need to update your `User` class to implement this part of the project!

Remember to test all Properties and Methods as you create them!

### Iteration 4 - Querying Messages

Now that we have multiple users creating messages, it would be nice to have a mechanism for doing some searches on all the messages.  For this iteration, we can step away from the user interaction and rely on our tests to make sure this query functionality is working.

As a starting point, create a `MessageManager` class that has:
* Properties:
    - List<User> Users
* Methods:
    - List<Message> AllMessages() - a list of all users' messages
    - List<Message> RecentMessages(int num) - a list of the `num` most recent messages.  If `num` is greater than the total number of messages, return all messages.

As a group, come up with another method for this class that you think would be interesting!  It can return any datatype, as long as it represents something about the messages or users of the application.

Remember to test all Properties and Methods as you create them!

## Project Presentation

As a group, you will present your project to the rest of the cohort.  Keep presentations to 10 minutes. Since we are all working on the same application, we would like you to address the following questions/topics in your presentation:

1. What additional classes (other than Message) did you create?  How did you determine what that class should be and do?
1. Imagine an interviewer is asking you about this project, how will you describe the goals, challenges, and outcomes?
1. How did the collaboration with your partner(s) go?  Were you able to stick to your Group Expectations?  What will you do differently next time you are in a group project setting?
1. This project is a VERY basic version of many popular applications.  Apps like Twitter, Instagram, and  Reddit are all based on a similar concept.  How do these types of apps create or erode inclusivity on the web?