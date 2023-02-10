# Database Migrations

We've learned the foundations of our ORM, Entity Framework. Today we're going to dive deeper into Entity Framework and what it would be like to use Entity framework on the job. 

## Learning Goals
- Explore business decisions that drive database changes
- Practice making simple database changes
- Discover what situations lead to complicated database changes and the dangers of these complicated changes
- Learn how to create seed data

## Warmup

<!-- Go over the questions from the preparation -->

1. How would you describe the process of evolving your model to add a new column?
1. What's one thing you learned about migrations from reading this documentation?
1. What's one question you currently have about migrations?

### Buisness Decisions that Drive DB Changes

Adding a column id one sort of database change you may be asked to implement on the job. There are many other types of DB changes you may run into such as modifying a column, deleting a column, adding a table, and more.

> With you group: Brainstorm buisness decisions that would cause a developer to modify the database table. What exactly would need to change in the database?


<!-- Maybe some examples in a dropdown? -->

<!-- Possible question for instructor to ask -->
<!-- Open question, if you rename a field in the UI does the database field need to change? -->

### Making a Simple DB Change
<!-- either adding a new column, or a new database. Possibly removing a column, borderline easy/hard? -->
https://learn.microsoft.com/en-us/ef/core/managing-schemas/migrations/?tabs=dotnet-core-cli

At a high level, migrations function in the following way:

When a data model change is introduced, the developer uses EF Core tools to add a corresponding migration describing the updates necessary to keep the database schema in sync. EF Core compares the current model against a snapshot of the old model to determine the differences, and generates migration source files; the files can be tracked in your project's source control like any other source file.

Draw attention to the up and down in a migration

❓Do we want to commit our migration files to github?

❓True or False, we should remove a migration after it has been applied to the database?

### Making a Complicated DB Change
https://learn.microsoft.com/en-us/ef/core/managing-schemas/migrations/managing?tabs=vs#column-renames

Rename a model property
If we rename the model property, what the EF does is, drop a column and create a new one. This will lead to data loss. If we change the FirstName property to FullName EF creates the migration as follows.

Oh no, this migration doesn't look right? How to fix, maybe good opportunity for studnets to google for answer. What did you google?



Easy or complicated?
<!-- Maybe list three buisness cases and students have to decide if this is an easy change or a complicated change. Trying to get at the idea that modifying columns or renaming things is complicated. -->


### Seed Data

Microsoft docs on database seeding: https://learn.microsoft.com/en-us/training/modules/persist-data-ef-core/4-interacting-data

<!-- Introduce as a way of starting with something so that you can experiment with delete and update and such. -->


#### Good Code Organization

Something about working on larger teams, may have many many model. Possibly mention multiple contexts?

<!-- Move into models and data folders -->



