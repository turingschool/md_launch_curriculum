# Collections

## Learning Goals
* Identify key differences between **arrays** and **lists**
* Define and use a dictionary
* Iterate through collections with `foreach` and `for`

## Array

From yesterday's lab work, answer the following questions.

1. What is an **array**?  How is it different from a string or integer?
1. What is at index 2 in this array: `string [] cars = { "Chevy", "Ford", "Toyota", "Tesla" }`
1. What are some drawbacks to using an array?

One of the major drawbacks of an array is that we can not add or remove element positions in the array. In other words, an array that is created to store 5 strings, will always have 5 **elements** in it - no more, no fewer.  An array is always the same size - great for storing collections of information that never change (like days of the week, or suits in a deck of cards), but not so great at storing information that will change in size.

Luckily, there is a built-in object in c# called a [**collection**](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/collections) that helps with this problem.  There are different types of collections, but today we will be focusing on **lists** and **dictionaries**.

## List

A list is very similar to an array - it is an **ordered** collection that can hold any number of related objects of the same type.  When creating a new list, you can use an **initializer**, or not.  An **initializer** allows us to create a list with elements already in it.

```c#
// with initializer

var dogBreeds = new List<string> { "labrador", "golden retriever", "poodle" }

// without initializer
var dogBreeds = new List<string> ();
dogBreeds.Add("labrador");
dogBreeds.Add("golden retriever");
dogBreeds.Add("poodle");
```

Just like arrays, a list can only contain **elements** of the same type - this is why we must declare what kind of object a List will contain.

### Accessing and Manipulating List Items

> With a partner, take a look at the resources linked below, and see if you can accomplish the following:  
> 1. [Resource](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/collections#BKMK_SimpleCollection): Add another dog breed to `dogBreeds`.
> 2. [Resource](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/collections#BKMK_SimpleCollection): Remove "poodle" from the list.
> 3. [Resource](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.sort?view=net-6.0): Use a method to sort the list alphabetically.
> 4. [Resource](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=net-6.0): Use the list to print "GOLDEN RETRIEVER" to the console.

** Instructor Note**: walk throught these examples showing _how_ you would research what to do.

## `foreach`

One of the benefits of holding information in a collection is the ability to do the same action to/with each item in the collection without repeating much code.

Imagine you need to print each dog breed to the console.  You might do something like:

```c#
Console.WriteLine("Dog Breeds:");
Console.WriteLine(dogBreeds[0]);
Console.WriteLine(dogBreeds[1]);
Console.WriteLine(dogBreeds[2]);
```

This isn't too bad, but what if you needed to print a list of all 199 dog breeds recognized by the Westminster Kennel Club? This would be A LOT of repeated code.

** Instructor Note ** Good place to get the students together to see if they can use a regular `for` loop to solve this problem.

When we need to do the same thing to/with an element in a collection, we can use a `foreach` loop:

```c#
foreach (var breed in dogBreeds)
{
    Console.WriteLine(breed);
}
```

> Take a moment to see if you can describe what might be happening in the code above - use what you know about a regular `for` loop!

A `foreach` is an **iterator**; it allows us to step through a collection element by element and do something with that element (in this case a single `breed`).  

## Dictionary

A list is great for singularly grouped collections.  But, we often need a little more organization for our collection.  For example, we might want to store a collection that represents a store inventory.  Consider the following list of items:

```
3 toasters
256 nails
1 mower
5 dog bowls
```

This _is_ a list, but it's not really made up of single elements - it is made up of **pairs** of information.  Each piece of information, or **element**, indicates an item AND the quantity on hand.  If we needed to store this idea in an array or list, it might look something like:

```c#
var inventory = new List<string> {
    "mower",
    "toaster",
    "toaster",
    "toaster",
    "dog bowl",
    "dog bowl",
    "dog bowl",
    "dog bowl",
    "dog bowl",
    "nail",
    "nail",
    "nail",
    "nail",
    // lots more nails.......
}
```

This `inventory` does technically hold the information we need, but not in a very understandable way.  Compare that to the **dictionary** below:

```c#
var inventory = new Dictionary<string, int> {
    {"mowers", 1},
    {"toasters", 3},
    {"dog bowls", 5},
    {"nails", 256}
}
```

Much more readable!  We now have a collection of **key/value** pairs.  The keys are the inventory item, and the values are the quantity of that item.  When working with an array or list, we access specific elements with it's **index**.  But, a dictionary is an **unordered** collection, so there is not concept of an index.  Instead of accessing specific elements with an index, we will access specific **values** with their **key**.

```c#
Console.WriteLine( $"toasters: {inventory["toasters"]}" );
Console.WriteLine( $"dog bowls: {inventory["dog bowls"]}" );

/* Output:
toasters: 3
dog bowls: 5
*/
```

> With a partner: Try to add a new key/value pair for an existing key `inventory.Add("nails", 7234);`. What happens?  And why?

You can also iterate over a dictionary collection.  Try running the code below; really think about what is happening on each line.

```c#
foreach (var (item, qty) in inventory)
{
	Console.WriteLine($"key: {item}, value: {qty}");
};
```

## Check for Understanding
* Create an Array of the names of your favorite foods; let's call it `favoriteFoods`.
* Imagine that you know need to change the list of your favorite foods (you've found you absolutely love green olives).  Recreate your `favoriteFoods` to the most appropriate collection type.
* Write a program that will output a summary of your favorite foods.  Include the names of your favorite foods and the number of favorite foods that you have.  For example:
```
Megan has 5 Favorite Foods:
Popcorn
Pepperoni Pizza
Pears
Pecans
Praline
```
* Describe the differences and similarites between an Array, a List, and a Dictionary.  What are some pros and cons of each?

