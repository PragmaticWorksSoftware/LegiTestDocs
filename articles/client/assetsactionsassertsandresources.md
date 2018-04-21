![](images/_LegiTestBanner.png)

# Assets, Actions, Asserts and Resources



Four key concepts in LegiTest are Assets, Actions, Asserts and Resources.

### Assets


Assets are items that are created at design time and used at runtime. So, for example, you might have a query or a reference to an SSIS package. These items are configured when you are creating tests and used when the tests run. There are many different types of asset available in LegiTest and you can read about those in the [Assets](Assets.md) section. Assets can also use parameters - so you may want to configure a connection string using the parameter system. Note that parameters are evaluated at the point that the asset is used.



Assets can either be part of a test suite / group or part of the test project itself. To add an asset to the project, right click on the project node in solution explorer and click Add -> LegiTest Asset... Project-level assets can be placed in subfolders of the project to aid in organization, but this doesn't affect their use. Assets at the project level are available to all test suites / groups, irrespective of what folder they are placed in. Assets that are defined within a test suite / group can only be used within that suite / group. Additionally, assets defined at the test level may only be used by that test.

### Actions


Actions produce some kind of outcome. For example they may execute a query to return a row count, process a cube, or execute a package. When an action returns information, such as a row count or data set (aka a grid), it is stored in a [resource](AssetsActionsAssertsAndResources.md). Actions will often use assets or resources as part of their input (for example, an action to load a grid will use a connection asset and a query asset - an action to filter a previously loaded grid will use the resource).



Actions can be placed in any of the execution areas except for the assert section - so they can be used for set-up and teardown at both the group and test level.



For the list of available actions, please see the [Actions](Actions.md) topic.

### Asserts


Asserts are used to test the results of actions. For example, we might use an integer assert to compare the result of a query action which returns a row count with some predetermined value. Asserts will compare the values in resource keys to each other, or to a static value entered into the Assert. A test which doesn't contain any asserts will always yield an 'Inconclusive' result - so it is important to make sure that all your tests actually include an assert to determine whether the test passed or failed. Asserts can only be placed in the assert section of a test.



For the list of available assertions, please see the [Asserts](Asserts.md) topic.

### Resources


Resources are items that are available only at runtime. So, for example, when you execute a query you may get a result back which you wish to compare. Resources are referred to by their 'resource key' which is a string that uniquely identifies that resource. Resources are usually loaded by actions (the exception being [data driven testing](DataDrivenTesting.md)) and can be referenced by other actions or assertions. You can view dependent elements for any element - which shows the elements that follow and use the resource(s) generated.



When data driven testing is being used - additional resources are available - one for each column of data used as the data source. For more information on this, please see the [data driven testing](DataDrivenTesting.md) section.



Resources can also be used in place of parameters by elements that follow them. So, for example, an execute scalar query might get back a resource called 'CutOffDate' - a query might then follow where the query is defined similarly to:



```sql
SELECT OrderId FROM Orders WHERE OrderDate > '{{CutOffDate}}'
```




Because parameters are evaluated when an asset is used, the resource 'CutOffDate' would be included in the query and used as a filter.

