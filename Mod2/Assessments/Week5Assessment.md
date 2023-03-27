# Week 5 Assessment

1. In at least two sentences, how would you define what seed data is and why it's useful? (1 point possible)

1. Deleting a database column is a dangerous action, what might happen if you delete a column you didn't mean to? (1 point possible)

1. Write out at least 3 steps to describe the process of adding a new column to your database using entity framework. (1 point possible)

1. When I run `Update-Database`, which function in the migration is used `Up` or `Down`? (1 point possible)

1. When was Entity Framework Core version 7.0 released? As always, feel free to use google as a resource in answering this question. (1 point possible)

1. True or False: When using Entity Framework to create database tables for a many-to-many relationship, you must create a class to represent the join table? Explain your answer. (1 point possible)

1. Replace the ____________s with the code required to create the models required for the following entity relationship diagram. Don't worry about `Routeid` vs `RoutesId` and `Stopid` vs `StopsId`, either is fine. Also, no need to include the `terminus` column. (2 points possible)

![Route and Stop Many-to-Many ERD](/Mod2/Images/Week5/route_stop_ERD.png)

```C#
namespace BusTransitApp
    {
        public class Route
        {
            _____________________
        }
    }

namespace BusTransitApp
    {
        public class Stop
        {
            _______________________
        }
    }
```
![citation](https://www.visual-paradigm.com/tutorials/how-to-model-relational-database-with-erd.jsp)

1. Replace the _______________s with the code required to seed at least one `Route` and at least one `Stop` that are part of a many-to-many relationship. (2 points possible)

```C#
namespace BusTransitApp.Data
{
    public class DataSeeder
    {
        public static void SeedRoutesAndStops(BusTransitContext context)
        {
            if (______________)
            {
                ______________________________
            }
        }
    }
}
```