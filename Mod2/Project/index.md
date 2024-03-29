# Message Logger

## Learning Goals
- Demonstrate:
    * Version Control, including branches and pull requests.
    * Understanding of database table relationships.
    * Database CRUD with an ORM.

- Explore:
    * Dive into a new (not written by you) code base!
    * Using TDD to add additional features! (For any new feature that you create, try writing the tests first, and then creating the code that makes those tests pass!)


## Project Description
the aim of this project is to build on the Message Logger we created in Mod1.  Now, a user should be able exit the application, and return later to review past mesages.  This will require us to add a database to our Message Logger projects.

This project will give you the opportunity to showcase all of the concepts we have learned this Mod.  There might be skills that we covered all the way back in week 1, so don't forget to go back and review those earlier lessons and labs!

**Project Setup**
To get started on this project:

1. **fork and clone** this [starter repo](https://github.com/turingschool-examples/LaunchMod2Project)
    * The starter repo has code that will be similar to your Mod1 Project.
2. Run all tests to make sure the project is working (all tests should be passing).

When you have completed the Project Setup, send a link to your cloned repository to all your instructors.


### Iteration 1 - Creating and Conecting a Database
In order to save messages and users so that they persist when a user exits and restarts the program, we will need to create a database for our Message Logger application.

You should create a branch for your work on this iteration.

* Review the classes that exist in the starter program - determine how these classes will be reflected in the tables of a database.  Be sure to think about what relationships may exist.
* Use the Npgsql.EntityFrameworkCore.PostgreSQL Nuget package to create a database context in your application.
* Update your Message and User classes to be used as a basis for your database tables.

When you are finished with iteration 1, create a pull request and schedule time with a cohort-mate for some code review.  During the code review, make comments on the pull request indicanting changes that you will make based on your review!

### Iteration 2 - User and Message CRUD

Now that the database is created, we need to start saving our users and messages!  You will need to review the `program.cs` file and identify where changes need to be made in order to maintain the user experience **and** save users and messages into the database.

You should create a branch for your work on this iteration.

* Annotate your `program.cs` file with notes on how you will update the code to save records into the database.  Commit these annotations and push up your branch.  DM your instructors a link to your GitHub repo - we will reach out with feedback on your plans!
* Update the program so that users and messages are being saved to the database.

When you are finished with iteration 2, create a pull request and schedule time with a cohort-mate or your instructor for some code review.

### Iteration 3 - Using LINQ to query the database

Since we are now saving more than one session's worth of messages, we should be able to write some fun LINQ methods to analyze our data.

In addition to the existing statistics about how many messages each user has written, update the program to output the following data at the end of each session:

* users ordered by number of messages created (most to least)
* most commonly used word for messages (by user and overall)
* the hour with the most messages
* Brainstorm your own interesting statistic(s)!

When you are finished with iteration 3, create a pull request and schedule time with a cohort-mate or your instructor for some code review.

## Version Control Expectations
In order to demonstrate what you have learned about version control, you will be using commits, branches and pull requests during this project.

You must gather feedback from cohort-mates and/or instructors prior to merging any code into your `main` branch.

You must provide feedback on at least one other student's pull request!

## Project Presentation

You will present your project to other members of the cohort.  Keep presentations to 10 minutes. Since we are all working on the same application, we would like you to address the following questions/topics in your presentation:
1. What was your process for building migrations?
1. What changes did you make based on peer or instructor feedback?
1. How did you ensure that messages and users were getting saved into the database appropriately?
