# sqlqueries window function(part 1)
some examples of sql queries.
use AdventureWorks2014

select*from Sales.SalesTerritory

select TerritoryID,Name,SalesLastYear from Sales.SalesTerritory

/* over() window function .
It is the replacement of GROUP BY. It creates a window with multiple rows.*/

select TerritoryID,Name,SalesLastYear,sum(SalesLastYear) over() as TotalSalesLastYear from Sales.SalesTerritory

/* Partition by() window function.
It is used to divide the result set from the query into data subsets.*/

select TerritoryID,Name,SalesLastYear,sum(SalesLastYear) over(PARTITION BY Name) as TotalSalesLastYear 
from Sales.SalesTerritory
