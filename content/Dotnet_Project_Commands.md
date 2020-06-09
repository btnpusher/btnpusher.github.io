# Dotnet Project Commands

The following is a list of typical dotnet commands used to manage packages for
a project.

## Create a project folder

Create a solution folder and change into it

```sh
> mkdir MyProject
> cd MyProject
```

## Generate a solution file

```sh
> dotnet new sln -n MyLibrary
```
This command generates a solution file called __MyLibrary.sln__

## List all available dotnet project templates

```sh
> dotnet new
```
This command lists all the available project templates we can choose from to create a dotnet project

## Create a dotnet F# project based on a template

```sh
> dotnet new classlib -lang F# -n MyLibrary
> cd MyLibrary
```
This command creates a subfolder called __MyLibrary__ and creates a fsharp project file within it called __MyLibrary.fsproj__ based on the __classlib__ template

It will also create some other files based on the template specified

## Edit the target framework within the project file

Launch vscode and edit the Target Framework in the __MyLibrary.fsproj__ file

Change From
```xml
<TargetFramework>netstandard2.0</TargetFramework>
```
Change To
```xml
<TargetFramework>net461</TargetFramework>
```

## Add a reference to the project file within the solution file
```sh
> dotnet sln add "MyLibrary/MyLibrary.fsproj"
```

## You can reference one project within another 
If I had created a second project within the solution called __MyApi__ with its own __MyApi.fsproj__ file, I could include within that project file a reference to the other project
__MyLibrary.fsproj__ file like so...

```sh
> dotnet add "MyApi.fsproj" reference "MyLibrary/MyLibrary.fsproj"
```

## Add a nuget package to our MyLibrary project
```sh
> cd MyLibrary
> dotnet add package RevitApi2020
```

This command will add the latest version of the __RevitApi2020__ package to our project file

## List all currently installed packages including versions
```sh
> dotnet list package
```

## To add a specific package version
```sh
> dotnet add package RevitApi2020 --version 1.0.0
```

## To make sure all packages are correctly installed
```sh
> dotnet restore
```

## To build the project
```sh
> dotnet build
```
