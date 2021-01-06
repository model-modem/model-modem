# SQL Server

## Find any Procedures Containing `<text>`

You can use these queries[^1] to search for stored procedures that contain the value `Foo`.

```sql
SELECT OBJECT_NAME(id) 
    FROM SYSCOMMENTS 
    WHERE [text] LIKE '%Foo%' 
    AND OBJECTPROPERTY(id, 'IsProcedure') = 1 
    GROUP BY OBJECT_NAME(id)
```

```sql
SELECT OBJECT_NAME(object_id)
    FROM sys.sql_modules
    WHERE OBJECTPROPERTY(object_id, 'IsProcedure') = 1
    AND definition LIKE '%Foo%'
```

----

!!! warn
    Note that `ROUTINE_DEFINITION` is cropped at 4,000 characters.  It's recommended to use one of the methods above using `OBJECTPROPERTY` instead.

```sql
SELECT ROUTINE_NAME, ROUTINE_DEFINITION
    FROM INFORMATION_SCHEMA.ROUTINES 
    WHERE ROUTINE_DEFINITION LIKE '%Foo%' 
    AND ROUTINE_TYPE='PROCEDURE'
```

[^1]: See: [https://stackoverflow.com/q/5079457/1356593](https://stackoverflow.com/q/5079457/1356593)