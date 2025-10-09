## RConstraints

Constrants are nothing but rules that needs to be followed while entring the data in reational database.

---

**Types of Constraints**
* Domain Constraints
* key constraints
* Entity integrity constraints
* Refrential integrity constraints
* Tuple uniqueness constraints


1. **Domain constraints:** It specify the acceptable value that a column can take. It gurantess data consistency and prevents from inaccurate data entry.
   * **Data type constraint:** Defines the kind of data that can be fill in the a column. eg. INTEGER
     * String Data types
       * CHAR(SIZE), VARCHAR(SiZE), TEXT(Size)
     * Numeric Data types
       * BOOL, INTEGER(Size), BIGINT(Size), FLOAT(Size, d), DOUBLE(Size, d), DECIMAL(SIZE, d). d: decimal point
     * Binary Data types
       * BINARY(Size), VARBINARY(Size), BLOB(Size), BIT(Size)
     * Date Data types
       * DATE, DATETIME(fsp), TIMESTAMP(fsp), TIME(fsp), YEAR, 
     * Money Data types
   * **Length constraint:** Defines the number of digits/chararater that can be enter in the columns. eg. VARCHAR(10)
   * **Range constraints:** Specify the range restriction.
     
         eg. Grade INT CHECK (Grade >= 0 AND Grade <= 100)
     
   * **Nullability constraints:** A columns having NULL vlues are known as nullability constraints. eg. columns with constraint NOT NULL cannnot take NULL values or leaved to empty.
   * **Unique constraints:** A Column that accets only unique values(no repeation of data in same column).
     
         Name VARCHAR(10) UNIQUE
     
   * **Check constraints:** A requirments that must be hold by any data that is placed in into the column.
     
         AGE INTEGER(3) CHECK (AGE > 45 and AGE < 50)
     
   * **Default constraint:** It autmatically assigns a values to a column, If no values is placed in column.

         Department VARCHAR(50) DEFAULT 'General'
  
2. **Key constriant:** It defines how values of one or more column of table are related to other table. Use to ensure data accuracy and consistency in database.
   * **Primary Key:** It gurantess that every entry follows certain conditions that are value must be single, unique and NOT NULL. Because this column is used to identify the each row of table uniquly.
     
         CREATE TABLE Employee (EID INTEGER(5) PRIMARY KEY, Name VARCHAR(50), Department VARCHAR(50));
     
   * **Foreign Key:** It is column that refrences to PRIMARY KEY of another table(this table should also contain the same column).
     
         CREATE TABLE Orders (Order_ID INT PRIMARY KEY, Order_Date DATE, Customer_ID INT, FOREIGN KEY (Customer_ID) REFRENCES Customer(Customer_ID));
     
     * here Customer is another table that is refrenced by the table Orders.
       
   * **Unique constraint:** It ensures that not two values inside a column are the same.
     
         CREATE TABLE Students (SID INT PRIMARY KEY, Student_name VARCHAR(50), Email VARCHAR(50) UNIQUE);
  
3. **Entity Integrity constraints:** It ensures the consistency and integrity of PRIMARY KEY attribute and make sure the primary-key does not take `NULL` values. it does not care about uniquness of values in primary-key.


4. **Primary-key constraints:** It ensures the consistency and integrity of PRIMARY KEY attribute and make sure the primary-key does not take `NULL` and as well as duplicate values.

        CREATE TABLE Students (Student_ID INT PRIMARY KEY, Student_name VARCHAR(50));
   
5. **Refrential/Foreign-key integrity constraints:**  Refrential integirty constraints ensures the consistency and accuracy of data between related tables.

       CREATE TABLE Auhors (Auther_id PRIMARY KEY, Author_name VARCHAR(50));
       CREATE TABLE Books(Book_ID INT PRIMARY KEY, Book_title VARCHAR(50), Author_ID INT, FOREIGN KEY (Author_ID) REFRENCES Authors(Author_ID) ON DELETE CASCADE);
   
     * ON DELETE CASCADE clause is used which means that if a record in the Authors is deleted, all the associated recored in the Books table with the Author_ID will automatically delete.
  

7. **Tuple uniquness constraint:** It is also knwon as composite key constraints, it is use to enforce uniqness in the table by the combination of multiple columns in the table. for example in a table Student, student name, DOB and age can be used to uniqly determine each individual student in table.

        CREATE TABLE Students (Student_ID INT, Student_name VARCAHR(50), Age INT(3), DOB DATE, CONSTRAINTS name_age_dob UNIQUE (Student_name, Age, DOB));
  * here name_age_dob is the name given to the combination of three column Student_name, Age and DOB
