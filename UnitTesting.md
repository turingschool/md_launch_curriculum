# Intro to Testing
### Learning Goals
* Understand why we use tests.
* Define the stages of a test.
* Implement a variety of Unit Tests.
### WarmUp
* Up to now, how have you known if your code was functioning?
* Imagine you are a developer working at Google; what might be some drawbacks to your current approach?
-----------------
**Instructor Led Discussion**
Gather answers from students to the warmup questions. Based on responses, lead a discussion on the benefits of _automated testing_.  Make sure to cover at least the following:
1. Faster than manual testing
1. More reliable than manual testing
1. Gives us immediate feedback when our code isn't working
1. Allows for confidence when making changes to our code
-----------------
## Testing with NUnit
**NUnit** is a _framework_ that we can use to test our code.  A _framework_ is some pre-built functionality that we can include in our projects to help with specific tasks (like testing!).
The standard file structure for testing our solutions is to have one test project for each solution project.  Within each test project, we will have one test file for each class in that project.  Take a look at a sample file structure below:
```
Solution
|--ProjectName
   |--SomeClass.cs
|--ProjectName.UnitTests
   |--SomeClassTests.cs
```
For this exploration, we will be using a starter solution: [Intro To Testing Starter Repo](https://github.com/memcmahon/IntroToTesting).
Follow these steps to clone the repository containing the starter code:
1.
2.
3.
4.
### Creating the Test Project
The first thing we need to do is create our NUnit Test Project.  In the Solution Explorer, right-click on the solution name `Solution 'IntroToTesting'` and select `Add > New Project`.  Search for and create a 'NUnitTestProject'.  Name this project 'IntroToTesting.UnitTests'.  We will discuss unit tests a bit later; for now, we just want to make sure you are using the standard naming convention of 'ProjectName.UnitTests'.
```markdown
**Breakout Exploration: On Creating a New NUnit Test Project**
When you create a new project using the 'New NUnit Test Project' generator, you are actually creating a standard Console project, with a few :sparkles:Enhancements:sparkles:.
Compare the Solution Explorer of this NUnit Test Project with the IntroToTesting project - what differences do you see?
Discuss with your group: what differences are there, and how might you create this NUnit Test Project from a plain Console project? Be ready to share out!
```
-----------------
**Instructor Led Discussion**
Ask groups to share what they discussed.  Use this discussion to talk about NuGet package manager, and how you can add packages after project creation.
-----------------
Once the test project is created, we will want to rename the test class, and test class file. Rename the file to `UserTests.cs`, and within that file, rename the class to `UserTests`.
Ensure that your test project is created correctly by Selecting `Test > Run All Tests`.  If everything is working, you will see the _Test Explorer_ pop up in a new window, or alongside your Solution Explorer.
![](./IntroToTestingTestSetupPassing.png)
### Writing Our First Test
Before we write our first test, we need to determine what we should test.  Generally, you want to have a test for all methods that you write. For now, we will pretend that you have written the User class.
```markdown
**What Should We Test**
Take a look at the User.cs file. Discuss with your group: How many methods are there? How many tests should we write?
```
-----------------
**Instructor Led Discussion**
Discuss what tests should be written - we want to write tests for all of the methods that we create.  We will have tests for:
* Our custom Constructor
* Properties
* Tweet()
* MostRecentTweet()
-----------------
We will come back to the Setup() method a bit later, but for now, let's focus on Test1.  We will want to change the name to something that represents the method we are testing, the circumstance we are testing, and the expected outcome.
```cs
[Test]
public void Constructor_WhenInstantiated_SetsStartingPropertyValues()
{
  var user = new User("Archie");
  Assert.That(user.Name, Is.EqualTo("Archie"));
  Assert.That(user.Tweets, Is.EqualTo(new List<string>()));
}
```
One of the first things you might notice as you create this test, is that we are getting some negative feedback from Visual Studio regarding the `User` object.  It seems as though it doesn't exist, but we know that it does!  Take a moment to think about why our Test class might not know about `User`.
In a solution, we might have one or more projects; within each project we might have one or more classes.  You can think of each project as a box, and boxes can not inherently 'see' into each other.  We need to tell a project about other projects in order to use their classes.  In .NET terms, we need to create a _reference_ so that our Test Project will know about our Implementation Project.
Add a _reference_ by right-clicking on the Test Project in the Solution Explorer.  Select 'Add > Project Reference', select 'IntroToTesting', and 'OK'.
(You may also need to add `using System.Collections.Generic;` to use the List object)
Run these Tests by clicking the play icon in the TestExplorer.
-----------------
**Instructor Led Discussion**
What are we testing for and why?
Where did Assert(), That(), Is, and EqualTo() come from?
Could be a good place to pull up the [docs](https://docs.nunit.org/articles/nunit/writing-tests/constraints/Constraints.html)
-----------------
Now that we have one test created, we will create tests for our remaining methods. Individually or, with a group, spend 15 minutes writing the additional tests for the User class.  When you have finished, you can compare your code to the [completedUserTests](https://github.com/memcmahon/IntroToTesting/tree/completedUserTests) branch of the starter repo.