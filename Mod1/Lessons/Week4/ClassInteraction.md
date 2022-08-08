# Class Interaction

## Learning Goals
* Implement appropriate class file structure
* Gain familiarity with passing around 'smart' objects
* Expand understanding of what an object can be

## Warm Up
Outline the classes you might neet to create a city-wide library system (multiple locations with physical books).  How do these classes relate to each other?

## Building Necessary Objects

To understand how objects can interact with each other, let's continue building on our Unicorn class from the [Classes Lesson](/Mod1/Lessons/WEek3/Classes.md).  Right now, our Unicorn has a list of Magical powers that are simple strings.

```c#
    public class Unicorn
    {
        public string Name;
        public string Color;
        public List<string> MagicalPowers;

        public Unicorn(string name, string color)
        {
            Name = name;
            Color = color;
            MagicalPowers = new List<string>();
        }

        public void AddPower(string power)
        {
            MagicalPowers.Add(power);
        }
    }
```

Let's expand this idea of a magical power to indicate how much energy that power takes to perform.  We could imagine an interaction like this:

```c#
var fred = new Unicorn("Fred", "Silver");
//Unicorns start with 100 power points.

fred.AddPower("Fly: 13");
fred.AddPower("Be Invisible: 28");

fred.Perform("Fly");
//Now fred has 87 power points (13 points have been deducted from fred's original 100 points).

fred.Perform("Be Invisible");
//Now fred has 59 power points.
```

This string version of a Magical Power now holds a lot of information: the name of the power, and the energy needed to perform it.  We _could_ work with these strings to accomplish the storage and performance of these powers, but we would need to do a lot of string manipulation anytime we want to perform one of the powers (we would need to constantly be separating the idea of the name of the power, from its energy usage).

A better way would be to create a `Power` Class that will hold these attributes.

> With a partner, build a class that will represent a Power.  Update your Unicorn to expect instances of that Power class, instead of strings.  If you have some additional time: how might we implement the idea of energy usage?

When complete, we should be able to execute the follwoing program:
```c#
var fred = new Unicorn("Fred", "Silver");
var frank = new Unicorn("Frank", "Purple");
var fly = new Power("Flight", 13);
var beInvisible = new Power("Invisibility", 28);


```

---------------------------------------

When we think about creating new classes, one of the first questions we need to answer is: Where should this class live?  (As in, what file should it be in).  Almost always, a class will live in its own file - there should be a one-to-one relationship between classes and files.  So, my file structure for this new class might look like:

![Image of Solution with multiple classes](/images/Mod1/ClassInteraction/SolutionFileStructure.png)

You can take a look at how I might create this additional class, and how it interacts with our Unicorn class.  You and your partner might have come up with something slightly different, and that's ok!

```c#
// Power.cs
    public class Power
    {
        public string Name;
        public int EnergyRequired;

        public Power(string name, int energyRequired)
        {
            Name = name;
            EnergyRequired = energyRequired;
        }
    }

// Unicorn.cs
    public class Unicorn
    {
        public string Name;
        public string Color { get; set; }
        public List<Power> MagicalPowers;
        public int Energy = 100;

        public Unicorn(string name, string color)
        {
            Name = name;
            Color = color;
            MagicalPowers = new List<Power>();
        }

        public void AddPower(Power magicalPower)
        {
            MagicalPowers.Add(magicalPower);
        }

        public void Rest()
        {
            Energy += 10;
        }

        public void PerformPowers()
        {
            foreach (var power in MagicalPowers)
            {
                Energy -= power.EnergyRequired;
            }
        }
    }
```



