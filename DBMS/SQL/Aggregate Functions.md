# Aggregate Functions

### 1. MIN
### 2. MAX
### 3. AVG
### 4. SUM
### 5. COUNT
* `COUNT` returns the number of records in relation including duplicated record and records containing NULL values. If `COUNT` is used with specific columns then it drops the NULL values still counting duplicate records. TO count distinct records use `COUNT( DISTINCT column_name )` to remove duplicacy( `COUNT(DISTINCT *)` is inavlid).

--- 
* These fucntions can work on multisets(set having duplicate values).
* MIN, MAX, AVG, SUM ignores because they works on specific attribute, COUNT also ignores NULL values only if used on specific attribute/column.
