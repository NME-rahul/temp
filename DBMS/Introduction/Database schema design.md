# Database Shema Design

Shema design is depends on the application's requirments.

### Types of schema design

1. Flat Model
2. Hierarchical Model
3. Network Model
4. Relational Model
5. Star Schema
6. Snowflake schema

### 1. Flat Model

It's a 2-D array in which every column contains the same types of data and elements in same row is related with each other in some manner.

<p align="center">
 <img height="500px" width="600px" src="https://media.geeksforgeeks.org/wp-content/uploads/20230228164450/Flat-model.png"/>
</p>


### 2. Hierarchical Model

The hierarchical has a tree-like structure, this tree structure contains the root node that links to its child nodes. Each child node & parent node have one-to-many relationship.

<p align="center">
 <img height="400px" width="700px" src="https://media.geeksforgeeks.org/wp-content/uploads/20200727111632/hierarchical.png"/>
</p>

### 3. Network Model

The network model and the Hierarchical model are quite similar, the only difference is Child & Parent node have many-to-many relationship.

<p align="center">
 <img height="400px" width="700px" src="https://media.geeksforgeeks.org/wp-content/uploads/20200727113000/network.png"/>
</p>

### 4. Relational schema

The relational schema 'R' denoted by R(A1, A2,...An) is made up of relation name R and a liste of attributes A1, A2,...An. Each attribute Ai contains the data from some domain D.

A relation schema is used to describe a relation and R is called the name of relation. The degree of relationsip is the number of attributes the table contains and the cardinality is defined as the number of rows/records a table have.

The degree of reationship of relational schema is the number of entities a schema have. The following relational schema have degree 7.

<p align="center">
 <img height="400px" width="700px" src="https://blog.hubspot.com/hs-fs/hubfs/Google%20Drive%20Integration/Database%20Schemas%20The%20Beginners%20Guide-2.png?width=1248&name=Database%20Schemas%20The%20Beginners%20Guide-2.png"/>
</p>

### 5. Star schema

Star schema is better for storing and analyzing large amounts of data. It has fact table at its center & multiple dimension tables connected to it just like a star, where the fact table contains the numerical data and the dimension table contains data related to dimensions such as product, time, people, etc.

<p align="center">
 <img height="400px" width="700px" src="https://media.geeksforgeeks.org/wp-content/uploads/20230324112549/2.jpg"/>
</p>

### 6. Snowflake schema

Just like star schema, the snowfake schema also has a fact table at it's center and multiple diemension tables connected to it, but the main difference in both models is that in snowflake schema dimension tables are further normalized into multipe related tables. It is use for analyzing large amounts of data.

<p align="center">
 <img height="400px" width="700px" src="https://media.geeksforgeeks.org/wp-content/uploads/20230324112618/3.jpg"/>
</p>
