In Indexing we store a subscidary file in MM which have search-key and block pointer, this is ussed because it is not possible to store all the records in the Main-memory. Blocks pointer, points to the block in which the record are stored and search-key helps to find the particular record in the database.

||Ordered| Unorderd|
|---|---|---|
|Key|Primary|Secondary|
|Non-key|Clustering|Secondary|

### Stucture of Indexing

|Serach-key|recored Pointer/Block pointer/ Data reference|
|---|---|

* Data filld in index file must be Ordered.

# primary Indexing

* Indexing is done on primary-key or any super-key.
* Data must be Ordered on index.
* It's always Sparse index.

  ![](https://iq.opengenus.org/content/images/2023/05/primary.jpg)

**Explanation:**

* when we have a table/records which have primary-key having data ordered then we use primary indexing.
* Here, the block size is 4, Block pointer helps to identify in which block the records are store and search-key helps to identify first record.
* Sparse indexing is done because we know the the data is sorted and unique and the block size is 4, so if we get the first recored we can determine the all 3 sucecesive records.
  
