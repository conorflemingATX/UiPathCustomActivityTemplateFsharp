# UiPathCustomActivityTemplateFsharp

This is a template for creating custom activities for use with UiPath using F# and the dotnet core toolset.

## Important Commands

To ready the package for use as a local package within UiPath studio, use:

```powershell
cd TemplateActivity
dotnet pack -o "$($env:LOCALAPPDATA)\UiPath\app-<UIPATH STUDIO VERSION>\Packages
```

Assuming that the PackageId which has been referenced in the TemplateActivity.fsproj file contains the word Activities, then the Custom Activity should be available to be installed into a library or process.