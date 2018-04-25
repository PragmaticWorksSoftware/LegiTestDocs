![](images/_LegiTestBanner.png)

# Required Permissions




Many of the features within Workbench only need db_owner when issuing database updates. This occurs when upgrading from an older version of Workbench to a newer version. Outside of database updates, those users only need db_datareader and db_datawriter permissions. Below is a comprehensive list of each feature and their required permissions.




- BI xPress Required Permissions

    - Best Practice Analyzer:

        - BI xPress database:

            - Regular Usage:

                - db_datareader

                - db_datawriter

        - Database updates:

            *  db_owner



    - Technology specific permissions:

        - Hive

            - Read permissions for the HDFS files that you wish to document

        - Informatica

            - View definition permissions on the Informatica repository

            - Read permissions within the Informatica repository on any folder and object you wish to document

        - SQL Server

            - Definition permissions for any object you wish to document

        - SQL Server Integration Services

            - SSIS Catalog:

                - Read and Modify permission for each project within the SSISDB the user wishes to analyze

        - SQL Server 2008 R2 (or higher) Reporting Services

            - Folder Security Settings:

                - Minimum Predefined User Roles required:

                    - My Reports

                    - Content Manager

                - Minimum Tasks required for a custom User Role:

                    - View Reports

                    - View Folders

                    - View Data Sources

                    - View Models

                    - Consume Reports

        - Web Service Security Settings:

            - Minimum Predefined System Role required:

                - System User

            - Minimum Tasks required for a custom System Role:

                - Execute Report Definitions

        - Oracle Permissions

            - Connect permissions on any schema that you wish to document

        - Tableau Permissions

            - User must be a part of the Server Administrator role



    - Data Generation:

        - Each table you wish to generate data within

            - db_datareader

            - db_datawriter



    - Deployment Wizard (2005 and 2008):

        - Permission to deploy to the SQL Server



    - SSIS Unit Test:

        - Permission to execute the packages you are testing (at their location, ex. file system, SQL server etc...)



    - SSRS Monitoring Console:

        - SSRS ReportServer database(s):

            - db_datareader



    - Monitoring Console:

        - BI xPress database:

            - Regular Usage:

                - db_datareader

                - db_datawriter

            - Database updates:

                - db_owner



    - Other Features:

        - For other features you will need permission to access and obtain the packages at their location.



### Required Permissions for other Workbench products:

- DBA xPress Required Permissions

    - Data Inspector, Data Space Analyzer, Data Surf, Object Browser, Schema Surf

        - Each object being manipulated:

            - db_datareader

            - db_datawriter



    - Schema Inspector, Schema Inspector Snapshot Tool

        - Each object being manipulated:

            - db_owner



- DOC xPress Required Permissions

    - DOC xPress database:

        - Regular Usage:

            - db_datareader

            - db_datawriter

        - Database updates:

            - db_owner



    - Technology specific permissions:

        - Hive

            - Read permissions for the HDFS files that you wish to document

        - Informatica

            - View definition permissions on the Informatica repository

            - Read permissions within the Informatica repository on any folder and object you wish to document

        - SQL Server

            - Definition permissions for any object you wish to document

        - SQL Server Integration Services

            - SSIS Catalog:

                - Read and Modify permission for each project within the SSISDB the user wishes to analyze

        - SQL Server 2008 R2 (or higher) Reporting Services

            - Folder Security Settings:

                - Minimum Predefined User Roles required:

                    - My Reports

                    - Content Manager

                - Minimum Tasks required for a custom User Role:

                    - View Reports

                    - View Folders

                    - View Data Sources

                    - View Models

                    - Consume Reports

            - Web Service Security Settings:

                - Minimum Predefined System Role required:

                    - System User

                - Minimum Tasks required for a custom System Role:

                    - Execute Report Definitions

        - Oracle Permissions

            - Connect permissions on any schema that you wish to document

        - Tableau Permissions

            - User must be a part of the Server Administrator role