![](images/_LegiTestBanner.png)

# How can I initialize a value once per run?



### One-Time Initialization for Values



Sometimes we may want a parameter to apply to all groups / tests in an assembly, and initialize it dynamically once per run. In order to do that, we use some custom code. To achieve this, we will add a new file to our project by right-clicking on the project in Solution Explorer, and clicking Add -> Class... In this example we name the file 'OneTimeInitialization'.



Within this file, we define the parameters that we'd like to initialize once only - in this example we have ProcessingDate that we derive from a database and FileCount that represent the count of files in a particular directory.



```csharp
using PragmaticWorks.LegiTest.Runtime;

using System;

using System.Data.SqlClient;

using System.IO;



namespace LegiTestProject

{

   static class OneTimeInitialization

   {

       public static Lazy<object> ProcessingDate { get; } = new Lazy<object>(LoadProcessingDate, true);



       static object LoadProcessingDate()

       {

           var parameterProvider = new ParameterProvider(Guid.Empty, typeof(OneTimeInitialization));

           using (var connection = new SqlConnection(parameterProvider.GetTypedParameter("SystemConnection", string.Empty)))

           {

               connection.Open();

               using (var cmd = new SqlCommand("SELECT MAX(LastProcessedDate) FROM dbo.ProcessTracking", connection))

               {

                   return cmd.ExecuteScalar();

               }

           }

       }



       public static Lazy<object> FileCount { get; } = new Lazy<object>(LoadFileCount, true);



       static object LoadFileCount()

       {

           var parameterProvider = new ParameterProvider(Guid.Empty, typeof(OneTimeInitialization));

           return Directory.GetFiles(parameterProvider.GetTypedParameter("WorkingPath", string.Empty)).Length;

       }

   }

}
```



Here we have two properties 'ProcessingDate' and 'FileCount' - both of type Lazy<object>. This is a system type that supports loading a value once and once only. There are also methods - one for each property - that are run once to initialize the object the first time it is requested.



We are using parameters defined in the test suite 'SystemConnection' and 'WorkingPath'. In order to do this we need to create a parameter provider:



```csharp
var parameterProvider = new ParameterProvider(Guid.Empty, typeof(OneTimeInitialization));
```




We can then get the value of the parameter by calling the 'GetTypedParameter' method:



```csharp
parameterProvider.GetTypedParameter("WorkingPath", string.Empty)
```




In the examples above, LoadProcessingData connects to the SQL Server using the connection string defined in the 'SystemConnection' parameter, and then we run the query to select the MAX value of LastProcessedDate from the dbo.ProcessTracking table. The LoadFileCount method gets a list of the files from the directory defined in the 'WorkingPath' parameter and returns the count.



### Using the Initialized Values in Tests



In order to use these one-time values in our tests, we use the 'BeforeTest' method to set the values into the resources. Note that we need to do this in each group where we want to use those values. To do this, we copy content similar to the following into the user file generated for each test group:



```csharp
namespace LegiTestProject.TestGroup1_Output

{

   using System.Collections.Generic;

       

   // This file provides a point at which partial methods can be implemented to augment tests.

   // The content of this file is preserved when the test suite is regenerated.

   public partial class TestGroup1

   {

       static partial void BeforeTest(string testName, Dictionary<string, object> testResources, ref bool cancel)

       {

           testResources["ProcessingDate"] = OneTimeInitialization.ProcessingDate.Value;

           testResources["FileCount"] = OneTimeInitialization.FileCount.Value;

       }

   }

}
```



This code makes the one-time values available as a resource to the test, and they can be referenced like a parameter, using the {{resourceName}} syntax. For example, if you wanted to use the ProcessingDate value in a SQL query, you would enter the query as:



```sql
SELECT * FROM [MyTable] WHERE [LastModifiedDate] >= '{{ProcessingDate | date:"yyyyMMdd"}}'
```




Using this approach, you can set up and use values that are initialized once and only once throughout your test suite. For more information on using resources and parameters please refer to the [Using Parameters](UsingParameters.md) section.

