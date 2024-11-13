## Super-key

A superkey is indeed a set of every possible combination of attributes that can uniquely determine the tuples in a relation. 

A super-key set is a superset of candidate key's, All candidate keys can be a super key, but the reverse is not true.

If there are N attributes then $2^{(N-k)}$ super-keys are possible(when k is the length of candidate keys).

eg. Student(Roll_no, Name, FatherName, DOB)

Superkeys: { {Roll_no}, {Roll_no, Name}, {Roll_no, FatherName}, {Roll_no, DOB}, {Roll_no, FatherName, DOB}, {FatherName, Name}, ......} 

If {FatherName, Name} can uniquely identify the any tuple in relation.

## Candidate-key

A candidate-key is a subset of the super-key, which uniquly determine each attribute of table. A candidate key is a super key with least number of columns. it is also called minimal super key.

Super-Key without any redundant key.

## Prime-key

A primary key is chosen from the set of candidate keys to uniquely identify tuples in a relation and that we will use in our implementation. Like candidate keys, the primary keys must be unique and cannot contain null values. Additional, the primary key is typically the key that is choosen to establish the relationship with the foriegn key.

Note: There is difference between primary-key and prime attributes, prime-attributes are those attrbutes which is part of candidate-key.

if AB is a candidate-key then A and B are prime attributes.

## Alternate-Key

All candidate keys apart from primary-key are called alternate key.

## Foriegn-key

It is used to ensure referential integrity. It can have NULL and non-unique values.

## Partial dependency

A partial dependency occurs when a non-prime attribute is functionally dependent on only a part of the primary key. It suggests that the table is not in 2NF.

## Full dependecny

A full functional dependency occurs when a non-prime attribute is functionally dependent on the entire primary key, and not just a part of it. In other words, removing any attribute from the primary key would break the functional dependency.
