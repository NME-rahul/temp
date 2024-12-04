# CONTAINS

* $A$ contains $B$ means $B \subseteq A$
* Division($R1 \div R2$) operator of realtional algebra is implemented b cntains set operation in SQL. R2 must be subset of R1


      SELECT attribute1, attribute2, ...
      FROM table
      WHERE
  
      (query: table that coorelates to outer query table; R1)
  
      CONTAINS
  
      (query: table that you associate with R1 ; R2)


----

Book(bid, title, Yr_pub)
User(cardno, name, city)
Borrow(bid, cardno, DoI)
Supplier(bid, sname, DoS)


      SELECT Sname
      FROM Supplier s1
      WHERE 

      (SELECT bid FROM Supplier s2 WHERE s1.bid = s2.bid AND s2.sname = s1.sname )

      CONTAINS

      (SELECT bid FROM User, Borrow WHERE User.cardNo = Borrow,cardNo AND User.name = "ABC" )


* Starts interprating from bootm query

      (SELECT bid FROM User, Borrow WHERE User.cardNo = Borrow,cardNo AND User.name = "ABC" )

1. It joins the Borrow and user table on cardno and select bid were user name is "ABC"
   * list out all bid which is issued by user "ABC"
  
   <div align="center"> 
     
    R2:
     
   |bid|
   |---|
   |101|
   |105|
   |111|
   </div>
  
     (SELECT bid FROM Supplier s2 WHERE s1.bid = s2.bid AND s2.sname = s1.sname )
2. It joins outer table with inner query(self join), Now we will go iteration by iteration and first we'll took one sname that is in outer table, let say x and matchs it with sname selected by inner query and list out all those corresonding bids that matchces with sname.
   * That iteration is possible by only nesting sname of outer query table with inner query table.

<div align="center"> 
  
R1:

   |bid|
   |---|
   |101|
   |102|
   |105|
   |109|
   |104|
   |111|
   </div>

3. Now, is R1 ```CONAINS``` R2 if yes then list corresponding sname that is selected by outer query.

      
