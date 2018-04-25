![](images/_LegiTestBanner.png)

# How can I migrate from suites to groups?



Starting with the 2017.4 release, the concept of individual groups was added to LegiTest, and is now the preferred method of implementing tests. There are several advantages to this approach:



- Because a smaller set of tests exists in a single file, conflicts between developers are reduced

- Similarly, source control is easier to manage

- Assets can be created at the project level and shared more widely

- Parameters become project level concerns and are easier to manipulate across a wider range of functions



In order to migrate to individual groups, right click on a LegiTest suite within solution explorer and click 'Migrate to individual groups...'



> ![](images/_ImportNoteIcon.png) Important Note:
> 
> It is always a good idea to ensure you have a backup before perfoming any sort of migration.
