# Week 4 Assessment

1. In your own words, how would you define an ORM?

1. Given the two classes for bike and owner, update the classes to include a one-to-many relationship where each bike has one owner, and each owner can have many bikes.

    ```C#
    namespace BikeApp
    {
        public class Bike
        {
            public int Id { get; set; }
            public string Type { get; set; }
            public DateTime PurchaseDate { get; set; }
        }
    }

    namespace BikeApp
    {
        public class Owner
        {
            public int Id { get; set; }
            public string Name { get; set; }
            public int Zipcode { get; set; }
        }
    }
    ```

1. When adding a new pizza table to our database, which of the following two lines of code would we run first? Why is it important to run these two line in that order?
    ```
    add-migration AddPizzaTable
    ```
    ```
    update-database
    ```

1. For all three parts of this question, imagine that you have used Entity Framework to create a database table using the following class and context. 
    1. What will the table name be?
    1. What will the column name(s) be?
    1. What is the name of the database you are connecting to?

    ```C#
    namespace BikeApp
    {
        public class Bike
        {
            public int Id { get; set; }
            public string Type { get; set; }
            public DateTime Date { get; set; }
        }
    }

    namespace BikeApp
    {
        public class BikeContext : DbContext
        {
            public DbSet<Bike> Bikes { get; set; }
            protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder) => optionsBuilder.UseNpgsql("Host=localhost;Username=postgres;Password=<your_password_for_postgres_user>;Database=Bikes").UseSnakeCaseNamingConvention();
        }
    }
    ```

1. What type of data does the `Contains` LINQ method return? As with all of our assessments, feel free to use google when answering this question.
    <br> a. String 
    <br> b. Integer 
    <br> c. Boolean

## Exercise

[Follow the instructions on this repl!](https://replit.com/@launch-team/Mod2Week4Assessment#main.cs)


