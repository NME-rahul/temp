## Super-key

A superkey is indeed a set of every possible combination of attributes that can uniquely determine the tuples in a relation. 

A super-key is a superset of candidate key's, All candidate keys can be a super key, but the reverse is not true.

If there are N attributes then $2^{(N-k)}$ super-keys are possible(when k is the length of candidate keys).

## Candidate-key

A candidate-key is a subset of the super-key, which uniquly determine each attribute of table. A candidate key is a super key with least number of columns. it is also called minimal super key.

## Prime-key

A primary key is chosen from the set of candidate keys to uniquely identify tuples in a  relation. Like candidate keys, the primary keys must not unique and cannot contain null values. Additional, the primar key is typically the key that is choosen to establish the foriegn key relationship.

## Partial dependency

A partial dependency occurs when a non-prime attribute is functionally dependent on only a part of the primary key. It suggests that the table is not in 2NF.

## Full dependecny

A full functional dependency occurs when a non-prime attribute is functionally dependent on the entire primary key, and not just a part of it. In other words, removing any attribute from the primary key would break the functional dependency.
