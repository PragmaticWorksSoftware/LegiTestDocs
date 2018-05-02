![](images/_LegiTestBanner.png)

# Assets



The asset elements are designed to be reusable pieces throughout test development. Many different items may require the same connection or query, but those elements achieve different goals. Instead of needing to retype a connection string every time, a user would store that connection string in a connection asset. Now every time that connection is needed, the user simply selects it from a list of available assets.



Assets can be defined at the project, suite, group or test level. Assets within each of those locations may only be used by elements within that location. So, for example, an asset defined at the test level can only be used by that test, whereas an asset defined at the project level can be used anywhere within that project.



**Table of Contents**

- [Cloud](CloudAssets.md)

    * [SalesForce Connection](SalesforceConnection.md)

- [Data Managment](DataManagement.md)

    * [Comparison Manifest](ComparisonManifest.md)

    * [Connection](Connection.md)

    * [Data Generation Solution](DataGenerationSolution.md)

    * [Delimited Content](DelimitedContent.md)

    * [Delimited File Reference](DelimitedFileReference.md)

    * [Fixed Width File Reference](FixedWidthFileReference.md)

    * [Grid Collection](GridCollection.md)

    * [Query](Query.md)

    * [Validation Manifest](ValidationManifest.md)

- [Directory](Directory.md)

    * [Directory Reference](DirectoryReference.md)

- [File](FileAssets.md)

    * [Text File](TextFile.md)

- [SQL Server](SQLServerAssets.md)

    * [T-SQL Backup / Restore](TSQLBackupRestore.md)

    * [T-SQL Bulk Insert](TSQLBulkInsert.md)

- [SSIS](SSISAssets.md)

    * [Package Reference](PackageReference.md)