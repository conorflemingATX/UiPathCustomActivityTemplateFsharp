# UiPathCustomActivityTemplateFsharp

This is a template for creating custom activities for use with UiPath using F# and the dotnet core toolset.

## Important Commands

To ready the package for use as a local package within UiPath studio, use:

```powershell
cd TemplateActivity
dotnet pack -o "$($env:LOCALAPPDATA)\UiPath\app-<UIPATH STUDIO VERSION>\Packages
```

Assuming that the PackageId which has been referenced in the TemplateActivity.fsproj file contains the word Activities, then the Custom Activity should be available to be installed into a library or process.

## Next Steps

1. Add a new namespace above the main TemplateActivity which will contain the business logic for the activity, and add some small function that is testable and can be seen using the activity in UiPath.

2. Set up testing within the TemplateActivityTests project to use FsUnit and FsUnit typed.

3. Run the test command and note the test command with the relevant dotnet watch context in the README.

4. Set up the build on the TemplateActivity project to use conditions on the ItemGroups so that the netcore version uses corewf, and so could be run within dotnet core, at least in theory, and for the net461 version of the build to use the proper reference assemblies from the framework.