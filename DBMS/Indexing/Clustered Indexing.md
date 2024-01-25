# Clustered Indexing

* Indexing is done on non-primary key attribute.
* Data must be ordered on indexing attribute.
* It is sparse indexing but not always.


<p align="center">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20200410115906/Clustered_Index.jpg" height="400" width="600">
</p>


* Indexing file keeps only the unique records of the file.
* Each unique record points the block in which the recored is appeaared first time even if the same recored is present in the another block.
* In above example we can see that we have done indexing for only unique records and pointing to the block when it appeared first time, record number 2 in indexing file is pointng to the first block of file even it is present also in the second block.

---

**Question**

* Number of records in DB: 1GB
* Record Size: 64 bytes
* Block size: 4096 bytes
* Index field: 10 bytes
* Block pointer size: 22 bytes
* Number of distinct values in index file: 16384
* Indexing is done on non-key, data is ordered on non-key.
* Indexing is done for unique values only.
* Find the total number of blocks in DB?
* Find total number of blocks required for index file?

**Solution**

* Total size of DB records = Number of records in DB * Size of a single record = $2^{30} * 64$ bytes
* Total number of blocks = Total size of DB records / size of a single block = $\frac{2^{30} * 64}{4096} \frac{bytes}{bytes}$ = $\frac{2^{36}}{2^{12}}$ = $2^{24}$
* Index file strcture

  |Index field|Block pointer|
  |---|---|

* size of each record in index file = Index field + Block pointer = 10 + 22 = 32 bytes

* size of index file = Number of distinct records in index file * size of each record in index file = 16384 * 32 bytes

* Number of blocks required for index file = size of index file / size of a single block  = $\frac{16384 * 32}{4096} \frac{bytes}{bytes} = \frac{2^{19}}{2^{12}} = 2^7$


