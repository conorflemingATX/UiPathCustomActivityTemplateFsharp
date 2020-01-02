# UiPathCustomActivityTemplateFsharp

This is a template for creating custom activities for use with UiPath using F# and the dotnet core toolset.

## Important Commands

To ready the package for use as a local package within UiPath studio, use:

```powershell
cd TemplateActivity
dotnet pack -o "$($env:LOCALAPPDATA)\UiPath\app-<UIPATH STUDIO VERSION>\Packages
```

Assuming that the PackageId which has been referenced in the TemplateActivity.fsproj file contains the word Activities, then the Custom Activity should be available to be installed into a library or process.

Testing is pretty straight forward,

From the root directory:

```powershell
dotnet test
```

or with dotnet watch in effect:

```powershell
dotnet watch --project .\TemplateActivity test .\TemplateActivityTests
```

From the TemplateActivity directory you can omit the project parameter for the watch, and from the test directory you can omit the argument after test.

---

P.S I had attempted to run a conditional build using the corewf package for System.Activities and having the net461 version build with the reference assemblies, but this didn't go very well. I may attempt it again for curiosity's sake, but I'm not really attempting to run the code activity using the core runtime anyway. In theory it would make it more testable, but the solution, and much better option from a separation of concerns perspective anyway is to include as little business logic as possible within the CodeActivity and reduce the execute method to simply passing the arguments to a function from the Lib module and assigning the result to OutArguments.