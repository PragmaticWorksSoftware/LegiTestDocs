# Setup Instructions

![](lib/_LegiTestBanner.png)

Setup Instructions

Table of Contents

•   [Hardware Requirements](HardwareRequirements.html)

•   [Software Requirements](SoftwareRequirements.html)

•   [Required Permissions](RequiredPermissions.html)

1. After the installation environment meets all [Hardware](HardwareRequirements.html) and [Software Requirements](SoftwareRequirements.html), open the installer.
1. Users can install LegiTest in one of two ways:
    -  If you are installing through the Pragmatic Workbench installer, go to [step 2](SetupInstructions.html#Step2)
    -  If you are installing through the [Visual Studio Gallery](https://visualstudiogallery.msdn.microsoft.com/856eb913-7ab7-4cd5-961d-d63f3795a923), go to [step 9](SetupInstructions.html#Step9)
1. If you do not wish to send feature usage statistics, uncheck the box "Send feature usage statistics to Pragmatic Works."
1. Make sure to read the License terms and conditions before checking "I agree to the License terms and conditions". Once you have agreed, click "Next".
![](lib/PWInstallStep1.png)
1. Select the type of installation you wish to perform. 
    1.   If you select "Custom", go to [Step 5](SetupInstructions.html#Step5).
    1.   If you select "Typical", go to [Step 6](SetupInstructions.html#Step6). 
![](lib/PWInstallStep2.png)
1. On the "Custom" installation page, you may select which features to install or leave out. After making your selections, click "Install".
![](lib/_ImportNoteIcon.png) Important Note:
By expanding BI xPress you may choose which version(s) of Visual Studio our add-in will be compatible with on your machine. You may also choose to include DBA xPress, DOC xPress, LegiTest and the optional prerequisites for DOC xPress and BI xPress' BI Compare.
![](lib/PWInstallStep3.png)
1. The installation progress view will appear.
![](lib/PWInstallStep4.png)
1. If you chose "Typical" install in [step 4](SetupInstructions.html#Step4) or opted to install the optional prerequisites*, you will see the following components request to be installed from the Microsoft ® site:
    - Microsoft ® System CLR Types for Microsoft ® SQL Server ® 2012 x86
    - Microsoft ® SQL Server ® 2012 Shared Management Objects x86
    - Microsoft ® SQL Server ® 2012 Analysis Management Objects x86
    - Microsoft ® SQL Server ® 2012 Transact-SQL ScriptDom x86
    - Mcrosoft ® System CLR Types for Microsoft ® SQL Server ® 2012 x64
    - Microsoft ® SQL Server ® 2012 Shared Management Objects x64
    - Microsoft ® SQL Server ® 2012 Analysis Management Objects x64
    - Microsoft ® SQL Server ® 2012 Transact-SQL ScriptDom x64
![](lib/_ImportNoteIcon.png) Important Note:
These components are "Optional Prerequisites" because Pragmatic Workbench will work without them. However, DOC xPress and BI Compare (a feature within BI xPress) do require them to be installed in order to document and compare SSAS and SQL Server database objects
1. After each component, the Workbench installer will continue. If any error messages appear during the installation of these components, please reference their error message against Microsoft's support site for resolution.
![](lib/PWInstallStep6.png)
1. If you chose "Typical" install in [step 4](SetupInstructions.html#Step4), opted to install LegiTest, or are installing LegiTest through the Visual Studio Gallery, the Visual Studio Extension installer will appear. This allows users to choose which versions of Visual Studio will contain LegiTest.
![](lib/VSIXInstaller.png)

Once the installation has completed, the selected Visual Studio editions will be ready to [create a new LegiTest project](Overview.html#CreatingANewProject).
