![](images/_LegiTestBanner.png)

# Why are my tests failing due to a "Mixed Mode Assembly" error?



If a test fails with the exception: "Mixed mode assembly is built against version 'v2.0.50727' of the runtime and cannot be loaded in the 4.0 runtime without additional configuration information", then a change to the vstest.executionengine.x86.exe.config file will be needed.



1.   Close Microsoft Visual Studio 2012 (and IIS express)

2.   Launch notepad.exe as an administrator

3.   Open the file "C:\Program Files (x86)\Microsoft Visual Studio 11.0\Common7\IDE\CommonExtensions\Microsoft\TestWindow\vstest.executionengine.x86.exe.config".

4.   Add and save the following lines in bold:



```xml
<?xml version="1.0" encoding="utf-8" ?>

<configuration>

<runtime>

<legacyUnhandledExceptionPolicy enabled="1" />

<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" >

<probing privatePath="Extensions" />

</assemblyBinding>

</runtime>

<system.diagnostics>

<switches>

<add name="TpTraceLevel" value="0" />

</switches>

</system.diagnostics>

<appSettings>

<switches>

<!--<add key="ExecutionThreadApartmentState" value ="MTA"/>-->

<!--<add key="TraceLogMaxFileSizeInKb" value ="10240"/>-->

<!-- MsTest Adapter Specific AppSettings -->

<add key="TestProjectRetargetTo35Allowed" value="true" />

</switches>

</appSettings>

<startup useLegacyV2RuntimeActivationPolicy="true" >

<supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0" />

</startup>

</configuration>
```
