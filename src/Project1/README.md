# Project 1

# Summary
Open the Project 1 using Visual Studio and Learn about the Visual Studio IDE (Integrated Development Environment) and the composition of a visual studio solution.  Some basic C# programming topic will also be covered.

# Pull the lastest update from the remote Repo
1. Run Git Bash
1. Set your current folder to `/c/github/learning`
1. You are now in the Learning Repo and your current branch should be your name.
1. Pull the lastest update from the github.com
    * Command: git pull

# The Solution
* Read: [Visual Studio Wiki Page](https://en.wikipedia.org/wiki/Microsoft_Visual_Studio)
* Double click on the file `/c/github/learning/src/Project1/Learning.sln`
    * Visual Studio 2017 should launch.  If it is the first time, it might prompt you to login.  Use the outlook email credential to login.  You can also login using the button on the upper right corner.
    * ![Figure 1: Visual Studio Solution](../../images/project1_solution.jpg)
* Observe: The solution tab within Visual Studio.
    * The Learning.sln file is a visual studio solution.
    * A solution file can contain many projects.
    * Currently there is only one project - Project1
        * If you open the folder: `/c/github/learning/src/project1`, you can find the project file with the extension of .csproj.
* A project represents a program.  There are different kinds of programs.  Some are Web programs served by a web server, others are console programs that can be executed on a shell.
    * Project1 is a console program.

# The Project
A project can contain many files.  Different files have different purposes.

* README.md file - That's this file!  md stands for Mark Down.  It is a popular file format used to create documents.  It is widely adopted by many web sites and companies.  Here is a guide for [Github Markdown](https://guides.github.com/features/mastering-markdown/).
* Dependencies - A group of files that are required for this project to function properly.
* Properties - Project settings and configurations;  Something that will be visited later.
* Program.cs - The Source code.  This is where you write your program.  
    
# The Source Code
A project could have many source code files.  Let's take a look at the Program.cs file

```csharp
//This is a comment; comment is created by leading double slashes
/* 
this is also a comment;
The comment section can be multiple lines
*/

// multiline comment can be created by using /* and */
// however, It is standard to use leading // for all comments.

//the souce code is referencing the System module.
using System;

//this is the namespaces
namespace Project1 {

    //this is the class
    public class Program
    { 
        //this is a method
        static int Main(string[] args) {
            Console.WriteLine("Hello World!");
            return 0;
        }
    }
}
```
## The structure of a C# source file
A C# source code file (files with .cs extension) will always have the following structure.
```csharp
//References
using Reference1;
using Reference2;
using Reference3;
//Namespace
namespace Company.Project{
    //Class
    public class Class1{
        ...
    }
    //Class
    public class Class2{
        ...
    }
}
```
* There is no restriction on how many namespaces or how many classes a source file can have.  But for the sake of clarity, each source file typically contains one class.
* It is OK to have a class without a namespace.
* It is OK to put references inside the namespace and before the class declaration.

## The Names
When it comes to programming, lots of names are used.  Meaningful names are important because it makes the program easier to read.  In most languages, names should be made of alphanumeric plus the underline characters.  The first character of a name cannot be numeric.  So here are some examples
```
//legal names
cat, _cat, CAT, Cat, cat0, _cat_0, _cat0_,

//illegal names
0cat, _ cat, cat^, cat_%, cat paw
```
## The scopes
A scope is a block of code.  Indicated by a pair of curly bracket: {}.
* Scopes are often encapsulated.
* A scope can be on its own.  The code below is perfectly OK.
    ```csharp
    {
        int i = 4;
        Console.WriteLine(i);
        {
            string s = "test";
            Console.WriteLine(s);
        }
    }
    ```
* But typically, a scope is associated with a function.
```csharp
namespace TestNameSpace{    //namespace scope
    public class TestClass{     //class scope
        public void TestMethod(){      //method scope
            ...
        }
    }
}
```
## Namespaces
Namespace is a way to organize your code.  It can be delimited using dot.  This is a legal namespace: `CompanyName.ProjectName`.  Please read this [article](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/namespaces/index) about namespaces.

## Classes
Class is a construct that enables you to create your custom types.  Please read this [article](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/classes).

## Method
Method is a code block that contains a series of statements.  A C# program does all of its work by running its methods.

# Build the Program
To get the program working, it will have to be built.  During the build process, the computer will analyse your code and check for errors.  If everything is fine, it should produce an output file that can run.

Start the build process by right clicking on the project and click "Build".  You can also type Ctrl-Shift-B on your keyboard or use the Build menu item on the top.  
* Observe: 
    * The output panel docked at the bottom of the window should be showing a series of build activities.
    * The errors panel should pop up as well.  It should have 0 error and 0 warning.  
    * Once the build is completed, its output can be found in this folder: `/c/github/learning/src/project1/bin/debug/net462/`.  
    * Open the folder and find the program output.  It should be:
        * Project1.exe - this is the exe file, this is the file that can be run.
        * Project1.pdb - this is a symbol file.

# Execute the output
* Using your bash shell, execute the your output by typing this command: `/c/github/learning/src/project1/bin/debug/net462/Project1.exe`.
* A quicker way to run your program is to press: Ctrl-F5 using Visual Studio.

# Exercise
## Make some changes
* Change the name of the class.
* Change the name of the namespace.
* Build and run again to see if you break anything.
* Change the name of the Main method.
    * Did this break something?
    * Where do you find the errors?
        * Both the output window and the errors window show the same error.  Which one do you prefer?
    * Could you find out why using google?
        * a good way to research is to google the error message.
        * [stackoverflow.com](http://stackoverflow.com) is a very good resource for programming.
    * Fix the error by changing the method name back to Main.
* Change the "Hello World" to something else.
    * Build and run to see if your changes work.

## Commit your change and push it to the cloud
* Remember how to push your changes to your remote repo from the last lesson?
    * if not, you can always find the instructions here [Make a change](../../README.md#make-a-change)

