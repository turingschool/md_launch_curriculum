# Database Migrations

We've learned the foundations of our ORM, Entity Framework. Today we're going to dive deeper into Entity Framework and what it would be like to work with a database on the job. 

We're going to continue building our plant tracker application, let's all go ahead and open that app.

## Learning Goals
- Explore business decisions that drive database changes
- Practice making database changes to add and remove columns
- Learn how to create seed data

## Warmup

Let's do a chat waterfall to hear the questions everyone had after reading the migrations documentation:
1. What's one question you currently have about migrations?

> With your partner, discuss your answers to the following questions:
> 1. How would you describe the process of evolving your model to add a new column?
> 1. What's one thing you learned about migrations from reading this documentation?

### Business Decisions that Drive DB Changes

Adding a column is one type of database change you may be asked to implement on the job. There are many other types of DB changes you may run into such as modifying a column, deleting a column, or adding a table.

Here is a real-world example from Zoe: My first task after joining the real estate company Orchard was to allow our real estate agents to record if their meetings with clients would take place virtually or in person. Our agents used to have all meetings in person, but because of COVID they started offering virtual appointments and we wanted to track that data in our database. Completing this task required adding a new column to the database.

> With you group: Brainstorm business decisions that would cause a developer to modify the database table. What exactly would need to change in the database?

Here are some sentence starters to help you get started!

**One business decision that would probably lead to a database change was when __________ decided to __________. The developers probably needed to update the database by ______________________.**

### Implementing DB Changes

Let's work together to make a DB Change in our plant app. We now want to keep track of when each plant was last watered so that we can remind our users when to water their plants. Let's call the column `last_watered` and make it type DateTime.

<!-- Instructor note, I recommend scrolling down to this section https://learn.microsoft.com/en-us/ef/core/managing-schemas/migrations/?tabs=dotnet-core-cli#evolving-your-model and having the documentation open next to your visual studio code. Then you can model following along in the documentation and using it to find the commands needed for migrations. You need to switch over to viewing the `Visual Studio` tab instead of `.Net Core CLI`. And you run the commands in the Tools > NuGet Package Manager > Package Manager Console -->

I'm going to pull up the documentation from the preparation to use as a reference. https://learn.microsoft.com/en-us/ef/core/managing-schemas/migrations/?tabs=dotnet-core-cli

>"At a high level, migrations function in the following way:
>When a data model change is introduced, the developer uses EF Core tools to add a corresponding migration describing the updates necessary to keep the database schema in sync. EF Core compares the current model against a snapshot of the old model to determine the differences, and generates migration source files; the files can be tracked in your project's source control like any other source file." - The Migration Documentation

#### Existing Records After Adding New Column

Take a look at what happened to the existing records when we added a new column. There needs to be some value for the column and the default is -infinity. It's a bit of a confusing value, but -infinity means it is earlier than all other timestamps.

<p align='center'>
  <img src='../../Images/Week5/new_column_infinity.png'>
</p>

#### Deleting a Column

With your partner, to try figure out how to delete a column. Feel free to try things, search in the documentation, or use google to try and figure it out!

<details><summary>View this after you've tried on your own!</summary>
The data that existed in that column will be lost, but deleting the column only requires removing the field from the model, making a migration, and updating the database to apply that migration.

While this guide is for a SQLite database (another type of SQL database), the process is the same when using postgreSQL. https://www.learnentityframeworkcore5.com/whats-new-in-ef-core-5/drop-column-from-sqlite-database
</details>

#### Up and Down Sections of Migrations

You may have noticed that each migration file has an `Up` function and a `Down` function.

> With you partner: What do you think these two functions are for? You can look at the screenshot below or the migrations in your plant tracker application. Google may also be helpful here!

<p align='center'>
  <img src='../../Images/Week5/migration_up_and_down.png'>
</p>

<details><summary>View this after you've tried on your own!</summary>

The `up` function is the instructions for how to update the database when running `update-database`. 

The `down` function is the instructions for how to undo the changes made in this migration. It's uncommon to need to do this, but the option is available to undo a migration and revert to how the database looked before.

</details>

❓Do we want to store our migration files in Github?

#### Code Organization

As our projects grow, we will get to a point where we want more organization in our project file structure. The convention when working with entity framework is to have a folder called `Models` and a folder called `Data`. 

Let's add those folders together and move our files into the appropriate folders. You will notice that Visual Studio suggests modifying the namespace, let's accept this suggestion. So the namespace for our models will be `PlantApp.Models` instead of just `PlantApp`.

<p align='center'>
  <img src='../../Images/Week5/folder_structure.png'>
</p>

### Seed Data

Database seeding is populating a database with an initial set of data. Oftentimes you want to start your database with some initial data so that as you're testing edit or delete functionality you have a set of data to experiment with. It's also common to start your users table with information for all of the company's employees so they don't need to be added manually.

There are many ways to create seed data. The approach we're going to use is building a DataSeeder Class similar to the following. Notice the `PlantApp.Data` namespace because this class belongs in the `Data` folder.

<!-- Instructor note, there may be a nicer way to get these dates working, but this works and so I'm going to leave it for now. -->
```C#
namespace PlantApp.Data
{
    public class DataSeeder
    {
        public static void SeedPlantsAndRooms(PlantTrackerContext context)
        {
            if (!context.Rooms.Any())
            {
                var fern_plant = new Plant {Type = "Fern", PurchaseDate = DateTime.Parse("1975-06-15T13:45:30-07:00").ToUniversalTime()};
                var rubber_plant = new Plant {Type = "Rubber", PurchaseDate = DateTime.Parse("2021-01-15T11:45:02-07:00").ToUniversalTime()};
                var jade_plant = new Plant {Type = "Jade", PurchaseDate = DateTime.Parse("2021-01-15T11:45:02-07:00").ToUniversalTime()};

                var rooms = new List<Room>
                {
                 new Room
                {
                    Name = "Office",
                    HasSunlight = true,
                    Plants = new List<Plant> {fern_plant, rubber_plant}
                },
                new Room
                {
                    Name = "Kitchen",
                    HasSunlight = true,
                    Plants = new List<Plant> {jade_plant}
                }
            };
                context.Rooms.AddRange(rooms);
                context.SaveChanges();
            }
        }
    }
}
```

When we want to run this file and seed some plants and rooms into our database we can add (or uncomment) the line `DataSeeder.SeedPlantsAndRooms(context);` Go ahead and add this line right after the line where you create your plant tracker context.

```C#
using (var context = new PlantTrackerContext())
{
    DataSeeder.SeedPlantsAndRooms(context);
}
```

### Checks for Understanding
1. How would you describe the process of removing a column from your database using Entity Framework?
1. What is the purpose of seed data?
1. True or False: After adding a new column to my database using Entity Framework, existing records will have no value for that column. Why?