# F# General Notes

## Add path to environment variables

so that you can run __fsi.exe__ from terminal, add this path to windows environment variables:

### Visual Studio 2017 Path

> C:\Program Files (x86)\Microsoft Visual Studio\2017\Professional\Common7\IDE\CommonExtensions\Microsoft\FSharp

## Convert a directory into an F# Project

Make a project directory (using PascalCase naming conventions), and change into that directory:

```sh
> mkdir MyProject
> cd MyProject
```

To convert a directory into an F# project directory, just run this in terminal:

```sh
> dotnet new <template> <switches>
```
Examples:

```sh
> dotnet new console -lang F#
> dotnet new classlib -h
```

## Templates

| template | description              |
|----------|--------------------------|
| console | Console Application - (compiles to .exe) |
| classlib | Class library - (compiles to .dll) |
| mstest | Unit Test Project |
| nunit | NUnit 3 Test Project |
| nunit-test | xUnit Test Project |
| web | ASP.NET Core Empty |
| mvc | ASP.NET Core Web App (Model-View-Controller) |
| webapi | ASP.NET Core Web API |

## Common Switches

| switch | description |
|--------|-------------|
| -h | help |
| -lang | (F#, C#, VB) |
| -f | (Target Framework) |

## Target Framework

| target framework | description |
|------------------|-------------|
| netstandard2.1 | .NET Standard |
| netcoreapp3.1 | .NET Core |
| net461 | .NET Framework |
| netcore451 [win81] | Windows Store |
| netmf | .NET Micro Framework |
| wpa81 | Windows Phone |
| uap10.0 [win10] [netcore50] | Universal Windows Platform |


## Build Your Project

To build/compile your project, use:

```sh
> dotnet build
```

## Run Your Executable Project

If your project is of an executable type like console then use:

```sh
> dotnet run
```

