# Object Oriented Programming

## Learning Goals
* Define OOP
* Introduce the 4 Pillars of OOP
* Identify different sytaxes for object instantiation

## What is OOP?

**OOP**, short for **Object Oriented Design**, is one of the most popular programming models.  OOP relies on **objects** to organize programs into simple and reusable pieces of code.  In C#, these objects are created using **classes**.

> Discuss with a partner: what are some of the components of a class or the objects created from a class definition?  What kinds of objects have we worked with so far?

The **class** structure is fundamental to OOP, because it allows us to group related **attributes** and **behaviors** to be reused in individual objects.  So, how does that help us?

To see this in action, let's imagine that we are building a program that will manage a dog sitting service.  You might want to have access to an animal's name, breed, birthday, and number of walks required.  _Without_ OOP, you might model that information like this:

```c#
namespace DogSitter
{
    internal class Program
    {
        static void Main()
        {
            var nile = new Dictionary<string, string>
            {
                { "name", "Nile" },
                { "breed", "Golden Mix"},
                { "birthday", "2018-07-04"},
                { "walks required", "3" }
            };

            var sammy = new Dictionary<string, string>
            {
                { "name", "Sammy" },
                { "breed", "Wirehaired Pointing Griffon" },
                { "birthday", "2012-10-13" },
                { "walks required", "1" }
            };

            var dogs = new List<Dictionary<string, string>> { nile, sammy };

            // Take dogs on a walk
            foreach (var dog in dogs)
            {
                var currentWalksRequired = int.Parse(dog["walks required"]);
                Console.WriteLine($"Taking {dog["name"]} for a walk...");
                dog["walks required"] = (currentWalksRequired - 1).ToString();
            }

            Console.WriteLine($"{nile["name"]} now needs {nile["walks required"]} walks");
            Console.WriteLine($"{sammy["name"]} now needs {sammy["walks required"]} walks");
        }
    }
}
```

> With a partner - what are some drawbacks to this code?  How easy or difficult would it be to add a new dog to our pack?

There is quite a bit of repeated code here, as well as some extra manipulations we need to do to change the value of required walks.  Imagine we also wanted to list out the age of each dog?  We would need to convert their birthday to a date, and calculate their birthday each time that information was required.

Compare what we built above with an OOP version below:

```c#
// Dog.cs
    public class Dog
    {
        public string Name;
        public string Breed;
        public DateTime Birthdate;
        public int WalksRequired;

        public Dog(string name, string breed, DateTime birthdate, int walksRequired)
        {
            Name = name;
            Breed = breed;
            Birthdate = birthdate;
            WalksRequired = walksRequired;
        }

        public void GoOnWalk()
        {
            WalksRequired--;
        }
    }
```

```cs
// Program.cs
public class Program
    {
        static void Main()
        {
            Dog nile = new("Nile", "Golden Mix", new DateTime(2018, 07, 04), 3);
            Dog sammy = new("Sammy", "Wirehaired Pointing Griffon", new DateTime(2012, 10, 13), 1);

            var dogs = new List<Dog> { nile, sammy };

            // Take dogs on a walk
            foreach (var dog in dogs)
            {
                Console.WriteLine($"Taking {dog.Name} for a walk...");
                dog.GoOnWalk();
            }

            Console.WriteLine($"{nile.Name} now needs {nile.WalksRequired} walks");
            Console.WriteLine($"{sammy.Name} now needs {sammy.WalksRequired} walks");
        }
    }
```

Here, we have a **class** that serves as a blue-print for any dog; instead of building a dictionary (or using some other method of storing dog information), we use the _idea_ of a dog.

> With a partner, talk through the code in these two files.  What is happening on each line? What are some benefits to this approach?  Are there any drawbacks?


With this OOP approach, it is much easier to update what a dog can do, or what information a dog stores.  We might want to be able to get a dog's age, for example. In the first version, we would need to calculate the age of each dog individually, but with OOP we can add a method to the Dog class.  Methods that exist on a class definition are availabe to be called on any instance of that object.

**Instructor Note**: we want to focus on the re-usability of code here.  Also make sure to discuss the different styles of instantiating obects `T variable = new T()` vs `T variable = new()` vs `var variable = new T()`

### Creating Instances of Objects

The process of creating instances of objects from a class definition is often referred to as **instantiation**.  In the `Dog` example above, we could say that we `instantiated two Dog objects, nile and sammy`.  Any time you see the `new` keyword being used, some kind of object is being instantiated.

![Image of three examples of object instantiation](/Mod1/Images/Week4/object-instantiation-examples.png)

We can see in this example that there are three valid ways to create an instance of a Dog object - any of these instantiation patterns will work for any type of object!

When instantiating an object, you _must_ include 2 things:
* `new` this is the keyword that tells our program that we are going to create an instance of something.
* the _type_ of thing that we are creating - in this case `Dog`.  

## Four Pillars of OOP

There are 4 principles of OOP which we will introduce here, and continue to learn more about as we go.  At this point, some of these concepts might not make sense - that's ok!  We want to get a start on recognizing these patterns today, and we will re-inforce these patterns throughout your time at Turing.

### Encapsulation

**Contain Information in an Object, Only Expose Necessary Information**
Encapsulation hides the internal implementation of attributes and behaviors inside of objects.  When we declare a class, we are indicating what properties and methods will be encapsulated in the objects created from that class template.  These attributes and behaviors can be either **public** or **private**.  Public components are available from _outside_ the object; these are the properties and attributes that we can call on objects.  Private components are only available within the class; there is no mechanism to call that method or property from an object.

Let's take a car as a methophor.  When a car is created, all of the components that make it run are **encapsulated** in the body of the car - engine, gauges, breaks, seatbelts, indicators, etc... .  Some of these components are public: blinkers to indicate turns, brake lights, the sound of a reving engine.  These public pieces of information can be seen from _outside_ the car.  Other components are kept private: engine temperature, occupancy, transmission type.  These private components are essential attributes/behaviors of the car, but they do not need to be exposed - this additional information is not needed outside the car.

### Abstraction

**Only Expose High Level Attributes and Methods**
Abstraction is the practice of exposing _only_ what a user _needs_.  

> With a partner, what are some examples of abstraction in the real world?  You might want to go back to previous lessons 😉

Benefits of Abstraction
* Simple User Interfaces
* Complex Code is Hidden
* Easier Software Maintenance
* Security

### Inheritance

**Child Classes Get Attributes/Behaviors From Parent Class**
When we think about objects in the real world, we can often describe two different objects as having a 'type-of' relationship.  For example, a car, a motorcycle, and a semi are all _types of_ vehicles.  They all share some attributes and behaviors:

![UML Diagram of Car Motorcycle and Semi Classes](/Mod1/Images/Week4/InheritancePre.png)

While these classes are not identical, they do share a lot of attributes and behaviors.  Inheritance allows us to create a **parent** class that contains the shared components, with **child** classes that **inherit** these components and can include any additional attributes and behavior.

![UML Diagram of Car/Moto/Semi inheriting from Vehicle](/Mod1/Images/Week4/Intherited.png)

**Instructor Note** Make sure to walk through UML class diagramming.  You could show them the free tool [smartdraw](https://cloud.smartdraw.com/)

We will learn how to implement and work with Inheritance later in this mod!

> With a partner: what other Inheritance relationships can you think of in the real world? (try to think of objects that are not humans!)

### Polymorphism

**Shared Behavior May Differ For Specific Types**
In some cases, we might have objects that share behavior with potential small variations.  Take a look at the diagram below:

![UML Diagram of Polymorphism](/Mod1/Images/Week4/Polymorphism.png)

In this example, all dogs can `Speak()`, but one type of dog has a very distinct bark that will **override** the behavior that is inherited from the parent class.  We want to inherit that behavior because _most_ of the types of that class behave in the same way, with just this one outlier.

Like Inheritance, we will continue to explore polymorphism in later lessons!

## Check for Understanding

* Imagine you have a class `Button` which has a constructor that takes no arguments.  Use three different syntax patterns to create three instances of the Button class.
* Think of your favorite board game (or you can think of [Connect Four](https://en.wikipedia.org/wiki/Connect_Four)); what are the classes that you would create to implement that board game in code?
* Review the class definition below.  What are some ways that encapsulation and inhertance are implemented?

```c#
    public class User
    {
        public string Name;
        public string Email;
        public string UserName;
        private string Role;
        private string Password;

        public void Register(string name, string email, string password)
        {
            Name = name;
            Email = email;
            Password = password;
            UserName = CreateUserName();
        }

        private string CreateUserName()
        {
            var index = Email.IndexOf("@");
            return Email.Substring(0, index);
        }

    }
```