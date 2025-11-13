# Set Operation

Book(bid, title, Yr_Pub)
User(cardNo, name, city)
Borrow(bid, cardNo, DOI)
Supplier(bid, sname, price, DOS)

### 1. UNION

        SELECT sid FROM Book UNION SELECT sid FROM Course;
* Select all sid that are in book tabel as well as in course

        SELECT bid FROM Book WHERE title = "DBMS" UNION SELECT bid FROM Boorow;

* Select all bid from book table where title is DBMS and and all books that are issued
    
### 2. INTERSECTON

        SELECT sid FROM Book INTERSECTION SELECT sid FROM Course;

* Select all sid that are common in book and course table.
* it remove duplicate tuples if present, to retail the duplicate tuples use `INTERSECT ALL`.
        
### 3. MINUS, EXCEPT

        SELECCT sid FROM Book MINUS SELECT sid FROM Course.
        
* Select all sid that are only in book table; Select all sid that are in Book table except sid' from course table.
  
* SOME
* ALL
* COUNT
* EXISTS
* NOT EXISTS
* UNIQUE
