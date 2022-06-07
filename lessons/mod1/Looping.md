## Learning Goals
* Identify and implement code blocks.
* Use `loop do`, `while`, and `for` to repeat code blocks.
* Recognize potential infinite loops.

## Warm-Up

Imagine you are writing a program that will shuffle and deal a deck of cards to two players.  Each player should have 5 cards.  The program might have tasks such as: shuffle, and distribute a card.

How many times will you shuffle the deck?
How many times will you distribute cards?

What if we need to deal 5 cards to 5 players?  Will the answers to the questions above change?

**Instructor Note**: lead a discussion around the pros and cons of explicitly repeating actions.  You could even pull up [this repo]() to show the card example.

## Looping

A loop is a set of instructions that is executed repeatedly until some condition is met. This condition may be a certain number of times that the loop is executed, for example:

- After baking cookies, you pull the cookie sheet out of the oven which holds 24 cookies. One by one, you remove each of the cookies from the sheet and place them on a cooling rack.
(Set of instructions that executes 24 times)

or it may be a question that returns a true/false (boolean) answer. For example:

- While looking for a parking spot at a crowded sporting event, a car continues to drive up and down the rows until an empty spot is found (full == false).   
(Loop that executes until a question returns true or false)


## `while` loop

A `while` loop will execute a block of code as long as a specific condition is `true`. 

![Diagram of while loop logic](/images/Mod1/Looping/WhileLoop.jpg)

```c#
while (condition)
{
  // code to execute as long as condition evaluates to true.
}
```

```c#
var parkingSpace = "full";

while (parkingSpace == "full")
{
  Console.WriteLine("Guess I'll keep driving");
}
```

> With a partner: What do you think will happen if we run the code above?

** Instructor Note **: discuss infinte loops.  In replit, you will need to `stop` the program to exit out.  

> How might we avoid the problem of an infinte loop?

> Practice: in a replit project, write a program that continuously asks a user for a random fact until the user enters 'exit'.

** Instructor Note **: this would be a great time to ask a few students to share out there code (solutions AND problems!).

## `for`

Often, we need to do a task a specific number of times; in these instances, a `for` loop can be helpful.

```c#
for (var i = 0; i < 5; i++ )
{
  Console.WriteLine(i);
}
```

A `for` loop is sometimes a bit difficult to understand at first.  To help us understand, let's take a look at the following `while` loop, that will result in the same outcome as the `for` loop above:

```c#
var i = 0;
while ( i < 5)
{
  Console.WriteLine(i);
  i = i + 1;
}
```

**instructor note** discuss increment and decrement operator here!

> With a partner, walk through the code below; at each point, indicate what the value of `i` is.  How many loops will be completed?
> ```c#
> for (var m = 15; i > 5; i -= 3)
> {
>    Console.WriteLine("The current value of i is: " + i);
> }
>```

## `do... while`

Another type of loop is a `do...while`.  Take a look at the example below:

```c#
var numCookies = 24;
do
{
  Console.WriteLine("Removing cookie number: " + numCookies);
  numCookies -= 1;
} while (numCookies > 0);

Console.WriteLine("All cookies removed!");
```

What is the difference between `while` and `do...while`?  How would you change the `while` diagram to account for this difference?

### Check for Understanding

Without running the code first, write down what the output of the following code would be:

```c#
for (var i = 0; i < 3; i++)
{
  var m = 5;
  while (m > 0)
  {
    Console.WriteLine($"i: {i}, m: {m}");
    m--;
  }
}
```