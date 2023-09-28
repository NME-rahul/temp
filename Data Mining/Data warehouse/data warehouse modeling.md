# Data Warehouse Modeling

Data Warehouse modeling is the process of designing the schemas of detailed and summarized information. It involves creating a logical and physical model of data.

There are two main reasons of data modeling:-
1. Through the schema, clients can visualize the relationship among the warehouse data.
2. a well-desgined schema allows an effective data warehouse structure.

### Designing data warehouse model

1. Logical data warehouse modeling
logical data warehouse modeling is the high-level repersentation of data warehouse without considering physically implementation detail. It primarily defines the structure, relationship and sementatics of data within warehouse.

**Features**
* It involves primary key for all entities
* List the relationship between different entities
* list all attributes for each entity
* Normalization

**ER Modeling**: it is a common tool used modeling the data, draws the relationship between entities. It uses set theory and graph theory to repersent entities and realtionship between them.

**Normalization**: In normalization, you try to eleminate functional dependencies, data redundancey, to enusre data integrity and reduce the risk of anomalies.

2. Physical Data Warehouse modeling
On the other hand, the physical modeling cocnerned about the implemntation of logical data warehouse to physically. It address how data will be stores, indexed, data types, constraints, primary key, foriegn key, and optimization for query performance.


**Concern**
* Convert entites to table
* Convert realationship to foreign key
* Convert attributes to column



### Types of data warehouse modeling

1. Enterprise warehouse
An enterprise warehouse collects all the records of organization. It support corporate-wide data integration.It generally contains detailes information as well as summarized information and can range in estimate from a few gigabyte to hundreds of gigabytes, terabytes or beyond. It requires business modeling and may take years to devvelop and build.

2. Data mart
Data mart is a subset of data from a company that is useful for specific user and focuses on selected subjects. For instance, a marketing data mart center is on customers, items, sales. data in data marts is usually summarized.

3. Virtual warehouse
Virtual data warehouse is a set of preception over the operational database. For effective query processing, only some of the possile summary vision may be materilized. A virtual warehouse is simple to build but requires excess capacity on operational database servers.
