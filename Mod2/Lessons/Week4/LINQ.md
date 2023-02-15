# LINQ

## Learning Goals
* Understand why we use LINQ
* Practice basic LINQ methods
* Recognize LINQ Query Syntax

## Warm Up

```c#
var names = new List<string>() {
    "Connor",
    "Megan",
    "Charlie",
    "Molly"
};
```

For the `names` list above, use `for` or `foreach` to get the following:
* A list of names that start with "C"
* A list of names that are 5 letters long
* 🌶️The first name that contains an 'e'

## LINQ

When working with collections (lists, arrays, dictionaries), we often need to use `for` or `foreach` to manipulate that list to give us some infomration about it.  We might need to get a subset of the collection, find a specific element in the collection, or get some information _about_ a collection (like if the collection contains a specific object).  These kinds of functions come up so often that many languages create special methods to handle working with collections.

In C#, these additional methods are in the LINQ package.  Most C# developers use LINQ methods to accomplish what you just did in the warm-up.  LINQ makes these tasks easier.

We are going to use [this repo](https://github.com/turingschool-examples/Launch_LinqLesson) to learn some LINQ methods.  Fork and clone the repo, and take about 5 minutes to familiarize yourself with the current code.

### Where

When you are trying to get a **subset** of a collection, you can use the LINQ method `WHERE`.

Compare the two approaches for filtering a list below:

```c#
var names = new List<string>() {
    "Connor",
    "Megan",
    "Charlie",
    "Molly"
};

// Using `foreach`
var cNamesForeach = new List<string>();

foreach (var name in names)
{
    if (name[0] == 'C')
    {
        cNamesForeach.Add(name);
    }
}

// Using LINQ

var cNamesLinq = names.Where(name => name[0] == 'C');
```

`Where` is a method that takes a [lambda expression]() as an argument.  In this case, the lambda expression is telling `Where` _how_ to filter the collection.  We want to look at each `name` and filter to only those names where `name[0] == 'C'` is true.

> With a partner, in the starter repo, work through the exercises under `// Filtering Collections`.
> Be ready to share out!

** Instructor Note ** As students are sharing, we want them to describe how the lambda expression is being processed by the Where method. 

### OrderBy

You can also use LINQ to order a collection by a specific characteristic.

```c#
var orderedNames = names.OrderBy(name => name.Length);
```

In the example above, we will get a list of the names ordered from shortest to longest.

> With a partner, in the starter repo, work through the exercises under `// Ordering Collections`
> Be ready to share out!

** Instructor Note ** We want to highlight for students that we should only order records by a 'comparable' object.  We shouldn't order songs by Artist, but we should order songs by Artist.Name.

### Count

LINQ methods do not always return a collection - some LINQ methods return an number!  For example, `Count` returns an int that represents the number of elements that match a certain criteria.

```c#
var numberOfCNames = names.Count(name => name[0] == 'C');
```

One thing that can be helpful when working with LINQ, is to verbalize what the method is doing.  For example, you might describe the method above as: `Count is taking a tally of each name that starts with the letter 'C'`.

> With a partner, in the starter repo, work through the exercises under `// Counting Records`
> Be ready to share out!


### Any and Contains

LINQ methods can also return boolean values that tell us something about a collection.  For example, `Any` tells us if any element matches a given criteria, and `Contains` tells us if the collection has a specific element.

```c#
var anyZNames = names.Any(name => name[0] == 'Z');

var containsMegan = names.Contains("Megan");
```

You'll see that `Contains` is slightly different than the other LINQ methods that we have seen so far - it does not take a lambda expression!  The input for `Contains` is the object that you are searching for.  Contains tells us if that exact object is in the collection.

> With a partner, in the starter repo, work through the exercises under `// Characteristics of the Collection`
> Be ready to share out!

### Combining Methods

### Researching
* All
* Sum
* First
* Distinct

## Query Syntax

## Checks for Understanding
