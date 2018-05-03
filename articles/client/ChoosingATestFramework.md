![](images/_LegiTestBanner.png)

# Choosing a Test Framework



LegiTest is, at its core, a code generation tool. The tests, groups and assets that you configure become code in the form of unit tests. There are multiple test frameworks available, each with their own benefits and drawbacks. LegiTest currently supports NUnit 2 and MSTest.



Pragmatic Works recommends NUnit as a better choice in most scenarios. Some of the specific benefits include:



- More powerful model for supporting Data Driven Testing

While Data Driven Testing is supported both in NUnit and MSTest - the way it works in MSTest means that your data driven query can be executed at unexpected times because of limitation in the framework.



- More powerful assert model

Assertions are a key aspect of testing. They are the part of the test where the code verifies that the result of the test (the actual result) matches the desired result (the expected result). NUnit has a lot more flexibility in this area - meaning the generated code is simpler and it is easier to write your own assertions should you wish to do so.



- Broader compatibility

NUnit tests operate in a way that means that there are less problems with execution of tests. Testing SSIS packages is one key area where NUnit is superior - packages loaded at the group level have issues under MSTest - while no similar problems occur using NUnit.