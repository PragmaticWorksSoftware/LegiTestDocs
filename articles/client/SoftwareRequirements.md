# Software Requirements

Before installing Workbench, make sure you meet the following system requirements:
- SQL Server Integration Services 2005, 2008, 2008 R2, 2012, 2014, 2016
- BIDS 2005, 2008, 2008 R2 (Business Intelligence Development Studio) or SSDT 2010, 2012, 2014, 2016, 2017 (SQL Server Data Tools)
- Microsoft ® .NET 3.5 with Service Pack 1
- Microsoft ® .NET 4.0
- Microsoft ® .NET 4.5 (2017 Providers only)
- Microsoft ® SQL Server ® 2012 Transact-SQL ScriptDom x86

The following operating systems are supported by Workbench:  
- 64-bit (x64) Operating Systems:
   - Windows Server 2008 R2
   - Windows Server 2012
   - Windows Server 2016
   - Windows 7
   - Windows 8
   - Windows 10
- 32-bit (x86) Operating Systems:
   - Windows Server 2008 R2
   - Windows Server 2012
   - Windows 7
   - Windows 8
   - Windows 10

The LegiTest extension requires an installation of one of the following editions of Visual Studio:
- Visual Studio 2013 Community, Professional, Premium, or Ultimate
- Visual Studio 2015 Community, Professional, or Enterprise
- Visual Studio 2017 Community, Professional, or Enterprise

Test Framework Requirements:
- MSTest (included with Visual Studio)
- NUnit 2.6.4 
   - NUnit 2.6.4 Console Runner for executing tests outside of Visual Studio
   - NUnit Test Adapter 2.1.1 for executing tests inside Visual Studio and displaying in the Visual Studio Test Explorer (installed via Nuget by default)
- Nunit 3.0
   - NUnit 3 Console Runner for executing tests outside of Visual Studio
   - NUnit 3 Test Adapter 3.10 for executing tests inside Visual Studio and displaying in the Visual Studio Test Explorer (installed via Nuget by default)

The following prerequisites are required to enable features within LegiTest:
- [SSIS Actions](SsisActions.md) and [Assets](SsisAssets.md)
  - Either an installation of SQL Server Integration Services (Developer, Standard, or Enterprise) that matches the version to be tested
  - Or SQL Server Data Tools for Visual Studio with the SQL Server Integration Services option selected
- [SSAS Actions](SsasActions.md)
  - Either an installation of SQL Server Analysis Services (Developer, Standard, or Enterprise) that matches the version to be tested
  - Or SQL Server Data Tools for Visual Studio with the SQL Server Analysis Services option selected
- [SSRS Actions](SsrsActions.md)
  - Either an installation of SQL Server Reporting Services (Developer, Standard, or Enterprise) that matches the version to be tested
  - Or SQL Server Data Tools for Visual Studio with the SQL Server Reporting Services option selected