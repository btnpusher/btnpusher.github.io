# Guides

[The F# Compiler Technical Guide](https://fsharp.github.io/2015/09/29/fsharp-compiler-guide.html)

[The F# Language Specification](https://fsharp.org/specs/language-spec/)

[Get Started with F# in Visual Studio Code](https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-vscode)

[F# Language Reference](https://docs.microsoft.com/en-us/dotnet/fsharp/language-reference/)


# Setup Visual Studio 2017 for F#

1) First fully update Visual Studio 2017, (the option's in the VS-Help Menu).

2) Install the Visual Studio Setup PowerShell Module

    ```http
    Install-Module -Name VSSetup
    ```

3) Download the powershell script from here:

    ```http
    https://raw.githubusercontent.com/Microsoft/visualfsharp/master/scripts/Install-VisualFSharpNightly.ps1
    ```

4) Run the powershell script with the -Quiet switch to install the VSIXInstaller:

    This will first uninstall the F# that ships with Visual Studio

    ```http
    .\Install-VisualFSharpNightly.ps1 -Quiet
    ```

5) Done.