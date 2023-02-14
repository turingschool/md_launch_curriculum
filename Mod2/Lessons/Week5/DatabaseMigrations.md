# Database Migrations

We've learned the foundations of our ORM, Entity Framework. Today we're going to dive deeper into Entity Framework and what it would be like to work with a database on the job.

## Learning Goals
- Explore business decisions that drive database changes
- Practice making simple database changes
- Learn how to create seed data

<!-- Instructor note: An additional goal I have outside of these is for students to start feeling the impact of their decisions as developers. To realize that some things like renaming, are much more difficult to do later than when building the db. -->

## Warmup

Let's do a chat waterfall to hear the questions everyone had after reading the migrations documentation:
1. What's one question you currently have about migrations?

> With your partner, discuss your answers to the following questions:
> 1. How would you describe the process of evolving your model to add a new column?
> 1. What's one thing you learned about migrations from reading this documentation?

### Business Decisions that Drive DB Changes

Adding a column is one type of database change you may be asked to implement on the job. There are many other types of DB changes you may run into such as modifying a column, deleting a column, or adding a table.

Here is a real-world example from Zoe: My first task after joining the real estate company Orchard was to allow our real estate agents to record if their meeting would take place virtually or in person. Our agents used to have all meetings in person, but because of COVID they started offering virtual appointments and we wanted to track that data in our database. In this situation, I needed to add a new column to the database.

> With you group: Brainstorm business decisions that would cause a developer to modify the database table. What exactly would need to change in the database?

Here are some sentence starters to help you get started!

**One business decision that probably to a database change was when __________ decided to __________. The developers probably needed to update the database by ______________________.**

### Our First DB Changes

Let's work together to make a DB Change in our plant app. We now want to keep track of when each plant was last watered so that we can remind our users when to water their plants. Let's call the column `last_watered` and make it of type DateTime.

I'm going to pull up the documentation from the preparation to use as a reference. https://learn.microsoft.com/en-us/ef/core/managing-schemas/migrations/?tabs=dotnet-core-cli


>"At a high level, migrations function in the following way:
>When a data model change is introduced, the developer uses EF Core tools to add a corresponding migration describing the updates necessary to keep the database schema in sync. EF Core compares the current model against a snapshot of the old model to determine the differences, and generates migration source files; the files can be tracked in your project's source control like any other source file." - The Migration Documentation

<!-- WHat's up with the existing data with a new column? -->
-infinity vs null, props should say tiny thing about optionally null.

#### Deleting a Column

With your partner, to try figure out how to delete a column. Feel free to try things, search in the documentation, or use google to try and figure it out!

<!-- Drop down here -->
The data that existed in that column will be lost, but deleting the column only requires removing the field from the model, making a migration, and updating the database to apply that migration.

While this guide is for a SQLite database (another type of SQL database), the process is the same when using postgreSQL. https://www.learnentityframeworkcore5.com/whats-new-in-ef-core-5/drop-column-from-sqlite-database

#### Up and Down Sections of Migrations

You may have noticed that each migration file has an `Up` function and a `Down` function.

> With you partner: What do you think these two functions are for? You can look at the screenshot below or the migrations in your plant tracker application. Google may also be helpful here!

<p align='center'>
  <img src='../../Images/Week5/migration_up_and_down.png'>
</p>

❓Do we want to store our migration files in github?

### Dangerous Database Changes

Now let's imagine that we decide after adding the column `type` we realize that we actually want the column name to be `common_name`.

Let's try renaming the field in our `Plant` model and creating a migration.

Oh no!! There is something very dangerous that might happen if we run this migration. 

> With you partner, try to figure out what's dangerous about this migration.

<!-- TODO, why isn't it making us dangerous migrations??? -->

<!-- Dropdown -->

If we run this migration, we will drop the column `last_watered` and all the data in that column would be deleted. Then we would create a new column called `last_watered_date` with no data in it. 

As the documentation says "EF Core is generally unable to know when the intention is to drop a column and create a new one (two separate changes), and when a column should be renamed."

Let's see the suggested approach to renaming a column and not losing data. https://learn.microsoft.com/en-us/ef/core/managing-schemas/migrations/managing?tabs=vs#column-renames

Replace

<!-- Maybe instead I try to remove a column and add a new column at the same time. And EF tries to rename which is incorrect? -->

<!-- Then to fix we break into two parts -->


# Takeaways About Database Migrations



### Seed Data

Microsoft docs on database seeding: https://learn.microsoft.com/en-us/training/modules/persist-data-ef-core/4-interacting-data

<!-- Introduce as a way of starting with something so that you can experiment with delete and update and such. -->

Or maybe you want to start your users table with information for all of the company's employees so they don't need to be added manually.

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


<!-- Instructor Note

Adding this to the context is one option

protected override void OnModelCreating(ModelBuilder builder)
        {
            base.OnModelCreating(builder);

            builder.Entity<Plant>().HasData(new List<Plant> {
                 new Plant { Id = 1, Type = "Fern", PurchaseDate = DateTime.Parse("1975-06-15T13:45:30-07:00").ToUniversalTime(), RoomId = 1 },
                 new Plant { Id = 2, Type = "Rubber", PurchaseDate = DateTime.Parse("2021-01-15T11:45:02-07:00").ToUniversalTime(), RoomId = 1},
                 new Plant { Id = 3, Type = "Jade", PurchaseDate = DateTime.Parse("2021-01-15T11:45:02-07:00").ToUniversalTime(), RoomId = 2 },
            });

            builder.Entity<Room>().HasData(new List<Room> {
                 new Room
                {
                    Id = 1,
                    Name = "Office",
                    HasSunlight = true,
                },
                new Room
                {
                    Id = 2,
                    Name = "Kitchen",
                    HasSunlight = true
                },
            });

        } 
-->


#### Good Code Organization

Something about working on larger teams, may have many many model. Possibly mention multiple contexts?

<!-- Move into models and data folders -->



