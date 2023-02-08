# Lesson List 

[Syllabus](https://docs.google.com/document/d/1mG_CBgZsy_mTbdaKlpmaLlnNlNQlSNGHFQ1hJKsR_qY/edit)

## Mod 1
### Week 1
* 🎒[Intro to Programming (How Computers Work)](/Mod1/Lessons/Week1/introToProgramming.md)
* 💡⬆️ [Intro to Labs](/Mod1/Labs/Week1/IntroToLabs.md)
* 🎒[Datatypes & Variables](/Mod1/Lessons/Week1/datatypesAndVariables.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week1/DatatypesAndVariables.md)
* 🎒[Conditional Logic](/Mod1/Lessons/Week1/ConditionalLogic.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week1/ConditionalLogic.md)
* 🧪[Weekly Assessment](/Mod1/Assessments/week1.md)
* 🎒[Topic Review](/Mod1/Lessons/Week1/WeekInReview.md)

### Week 2
* 🎒[Looping](/Mod1/Lessons/Week2/Looping.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week2/Looping.md)
* 🎒[Collections](/Mod1/Lessons/Week2/Collections.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week2/Collections.md)
* 🎒[Methods](/Mod1/Lessons/Week2/Methods.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week2/Methods.md)
* 🧪[Weekly Assessment](/Mod1/Assessments/week2.md)
* 🎒[Topic Review](Mod1/Lessons/Week2/WeekInReview.md)

### Week 3
* 🎒[Classes](/Mod1/Lessons/Week3/Classes.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week3/Classes.md)
* 🎒[OOP](/Mod1/Lessons/Week3/OOP.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week3/OOP.md)
* 🎒[Class/Object Interaction](/Mod1/Lessons/Week3/ClassInteraction.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week3/ClassInteraction.md)
* 🧪[Weekly Assessment](/Mod1/Assessments/Week3.md)
* 🎒[Topic Review](/Mod1/Lessons/Week3/WeekInReview.md)

### Week 4
* 🎒[Intro to IDEs](/Mod1/Lessons/Week4/IntroToIDE.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week4/IntroToIDE.md)
* 🎒[Debugging](/Mod1/Lessons/Week4/Debugging.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week4/Debugging.md)
* 🎒[Unit Tests I](/Mod1/Lessons/Week4/UnitTestingI.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week4/UnitTestingI.md)
* 🧪[Weekly Assessment](/Mod1/Assessments/Week4.md)
* 🎒[Topic Review](/Mod1/Lessons/Week4/WeekInReview.md)

### Week 5
* 🎒[Refactoring](/Mod1/Lessons/Week5/Refactoring.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week5/Refactoring.md)
* 🎒[Unit Tests II](/Mod1/Lessons/Week5/UnitTestingII.md)
* 💡⬆️ [Lab/Exercise](/Mod1/Labs/Week5/UnitTestingII.md)
* 🎒[Scope and Access Modifiers](/Mod1/Lessons/Week5/scope.md)
* 🧪Module Assessment
* 🎒Module Review
### [Project](/Mod1/Project/Index.md)


## Mod 2
Lab Project Goals:  
Create a Database for a Library Application  
Use EF to create a connection to the DB  
Use EF to create and manipulate DB records  
Use TDD to create classes  
Test DB connections and records  
### Week 1
* 🎒[Version Control and Solo Git/GitHub](/Mod2/Lessons/Week1/VersionControlAndSoloGit.md)
    - Describe the benefits of Version Control
    - Create a repository
    - Use branch workflow
* 💡[Lab/Exercise](/Mod2/Labs/Week1/VersionControl.md)
* ➡️[Preparation: Intro to Databases](/Mod2/Preparation/IntroToDatabases.md)
* 🎒[Lesson: Intro to Databases](/Mod2/Lessons/Week1/IntroToDatabases.md)
    - Describe a database its uses in various applications
    - Define relational data and data normalization
    - Create a Database with Postgresql and PgAdmin  
* 💡[Lab/Exercise](/Mod2/Labs/Week1/IntroToDatabases.md)
        * Lab Project: Create Database for Library (not connected)
* ➡️[Preparation: SQL CRUD](/Mod2/Preparation/SQLCRUD.md)
* 🎒[Lesson: SQL CRUD](/Mod2/Lessons/Week1/SQLCRUD.md)
    - Use SQL to SELECT, INSERT, REMOVE and UPDATE records
    - Use basic WHERE clause to filter records  
        * Lab Project: Use SQL to insert and query library records in the DB
### Week 2
* ➡️[Preparation: TDD](/Mod2/Preparation/TDD.md)
* Lesson: Test Driven Development
    - Describe the benefits of TDD
    - Practice a TDD workflow
* Lab/Exercise
    * Lab Project: use TDD to create classes for library records
* Lesson: Git for Pairs
    - Outline a workflow for collaborating on a single repository
    - Identify and resolve merge conflicts
### Week 3
* ➡️[Preparation: Data Relationships](/Mod2/Preparation/Week3/DataRelationships.md)
* 🎒[Lesson: Data Relationships](/Mod2/Lessons/Week3/DataRelationships.md) (One to One, One to Many, Many to Many)
    * Solidify understanding of Primary Keys and Foreign Keys
    * Visualize One-to-One, One-to-Many, and Many-to-Many relationships
    * Implement a Many-to-Many relationship using a join table
    * Practice describing different relationships 
* 💡 [Lab/Exercise](/Mod2/Labs/Week3/DataRelationships.md)
    * Lab Project: Add an Author Table to the Library Db (many-to-many)
* Lesson: SQL JOINS
    - Use JOIN to query related records
    - Use WHERE to filter joined queries  
  Lab Project: User SQL to select related records
* Lesson: SQL Aggregates
    - Develop a visualization for grouping and aggregating data
    - Use GROUP BY, COUNT, SUM, and AVERAGE
    - Research additional aggregate functions  
  Lab Project: Use SQL to query some Library Statistics

Other ORM Learning Goals that need to go somewhere
- Work with one-to-many relationship using an ORM
- Work with many-to-many relationship using an ORM
- Write Asynchronous code when interacting with DB? Asynchronous code was introduced in EF 6. Not sure if it's crucial or a bonus...The tutorials I'm seeing start with sync, then have a "How to use async" section. https://www.entityframeworktutorial.net/crud-operation-in-connected-scenario-entity-framework.aspx
- Should retrieving the data go in the intro to ORM lesson? Feels like that helps build the full picture, but don't want to much in one day.

### Week 4
* Lesson: Intro to LINQ
    - Use LINQ syntax with collections not related to a Database
    - For example syntax such as .OrderBy(b => b.BlogId) 
  Lab Project: ????
* Lesson: Intro to ORM (Migrations & Schema)
    - Define ORM and Framework
    - Describe the benefits of working with Objects
    - Set up Entity Framework in a Console Application
    - Create a one-to-many relationship using an ORM
  Lab Project: Create some of the tables from our library DB, should we have a separate DB to not write over the existing DB?
* Lesson: CRUD with ORM
    - Deepen understanding of test setup by creating a test database
    - Use TDD to implement CRUD functionality in a console application  
    - Use EF and LINQ to query database records
  Lab Project: Use TDD and EF to create library records

### Week 5
* Lesson: Migrations and changing Db tables
    - Explore business decisions that drive DB changes
    - Practice making simple db changes
    - Describe the dangers of database changes  
  Lab Project: use a migration to add a table to the database
* Lesson: Many-to-Many using an ORM
    -   Reinforce how to structure many-to-many database relationships
    -   Implement a many-to-many relationship using EF
  Lab Project: Create whatever the one to many relationship was from the library DB using EF

## Mod 3
### Week 1
* HTTP Request/Response Cycle
    - Develop a diagram of how the web works
    - Identify the key responsiblities of Backend and Frontend development
* HTML
    - Define HTML and its purpose
    - Identify and use attributes for appropriate elements
    - Understand the importance of semantic HTML
* CSS
    - Define CSS and its purpose
    - Practice Debugging with Chrome Dev Tools
    - Demonstrate an understanding of the box model
### Week 2
* Interfaces (we need to learn this so that students can understand some of the setup for a .NET MVC project)
    - Identify objects that have shared structure/behavior
    - Implement an interface structure
    - Practice identifying interfaces in existing code
* Intro to MVC
    - Identify the elements of the MVC design pattern
    - Describe the single responsibility of each of the Model, View, and Controller
    - Describe how data is passed through the MVC pattern
* Feature Testing
    - Understand why feature testing is important
    - Make connections between a browser and an in-project client
    - Practice testing basic user interactions with xUnit and Selenium.
### Week 3
* REST
    - Define REST
    - Identify RESTful and non-RESTful routes
    - Explore the pros and cons of REST
* Creating and Reading Single Resources
    - Diagram the Request/Response cycle with a form submission
    - Use a form to create single resources
    - Create Index and Show pages for a single resource
* Creating and Reading Related Resources
    - Use a form to create a one-to-many relationship
    - Create Show Page for a Resource with related data
### Week 4
* Dynamic Routing
    - Understand how data is dynamically passed using Routes
    - Use dynamic routing to filter data on a Show and Index page
* Updating Resources
    - Use a form to update single resources
    - Use a form to create a one-to-many relationship
* Destroying Resources
    - Describe some common pitfalls when destroying resources
    - Practice destruction of single and related resources

## Mod 4
### Week 1
* Intro to APIs
    - Understand how an API works at a conceptual level
    - Expand our understanding of what a 'client' could be
    - Create an in-app client to manipulate HTTP responses
* JavaScript (Likely 2 lessons)
    - Understand why it is important to be familiar with JavaScript
    - Available DataTypes
    - How to Build a Function
    - Accessing DOM elements and events
### Week 2
* Building an API
    - Review HTTP Request/Response Structure 
    - Use TDD to Implement CRUD endpoints through an API
    - Define and identify valid JSON data structures
* Testing Strategies when Consuming an API
    - Understand the necessity of faking API requests in tests
    - Implment mock/vcr to maintain test coverage
### Week 3
* Maintaining State
    - Identify the limitations of Stateless HTTP
    - Introduce the concept of Sessions & Cookies
    - Implement a simple Cookie
* Authentication
    - Explain the use of Authentication and its importance
    - Implement Authentication
* Authorization
    - Identify the difference between Authentication and Authorization
    - Implement User Roles with Authorization
### Week 4
* ?Advanced Data Manipulations? On the scope and sqnce doc, the learning goal includes Advanced SQL
    - https://backend.turing.edu/module3/lessons/advanced_activerecord


## Mod 5
### Week1
* Customizing JSON Responses
    - Define and implement a Serializer
    - Expand our understanding of MVC responsibilities
    - Describe how a Serializer can support OOP Principles
* Data Validations
    - Identify the differences between Error Handling, and program crashing
    - Throw situation-specific errors
    - Implement try/catch blocks 
* SOLID (Refactoring Patterns)
    - Reinforce our understanding of SRP
    - Introduce OLID Principles
### Week2
* Working with 3rd party APIs
    - Implement Secure Environment Variables
* Writing Good Documentation
    - Understand the reasons for good documentation
    - Identify what to include in your documentation
* Interview Lifecycle
    - Identify the varying steps of an interview
    - Common Pitfalls in Interviewing
    - The graceful exit
### Week3
* Caching
    - Define Caching and why it is useful
    - Implement caching
* Background Workers
    - Identify opportunities to use background workers
    - Implement a background worker
* BigO and Process Optimization
    - Understand the impact of poor optimization
    - Introduce the problem of over-iteration and optimization
    - Gain a familiarity with Big0 terminology (I've heard of this thing, but may not be an expert)


## Mod 6
