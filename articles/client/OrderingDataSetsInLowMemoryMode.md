![](images/_LegiTestBanner.png)

# Ordering data sets in low-memory mode



When extracting data sets for comparison, they must be orderable. Small data sets are no problem, as they can be stored in memory and ordered simply. For larger data sets we can use low-memory mode - which stores the data in a file on disk. However, a requirement for data sets in low-memory mode is that they are ordered when they are produced. Most of the time a simple ORDER BY clause allows us to order the set in the same order as the comparison keys.



However, when using a string as a key issues can arise from the fact that SQL will order strings according to the collation defined on the source. The comparison within LegiTest uses binary collation - so the order by clause has to be specified with a binary collation. For example:



```sql
SELECT * FROM [Person].[Person]

ORDER BY [LastName] COLLATE Latin1_General_100_BIN
```




It is important to note that the columns specified in the ORDER BY clause must match the keys specified in the comparison manifest, in the same order. So, if you comparison manifest has the keys 'LastName', 'FirstName', 'Age' then the ORDER BY clause must also specify LastName, FirstName, Age.