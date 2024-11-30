# UNIQUE

* It is a function.
* It returns TRUE when result of subquery inside UNIQUE function returns only unique tuples and FALSE when sunquery returns at least one duplicate tuple.

      SELECT name
      FROM User u1
      WHERE UNIQUE(
            SELECT u2.CardNo FROM USER u2, Borrow
            WHERE Borrow.CardNo = u2.CardNo AND u1.CardNo = u2.CardNo
      )

* What if inner query returns empty table?
  * If inner query returns empty table then also UNIQUE function will return TRUE.
* IF you want FALSE on empty table then use ```EXISTS``` with ```UNIQUE```

      SELECT name
      FROM User u1
      WHERE UNIQUE AND EXISTS (
            SELECT u2.CardNo FROM USER u2, Borrow
            WHERE Borrow.CardNo = u2.CardNo AND u1.CardNo = u2.CardNo
      )

