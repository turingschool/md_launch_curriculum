## Learning Goals

* Recognize each of the main c# datatypes.
* Speak to a few common methods for each data type.
* Practice researching built-in c# methods.

## Warm Up

With a partner, group the following items into two or more categories (you get to determine appropriate categories!)

> * horse
> * 3
> * run
> * jump
> * fourteen
> * dog
> * true
> * rock
> * apple
> * 525600
> * nothingness
> * 3.14

# Variables

One of the most important concepts in programming is assigning information to a variable.  Let's take a look at [this replit project](https://replit.com/@MeganMcMahon1/VariableAssigment#main.cs) to get a better understanding.

![Screenshot showing two variables being assigned and used](/images/Mod1/DataTypesAndVariables/VariableAssignment1.png)

> With a partner discuss what this program is doing - what is happening on each line?  What is printed to the console when the program is run, and why?

Admittedly, this is a somewhat silly example, but it illustrates an important programming problem.  We often need to re-use the same piece of information over and over again throughout out our application (as in the need for "Megan McMahon" in three different places).  And/Or, we need to use information that might change periodically (as in a person's job title).  It would be time consuming and allows for more data-entry errors. **Variables** give us a way to put a label on a piece of information, and then use that label throughout our program.  That way, if we need to update the information, we only have to make the change in one place.  For example, if we want to change `"Megan McMahon"` to `"Megan"`, we only need to change the value on line 7 and we will see the change throughout our program.

![Screenshot showing variable values changed](/images/Mod1/DataTypesAndVariables/VariableAssignment2.png)

## Declaration and Assignment

When creating a variable, we need to think about two things:  declaring the variable, and assigning a value to it.  Declaring a variable tells our program to set aside some memory (a spot where the information can live while the program is running), and assignment indicates precisely *what* information should be stored.  These two operations can be performed separately, or at the same time.

![Example of variable declaration and assignment](/images/Mod1/DataTypesAndVariables/DeclarationAndAssignment.png)

In this example, we have two variables: `name` and `jobTitle`.  `name` is an example of declaration (on line 6) *and then* assignment.  We first tell our program that we will need a variable called `name` that will hold a **string**; different types of data require different kinds of storage, so it is necessary to know what kind of information the variable will hold when we declare it.  Then (on line 9), we use the **assignemnt operator** `=` to give that variable a value.  For the variable `jobTitle` we have combined these two operations into one line of code.

> Time to create your own variables!  Create at least 5 new variables, give them values, and print those variables to the console with `Console.WriteLine(variableName)`.  Be creative with your variable names; there are rules for what you can name a variable - see if you can break those rules!


# Datatypes

We've played around with some text, but that's not the only type of data we will work with.

> Other than text, what other datatypes can you imagine?

Any piece of information can be grouped into one of four categories:
* Text
* Number
* Boolean
* Nothingness 🧐

Let's look at some examples of each category and the **datatypes** that make up those categories.

## Text
### String

A **string** is any combination of characters surrounded by double quotes `""`

```c#
string aString = "this is a string with words in it";
string anotherString = "32 horses walk into a bar";
string aSillyString = "525600";
```

### Char

A **char** is a single alpha character surounded by single quotes `''`

```c#
char a = 'z';
char b = 'y';
```

## Numbers
### Int

**Int**s are whole numbers.  the **int** datatype can hold 4 bytes of data (numbers from -2,147,483,648 to 2,147,483,647)

```c#
int number = 525600;
int age = 45;
int year = 2022;
```

### Float

**Float**s are fractional numbers (numbers with a decimal point).  Floats can hold 4 bytes of data.
```c#
float notQuitePi = 3.14F;
float price = 2.99F;
```

When assigning a float, you need to append the number with `F`!

### Double

```c#

```

### Others

## Boolean

## Nothingness

# Using `var`

# Check for Understanding

- Group the following items into each of their C# datatype (are there any that could be classified as more than one type?)
    > * horse
    > * 3
    > * run
    > * jump
    > * fourteen
    > * dog
    > * true
    > * rock
    > * apple
    > * 525600
    > * nothingness
    > * 3.14