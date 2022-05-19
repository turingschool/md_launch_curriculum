# Methods

## Learning Goals
* Define the terms Method, Argument, Return Value, and Object.
* Explain why we use methods
* Define methods in c#
* Understand how abstraction helps us program

## Warm Up

```c#
string hello = "Hello World";
List<int> nums = new () { 1, 3, 5, 7 };

hello.ToUpper();
nums.Add(9);

Console.WriteLine(hello);
Console.WriteLine(nums);
Console.WriteLine(hello.ToUpper());
```

With a partner, try to identify the `methods` and `arguments` that are in the code snippet above.

## What is a Method?

A **method** is a group of related instructions that achieve some purpose or responsibility.  In the warm up, `Add()` is a method that instructs the `nums` array to append something to the end of the list; `ToUpper()` is a method that **returns** a string in all uppercase.

> In a group, imagine that `ToUpper()` doesn't exist.  How might you achieve the same goal?

One huge benefit of methods is the reusability of code.  We _could_ recreate the functionality of `ToUpper()` adhoc, or whenever we need it in our program, but that would be very tedious and repetitive.  The method exists to cut down on repetition of repeated instructions.

In the warm-up example, we call methods on **objects** - we give the `ToUpper()` instructions to a specific string, and the `Add()` instructions to a specific list.

All methods _do_ something, they have some instructions.  Some methods have a **return value**.

![Image of assigning method calls to variables](/images/Mod1/Methods/AssigningReturnValues.png)

In the image above, we can see that it is _sometimes_ possible to assign a variable based on a method call.  The method `ToUpper` has a **return value** that we can store in a variable; its job is to return an up-cased version of the string.  But, `Add()` has no return value; its job is to change the list in some way.

## Method Signature

Let's take a look at how we can define our own methods.

```c#
void Main()
{
	static void SayHello()
	{
		Console.WriteLine("Hello World");
	}
}
```

Here, we have **defined** the method `SayHello()` and indicated that it will have _no return value_. When we run this code, does anything happen?  Not yet!  A method definition is only telling our program that we now have a method that we can call at a later time.  To actually see "Hello World" printed to the console, we need to call the method:

```c#
void Main()
{
    // define the method
    static void SayHello()
    {
        Console.WriteLine("Hello World");
    }

    // call the method
    SayHello();
}
```

Another example:

```c#
void Main()
{
    static void Greet(string name)
    {
        Console.WriteLine($"Hello {name}");
    }

    Greet("Megan");
    Greet("Eric");
}
```

> With a partner: run the code above and describe what is happening on each line.  Compare it to `SayHello()` - what is similar? what is different?

`Greet` is a method that can take an **argument**.  Arguments are input to methods that allow them to complete their instructions appropriately.  In this case, we need to give the method a string that represents a person's name.

> With a partner: what do you think would happen if you try to call `Greet(13)`?

When we define a method that takes a string argument, that is the only datatype that the method will accept.

> Create a method that takes 2 arguments.

Let's look at one more example:

```c#
void Main()
{
    static int Add(int num1, int num2)
    {
        return num1 + num2;
    }

    Console.WriteLine($"1 + 1 = {Add(1, 1)}");
    Console.WriteLine($"1 + 2 = {Add(1, 2)}");

    int sum = Add(24, 67);
    Console.WriteLine($"24 + 67 = {sum}");
}
```

> with a partner, walk through this code explaining what is happening on each line.  What makes this method different from those above?

When a method has a **return value**, we must indicate what type of object will be returned, and explicitly `return` something from the method.

When we define new methods, we are creating a **method signature**

![Diagram of Method Signature](/images/Mod1/Methods/MethodSignature.png)

A method signature includes the return value of the method (or `void` if there is none), the name of the method, and any arguments necessary for the method to execute. We will discuss more about **static** in a later lesson 😊.

## Abstraction

One of the advantages of using methods is that we can build methods that operate at higher levels of abstraction than other methods. Abstraction is a practice where less complex functionality is exposed in an interface and more complex functionality is suppressed. In some ways, this is like a pyramid where higher level methods rely on lower level methods to take care of the details.

Think about how you drive a car. You don’t need to know how a combustion engine works in order to drive it. All you need to know is that when you put your foot down on the gas pedal, the car moves. The details of how the engine work are abstracted away from you. You only need to know how the gas pedal works, the interface.

Abstraction is an object-oriented programming concept that means that complexity is being hidden from the user.  We will continue to build on this idea as we learn more about programming.


## Checks for Understanding
What will be the output of the following program:

```c#
void Main()
{
    static void Print(string content)
    {
        Console.WriteLine(content);
    }

    static int Add(int num1, int num2)
    {
        return num1 + num2;
    }

    static int Subtract(int num1, int num2)
    {
        return num1 - num2;
    }

    int num1 = Add(5, 10);
    int num2 = Subtract(100, num1);
    Print(num2.ToString());
}
```

What would happen if we didn't call `ToString()` on `num2`?