## Lab Objectives
* Create a Database for our MessageLogger application
* Explore inserting data into the database tables

In our Mod2 Labs, we are going to be building and working with a Database that could be used in our Message Logger application from Mod1.  This new 'feature' will give us the ability to store user's messages to be shown at a later date, and give users a better experience with the application.

** Instructor Note **  This lab includes group, and individual work.  Start with groups of 3/4 students for the outlining section, then let them work individually to create the database tables.  As an 'exit ticket' we will ask everyone for the SQL create statements they used - the key piece to verify is how students used primary and foreign keys.


## Practice
### Outlining Database Tables

In small groups, discuss what data you might want to store from the Message Logger application.  What tables would you need in a database?  What columns would those tables have?  How are those tables related?

You should come up with at least 2 tables.

** Instructor Note ** As groups are working through the brainstorming process, visit each breakout room and offer guidance.  We don't expect students to be masters at determining database structure, so its ok to give a little nudge in the right direction.

### Create the Database and Tables

When your group is happy with the outline of the database, use PgAdmin to create it!

Following the same process we used in class:
1. Create the database.  You can call it `MessageLogger`
2. Create the tables that you outlined in your group.  If you need help with naming, reach out to an instructor!

#### Exit Ticket!
You will not need to create databases from scratch very often on the job; so it's not something that we expect you to become experts at!  We do want to make sure that you have created your database successfully, so when finished, send your instructors your current table configuration by doing the following for each table you created:

In PgAdmin:
1. Select your Database
2. Go to the Query Tool
3. Create a `SELECT * ` query
4. Run the query
5. Send a screenshot (including the output) to your instructors!

![](/Mod2/Images/Week1/ExitTicket.png)

## Preparation

So far, we have created the structures of a database, but we have not created any data.  Work through [this W3Schools' Insert Documentation](https://www.w3schools.com/sql/sql_insert.asp).  Complete as much of the [exercise](https://www.w3schools.com/sql/exercise.asp?filename=exercise_insert1) at the bottom as you can.

When you have completed, or spent 30 minutes working, reflect on the following questions:
* What information do you need to know about a table to insert rows into it?
* How do you insert partial data?
* How can you confirm that you successfully created new rows?





