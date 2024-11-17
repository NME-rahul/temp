# Relational Algebra
* Relattional algebra is procedural language, we have to specify what to do and how to do.
  
## Relational operations

1. Unary
   * Select 𝞂
   * project 𝛑

2. Binary
     * Union ∪
     * Intersection ⋂
     * Difference -
     * Join ⨝
     * Divide /
     * cartesian product x
  
---

**Table N:**

<div align="center">
  
|Roll No.|Name|Semester|Percentage|
|---|---|---|---|
|22|Arun|7|45%|
|31|Bindu|6|55%|
|58|Sita|7|35%|
</div>

**Table R:**

<div align="center">
  
|Roll No.|Name|Semester|Percentage|
|---|---|---|---|
|28|Suresh|4|65%|
|31|Bindu|6|55%|
|44|Pinky|4|75%|
|58|Sita|7|35%|
</div>

----

## Select:

* Selects records according to the specified condition $\sigma_{condition} (tableName)$.
* It will not change the no of attributes in output table.
* The output table have no name.
* If there is no condition then resultant table have all records of table.


$$\sigma_{Semester = 4}(R)$$

$$\sigma_{Roll no > 35}(R)$$

$$\sigma_{Roll no > 30 AND Roll no < 45}(R)$$


## Project

Project/show all the table record according specified table. return only unique tuples.

$$\pi_{col1, col2, ..., coln}(tableName)$$

$$\pi_{Semester}(N)$$


## Union

it is represented as R U N. like set operation, selects all the records from both the table without replication.

* To do union operation.
  * Both realtion(tables) must have same arity.
    * Same number of columns and same domains.
    * Same Name of columns with same order.

<div align="center">
  
R U N
|Roll No.|Name|Semester|Percentage|
|---|---|---|---|
|22|Arun|7|45%|
|31|Bindu|6|55%|
|58|Sita|7|35%|
|28|Suresh|4|65%|
|44|Pinky|4|75%|
</div>

## Intersection

it is represented as R ⋂ N. like set operation, selects all the common records from both the table.

<div align="center">

R⋂N
|Roll No.|Name|Semester|Percentage|
|---|---|---|---|
|22|Arun|7|45%|
|31|Bindu|6|55%|
|58|Sita|7|35%|
</div>

* To do Interscetion operation.
  * Both realtion(tables) must have same arity.
    * Same number of columns and same domains.
    * Same Name of columns with same order.

## Difference
it is represented as R-N. like set operation, it removes all the records from R that are present in the table N.

|Roll No.|Name|Semester|Percentage|
|---|---|---|---|

* To do Difference operation.
  * Both realtion(tables) must have same arity.
    * Same number of columns and same domains.
    * Same Name of columns with same order.

## Cartesion product

It is represented as RxN. it multiplies Every row of table R with every row of table N. if table R have n rows and table N have m rows then RXN will have nxm rows.
* The resultant table have no name.

<div align="center">

|Roll No.|Name|Semester|Percentage|Roll No.|Name|Semester|Percentage|
|---|---|---|---|---|---|---|---|
|22|Arun|7|45%|28|Suresh|4|65%|
|22|Arun|7|45%|31|Bindu|6|55%|
|22|Arun|7|45%|58|Sita|7|35%|
|31|Bindu|6|55%|28|Suresh|4|65%|
|31|Bindu|6|55%|31|Bindu|6|55%|
|31|Bindu|6|55%|58|Sita|7|35%|
|58|Sita|7|35%|28|Suresh|4|65%|
|58|Sita|7|35%|31|Bindu|6|55%|
|58|Sita|7|35%|58|Sita|7|35%|
|28|Suresh|4|65%|28|Suresh|4|65%|
|28|Suresh|4|65%|31|Bindu|6|55%|
|28|Suresh|4|65%|58|Sita|7|35%|
|44|Pinky|4|75%|28|Suresh|4|65%|
|44|Pinky|4|75%|31|Bindu|6|55%|
|44|Pinky|4|75%|58|Sita|7|35%|
</div>

## Join

A join operation combines tuples/rows from different tables/relations, if and only if it satisfy some specific condition.
1. Natural Join
2. Outer join
3. Inner/Equi join

### Natural join

Join the set of tuples of all combinations based on common attribute or with foriegn key. Join only those records that satisfy the condition of the natural join.

> Natural join = cartesin_product + selection + projection

<div align="center">

Employee Table
| EmployeeID | EmployeeName | DepartmentID | Salary |
|------------|--------------|--------------|--------|
| 1          | John         | 101          | 50000  |
| 2          | Jane         | 104          | 60000  |
| 3          | Mark         | 103          | 55000  |
| 4          | Joy          | 105          | 78000  |
| 5          | Alex         | 102          | 21000  |


Department Table
| DepartmentID | DepartmentName |
|--------------|----------------|
| 101          | HR             |
| 102          | IT             |
| 103          | Finance        |

</div>

    Select * from Employee NATURAL JOIN Department;

<div align="center">

|EmployeeID|EmployeeName|DepartmentID|Salary|DepartmentID|DepartmentName|
|----------|------------|------------|------|------------|--------------|
|1         |John        |101         |50000 |101         |HR            |
|1         |John        |101         |50000 |102         |IT            |
|1         |John        |101         |50000 |103         |Finance       |
|2         |Jane        |104         |60000 |101         |HR            |
|2         |Jane        |104         |60000 |102         |IT            |
|2         |Jane        |104         |60000 |103         |Finance       |
|3         |Mark        |103         |55000 |101         |HR            |
|3         |Mark        |103         |55000 |102         |IT            |
|3         |Mark        |103         |55000 |103         |Finance       |
|4         |Joy         |105         |78000 |101         |HR            |
|4         |Joy         |105         |78000 |102         |IT            |
|4         |Joy         |105         |78000 |103         |Finance       |
|5         |Alex        |102         |21000 |101         |HR            |
|5         |Alex        |102         |21000 |102         |IT            |
|5         |Alex        |102         |21000 |103         |Finance       |

</div>

* Here, the Natural join point is DepartmentID, eleminate those rows mismatching DepartmentId value.

<div align="center">

|EmployeeID|EmployeeName|DepartmentID|Salary|DepartmentID|DepartmentName|
|----------|------------|------------|------|------------|--------------|
|1         |John        |101         |50000 |101         |HR            |
|3         |Mark        |103         |55000 |103         |Finance       |
|5         |Alex        |102         |21000 |102         |IT            |
</div>

* Now remove common coloumns, resultant table will be your output for the natural join.

<div align="center">

|EmployeeID|EmployeeName|DepartmentID|Salary|DepartmentName|
|----------|------------|------------|------|--------------|
|1         |John        |101         |50000 |HR            |
|3         |Mark        |103         |55000 |Finance       |
|5         |Alex        |102         |21000 |IT            |
</div>

### Inner join


<div align="center">
  
Customers
| ID | Name    | Location  |
|----|---------|-----------|
| 1  | Alice   | New York  |
| 2  | Bob     | London    |
| 3  | Charlie | Paris     |

Orders
| ID  | Amount | Customer |
|-----|--------|----------|
| 101 | 100    | 1        |
| 102 | 200    | 2        |
| 103 | 300    | 1        |
| 104 | 150    | 3        |
</div>

    SELECT C.Name, O.Ammount FROM Customer AS C INNER JOIN Order AS O ON C.ID = O.ID;

### Outer Join

<p align="center">
  <img src="https://d1wl9nui6miy8.cloudfront.net/media/969825/2013-06-inner-outer-join-venn.jpg" />
</p>

### Left Outer join:
* Take all records from left table(table1).

<div align="center">
  
Student
| StudentID | StudentName |
|-----------|-------------|
| 1         | John        |
| 2         | Jane        |
| 3         | Smith       |

Marks
| StudentID | Grade |
|-----------|-------|
| 1         | 85    |
| 3         | 92    |

Output
| StudentID | StudentName | Grade |
|-----------|-------------|-------|
| 1         | John        | 85    |
| 2         | Jane        | NULL  |
| 3         | Smith       | 92    |
</div>

        SELECT S.StudentID, S.StudentName, M.Grage FROM Student S LEFT JOIN Marks M ON S.StudentId = M.studentID;

### RIGHT outer Join

<div align="center">
   
Table: Orders
|OrderID|	CustomerID|	OrderDate|
|---|---|---|
|1|	101|	2023-10-01|
|2|	102|	2023-10-05|
|3|	103|	2023-10-10|
      
Table: Customers
|CustomerID|	CustomerName-|	ContactName  |OrderID| OrderDate|
|----------|---------------|---------------|-------|----------|
|101       | Alfreds	Maria|         Anders|1      |2023-10-01|
|102       |	    Berglunds| Christina Berg|2      |023-10-05 |
|105       |	       Centro|Francisco Chang|NULL   |NULL      |

    SELECT O.OrderID, C.CustomerName, O.OrderData FROM Orders O RIGHT OUTTER JOIN Customers C ON O.CustomerID = C.CustomerID;

Output
|CustomerID|	CustomerName|	ContactName|
|---|---|---|
|101|	Alfreds	Maria| Anders|
|102|	Berglunds|	Christina Berg|
|105|	Centro|	Francisco Chang|
</div>

### Full outer join

<div align="center">
      
Employees:
|EmployeeID|EmployeeName|	DepartmentID|
|----------|------------|-------------|
|1         |	      John|	         101|
|2         |	      Jane| 	       102|
|3         |	       Bob|	         104|
|4         |	     Alice|          103|
      
Departments:
|DepartmentID|DepartmentName|
|------------|--------------|
|101         |	          HR|
|102         |	     Finance|
|104         |	          IT|

          SELECT * FROM CUSTOMER FULL OUTER JOIN Departments;

Output
|EmployeeID|EmployeeName|	DepartmentID|	DepartmentName|
|----------|------------|-------------|---------------|
|1         |	      John|	         101|             HR|
|2         |	      Jane|	         102|        Finance|
|3         |	       Bob|	         104|             IT|
|4         |	     Alice|	         103|           NULL|
</div>

|Natural Join|Inner Join| Outer Join|
|---|---|---|
|Based on the columns that have the same name and data type in the tables being joined| Returns the rows that ahve matching values in both tables based on the sspecified condition in the ON clause| Includes the matched rows from both tables, as well as any unmatched rows from one or both of the tables|
|It automatically matches the columns between the two tables with the same name and select the rows that have same values|It combines the rows from both tables that satisfy the join condition|**left join** includes all the rows from the left table and the matching rows from the right table. if there are no matching rows, it includes NULL values. **Right join** includes all the rows from the right table and the matching rows from the left table. if there are no matching rows it returns NULL. **Full join** includes all the rows from both tables, including the unmatched rows. if a row from one table doesn't have a corresponding row in the other table, the column from other table will have NULL values|
|The result set contains only the rows with the same values in common column| The result set contain only the matched rows from both tables, excluding the unmatched rows.||
|join matching columns| join matching rows| join each row|


## Division(/):
   * all Tuple of table2 associated with tuples of table1.
   * Attributes of B is proper subset of attibutes of A, here in example attribute of tabel1 'course' attribute is also ocuring in table2
   * every, all, at all, for all, in all, for every like phrases will come in question then we have to perform division. for eg. Find the the person that has account in all the banks of a particular city.
   * It is derived operator
     * $$\pi(table1) * \pi(table2) - (table1)$$
     * $$A(X,Y) / B(Y) = C(X)$$

<div align="center">
table1
|Name|Course|
|---|---|
|System|B.tech|
|Database|M.tech|
|Database|B.tech|
|Algebra|B.tech|

table2
|Course|
|---|
|B.tech|
|M.tech|

resultant:
|Name|
|---|
|database|

</div>
