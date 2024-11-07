# Constrainsts

Constraints are basically condition or restriction that must be satisfied in Relationship.

# Types of Constrainsts

1. Domain Constraints
2. Key Constraints
3. Entity Integrity Constraints
4. Referntial Integrity Constraints
5. Tuple Uniqueness Constraints

### 1. Domain Constraints

* Define the valid values that a attribute(column) can hold, like range of values, data type of values, etc..
* Their are various type of domain constraints
  * Not NULL costraints: the columns must not have NULL values.
  * Check Constraints: while inserting or updating column the database check for some predefined conditions that must be hold after modification.
 
### 2. Key Constraints
* It defines the constraints on keys to ensure integrity of data for example primary-key must not have NULL, and non-unique values called primary-key constraint.
* There are various type of Key constriants.
  1. Unique-key constrints: it only restricts from filling duplicate values but can fill NULL values.
  2. Primary-Key Constriants: primary-key must not have NULL and non-unique values.
  3. Foriegn-key Constraints: A Foreign-key is an coloumn that reffers to the primary-key of another table. The foriegn-key constrainsts ensures that values in the foreign-key column match with values in the referenced primary-key column(s). It ensures Referential Integirty. no of values in refernced primary-key can be more then or equal to no. of values in forien-key column.

### 3. Entity Integirty constraints

* It is same as key-constriant, it is just a subset of key constraints.
* The key constraint states that the Primary Key attributes should be unique and must not contain null values.
* However, Entity Integrity Constraint states that any attribute of a Primary key must not be null.
* The perspective that this constraint holds is that if null values are allowed in the Primary key attributes, then there can be multiple null values. Hence, the constraint of a Primary Key being unique for every tuple will be violated.

### 4. Referntial Integirty Constraints

* Referntial interiy constinats concept ensured the consistency and accuracy of data beteen related tables.
* It is maintained through the Primary-key and foriegn-key.
* Here, Foriegn-key refernces the primary-key of other table before inserting and updating. Thes constrinsts can be controlled and defined by user for example by default any record present in refernced table must not be deleted or updated because it can be the case that prevoiusly inserted records are referenced with deleted or updated record, that can violate the referential integrity.

**Self-referencing relationship:** is also called recursive relation, Here a foriegn key refers to its table's primary-key. For eg, a manager that manages employees is also a part of the table ```Employee```,

<div align="center">
 <table>
  <tr>
   <th>EmployeeID</th><th>EmployeeName</th><th>ManagerID</th>
  </tr>
  <tr>
   <td>1001</td><td>Ramesh</td><td>NULL</td>
  </tr>
  <tr>
   <td>1230</td><td>Latika</td><td>NULL</td>
  </tr>
  <tr>
   <td>3423</td><td>Gaurav</td><td>7892</td>
  </tr>
  <tr>
   <td>3123</td><td>Rahul</td><td>1230</td>
  </tr>
  <tr>
   <td>3875</td><td>Mayank</td><td>3902</td>
  </tr>
  <tr>
   <td>1001</td><td>Nikhil</td><td>3902</td>
  </tr>
  <tr>
   <td>3902</td><td>Rama</td><td>NULL</td>
  </tr>
 </table>
</div>
* Here, ```MangerID``` is aForiegn-key that refers to its own table's ```EmployeeID``` that is a primary-key.

    
### 5. Tuple Uniqueness Constraint

* The tuple uniqueness constraint in DBMS specifies that each tuple in the table must be unique.
* A tuple is said to be duplicate if all the corresponding attribute values of that tuple are present in some other tuple simultaneously in the table.
* It ensures that attributes that helps to unique identification of records/tupes/entity must posses unique values and enforce using unique-key or primary-key.
* Tuple Uniqueness Constraint not necessarily ensures about ```NULL``` values in column.
    
