![](images/_LegiTestBanner.png)

# How can I add custom assertions?



Sometimes the assertions in LegiTest don't quite allow you the flexibility that you want, and you want to write some C# code that adds some more logic to your tests. In order to do this, we can add code to the user file that LegiTest generates. There are four types of code that can be run:



- Before Test

- After Test

- Before Test Element

- After Test Element



For each of those, the following method declarations should be added to the user file.



```csharp
static partial void BeforeTest(string testName, Dictionary<string, object> testResources, ref bool cancel)
```

```csharp
static partial void AfterTest(string testName, Dictionary<string, object> testResources)
```


```csharp
static partial void BeforeTestElement(string testName, string elementName, Dictionary<string, object> testResources, ref bool cancel)
```


```csharp
static partial void AfterTestElement(string testName, string elementName, Dictionary<string, object> testResources)
```




Note that the 'before' methods have the 'cancel' parameter. This can be set to true within the body of the method, which would cancel the execution of the element.



For example, we might want to execute some code after an element called 'Execute Query (Grid)' in a test called 'Test 1' is run.



The method implementation might be similar to the following:



```csharp
static partial void AfterTestElement(string testName, string elementName, Dictionary<string, object> testResources)

{

    if (testName == "Test 1" && elementName == "Execute Query (Grid)")

    {

        if (!testResources.ContainsKey("ExecuteQuery(Grid)_TargetResourceKey"))

        {

            NUnit.Framework.Assert.Fail("There was no grid placed in the resources by the test element.");

        }

        var grid = (PragmaticWorks.Common.Sql.RowStoreGrid.IGrid)testResources["ExecuteQuery(Grid)_TargetResourceKey"];

        if (grid.RowCount < 100)

        {

            NUnit.Framework.Assert.Fail("We needed 100 or more rows to be returned from the execute query element.");

        }

    }

}
```



First, we check that the testName and the elementName are the ones we want. We can find these easily by searching for 'AfterTestElement' in the generated code file.



After this, we check that the test resources passed to us contains the item we want. We are using the 'Resource key' from the execute query (grid) configuration to identify the resource. If the resource is not present - we fail the test. This test was built with NUnit - so we are using NUnit.Framework.Assert.



Once we are sure we have the resource in place, we get it back as a local variable by casting it to the correct type. Grid resources are always of the type PragmaticWorks.Common.Sql.RowStoreGrid.IGrid.



We then check that the RowCount is 100 or more, and if not then we again fail the test.



> ![](images/_ImportNoteIcon.png) Important Note:
> 
> This code will not be automatically modified when you change the name of tests, elements or resource keys. Make sure that any changes are reflected in the user code.
