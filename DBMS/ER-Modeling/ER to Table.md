# Approach

## 1. $1:1$ cardinality

### Case 1. Total Participation From both Side


eg. Every employee is assciated with the 1 department and similariy every department have 1 employee

<div align="center">
  
</div>

* Because relation is $1:1$ and every entity is participating(Toal participation) so, it automatically will become neccsary that both the tables have equal cardinality.

Note: You can merge tables here, primary-key can be any table's primary-key because of equal caridnality of entity-sets


### Case 2: Total participation from one side and partial participation from other side

<div align="center">
</div>

Note: You can merge tables here, primary of the entity-set which is is participating partially will become the primary key of merged table.
* Merging is possible but design is inefficient because of we can have many $NULL$ entires


### Case 3: Partial Participation from both the sides

<div align="center">
  
</div>

* We can move primary-key and table to other side.

Note: We can not merge tables because both can have entites which are not related to have so resulting table may have $NULL$ entries.


## 2. $M:N$ Minimum Caridinality

### Case 1: Partial Participation From both the sides

<div align="center">
</div>
image to show why we cant merge tables and also why we can't take primary key

* You can not Merger the tables here, in fact you will require one more table, due to partial relation from both.
* Many-to-Many with partial relation from both side can leads $NULL$ entries whether you merge both tables or take primary key of one table to other side. So, it become necessary to create a sperate table for their relation which have only those entries which are participating in relation.
* One more intresting fact is that the primary key will be the composit key of prime-key's of both tables in relation because of many-to-many relation and both columns allowed have duplicate entries.

### Case 2: Total prticipation from both side.

<div align="center">
  <img height="300px" width="400px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/WhatsApp%20Image%202024-11-15%20at%202.25.43%20AM.jpeg" />
    <img height="300px" width="400px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/WhatsApp%20Image%202024-11-15%20at%202.25.43%20AM%20(1).jpeg" />
  
</div>

* We can merge the table in this case due to total many-to-many relation we dont' have any $NULL$ entires but We are allowed to have duplicate entries and the prime-key in merged table will be the composit-key of primary id's of both tables, because compositly they're unique.

<div align="center">
  <img height="300px" width="400px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/WhatsApp%20Image%202024-11-15%20at%202.28.03%20AM.jpeg" />
</div>

#### What if Relation have attribute?
Merge the attribute column also in table, but still the prime-key will be the composit of primary-key's of bothe table in relation

<div align="center">
  <img height="300px" width="400px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/WhatsApp%20Image%202024-11-15%20at%202.25.43%20AM%20(2).jpeg" />
</div>

### Case 3: Total from one side and partial from other side

<div align="center">
</div>

* We can not merge tables because of partial side will lead to $NULL$ entires in total participaing side when partial side has higher cadinality then total partcipating entity-set and because we allowed to have many-to-many relation we have duplicated entries so niether compositly nor indvidually we are going to have primary-key.
* What if total side hav higher cardinality then partial side?
  * No, it will not be possible because we have partial parital participation from one side, and it is neccessary that at least one entity should be there that is not participating in relation. you will always see $NULL$ entires in total side entity-set's columns in row where partial side's entity is not participating.
