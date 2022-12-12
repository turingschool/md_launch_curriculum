# Week 2 Checks for Understanding

With your group, answer each question below.  Spend some time discussing each question _without_ using any resources; use your own recall of the topics covered this week.  If, after you have discussed without resources, your group needs assistance, use the raise hand feature and an instructor will come help!

1. Define the following terms:
    * Loop
    * Iteration
    * Infinite Loop
1. Annotate the code below.  What is happening on each line?
    ```c#
    string userInput = "";
    int index = 0;

    while (userInput != "stop" && index < 101)
    {
        Console.WriteLine($"Current Count is: {index}");
        index++;
        Console.WriteLine("Enter to continue counting, 'stop' to exit");
        userInput = Console.Readline();
    }

    if (index > 100)
    {
        Console.WriteLine("I don't know any more numbers");
    }
    else
    {
        Console.WriteLine($"Thanks for letting me count to {index}");
    }
    ```
1. How many **code blocks** are in the example above?
1. Write a **for loop** that will ask a user for 10 items to put on a wish list.  Store these items in a string called `wishList`.
1. Visual Studio is an IDE.  In your own words, what is an IDE?
1. Spend 1 minute googling to see if you can find any other IDEs. How many others did you find?
1. Imagine you are chatting with your 10 year old niece about what you are learning at Turing.  How would you explain to them what a **bug** is?
1. What is a **breakpoint**, and why would we use one?
1. The code below has a bug; where would you put a breakpoint to start debugging what might be happening (feel free to recreate this code in Visual Studio and try running it 🙂)
```
// This program should print an abbreviated version of a kids song to help them learn the numbers 1 to 20.  The song should display every number, and never go above 20.

1  Console.Write("First comes: ");
2  
3  for (var i = 0; i < 20; i++)
4  {
5      Console.WriteLine(i);
6      Console.Write("then comes: ");
7  }
8  Console.WriteLine("And that's how you count to 20!");
9
```

