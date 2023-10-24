## 1 NF

* Fileds must contain atomic values.

## 2 NF

* The table should be in 1NF.
* Each non-key in table should fully-functionally dependent on the primary-key or candidate-key.
* **Functioanly dependent:** If values of field B is determined by the field B, and there can be only one value in field B.
  * **Symbolic repersentation:** A ---> B
* **To do this:**
  * create a table for functionlaly dependent attributes. primary-key --> non-key1, primary-key --> non-key2, primary-key --> non-key3...,.
  * Think about primary key for each table.

|EmployeeID|Last Name|First Name|Project Number|Project title|
|---|---|---|---|---|

* Here, EmployeeID is a primary-key, and others are the non-key attributes.
* Last Name, First Name is functioanly dependent on the EmployeeID and project title on Project Number, so create a table for each functionaly dependent attributes.
    
    |EmployeeID|Last Name|First Name|    
    |---|---|---|
    
    |Project Number|Project title|
    |---|---|

  * now, create a new table, having attribute of both the table's primary-key, candidate-key or we can say the attribute on which they are dependent. here, EmployeeID and Project Number.
    |EmployeeID|Project Number|
    |---|---|


## 3 NF

* Table should be in 2NF.
* There should be no transitive dependencies.
  * **Transitive dependencies:** If a non-key field is determined by the value in another non-key and that is not a candidate key. A ---> B ---> C
* **To remove this:**
  * Find the attributes that are transitively dependent.
  * Create seprate table for each of dependencies, A ---> B and B ---> C

|ProjectNum|ProjectTitle|ProjectMgr|Phone|
|---|---|---|---|

* Here, Phone is determined by projectMgr because multiple repetition of ProjectMgr in multiple projects and ProjectMgr is determined by the ProjectNum they have assigned.
* So, there is transitive functional dependencies in attributes, ProjectNum ---> ProjectMgr ---> Phone
* create table for each of dependencies, ProjectNum ---> ProjectMgr and ProjectMgr ---> Phone
  
  |ProjectNum|ProjectTitle|ProjectMgr|
  |---|---|---|
  
  |ProjectMgr|Phone|
  |---|---|

* adding ProjectTitle because ProjectNum and ProjectTitile are functionaly dependent, to ensure 2NF.
* ProjectMgr will work as foriegn-key.
* At last add necessary foriegn-key's and primary-key's.
 

## Boyce-Codd Normal Form(BCNF)

* It is a new 3NF.
* The table should be in 3NF.
* There should be no overlapping candidate keys.
  * **Overlapping Candidate key:** If we have more then one combination of keys(composit-key) that uniquly determines the record, and composit-key have a common attribute, then the keys are called  the overlapping candidate keys. eg (A,B) and (A,c)
* **To remove this:**
  * Create seprate table for each unique combination of composit-key's attribute. (A,B), (A,C) and (B,C)

|CourseNum|Student|TA|
|---|---|---|

* Here (CourseNum, Student) and (Student, TA) are composit-keys, and each have Student attribute common.
* Crate table for each unique combination of composit-key,
  |CourseNum|Student|
  |---|---|

  |CourseNum|TA|
  |---|---|

  |Student|TA|
  |---|---|


## 4 NF

* The table should be in BCNF.
* There should be no multi-valued dependency.
  * **Multi-valued dependencies:** In field A, there is a set values for field B and a set of values for field C but fields B and C are not related.
* **To remove this:**
  * crate seprate table for each relationship. (A,B) and (A,C)
 
|Movie|Star|Producer|
|---|---|---|

* Here, A movie can have more then one star and producer, so for each record of tuple there can set of values on Start and Producer column.
* Create seprate table for (Movie,Start) and (Movie,Producer).
  |Movie|Star|
  |---|---|

  |Movie|Producer|
  |---|---|

|DeptCode|ProjectNum|ProjectMgr|Equipment|PropertyID|
|---|---|---|---|---|


## 5 NF

* The table should be in 4NF.
* There should be no cyclic dependency.
  * **Cyclic dependency:** It occures when you have multifield primary-key consisting three of more fields. for example, let's say your primary key consists of fields A, B, C. the cyclic dependency would arise when fields were related in pairs of {A,B}, {B,C} and {C,A}.
* **To remove this:**
  * create seprate table for each of pairs.

|Buyer|Product|Company|
|---|---|---|

* Here, Primary-key consists of all three fileds.
* To eleiminate cyclic redundancy, create seprate table for each pair of fields.
  |Buyer|Product|
  |---|---|

  |Buyer|Company|
  |---|---|

  |Company|Product|
  |---|---|
