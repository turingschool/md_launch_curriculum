# Introduction to MVC

https://docs.google.com/presentation/d/1YKc7fF2SyeWJUmmw2Elw4HujCgkRUVbwuE9SXzimqdo/edit?usp=sharing

## Learning Goals
* Identify the elements of the MVC design pattern
* Describe the single responsibility of each of the Model, View, and Controller
* Build our first ASP.NET MVP Application

### Building and Running The Starter Project
TODO Instructor Note: Make sure students don't select the template just titled `asp.net core web app` without the MVC at the end, that uses Razor Pages

TODO: Insert first image here of selecting project

Visual Studio has now used the template to create a fully working app! We will build off of that starter project.

But first, let's run this starter project.

Click outlined "play" button to "Start Without Debugging". You will probably see the following confirmations

TODO Insert second image here

Visual Studio runs the app and opens it in the default browser. You should see a page that says "Welcome
Learn about building Web apps with ASP.NET Core."

<!-- TODO, how much to talk about ports. Should that also come in http lesson? -->
The address bar shows localhost:<port#>. Localhost means the application is running on your local computer. When Visual Studio creates a web project, a random port is used for the web server.

### Adding a Controller

Controllers are Classes that
* Handle browser requests.
* Retrieve model data.
* Call view templates that return a response.

TODO: Third image here

using Microsoft.AspNetCore.Mvc;
using System.Text.Encodings.Web;

Replace the contents of Controllers/HelloWorldController.cs with the following code:
```C#
namespace MvcMovie.Controllers
{
    public class HelloWorldController : Controller
    {
        // 
        // GET: /HelloWorld/

        public string Index()
        {
            return "This is my default action...";
        }

        // 
        // GET: /HelloWorld/Welcome/ 

        public string Welcome()
        {
            return "This is the Welcome action method...";
        }
    }
}
```

Every public method in a controller is callable as an HTTP endpoint. In the sample above, both methods return a string.

An HTTP endpoint:
* Is a targetable URL in the web application, such as https://localhost:5001/HelloWorld.

Combines:
* The protocol used: HTTPS.
* The network location of the web server, including the port: localhost:5001.
* The target URI: HelloWorld.

In your browser, navigate to https://localhost:{PORT}/HelloWorld.
     <!-- add fourth image here, browser with url -->
❓How can we get "This is the Welcome action method..." to show up in our browser?

<!-- TODO, lesson in the future talking about path parameters??? -->

<!-- TODO, maybe a lab like section here of students practicing taking in data via parameters and sending back in the string??? -->

### Adding a View

In this section, you modify the HelloWorldController class to use Razor view files.

View templates are created using Razor. 

<!-- TODO, open question, do we introduce Razor the day before in addition to interfaces? -->
Razor-based view templates:
* Have a .cshtml file extension.
* Provide an elegant way to create HTML output with C#.


Currently, the Index method returns a string with a message in the controller class. In the HelloWorldController class, replace the Index method with the following code:

```C#
public IActionResult Index()
{
    return View();
}
```

This will use the view template that corresponds with this controller to generate an HTML response.

#### Add a View

<!-- Add Image here of creating a view -->

Replace the contents of the Views/HelloWorld/Index.cshtml Razor view file with the following:

```C#
@{
    ViewData["Title"] = "Index";
}

<h2>Index</h2>

<p>Hello from our View Template!</p>
```

Navigate to `https://localhost:{PORT}/HelloWorld`:

The `Index` method in the `HelloWorldController` ran the statement `return View();`, which specified that the method should use a view template file to render a response to the browser.

A view template file name wasn't specified, so MVC defaulted to using the default view file. The default view has the same name as the action method, `Index` in this example. The view template `/Views/HelloWorld/Index.cshtml` is used.

<!-- Add image here -->

<!-- TODO, how to get hot reloading??? I have to restart the app to get changes -->

<!-- TODO, changing the layout stuff could be lab time practice? Not necessary for the lesson: https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-mvc-app/adding-view?view=aspnetcore-6.0&tabs=visual-studio#change-views-and-layout-pages -->



Change the title and <h2> element as highlighted in the following:
<!-- Todo: make this a student challenge with a dropdown -->

```C#
@{
    ViewData["Title"] = "Movie List";
}

<h2>My Movie List</h2>

<p>Hello from our View Template!</p>
```

<!-- TODO, maybe student practice with putting in Razor view template stuff? -->


<!-- How does the title get onto the page, that's part of the layout you will look into that during lab time. -->

<!-- ### Passing Data from the Controller to the View

TODO, do we want to show passing data via ViewData or skip right to the model? -->

## Adding a Model

These model classes are used with Entity Framework Core (EF Core) to work with a database.

### Add a data model class
<!-- Todo, add image here -->

Update the Models/Movie.cs file with the following code:

```C#
using System.ComponentModel.DataAnnotations;

namespace MvcMovie.Models
{
    public class Movie
    {
        public int Id { get; set; }
        public string? Title { get; set; }

        [DataType(DataType.Date)]
        public DateTime ReleaseDate { get; set; }
        public string? Genre { get; set; }
        public decimal Price { get; set; }
    }
}
```

<!-- Todo, cut some of this, what's important?? -->
The Movie class contains an Id field, which is required by the database for the primary key.

The DataType attribute on ReleaseDate specifies the type of the data (Date). With this attribute:

The user isn't required to enter time information in the date field.
Only the date is displayed, not time information.
DataAnnotations are covered in a later tutorial.

The question mark after string indicates that the property is nullable. For more information, see Nullable reference types.

#### Add NuGet packages

<!-- TODO, not using image here installing packages. -->
`From the Tools menu, select NuGet Package Manager > Package Manager Console (PMC)`

```
Install-Package Npgsql.EntityFrameworkCore.PostgreSQL
<!-- Install-Package Microsoft.EntityFrameworkCore.Design -->
```
Make sure to install version 6 not version 7!

<!-- Todo, why is it still connecting to SQL server DB? -->

#### Scaffold Movie Pages

<!-- TODO, when do we talk about dependency injection, it's key to understanding how the parts connect and how the DBContect gets into the controller, but is too much for this lesson. -->




Add-Migration InitialCreate
Update-Database

<!-- Scavenger hunt for familiar parts? Where is db connection string. Where is context? -->

### How are The Model, View, and Controller Connected?

Controller is passing model data into the View.

Controller, tells what view to send back. Have students find where that happens.

View is using the data from the model in displaying content.



Back to the powerpoint, try to draw out what's going on with the file names in the picture.
