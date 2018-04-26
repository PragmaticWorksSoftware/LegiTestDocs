![](images/_LegiTestBanner.png)

# Project Organization



LegiTest projects are basically C# projects and are organized very similarly. There are a few different types of file that can be added and are handled specially within LegiTest projects:



- LegiTest group (.legitestGroup)

    These files define a single LegiTest group. LegiTest, in previous releases, used suite files (.legitest) which contained many groups. To allow a better organization of projects the group files were added. This has particular benefits for any teams using source control. With groups in individual files it becomes much less likely that a complicated merge is required when more than one person is working on a project. A group file will emit a single C# class that contains the tests that are defined.



- LegiTest settings file (.legitestSettings)

    Settings files come in two types - settings and project settings. Settings files contain parameters and their values - and there can be more than one if desired. For more information on settings files see the help topic [here](SettingsFilesAndGlobalParameters.md). A project can only contain one project settings file - and the project settings file defines both the [server that the project is associated with](IntegratingWithLegiTestServerOrL.md) and the [test framework type](ChoosingATestFramework.md).



- Asset file (.asset)

    Asset files are used to define assets that are generally useful across multiple groups / suites. They are the same as assets defined within suites / groups / tests but defined at the project level. This gives the benefit that they are easier to change in isolation (i.e. changing one asset doesn't mean that the suite / group file has to be check in to source control) and they give us a better way to organize the data within our projects. More information on assets can be found [here](AssetsActionsAssertsAndResources.md) and [here](Assets.md).



> ![](images/_tip.png) Helpful tip:
> 
> Folders in the solution can be used to group all types of item together. A large testing project with many groups, assets and settings can become hard to manage unless it is well organized.
