## Learning Goals
* Identify and implement code blocks.
* Use `loop do`, `while`, and `for` to repeat code blocks.
* Recognize potential infinite loops.

## Warm-Up

Imagine you are writing a program that will shuffle and deal a deck of cards to two players.  Each player should have 5 cards.  The program might have tasks such as: shuffle, and distribute a card.

* How many times will you shuffle the deck?
* How many times will you distribute cards?

What if we need to deal 5 cards to 5 players?  Will the answers to the questions above change?

**Instructor Note**: lead a discussion around the pros and cons of explicitly repeating actions.  You could even pull up [this repo](https://replit.com/@MeganMcMahon1/CardShuffle#main.cs:9:9) to show the card example.

## Looping

A loop is a set of instructions that is executed repeatedly until some condition is met. This condition may be a certain number of times that the loop is executed, for example:
<!-- In the below example, could we break out this block of text into separate steps/instructions? I wonder if we did that if it will a) look more code-like and b) reiterate the step by step nature of setting up a loop -->
- After baking cookies, you pull the cookie sheet out of the oven which holds 24 cookies. One by one, you remove each of the cookies from the sheet and place them on a cooling rack.
(Set of instructions that executes 24 times)

or it may be a question that returns a true/false (boolean) answer. For example:

- While looking for a parking spot at a crowded sporting event, a car continues to drive up and down the rows until an empty spot is found (full == false).   
(Loop that executes until a question returns true or false)


## `while` loop

A `while` loop will execute a block of code as long as a specific condition is `true`. 

![Diagram of while loop logic](/images/Mod1/Looping/WhileLoop.png)

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

When we have a loop where the condition always evaluates to `true`, we have created an **infinite loop**.  The loop will continue running forever (or until our computers run out of processing power!).  Because of this danger, it is always good to consider early in the implementation process, how a loop will stop.

> How might we avoid the problem of an infinte loop in this parking space example?

> Practice: in a replit project, write a program that continuously asks a user for a random fact until the user enters 'exit'.

** Instructor Note **: this would be a great time to ask a few students to share out there code (implementations AND bugs!).

### Code Blocks
Now that we have worked with if statements and loops, you might have started to notice that we often group statements inside of two curly brackets `{}`.  We refer to this group of statements as a **block of code** or a **code block**.

```c#
if (isHungry == true)
{
  // Everything between the curly braces is the code block (even this comment).
  Eat();
}
```

```c#
while (isHungry == true)
{
  // this is a code block.
  if (foodExists == true)
  {
    // this is another code block nested INSIDE the while block.
    Eat();
  }
}
```
<!-- In the below, I think it might be worthwhile to explain in a few more words what "readability" means and why it is important. -->
Code blocks can be nested inside other blocks (though we generally want to avoid too much nesting, for readability).

It is important for us to start recognizing code blocks because these blocks are how are program knows to end one task, and move on to the next one.  For example, how does the program below know when to check the condition again?  When we get to the end of the while statement's code block!

```c#
Console.WriteLine("What is the best cookie?");
var userInput = Console.ReadLine();

while (userInput != "Snickerdoodle")
{
  Console.WriteLine("Wrong! What is the best cookie?");
} // <-- this is the end of the while statement's code block.

Console.WriteLine("Yes! You are so smart.");
```

Without the idea of a code block, this program might mistakenly encourage users to believe that chocolate chip, or peanut butter were the best cookie.  We need the code block to _contain_ the code that we want to repeat as along as the  condition is true.

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
<!-- In the below example, is declaring the initializer as "m" intentional?  -->
> With a partner, walk through the code below; at each point, indicate what the value of `i` is.  How many loops will be completed?
> ```c#
> for (var m = 15; i > 5; i -= 3)
> {
>    Console.WriteLine("The current value of i is: " + i);
> }
>```

<!-- I think if we focus on for loops, we will likely need to beef this section up to break down each component more explicitly. I think the FE lesson on this actually does an OK job of breaking down the different parts: https://frontend.turing.edu/lessons/module-1/js-for-loops.html -->
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

The `do... while` loop is similar to a `while loop`; the difference is that the conditional code block is run _first_ and then the condition is evaluated.

> With a partner: How might you change the `while` diagram to account for this difference?

### Check for Understanding


* What might cause an infinite loop? What is a good way to avoid an infinite loop?
* Write a **for** loop that will output a countdown from 10 to 1.
* Write a **while** loop that will continually ask a user what the best animal is, until they provide the answer "Unicorn".
<!-- Could adding annotations to the code block below also be a good CFU for students? Maybe we could model annotating this when we review it as a group too. -->
* Without running the code first, write down what the output of the following code would be:
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
After making a prediction, copy this code into a replit project and see if you were correct!  
* How many code blocks are in the example above?

<!-- My initial takeaway on this lesson is that there are a LOT of different ways to handle looping and they all have very different syntax. I can imagine a new student feeling pretty overwhelmed with all of the different options. My main question here is: do we NEED to introduce all of these options in this lesson? Perhaps it's my old-school FE thinking, but part of me thinks digging into for loops allows us to cover looping, code blocks, variable assignment/reassignment, common code conventions (such as using the variable "i" as the initializer), etc.  -->

<!-- Regardless of how many methods of looping we introduce, I think having some more hands-on REPL practice after each way of looping is introduced is probably a good way to break up teacher-talktime and put more on students to explore, break, etc. I imagine there will be time dedicated to this in lab as well, but definitely think there are still opportunities within lessons as well. -->
