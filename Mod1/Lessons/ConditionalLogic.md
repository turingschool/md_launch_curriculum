## Learning Goals

* explain the flow of execution through code  
* use `if/else` statements to control execution


# Conditions

In programming, we refer to something that is either `true` or `false` as a **Boolean**.

A **condition** is something that evaluates to a Boolean. This can be as simple as a variable that holds a Boolean value:

```c#
bool playAgain = false
```

We can also use **comparison operators** to create a condition by comparing two values. The important comparison operators are:

* `==` equal to
  * Be careful not to mix this up with `=` which is used for **variable assignment**
* `>` greater than
* `>=` greater than or equal to
* `<` less than
* `<=` less than or equal to
* `!=` not equal

We can use them like so:

![Image of Comparison Operators in action](/images/Mod1/ConditionalLogic/ComparisonOperators.png)

You can also use the negation operator `!` (also known as a "bang") to reverse something from true to false. The "bang" will always return the opposite boolean of the boolean that is returned from a method or variable. I use the word `not` in my head in conjunction with the negation operator.

![Image of Not Operator](/images/Mod1/ConditionalLogic/NotOperator.png)

## `||` and `&&`

We can use the "or" operator `||` and the "and" operator `&&` to combine two conditions into a single condition. `||` evaluates to true if one of the conditions is true. `&&` evaluates to true if both are true:

![Image of And and Or Operators](/images/Mod1/ConditionalLogic/AndOrOperators.png)

**Instructor Note** Discuss the importance of putting a condition on either side of the operators - c# will not compile code unless you do this, but it is a common error!

# Conditional Branching

In programming, branching refers to a choice that is made depending on whether or not a condition is true or false. Think of branching as "choose your own adventure".

Examples:

- If a person is 16 or older, they can apply for a driver's license. (One branch)

```c#
if (age >= 16)
{
  Console.WriteLine("Head on down to the DMV!");
}
```

![inline](/images/Mod1/ConditionalLogic/if_condition.jpg)


- If you want to spend a lot of money for dinner, go to a fancy restaurant. Otherwise, cook at home. (Two branches)

```c#
if (spendThatMoney == true)
{
  Console.WriteLine("Go get a fancy dinner!");
}
else
{
  Console.WriteLine("Eat at home.");
}
```

![inline](/images/Mod1/ConditionalLogic/if_else_condition.jpg)


## `if`

All of our conditional branches will begin with an `if`. The code following the `if` will run if the condition is true.

```c#
if (condition)
{
  // code to execute if the condition evaluates to true
}
```

## `elsif`

Use an `else if` to create more branches.

```c#
if (condition1)
{
  // code to execute if above condition1 evaluates to true
}
else if (condition2)
{
  // code to execute if above condition2 evaluates to true
}
else if (condition3)
{
  // code to execute if above condition3 evaluates to true
}
```

## `else`

Code inside an `else` will run when none of the previous conditions are true.

```c#
if (condition1)
{
  // code to execute if above condition1 evaluates to true
}
else if (condition2)
{
  // code to execute if above condition2 evaluates to true
}
else if (condition3)
{
  // code to execute if above condition3 evaluates to true
}
else
{
    // code that will execute if none of the conditions above evaluate to true
}
```

## Other rules

* Conditional branches have exactly one `if`
* The `if` can be following by any number of `else if`s
* A conditional branch will have either zero or one `else`
* The `else` comes after the `if`/`else if`s
* Only one branch can be taken.
* Conditions are evaluated in order.

## Check for Understanding

What will the following code print to the screen?

```c#
var playAgain = true;
var lives = 3;
if (lives == 0)
{
    Console.WriteLine("You Lose!");
}
else if (!playAgain)
{
    Console.WriteLine("Game Over!");
}
else if (playAgain && lives > 0)
{
    Console.WriteLine("Welcome back!");
}
else
{
    Console.WriteLine("Invalid input.");
}
```

What values would `playAgain` and `lives` need to be assigned to in order to print each of the following to the console:
  * "You Lose!"
  * "Game Over!"
  * "Welcome back!"
  * "Invalid input."