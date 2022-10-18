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

This project will give you the opportunity to showcase all of the concepts we have learned this Mod.  There might be skills that we covered all the way back in week 1, so don't forget to go back and review those earlier lessons and labs!

We are going to work throught this project in small chunks, called **iterations**.  Completing each iteration will get you closer to building an application that will allow a user to: 

* start up the program
* Create a user profile
* log a Message
* List all Messages that have been logged.
* Filter for messages by time

This project will be completed in small groups of 2 or 3 students.  This is a great opportunity for you to practice collaboration and communication.

### Iteration 1 - Group Expectations and Project Setup
As a group, you will produce **one** project; this means that even though your code will live on one person's computer, you all have ownership of what is produced.  In order to set your group up for success, answer the following questions together.  Keep a record of your discussion by taking notes in a shared document (like google docs) or in a slack message with all project partners.

**Group Expectations**
1. Who is going to be the 'Keeper of the Code'?  Whose computer is going to be used as the main workspace - this will be the person that we ask to share their screen during project check-ins.

2. How will you manage working collaboratively?  The 'Keeper of the Code' is not a solo worker - every group member should be contributing ideas and code to the project.  This means that there will be times when one group member is dictating to others, or might be sending code snippets through slack.  Remember that everyone shares ownership of the project and that during project checkins, we will ask everyone to discuss the code that is being written.  Plan to discuss your code together throughout the project!

3. How will you manage disagreements? When there are two conflicting ideas, how will you determine a path forward?  On the job, you will experience times when there are multiple ideas presented to solve a common problem; it is important to practice discussing these options and agreeing as a group on the best option (which is often a combination of ideas!).

**Project Setup**
To get started on this project:

1. The 'Keeper of Code' will **fork and clone** this [starter repo]()
    * The starter repo has the project and test project set up already
2. Make sure that the Test Project references the Project

When you have completed the Group Expectations and Project Setup, send a link to your cloned repository to all the instructors.


### Iteration 2 - Message

When new software is being developed, the first step is to create what is referred to as the **MVP**.  In this case, MVP stands for **Minimum Viable Product** and it refers to the smallest possible version of the final application that would be useful.  The MVP will look different for different applications and projects, but will always be something less than the final product.  For our Message Logger, we will complete our MVP by implementing a way for users to log messages through the console.  

When completed, a user should be able to complete an interaction like this (feel free to add your own flair!):

![Possible Completed version of Iteration1](/Mod1/Images/Project/1MessageLogger.png)

To complete this interaction, your project will need a class `Message` that has two properties:
- string Content - the text of a message.
- DateTime CreatedAt - the time that the message was created.


### Iteration 3 - User

Logging messages as a single user is great, but wouldn't it be nice to have multiple users logging messages? For this iteration, we will update our application so that multiple users (on the same computer) can log messages.  When completed, users should be able to complete an interaction like this:

![Possible Completed version of Iteration2](/Mod1/Images/Project/2MessageLogger.png)

To complete this interaction, your project will need to have another class `User` that has three properties:
- string Name
- string UserName
- List<Message> Messages

A `User` will also need a method that will add a message to their `Messages`.


### Iteration 4 - Querying Messages

Now that we have multiple users creating messages, it would be nice to have a mechanism for doing some searches on all the messages.  For this iteration, we can step away from the user interaction and rely on our tests to make sure this query functionality is working.

As a starting point, create a `MessageManager` class that has:
* Properties:
    - List<User> Users
* Methods:
    - List<Message> AllMessages() - a list of all users' messages
    - List<Message> RecentMessages(int num) - a list of the `num` most recent messages.  If `num` is greater than the total number of messages, return all messages.

As a group, come up with another method for this class that you think would be interesting!  It can return any datatype, as long as it represents something about the messages or users of the application.

## Project Presentation

As a group, you will present your project to the rest of the cohort.  Since we are all working on the same application, we would like you to address the following questions/topics in your presentation:

1. Imagine an interviewer is asking you about this project, how will you describe the goals, challenges, and outcomes?
1. How did the collaboration with your partner(s) go?  Were you able to stick to your Group Expectations?  What will you do differently next time you are in a group project setting?
1. This project is a VERY basic version of many popular applications.  Apps like Twitter, Instagram, and  Reddit are all based on a similar concept.  How do these types of apps create or erode inclusivity on the web?