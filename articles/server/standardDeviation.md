# Database Column Standard Deviation

The Database Column Standard Deviation checks the standard deviation of values within a database table column.

![standard deviation recipe](images/standardDeviation.png)

* __Name__ - Name to give the assembly that will contain the test generated from the recipe.
* __Test Framework__ - The test framework the test will be created with. Can select from NUnit 2, NUnit 3, or MSTest.
* __Remote Agent__ - Selecting a remote agent is optional. If a remote agent is selected, then the connection string supplied will apply to the machine running the remote agent.
* __Select a Provider__ - The provider for the connection string.
* __Connection String__ - Connection string to the data source.
* __Table__ - Once the provider and connection string are set, this drop down will show all available tables found.
* __Standard Deviation Column__ - The column to calculate standard deviation on.
* __Grouping Columns__ - Columns from the selected table. Choose which columns to group on.
* __Max Standard Deviation__ - Standard deviation limit to check against.