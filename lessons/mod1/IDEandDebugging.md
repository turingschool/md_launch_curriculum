# Using an Integrated Development Environment

## Learning Goals
* Define and start using an IDE
* Identify the benefites of using an IDE
* Practice Debugging with Breakpoints

## Warm Up

> Thinking back to what we learned about Computers and Programming, write down some ideas on why we have been using REPLit to create programs, rather than a text editor like Word, Docs, or Notepad?

## IDE
In order for our computers to execute code that we write, that code needs to be compiled, or built, into an executable program that a computer can understand.  We write programs in language that is easy for us, as humans, to read (in this course, we use c#), but that is not what is executed by computers directly.  Before a computer can understand the instructions of a program, our code needs to be transformed (compiled, or built) into computer language.  The important thing  to understand is that there are multiple steps happening in the background when we 'run' a program.

Think about the programs we have built in REPLit.  When we hit the 'Run' button, does anything happen immediately? No.  The REPLit program has to:
    1. Compile our code into an executable program.
    2. Tell its internal computer to execute (run) that program.

The good news is that we do not have to worry too much about all this 'behind the scenes' stuff because we have **Integrated Development Environments (IDEs)** that do this work for us. An IDE combines the activities of: editing code, building executables, and debugging.

REPLit is a very simple IDE.  Today, we are going to start working with a much more robust IDE - [Visual Studio](https://visualstudio.microsoft.com/free-developer-offers/)

### Downloading Visual Studio
We will follow these steps to download Visual Studio Community (a free IDE that is designed with C# in mind).

1. Go to [https://visualstudio.microsoft.com/free-developer-offers/](https://visualstudio.microsoft.com/free-developer-offers/)
2. Click `Free Download` for the Windows Visual Studio Community option
![](/images/Mod1/ideanddebugging/VisualStudioDownloadButton.png)
3. Click on the VisualStudioSetup.Exe file download
![](/images/Mod1/ideanddebugging/EXEfiledownload.png)
4. When asked if you want to allow this program to make changes to your computer, click 'YES'.
5. Follow the prompts of the download wizard to complete setup.  We will use all of the default settings.
6. When completed, you should see a screen like this (with fewer options on the left hand side)
![](/images/Mod1/ideanddebugging/VisualStudioDownloaded.png)

### .NET and Different Types of Programs
Now that we have our IDE downloaded, let's start by creating a new program.

![](/images/Mod1/ideanddebugging/CreateANewProject.png)

In REPLit, when we create a new project, all we do is select a language and we are good to go.  With the Visual Studio IDE, there is a bit more to it.

We first need to decide what **type** of program we are going to create. Up to now, we have created programs that allow us to interact with the **console**; in other words, we have created **Console Applications**.  We will continue working with Console Applications for now, but you can see there a lot of different types of programs we could choose from: ASP.NET Core Web App, Blazor Server App, ASP.NET Core Web API, etc...

#### .NET
Many of these program types reference [.NET](https://dotnet.microsoft.com/en-us/learn/dotnet/what-is-dotnet-framework).  .NET is a **framework** and **Common Language Runtime** for developing lots of different types of applications.

A **Framework** is a developer tool that give us additional classes and methods that would not exist in plain c#.

A **Common Language Runtime (CLR)** is the engine that handles running applications. CLRs translate the code that we write into Machine Code (ones and zeros).  The .NET CLR can handle C#, F#, and Visual Basic Code.  We will continue to code in C#, but it is good to understand that there are other options available to us!

![Diagram of .NET CLR](/images/Mod1/ideanddebugging/NET-CLR.png)

Let's go back to our Visual Studio, select `Console App`, and click `Next`.

![](/images/Mod1/ideanddebugging/ChooseANewProject.png)




## Debugging

## Checks for Understanding