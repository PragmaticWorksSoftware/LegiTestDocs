![](images/_LegiTestBanner.png)

# Parameter Replacement Methods



Elements, Assets and Assertions within LegiTest can use parameters in one of three replacement methods



- Direct Property Replacement: Users can map a parameter to a property within the test suite / group

- Parameter Token Replacement: Users can insert tokens within a property value. When using this method, LegiTest interprets these as a parameter.



```sql
{{ParameterName}}
```




- Environment Variable Replacement: Users can insert system environment variables within a property value. When using this method, LegiTest interprets these as environment variables.



```sql
%EnvironmentVariableName%
```




At test execution, LegiTest replaces all parameters with the supplied value. This parameter replacement occurs regardless of the method used. For examples of the parameter replacement methods in use, please see the [Parameter Tutorial](ParameterTutorial.md).



> ![](images/_ImportNoteIcon.png) Important Note:
> 
> Direct Property Replacement is the only method of mapping a parameter to a value that is not a string.




### Formatting Parameters



Sometimes it is necessary to format our parameters. For example, consider the SQL Query:



```sql
SELECT * FROM [MyTable] WHERE [LastModifiedDate] >= '{{ProcessingDate}}'
```




In this example, we would like the parameter to be formatted as four digits for the year, two for the month and two for the day. We can use filters that are defined by the DotLiquid markup to format the parameters as we would like:



```sql
SELECT * FROM [MyTable] WHERE [LastModifiedDate] >= '{{ProcessingDate | date:"yyyyMMdd"}}'
```




A reference of the available filters can be found on the [DotLiquid](https://github.com/dotliquid/dotliquid/wiki/DotLiquid-for-Designers) for Designers page.