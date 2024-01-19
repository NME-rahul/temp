### Attribute types


||Simple|Composite|
|----|----|----|
|1.|Attributes Having single/atomic Values that cannot be furhter divide into meaningful components.|A Composit address can be divided into smaller subparts, these sub-parts may or may not represent the simple attributes.|
|2.||A composit attribute contains the data from different domains.|
|3.|eg. marks|eg. An address can be subdivide into the city, postal code, street etc.|



||Single-valued|Multi-valued|
|----|----|----|
|1.|The attributes which takes up only a single value for each entity instance is a single-valued attribute.|An attribute can have set of values for the same entity|
|2.|eg. Age|eg. Phone number|



||Stored|Derived|
|----|----|----|
|1.|Attributes which doen't require any type of further update since they are stored in the database|An attribute that can be derive from other attributes.|
|2.|eg. DOB|eg. Age can be derived from the DOB|


5. **Complex Attributes**:
* Arbitrary nested Composit and multi-valued attributes.
* composit componnet is represented by the ().
* and multi-valued is represented by the {}.
* eg. a person can have more then one residence and each residence can have multiple phones.

