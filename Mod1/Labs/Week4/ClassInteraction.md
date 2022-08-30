Lab Objectives
* Reinforce Creating Classes that have a collection of Objects
* Practice using object methods within other class methods.

** Instructor Notes ** Before the lab, prepare groups of 2/3 students and post to slack. Today's lab will be heavy on the practice side.  Plan to bring the group back together partway through the practice section to answer any questions and cover common misunderstandings (from your observations in breakout rooms.)

## Practice
To re-inforce the concept of object interaction, and classes including references to other classes, let's build on the Library exercise from todays [warmup](/Mod1/Lessons/Week4/ClassInteraction.md#warm-up).

In small groups, create a new Console app called DenverLibrary. In this project, create the following classes:

![Image of three class diagrams with required Properties and Methods](/Mod1/Images/Week4/LibraryUML.png)

A `Book` should have two properties that are set on instantiation: string Title, and string Author.  Other than a constructor, `Book` does not need any methods.

A `Branch` represents a location in the library system, like ["Central Library"](https://www.denverlibrary.org/content/central-library), or ["John "Thunderbird Man" Emhoolah, Jr. Branch Library"](https://www.denverlibrary.org/thunderbird-man-branch-library).  A branch should have one property that is set on instantiation: string Name.  The branch constructor should also create an empty `List<Book>` assigned to the Property Books. In addition to these to properties, a Branch should be able to add a book to it's Books, and provide a `List<string>` of all authors represented at that branch.

A `Library` represents a city-wide library, like ["Denver Public Library"](https://www.denverlibrary.org/).  A library should have one property that is set on instantiation: string Name.  The library constructor should also create an empty `List<Branch>` assigned to the Property Branches. In addition to these to properties, a Library should be able to add a branch to it's Branches.  A Library should also be able to provide a `List<string>` of the names of all it's branches, as well as a `List<string>` of the titles of all of the books contained within all of its branches.

When complete, the following code should be able to be run in `Program.cs`.

```c#
using DenverLibrary;

var hungerGames = new Book("The Hunger Games", "Suzanne Collins");
var catchingFire = new Book("Catching Fire", "Suzanne Collins");
var mockingjay = new Book("Mockingjay", "Suzanne Collins");
var faultyStars = new Book("The Fault In Our Stars", "John Green");
var mockingbird = new Book("To Kill a Mockingbird", "Harper Lee");

var centralLibrary = new Branch("Central Library");
centralLibrary.AddBook(mockingbird);
centralLibrary.AddBook(mockingjay);

var thunderbirdMan = new Branch("John \"Thunderbird Man\" Emhoolah, Jr. Branch Library");
thunderbirdMan.AddBook(faultyStars);
thunderbirdMan.AddBook(catchingFire);
thunderbirdMan.AddBook(hungerGames);

List<string> centralAuthors = centralLibrary.AllAuthors();
// { "Harper Lee", "Suzanne Collins" }

List<string> thunderbirdAuthors = thunderbirdMan.AllAuthors();
// { "John Green", "Suzanne Collins", "Suzanne Collins" }
// Note: it is possible to return a list of *unique* authors, but you do not have to focus on that particular problem now :) 

var denverPublicLibrary = new Library("Denver Public Library");
denverPublicLibrary.AddBranch(centralLibrary);
denverPublicLibrary.AddBranch(thunderbirdMan);

List<string> branchNames = denverPublicLibrary.BranchNames();
// { "Central Library", "John \"Thunderbird Man\" Emhoolah, Jr. Branch Library" }

List<string> allBooksTitles = denverPublicLibrary.AllBooks();
// { "To Kill a Mockingbird", "Mockingjay", "The Fault In Our Stars", "Catching Fire",  "The Hunger Games" }
```

**Keep nn Eye on Slack!** We will be coming back together a few times to answer questions and any common issues that are coming up.

## Preparation

Individually, spend 10-15 minutes reflecting on the following questions. Take notes on your reflection to share out in tomorrow's lesson warm-up.

* Up to now, how have you known if your code was functioning?
* Imagine you are a developer working at Google; what might be some drawbacks to your current approach?

