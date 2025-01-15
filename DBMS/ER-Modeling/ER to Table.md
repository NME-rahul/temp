# Approach

# 1. $1:1$ cardinality

* We can move primary-key to any side.


### Case 1. Total Participation From both Side

eg. Every employee is assciated with the 1 department and similariy every department have 1 employee

<div align="center">
  
</div>

* Because relation is $1:1$ and every entity is participating(Toal participation) so, it automatically will become neccsary that both the tables have equal cardinality.

Note: You can merge tables here, primary-key can be any table's primary-key because of equal caridnality of entity-sets


### Case 2: Total participation from one side and partial participation from other side

<div align="center">
</div>

Note: You can merge tables here, primary-key of the entity-set which is is participating partially will become the primary-key of merged table.
* Merging is possible but design is inefficient because of we can have many $NULL$ entires


### Case 3: Partial Participation from both the sides

<div align="center">
  
</div>

Note: We can not merge tables because both can have entites which are not related to have so resulting table may have $NULL$ entries.


# 2. $M:N$ Minimum Caridinality

### Case 1: Partial Participation From both the sides

<div align="center">
  <img height="300px" width="400px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/many-many%2C%20partial-partial/WhatsApp%20Image%202024-11-15%20at%201.28.06%20PM%20(1).jpeg" />
    <img height="300px" width="400px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/many-many%2C%20partial-partial/WhatsApp%20Image%202024-11-15%20at%201.28.06%20PM.jpeg" />
  
</div>

* Can you merge tables?
  * No, You can not Merge the tables here.
  
 <div align="center">
  <img height="300px" width="300px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/many-many%2C%20partial-partial/WhatsApp%20Image%202024-11-15%20at%201.28.05%20PM.jpeg" />
</div>

* Many-to-Many with partial relation from both side can leads $NULL$ entries whether you merge both tables or take primary key of one table to other side. So, it become necessary to create a sperate table for their relation which have only those entries which are participating in relation.

<div align="center">
  <img height="300px" width="300px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/many-many%2C%20partial-partial/WhatsApp%20Image%202024-11-15%20at%201.28.05%20PM%20(1).jpeg" />
    <img height="300px" width="300px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/many-many%2C%20partial-partial/WhatsApp%20Image%202024-11-15%20at%201.28.05%20PM%20(2).jpeg" />
</div>

* we can not take primary-key of one side as foriegn-key to other side, in fact we have to create one more table to form a relation and this table have entry of only those entities whic are taking taking part in relation
* One more intresting fact is that the primary key will be the composit key of prime-key's of both tables in relation because of many-to-many relation and both columns allowed have duplicate entries.

 <div align="center">
  <img height="300px" width="300px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/many-many%2C%20partial-partial/WhatsApp%20Image%202024-11-15%20at%201.28.06%20PM%20(2).jpeg" />
</div>

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
  <img height="300px" width="400px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/many-many%2C%20total-partial/WhatsApp%20Image%202024-11-15%20at%2012.55.42%20PM.jpeg" />
    <img height="300px" width="400px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/many-many%2C%20total-partial/WhatsApp%20Image%202024-11-15%20at%2012.55.42%20PM%20(1).jpeg" />
</div>

* Can we merge the table?
  * No, we can't, because after merging resulting table will have duplicate, as well $NULL$ values. so we can not any attribute or composit attribute as prime-key.
  
<div align="center">
  <img height="300px" width="400px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/many-many%2C%20total-partial/WhatsApp%20Image%202024-11-15%20at%2012.55.43%20PM.jpeg" />
</div>

* To make a relation between them we have take partial-side's prime-key to total side by this way we will not have any $NULL$ values in any column, and the prime-key will be composit of foriegn-key and prime-key of current table(total-side).

<div align="center">
  <img height="400px" width="400px" src="https://github.com/NME-rahul/temp/blob/main/DBMS/Images/many-many%2C%20total-partial/WhatsApp%20Image%202024-11-15%20at%201.28.07%20PM.jpeg" />
</div>

# 3. $M:1$ or $1:M$

### Case 1: Partial relation at both side

* We can not merge the tables beause if we do then, we have following problems
  * We can have duplicate values in "One" side column
  * and **NULL** values in both side of column due to partial participation

* can we make prime-key of One side as foreign-key in many side
  * yes, we can do!, it is working because an entity of "many" side relates to only one entity of "One" side, but an entity of "One" side relates to many entites at "many" side. so we can keep uniqness at "many" side.
    * What if we have many one side enity-set have more cardinality then one side? dont' worry we only include those entry(entity) of "One" side which are taking part in relation others will remain in their original table.

### Case 2: Partial at one side and Total from other side

* We can move primary-key of partial side at total side to create foreign-key.

* Can we merger the tables ?
  * No, we can not merge the tables because it will create duplicacy in partial side and NULL at total side.
 

### Case 3: total at one side and Total from other side

* we can move the primary-key at either side and the new primary-key will be the combination of old primary-key and newly formed foreign-key.

* can we merge the tables?
  * yes we can merge the tables, and again primar-key will be combination of both side primary-key due to dulicacy in either columns(of primary-key).
----

### What should we do when we have attributes in relation?
* Do what you do with relation without having and attribute. like if you are merging two entity-set then include in merged table.
* and if you making parimary-key of one side as foriegn-key to other side then also include the attribute of relation to the table where you'r inlcuding foriegn-key.




 
