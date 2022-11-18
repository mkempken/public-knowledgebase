# How to Connect Alteryx 2020.1 and Later to Exasol 7.1

## Question
Has anyone been successful connecting Alteryx 2020.1 (or later) to Exasol 7.1?  My associate is getting an "unable to create socket" exception even though ODBC Driver Manager connects successfully.

## Answer
There is an undocumented flag which resolves windows ODBC connection issues from tools like Excel and Alteryx in version 7.1
In the ODBC data source administration, supply the additional, advanced parameter LegacyEncryption=Y.
1. Go to ODBC Data Source Administrator (64-bit).  
2. Select the DSN and click Configure.
3. Go to Advanced tab.
4. In the field of Additional connection string parameters, add the below line

    LegacyEncryption=Y
     
5. Now, go to Connection tab and click Test Connection. If the connection is successful, then click Ok else check the configuration once again.
6. Now, try to establish the connection using the configured DSN in Microsoft Excel. If still the error is persisting, then please send the ODBC log file generated by the Microsoft Excel for the newly configured DSN.

Thank you support for finding a solution.  I suspect there will be a new approach in the future.