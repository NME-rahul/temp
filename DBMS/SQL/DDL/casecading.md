# ON DELETE CASECADE

* It is a constraint to statisfy the foreign-key constraint/refrential integrity constraint by removing dependent tuples preventing consistency.
* Whenever a row in parent table is deleted the refrenced key row also automatically deletes from child table and if 'ON DELETE CASCADE' is used with foreign-key constraint then any grandchilderen will also deletes.


      CREATE TABLE Enroll
      (
        StudentID varchar(6) REFRENCES Student(StudentID) ON DELETE CASCADE,
        CourseID varchar(5),
        CourseName varchar(20),
        EnrollDate Date
      )
