# primary Indexing

* Indexing is done on primary-key or any super-key.
* Data must be Ordered on index.
* It's always Sparse index.

  ![](https://iq.opengenus.org/content/images/2023/05/primary.jpg)

**Explanation:**

* when we have a table/records which have primary-key having data ordered then we use primary indexing.
* Here, the block size is 4, Block pointer helps to identify in which block the records are store and search-key helps to identify first record.
* Sparse indexing is done because we know the the data is sorted and unique and the block size is 4, so if we get the first recored we can determine the all 3 sucecesive records.
  
