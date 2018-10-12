# SQL and T-SQL

## 1. What are the advantages of Normalization versus denormalization?
> Normalization is better for OLTP (On-line Transaction Processing) systems:
> - Quick updates – data is in one place, no duplication
> - Quick inserts - data is in one place, no duplication

> Denormalization is better for OLAP (On-line Analytical Processing) systems:
> - Quick reports – no need for joins

## 2. What is BASE?

> - **B**asic **A**vailability - The database appears to work most of the time.
> - **S**oft-state - Stores don’t have to be write-consistent, nor do different replicas have to be mutually consistent all the time.
> - **E**ventual consistency - Stores exhibit consistency at some later point (e.g., lazily at read time).

## 3. What does the CAP theorem state?
> TODO: 

## 4. - What is ACID?

> - **A**tomicity - either all of the pieces of information are committed or none are
> - **C**onsistency - A transaction either creates a new and valid state of data, or returns all data to its state before the transaction was started.
> - **I**solation - A transaction in process and not yet committed must remain isolated from any other transaction.
> - **D**urability - Committed data is saved by the system such that, even in the event of a failure and system restart, the data is available in its correct state.

## 5. What are the differences between clustered and non-clustered indices?

> - With a clustered index the rows are **stored physically** on the disk in the same order as the index. There can therefore be only one clustered index.
> - With a non-clustered index there is a **second list that has pointers to the physical rows**. You can have many non-clustered indexes, although each new index will increase the time it takes to write new records.
> - It is generally **faster to read from a clustered index** if you want to get back all the columns. You do not have to go first to the index and then to the table.
> - **Writing to a table with a clustered index can be slower**, if there is a need to rearrange the data.

## 6. What are the differences between primary keys and unique indexes?

> - A **primary key also implies NOT NULL**, but a unique index can be nullable.
> - There can be **only one primary key**, but there can be multiple unique indexes.
> - If there is **no clustered index defined, then the primary key will be the clustered index**.

## 7. What are dirty reads, non-repeatable reads and phantom reads?

> - **Dirty Reads** - A dirty read occurs when a transaction reads data that has not yet been committed. For example, suppose transaction 1 updates a row. Transaction 2 reads the updated row before transaction 1 commits the update. If transaction 1 rolls back the change, transaction 2 will have read data that is considered never to have existed.
> - **Non-repeatable** - Reads A non-repeatable read occurs when a transaction reads the same row twice but gets different data each time. For example, suppose transaction 1 reads a row. Transaction 2 updates or deletes that row and commits the update or delete. If transaction 1 rereads the row, it retrieves different row values or discovers that the row has been deleted.
> - **Phantoms** - A phantom is a row that matches the search criteria but is not initially seen. For example, suppose transaction 1 reads a set of rows that satisfy some search criteria. Transaction 2 generates a new row (through either an update or an insert) that matches the search criteria for transaction 1. If transaction 1 reexecutes the statement that reads the rows, it gets a different set of rows.

## 8. What are the transaction isolation levels?

> - **Read Uncommitted** – Read Uncommitted is the lowest isolation level. In this level, one transaction may read not yet commited changes made by other transaction, thereby allowing dirty reads. In this level, transactions are not isolated from each other.
> - **Read Committed** (default for MSSQL, PostgreSQL) – This isolation level guarantees that any data read is committed at the moment it is read. Thus it does not allows dirty read. The transaction hold a read or write lock on the current row, and thus prevent other rows from reading, updating or deleting it.
> - **Repeatable Read** (default fro MySQL, MariaDB) – This is the most restrictive isolation level. The transaction holds read locks on all rows it references and write locks on all rows it inserts, updates, or deletes. Since other transaction cannot read, update or delete these rows, consequently it avoids non repeatable read.
> - **Serializable** – This is the Highest isolation level. A serializable execution is guaranteed to be serializable. Serializable execution is defined to be an execution of operations in which concurrently ececuting transactions appears to be serially executing.

|                  | Dirty reads | Nonrepeatable reads | Phantoms |
| ---------------- | :---------: | :-----------------: | :------: |
| Read uncommitted | Yes         | Yes                 | Yes      |
| Read committed   | No          | Yes                 | Yes      |
| Repeatable read  | No          | No                  | Yes      |
| Serializable     | No          | No                  | No       |

## 9. What is a SQL injection?

> A type of an injection attack where the attacker executes a malicious batch of SQL inside our database server.

## 10. How can we protect ourselves from a SQL injection?

> - NEVER, f**cking EVER execute a raw SQL query
> - Sanitize your query manually (But srly, we are not in the 90s – use something else).
> - User parametrized queries
> - Use an ORM

## 11. What are the different types of joins?

![alt text](../assets/join-types.jpg)

## 12. What is `COALESCE`?

> `COALESCE` will take any number of parameters, and return the first value encountered that isn't `NULL`.

## 13. What is the difference between `DELETE` and `TRUNCATE`?

> TODO:

## 14. What does UNION do? What is the difference between UNION and UNION ALL?

## 15. What is the difference between the WHERE and HAVING clauses?

## 16. What are the difference between stored procedures and user defined functions?

## 17. What is the difference between "stored procedure" and "dynamic SQL"?

> - Stored procedures are stored in data base in complied form.
> - Dynamic SQL statements are dynamically constructed at run time.

## 18. What's the difference between CREATE PROC and CREATE PROCEDURE?

> They are the same.

## 19. Can we call trigger inside a stored procedure?

> No, triggers cannot be called manually.

## 20. What are CLR stored procedures?

> Stored procedures written in a CLR compatible language like C#, VB.NET (How about no.), F#, etc.

## 21. When to use CLR stored procedures and when T-SQL ones?

> - If your logic mostly includes transformations of massive sets of data, which can be performed using set operations, then use T-SQL.
> - If your logic mostly includes complex computations of relatively small amounts of data, use CLR.

## 22. What is the best approach to check if a query has returned a result?

> - It’s generally a better idea to use the `EXISTS` function over the `COUNT`.
> - `EXIST` is a short circuiting operator, meaning it stops execution of the query after a single result is fount.
> - `COUNT` on the other hand, check all the rows that satisfy the conditions of the query.

## 23. Correlated subqueries vs uncorrelated subqueries?

> - Correlated Subquery is a sub-query that uses values from the outer query. In this case the inner query has to be executed for every row of outer query.
> - Simple subquery doesn't use values from the outer query and is being calculated only once.
> - Use uncorrelated subqueries when possible – better performance.

## 24. What is parameter sniffing?

> - During compilation, the value passed as the store procedure parameter is evaluated and used to create an execution plan.
> - That value is also stored with the execution plan in the plan cache.
> - Future executions of the plan will re-use the plan that was compiled with that reference value.

## 25. How can we optimize incorrect parameter sniffing?

> - Recompiling

```sql
-- stored procedure version
CREATE PROCEDURE dbo.sample @ProductID INT
WITH RECOMPILE
AS
/* do something */
-- single statement version
SELECT * FROM Sales.SalesOrderHeader
OPTION (RECOMPILE);
```

> - Optimize for value

```sql
ALTER PROCEDURE Get_OrderID_OrderQty
@ProductID INT
AS
SELECT SalesOrderDetailID, OrderQty
FROM Sales.SalesOrderDetail
WHERE ProductID = @ProductID
OPTION (OPTIMIZE FOR (@ProductID=945));
```

> - Optimize for unknown

```sql
CREATE PROCEDURE dbo.GetCities
@StateProvinceID int
AS
SELECT DISTINCT City
FROM Person.Address
WHERE StateProvinceID=@StateProvinceID
OPTION (OPTIMIZE FOR UNKNOWN)
```

> - Exceptions - Just use branching logic a.k.a. IF/ELSE

## 26. What the logarithmic complexity if the different query operations?

> - Clustered Index Scan – O(n)
> - Index Scan – O(n)
> - Index Seek – O(log(n))
> - Key Lookup – O(1)
> - Nested Loops – O (n*m)
> - Merge Join – O (n + m)
> - Hash Join – O (n + m)

## 27. Can you name some optimization tips?

> - Use appropriate Indices (clustered, non-clustered)
> - Inspect your WHERE clauses, when performance is an issue
> - Denormalizaton vs many joins?
> - Do not overuse indices
> - Consider if you need fast SELECT or fast INSERTs/UPDATEs – indices slow down the latter.
> - If you can – always prefer using set based operations over cursors
