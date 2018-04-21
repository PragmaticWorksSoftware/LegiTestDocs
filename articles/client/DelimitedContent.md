![](images/LoadDelimitedFileAction.png)

# Delimited Content



The Delimited Content asset allows the user to store some delimited data that becomes part of the test assembly. This enables, for example, an easy set up for static data as a data driven testing source.



### Initial view

![](images/DelimitedContent1.png)





**File content -**  Here you can type the data that you would like to store in the test assembly. This data will be stored in asset files and can be in any delimited format.



**Delimiter / Quote -** These are the delimiter and quote that the file has. The asset's format detection routine will always check tab, pipe and comma for delimiters and both single and double quotes for the quote. If your file uses a different delimiter or quote, you can enter them here.



**Detect format -** Clicking this button will begin the process of detecting the format of the file and columns.



### After scan view

![](images/DelimitedContent2.png)







**Format -** This lists the formats that have been evaluated, along with their scores. A higher score indicates better compliance (consistent number of columns across rows and a higher number of columns in total). The format with the highest score will be pre-selected - unless a custom delimiter or quote was specified, in which case the custom format will be pre-selected. Note that the format selection is only available immediately after running the format detection process. When coming back to edit the asset later, this option will disappear.



**Delimiter / Quote -** Shows the currently selected delimiter and quote.



**Lines to skip -** The number of lines of pre-amble to skip.



**Has header row -** Check this is the file has a header row containing column names. The header row comes after any pre-amble.



**Treat empty as NULL -** Check this if empty values should be rendered as NULL values.



**Encoding -** This is the encoding that will be used to read the file. If your file contains special characters that are represented incorrectly on preview, it is likely that the encoding needs changing.



**Culture -** This is the culture that is used to interpret the source data as typed values. Decimal points and date formats are those where the culture requires particular attention.



**Preview Data -** This button will show the preview of the data using the selected option in a grid view.



**Change content -** This button allows you to change the content stored in the test assembly and run the format detection again.



**Column list -** Each column is presented along with a list of types. This list is derived by attempting format conversion on a variety of formats. You can change the resulting type to any of the allowable formats.