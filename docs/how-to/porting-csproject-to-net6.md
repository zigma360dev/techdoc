# Porting Projects to .NET 6

This article provides an overview of what you should consider when porting your code from .NET Framework to .NET (formerly named .NET Core). Porting to .NET from .NET Framework for many projects is relatively straightforward. The complexity of your projects dictates how much work you'll do after the initial migration of the project files.

Projects where the app-model is available in .NET (such as libraries, console apps, and desktop apps) usually require little change. Projects that require a new app model, such as moving to ASP.NET Core from ASP.NET, require more work. Many patterns from the old app model have equivalents that can be used during the conversion.

## 1. Understand goals

* Understand if you need to port at all
  - Only port projects that you need to innovate in
  - Maintenance-only projects can safely remain on .NET Framework
* Make note of your desired target
  - .NET Core 3.1 vs .NET 6
  - Windows vs MacOS vs Linux
* Plan & ensure you have click stops
  - So that you can keep shipping working software

## 2. Inventory

* Inventory your code and its dependencies
  - Use **API Port** to do that
* Analyze your code for legacy
  - Maybe you can drop that before Porting
* Analyze your dependencies
  - Ensure they offer support for .NET 6

## 3. Convert projects

* Replace packages.config
  - With <PackageReference> elements in the project
* Migrate the project files to SDK-style
  - Use **Try-Convert** to automate this
* Consider only migrating the project files
  - and not changing the target framework yet
  - Click stops!

## 4. Move to .NET 6

* Understand your dependency graph
  - Identify if you have shared components that needs to continue to work on .NET Framework
  - Retarget those to .NET standard
* Retarget remainder to .NET Core 3.1 or .NET 6

## 5. Move to other OS

* If you want to go cross-platform:
  - Ensure you have a CI system that can support multiple legs
  - Azure DevOps, GitHub actions etc.
* Add a leg per operating system
  - And run tests!

## Example of migrating by try-convert

Open Windows PowerShell console and go to your solution.
Run this command to get list of all installed dotnet tools:

```
$ dotnet tool list -g

Package Id      Version      Commands
--------------------------------------
dotnet-ef       6.0.0        dotnet-ef
```

First install the microsoft.dotnet-interactive tool:

```
$ dotnet tool install -g microsoft.dotnet-interactive

You can invoke the tool using the following command: dotnet-interactive
Tool 'microsoft.dotnet-interactive' (version '1.0.260601') was successfully installed.
```

Then install the api-port and try-convert tools:

```
dotnet tool install -g apiport
```

```
dotnet tool install -g try-convert
```

To analyze the solution for compatibility with .NET Core run this command and you will get a report in the ApiPortAnalysis.xlsx file:

```
apiport analyze -f .
```

To convert you solution or project run this command:

```
try-convert -w .
```

Now you get `conversion complete!` and this means that your project or solution is successfully converted to .NET Core framework.
