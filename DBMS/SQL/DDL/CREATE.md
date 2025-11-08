# DELETE

It is used to create table.


    CREATE TABLE <table_name>
    (
    <attribute1> <datatype>(<size>) [constraint],
    <attribute2> <datatype>(<size>) [constraint],
    <attribute3> <datatype>(<size>) [constraint],
    .
    .
    .
    )

---

    CREATE TABLE Book
    (
      Bid int(5),
      CardNo int(5) REFRENCES User, //REFERENCE keyworkd is use to make foriegn-key, here CardNo is referencing to the User table's primary_key that is CardNo
      DOT DATE,
      PRIME KEY(Bid, CardNo) //defining composit key
    );

* if want to referece another attribute then primary-key then we can use following syntax.

      CREATE TABLE Book
      (
        Bid int(5),
        CardNo int(5) REFRENCES User(Name), //REFERENCE keyworkd is use to make foriegn-key, here CardNo is referencing to the User table's Name attribute
        DOT DATE,
        PRIME KEY(Bid, CardNo) //defining composit key
      );

---

    CREATE TABLE Supplier
    (
      SuppId int(5) PRIME KEY,
      Price int(5) CHECK Price < 1000,
      PUB_YR DATE
    );

----

    CREATE TABLE Student
    (
      Name varchar(10) UNIQUE,
      Semester int(1) Default 1,
      Sid int(5) CONSTRAINT P_K PRIME KEY,  //CONTRAINT P_k here ```CONSTRIANT``` is a keyword and P_K is name of contraint
    );

  * naming constraint makes easy to refer it and that is useful to delete, rename, update etc with ```ALTER``` command
