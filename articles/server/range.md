# Database Column Range Check

The Database Column Range Check checks the values within a specific database table column are within a defined range. 

![range recipe](images/rangeRecipe.png)

* __Name__ - Name to give the assembly that will contain the test generated from the recipe.
* __Test Framework__ - The test framework the test will be created with. Can select from NUnit 2, NUnit 3, or MSTest.
* __Remote Agent__ - Selecting a remote agent is optional. If a remote agent is selected, then the connection string supplied will apply to the machine running the remote agent.
* __Select a Provider__ - The provider for the connection string.
* __Connection String__ - Connection string to the data source.
* __Table__ - Once the provider and connection string are set, this drop down will show all available tables found.
* __Columns__ - Once a table is selected, the columns will be populated. Select the column check range rules against.
* __Minimum Value__ - Minimum accteptable value to be in the selected column.
* __Maximum Value__ - Maximum acceptable valye to be in the selected column.